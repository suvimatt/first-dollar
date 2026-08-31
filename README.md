# The Agent Bootstrapper

> **Build on agents. Validate with users. Grow with revenue.**

**Agents as infrastructure. Prototypes as questions. User behavior as evidence. Revenue as fuel.**

The Agent Bootstrapper is an experimental field guide and collection of reusable Agent Skills for developers and solopreneurs building customer-funded businesses with coding agents such as Codex, Claude Code, and Hermes. It favors starting with as little capital as practical, earning from customers early, and compounding customer value rather than chasing growth at any cost.

Starting small limits risk and keeps the business close to its customers; it is not a ceiling on ambition. The goal is to grow stronger with every customer served: more useful, more profitable, more trusted, and more capable.

The project's current foundation is adapted from [*The Minimalist Entrepreneur*](https://www.minimalistentrepreneur.com/) by Sahil Lavingia. Its commercial philosophy remains: start with a community, create customer value, earn revenue early, stay profitable, and grow sustainably. The operating method has changed.

## What coding agents change

When software was expensive to build, extensive discovery or manual delivery often had to come before a working product. Coding agents such as Codex, Claude Code, and Hermes can now turn a sufficiently narrow idea into a testable product in hours. When building is cheap, safe, and disposable, the prototype itself becomes a research instrument.

Vibe coding is one visible expression of this shift: an entrepreneur can move from intent to working software through a tight conversation with an agent. The opportunity is not to generate more products. It is to replace prolonged speculation with shorter, more concrete feedback loops.

**Agents disrupt how we validate, not what counts as validation.**

The new default loop is:

1. Learn just enough about a reachable user and a problem to define a test.
2. State the riskiest assumption.
3. Timebox the smallest usable prototype—often to half a day—and build it with agents.
4. Put it in front of real users and observe behavior, objections, repeat use, and willingness to pay.
5. Discard it, iterate, or turn it into a deliverable offer; grow only as customer revenue and evidence justify.

A prototype is a question, not proof of demand. Agents reduce the cost of building, not the need for customer contact, trust, domain knowledge, or payment evidence. Build on agents; let users and revenue decide what survives. Upfront research still comes first when mistakes are costly, regulated, unsafe, or impossible to test with a disposable prototype.

## Project status

The Agent Bootstrapper is independent, experimental, and evolving. It is not an official companion to the book or a claim of proven entrepreneurial success. The maintainer is using the project in his own entrepreneurial journey, so its guidance is treated as hypotheses to test through real practice, user feedback, payment, and delivery—not as guaranteed business outcomes.

## Install

> The skills follow the open [Agent Skills specification](https://agentskills.io) and work with compatible agents including Codex, Claude Code, OpenClaw, and Hermes.

Use the cross-agent [`skills`](https://skills.sh) installer:

```bash
npx skills add suvimatt/agent-bootstrapper
```

The installer detects supported agents and lets you choose which skills to install.

## Upgrade to get the latest version

```bash
npx skills update suvimatt/agent-bootstrapper
```

## Skills

| Skill | Command | When to use |
|-------|---------|-------------|
| **First Dollar** | `/first-dollar` | Want one guided path from a reachable problem to a verified customer payment |
| **Find Community** | `/find-community` | Looking for a business idea, trying to find your community |
| **Validate Idea** | `/validate-idea` | Choose the cheapest credible test for a business idea |
| **MVP** | `/mvp` | Build the smallest user-testable question with agents, manual work, or both |
| **Processize** | `/processize` | Design a credible human-agent delivery loop before durable automation |
| **First Customers** | `/first-customers` | Have a product, need to find your first 100 customers |
| **Pricing** | `/pricing` | Setting prices, considering price changes |
| **Marketing Plan** | `/marketing-plan` | Have product-market fit, ready to scale with content |
| **Grow Sustainably** | `/grow-sustainably` | Making decisions about spending, hiring, or scaling |
| **Company Values** | `/company-values` | Defining culture, preparing to hire |
| **Minimalist Review** | `/minimalist-review` | Gut-checking any business decision |

## From First Dollar to Sustainable Growth — v0.1

A first dollar is evidence, not the destination. Use `/first-dollar` as the guided entry point when you want the system to identify the current bottleneck, route to the relevant skill, preserve an evidence checkpoint, and return one next action.

Version 0.1 closely follows *The Minimalist Entrepreneur*. The `/first-dollar` journey adds a strict definition of verified customer payment, an evidence-tracked path from a reachable problem through payment and delivery, and these initial agent-powered adaptations:

- **Agents collapse the cost of building, not demand risk.** A generated prototype does not replace buyer commitment, payment, or repeat use.
- **Build when building is the cheapest credible experiment.** Prefer a timeboxed, disposable prototype over prolonged speculation when users can safely experience it.
- **Learn from behavior, not the artifact.** What users do, request, repeat, and pay for matters more than what the agent successfully generates.
- **Keep consequential judgment human-owned.** Agents can research, draft, prototype, and operate; people remain responsible for customer promises, evidence interpretation, and external actions.

The current companion skills retain the book's progression:

1. **Community** — Start by finding your people
2. **Validate** — Make sure the problem is worth solving
3. **Build** — Use agents when a disposable prototype is the cheapest credible test
4. **Processize** — Turn observed value into a human-agent delivery loop
5. **Sell** — Get to 100 customers one by one
6. **Price** — Charge something from day one
7. **Market** — Build an audience through content
8. **Grow** — Stay profitable, grow sustainably
9. **Culture** — Build the house you want to live in
10. **Review** — Apply minimalist principles to every decision

This repository began as a continuation of [`slavingia/skills`](https://github.com/slavingia/skills). The Agent Bootstrapper is now an independent adaptation that continues to credit the book as its primary foundation while testing how coding agents change the work of bootstrapped entrepreneurship. See [References](REFERENCES.md) for the current relationship to source ideas and [Field Notes](FIELD-NOTES.md) for the learning format that will guide future changes.
