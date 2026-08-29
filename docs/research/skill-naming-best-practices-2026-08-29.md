# Agent Skill naming: brand prefix or capability name?

Date: 2026-08-29

## Question

For a public collection of related Agent Skills, should every Skill carry a shared brand prefix such as `fd-` or `first-dollar-`, when uninstall behavior is out of scope?

## Conclusion

Do not add a blanket `fd-` or `first-dollar-` prefix to every Skill merely because the Skills ship from the same repository. Current leading practice is to make each Skill name describe the activity, capability, tool, or domain that should route a task to it. Use a prefix only when that prefix is itself meaningful task context, such as `shopify-`, `figma-`, or `notion-`.

For First Dollar:

- Keep `first-dollar` as the product's public entry point and journey orchestrator.
- Keep companion Skill names capability-oriented.
- Put the collection identity in the plugin/package display name, repository, README, and UI metadata.
- Improve overly generic companion names with semantic scope when real user tests show ambiguity. Prefer `pricing-first-offers` over either `pricing` or `fd-pricing`.
- Make descriptions explicitly state the first-dollar stage, intended user, and trigger. Description quality matters more than a repeated brand prefix for implicit activation.

## What the standards and hosts establish

### Agent Skills specification

The open specification requires a lowercase hyphenated `name` of at most 64 characters and a `description` that explains what the Skill does and when to use it. It recommends specific keywords in the description to help agents identify relevant tasks. It does not define package namespaces or recommend repository/brand prefixes.

Source: [Agent Skills specification](https://agentskills.io/specification)

### OpenAI Codex and ChatGPT

OpenAI documents progressive disclosure as starting from every Skill's name and description. Explicit invocation selects a named Skill, while implicit invocation is based on the task matching the Skill description. OpenAI advises front-loading the use case and trigger words in the description because descriptions can be shortened when many Skills are installed.

OpenAI also states that duplicate Skill names are not merged; both can appear in selectors. For distributing two or more Skills, OpenAI recommends a plugin, which provides a package-level home for the collection without requiring the package identity to be repeated in every Skill name.

Source: [OpenAI Build skills](https://learn.chatgpt.com/docs/build-skills)

### Anthropic Claude

Anthropic recommends consistent, descriptive names and suggests gerund/activity forms such as `processing-pdfs`, `analyzing-spreadsheets`, `managing-databases`, and `testing-code`. It warns against vague or overly generic names. Anthropic separately calls the description critical for selection from potentially 100+ installed Skills.

This guidance favors semantic activity names, not opaque collection abbreviations.

Source: [Anthropic Skill authoring best practices](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices)

## What leading official repositories do

The following counts were taken from each repository's `main` tree on 2026-08-29. They are descriptive samples, not a universal benchmark.

### OpenAI

The OpenAI repository contained 44 `SKILL.md` files. It did not apply `openai-` to the whole collection. Instead, it used semantic families where a tool or domain mattered: eight `figma*` names, four `notion*` names, three `security*` names, and two `openai*` names. Other names remained direct capabilities such as `pdf`, `screenshot`, `transcribe`, `gh-fix-ci`, and `cloudflare-deploy`.

Source: [openai/skills](https://github.com/openai/skills/tree/main/skills)

### Anthropic

The Anthropic repository contained 20 `SKILL.md` files, zero with an `anthropic-` prefix and one with a `claude-` prefix (`claude-api`). Most names described the capability directly, including `algorithmic-art`, `doc-coauthoring`, `frontend-design`, `mcp-builder`, `webapp-testing`, `pdf`, and `xlsx`.

Source: [anthropics/skills](https://github.com/anthropics/skills/tree/main/skills)

### Shopify

The Shopify AI toolkit contained 21 `SKILL.md` files, 20 beginning with `shopify-`. This is a useful counterexample: Shopify is not merely the publisher brand. It is the platform/domain required to understand and execute the task, so names such as `shopify-admin`, `shopify-functions`, and `shopify-storefront-graphql` provide routing information.

Source: [Shopify/shopify-ai-toolkit](https://github.com/Shopify/shopify-ai-toolkit/tree/main/skills)

## Decision rule

Ask: "If the prefix were removed, would the user request or required execution context become ambiguous?"

- If yes, use the prefix. `shopify-functions` is meaningfully different from generic serverless functions; `figma-generate-design` requires Figma context.
- If no, omit it. A publisher abbreviation such as `fd-` adds identity but no task semantics.
- If the unprefixed name is too broad, add semantic scope instead of brand: `pricing-first-offers`, `validating-business-ideas`, or `planning-content-marketing`.

## User-experience trade-offs

### Blanket brand prefix

Benefits:

- Visually groups names in flat selectors.
- Makes provenance obvious.

Costs:

- Makes every explicit invocation longer.
- Repeats the same low-information token across the initial Skill list.
- Can make a library look cohesive while leaving the actual capability name vague.
- An opaque abbreviation such as `fd` makes discovery and recall worse for users who do not already know the brand.

### Capability-oriented names

Benefits:

- Users can understand and invoke a Skill without learning the package brand.
- Names contribute useful routing information.
- Matches current OpenAI and Anthropic examples.

Costs:

- Very generic names can collide or appear ambiguous in selectors.
- Collection membership must be communicated at plugin/package/UI level.

The SOTA response to the downside is semantic scoping and package-level presentation, not a universal short prefix.

## Recommendation for First Dollar

Keep the current naming architecture for now:

```text
First Dollar plugin/package
└── first-dollar             # one public journey entry point
    ├── find-community
    ├── validate-idea
    ├── processize
    ├── mvp
    ├── first-customers
    ├── pricing
    ├── marketing-plan
    ├── grow-sustainably
    ├── company-values
    └── minimalist-review
```

Do not mechanically change these to `fd-*` or `first-dollar-*`. Instead, test the current names and descriptions. If users or agents confuse a generic Skill with unrelated installed Skills, rename only that Skill using semantic scope. Illustrative candidates are:

| Current | Better scoped candidate | Why |
|---|---|---|
| `pricing` | `pricing-first-offers` | Names the stage and object being priced. |
| `mvp` | `building-manual-mvps` | Names the activity and manual-first method. |
| `marketing-plan` | `planning-content-marketing` | Distinguishes the content-first approach. |
| `minimalist-review` | `reviewing-business-decisions` | States the user-visible job. |

These are hypotheses, not required renames. Validate them with explicit-invocation recall and implicit-trigger evaluations before introducing breaking names.

## Minimum evaluation before renaming

Test current and candidate names against the same descriptions on every intended host:

1. Positive implicit triggers in Chinese and English.
2. Near-neighbor negative cases that should select another Skill or no Skill.
3. Ambiguous cases where two installed Skills could plausibly match.
4. Explicit selection from the UI and explicit `$skill-name`/slash invocation.
5. A fresh user who has not seen the First Dollar brand: can they predict what the Skill does from its name?

Prefer the shortest semantic name that wins these tests. Brand consistency alone is not sufficient evidence for a prefix.
