# Agent Skill compatibility and distribution research

Verified 2026-08-28 against first-party documentation and source repositories.

## Recommendation

Describe this repository as **compatible with agents that support the open Agent Skills standard**, not “compatible with all general agents.” The ten `skills/*/SKILL.md` files use only the standard `name`, `description`, and Markdown body; no Claude-only or Codex-only frontmatter appears in them. Host-specific plugin manifests are distribution wrappers, not part of the portable skill format.

The shortest cross-agent installation is:

```bash
npx skills add suvimatt/agent-bootstrapper
```

The Vercel `skills` CLI discovers `skills/<name>/SKILL.md`, detects installed agents, and supports Claude Code, Codex, OpenClaw, Hermes Agent, and many others. It installs to each host's expected directory. Use `--all` only when intentionally installing every skill to every supported agent; the interactive default is safer and less surprising. Choose the installer's **Copy** method for the broadest compatibility (see the OpenClaw symlink caveat below).

Source: [vercel-labs/skills README](https://github.com/vercel-labs/skills/blob/main/README.md)

## Compatibility findings

| Host | Core format | Repository/project location | Finding |
| --- | --- | --- | --- |
| Codex | Open Agent Skills | `.agents/skills/` | Directly compatible. Codex explicitly says skills build on the open standard and follows symlinked skill folders. |
| Claude Code | Agent Skills open standard plus Claude extensions | `.claude/skills/`, or a plugin's `skills/` | The skill content is compatible. Claude's plugin manifest and slash-command behavior are host-specific packaging/UX. |
| OpenClaw | AgentSkills spec plus OpenClaw metadata extensions | `<workspace>/.agents/skills/` or `<workspace>/skills/` | The skill content is compatible, but the repository's `.agents/skills` symlink resolves outside `.agents`; OpenClaw's path-containment policy may reject it unless the target is explicitly allowed. A copied installation avoids this issue. OpenClaw also accepts `skills-sh:` references. |
| Hermes Agent | agentskills.io standard plus Hermes metadata extensions | `<project>/.agents/skills/`, `<project>/.hermes/skills/`, or `~/.hermes/skills/` | The skill content and project convention are compatible. A copied installation is the conservative cross-host choice because Hermes' cited documentation does not establish identical symlink semantics. Hermes also integrates skills.sh, ClawHub, direct GitHub paths, and GitHub taps. |

Primary sources:

- [OpenAI: Build skills](https://developers.openai.com/codex/skills/) — open standard, required structure, Codex discovery paths, and symlink support.
- [Anthropic: Extend Claude with skills](https://code.claude.com/docs/en/skills) — explicit open-standard support, Claude extensions, locations, and plugin skills.
- [OpenClaw: Skills](https://docs.openclaw.ai/tools/skills) — `.agents/skills` discovery, AgentSkills compliance, and install commands.
- [Hermes Agent: Skills System](https://github.com/NousResearch/hermes-agent/blob/main/website/docs/user-guide/features/skills.md) — agentskills.io compatibility, project-local `.agents/skills`, Skills Hub sources, and GitHub taps.
- [Agent Skills specification](https://agentskills.io/specification) — portable `SKILL.md` contract.
- [Agent Skills client showcase](https://agentskills.io/clients) — lists all four hosts as supporting clients.

## Common standard versus host packaging

Portable layer:

- One directory per skill.
- `SKILL.md` with YAML frontmatter containing `name` and `description`.
- Markdown instructions and optional `scripts/`, `references/`, and `assets/`.

Host-specific layer:

- `.claude-plugin/*` is Claude Code marketplace/plugin packaging.
- `.codex-plugin/plugin.json` is Codex/ChatGPT plugin packaging.
- Invocation syntax, install paths, invocation-control fields, hooks, and host metadata are not universally portable.

Therefore the repository can advertise broad Agent Skills compatibility while retaining both manifests. It should not imply that every AI agent can load the repository or that every host-specific extension behaves identically.

### Current symlink caveat

The checked-in `.agents/skills` entry is a symlink to `../skills`. Codex explicitly supports symlinked skill folders. OpenClaw, however, requires discovered skill realpaths to remain inside the configured root unless `skills.load.allowSymlinkTargets` explicitly trusts the target. Therefore:

- the portable source of truth remains `skills/`;
- use the Vercel installer with its **Copy** method for a no-configuration cross-host install;
- do not claim that opening this checkout makes the symlinked `.agents/skills` work unchanged in every host.

## Hubs and registries

### skills.sh: best default distribution route

[skills.sh](https://skills.sh/) is Vercel's Agent Skills directory, paired with the open-source [`skills` CLI](https://github.com/vercel-labs/skills). The CLI already recognizes this repository's `skills/` layout and supports the four target hosts.

Install without cloning:

```bash
npx skills add suvimatt/agent-bootstrapper
```

When prompted for installation method, select **Copy** for maximum host compatibility.

Useful explicit variants:

```bash
# List skills without installing
npx skills add suvimatt/agent-bootstrapper --list

# Install one skill globally for Codex
npx skills add suvimatt/agent-bootstrapper -g -a codex -s validate-idea

# Install all skills for the four verified hosts
npx skills add suvimatt/agent-bootstrapper -g \
  -a codex -a claude-code -a openclaw -a hermes-agent \
  -s '*' --copy -y
```

The current official CLI README documents installation and anonymous install telemetry, but it does **not** document a separate author submission form or publish command for skills.sh. Its source sends public-repository install events to the directory service unless telemetry is disabled. A live query of the CLI's documented search API on 2026-08-28 returned no `suvimatt` result for `validate-idea`, so this repository is **not currently confirmed as indexed**. Do not claim “published on skills.sh” merely because the CLI can install it.

Verification endpoint:

```text
https://skills.sh/api/search?q=validate-idea&owner=suvimatt&limit=20
```

Sources: [CLI README](https://github.com/vercel-labs/skills/blob/main/README.md), [telemetry source](https://github.com/vercel-labs/skills/blob/main/src/telemetry.ts).

### ClawHub: real registry publication, but separate and state-changing

[ClawHub](https://clawhub.ai/) is OpenClaw's public versioned registry. Unlike skills.sh's GitHub-source installation, ClawHub has an explicit authenticated publish workflow:

```bash
npm i -g clawhub
clawhub login
clawhub skill publish skills/validate-idea \
  --slug validate-idea \
  --name "Validate Idea" \
  --version 1.0.0
```

Each skill is a separate registry artifact. Publication uploads content, requires authentication, and is subject to ClawHub's GitHub-account age gate and security/moderation checks. It should be done only after the owner approves names, versions, and changelogs. After publication, users install without cloning:

```bash
openclaw skills install @owner/validate-idea
```

Sources: [OpenClaw ClawHub documentation](https://docs.openclaw.ai/clawhub), [OpenClaw Skills documentation](https://docs.openclaw.ai/tools/skills#installing-from-clawhub).

### Hermes: no registry registration required

Hermes can consume the repository directly as a GitHub tap:

```bash
hermes skills tap add suvimatt/agent-bootstrapper
hermes skills install suvimatt/agent-bootstrapper/validate-idea
```

It can also install a single GitHub path directly:

```bash
hermes skills install suvimatt/agent-bootstrapper/skills/validate-idea
```

Once skills.sh has a confirmed listing, Hermes can install its identifier through the `skills-sh` source as well. Source: [Hermes Skills System](https://github.com/NousResearch/hermes-agent/blob/main/website/docs/user-guide/features/skills.md#skills-hub).

## README implications

Keep the public README concise:

1. Title/intro: “Agent Skills for Codex, Claude Code, OpenClaw, Hermes, and other Agent Skills-compatible agents.”
2. One default install command: `npx skills add suvimatt/agent-bootstrapper`.
3. Keep Claude's marketplace commands only as an optional native install path if desired.
4. Remove per-host command columns from the skills table; users can invoke skills using their host's normal UI/syntax.
5. Do not add a ClawHub badge or publication claim until the artifacts have actually been published and read back from the registry.
