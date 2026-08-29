# First Dollar — An evolving AI-native startup field guide for developers.

> Talk is cheap, earn me the money.

First Dollar helps developers work toward their first verified customer payment through an evidence-tracked journey and reusable Agent Skills.

Its current foundation is adapted from [*The Minimalist Entrepreneur*](https://www.minimalistentrepreneur.com/) by Sahil Lavingia. First Dollar preserves the book's emphasis on community, early sales, manual validation, profitability, and sustainable growth while exploring how AI agents change the cost and speed of research, prototyping, delivery, and iteration.

## Project status

First Dollar is independent, experimental, and evolving. It is not an official companion to the book or a claim of proven entrepreneurial success. The maintainer is using the project while beginning his own product journey, so its guidance is treated as hypotheses to test through real practice, user feedback, payment, and delivery—not as guaranteed business outcomes.

## Install

> The skills follow the open [Agent Skills specification](https://agentskills.io) and work with compatible agents including Codex, Claude Code, OpenClaw, and Hermes.

Use the cross-agent [`skills`](https://skills.sh) installer:

```bash
npx skills add suvimatt/first-dollar
```

The installer detects supported agents and lets you choose which skills to install.

## Upgrade to get the latest version

```bash
npx skills update suvimatt/first-dollar
```

## Skills

| Skill | Command | When to use |
|-------|---------|-------------|
| **First Dollar** | `/first-dollar` | Want one guided path from a reachable problem to a verified customer payment |
| **Find Community** | `/find-community` | Looking for a business idea, trying to find your community |
| **Validate Idea** | `/validate-idea` | Testing if a business idea is worth pursuing |
| **MVP** | `/mvp` | Ready to build your first product, struggling with scope |
| **Processize** | `/processize` | Have a product idea, want to deliver value by hand before writing code |
| **First Customers** | `/first-customers` | Have a product, need to find your first 100 customers |
| **Pricing** | `/pricing` | Setting prices, considering price changes |
| **Marketing Plan** | `/marketing-plan` | Have product-market fit, ready to scale with content |
| **Grow Sustainably** | `/grow-sustainably` | Making decisions about spending, hiring, or scaling |
| **Company Values** | `/company-values` | Defining culture, preparing to hire |
| **Minimalist Review** | `/minimalist-review` | Gut-checking any business decision |

## First Dollar Journey — v0.1

Use `/first-dollar` as the guided entry point when you want the system to identify the current bottleneck, route to the relevant skill, preserve an evidence checkpoint, and return one next action.

Version 0.1 closely follows *The Minimalist Entrepreneur*. First Dollar adds a strict definition of verified customer payment, an evidence-tracked journey, and these initial AI-native adaptations:

- **AI reduces building cost, not demand risk.** Generated products, content, traffic, and likes do not replace buyer commitment, payment, or repeat use.
- **Prefer the cheapest credible experiment.** Manual delivery is often best, but an AI-assisted prototype is valid when it produces credible learning faster and more cheaply.
- **Specificity matters more as supply gets cheaper.** Reachable buyers, narrow problems, trust, proprietary context, and distribution become more important as AI increases supply.
- **Keep consequential judgment human-owned.** Agents can research, draft, prototype, and operate; people remain responsible for customer promises, evidence interpretation, and external actions.

The current companion skills retain the book's progression:

1. **Community** — Start by finding your people
2. **Validate** — Make sure the problem is worth solving
3. **Build** — Ship a manual process, then productize it
4. **Processize** — Turn your product idea into a manual process you can deliver today
5. **Sell** — Get to 100 customers one by one
6. **Price** — Charge something from day one
7. **Market** — Build an audience through content
8. **Grow** — Stay profitable, grow sustainably
9. **Culture** — Build the house you want to live in
10. **Review** — Apply minimalist principles to every decision

This repository began as a continuation of [`slavingia/skills`](https://github.com/slavingia/skills). First Dollar now provides an independent upper-level brand and AI-native adaptation while continuing to credit the book as its primary foundation. See [References](REFERENCES.md) for the current relationship to source ideas and [Field Notes](FIELD-NOTES.md) for the learning format that will guide future changes.
