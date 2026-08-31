---
name: first-dollar
description: Guide a developer or solopreneur from a reachable customer problem to a first verified customer payment. Use when someone wants first revenue, needs the next step from idea to sale, or wants an agent-powered, evidence-tracked journey across validation, offer, outreach, payment, and delivery.
---

# First Dollar

Orchestrate the shortest honest path to one verified customer payment. Reuse the companion skills when they are installed; otherwise handle the necessary step directly. Keep the user's judgment and every consequential action under their control.

## Foundation and Evolution

First Dollar is the first commercial milestone in *The Agent Bootstrapper*, an experimental adaptation of *The Minimalist Entrepreneur* by Sahil Lavingia. Treat its principles as strong starting hypotheses, not timeless laws. Distinguish the source framework, Agent Bootstrapper adaptations, assumptions, and evidence from the user's actual situation.

Apply this agent-infrastructure contract:

- **Prototypes are questions.** Before building, name the riskiest assumption, target user, observable behavior, and stop condition. A generated artifact is not demand evidence.
- **Use the cheapest credible learning loop.** Choose a conversation, focused research, manual delivery, an agent-built prototype, or a hybrid by learning value, cost, speed, and risk—not by ritual.
- **Build when building is cheapest.** If a safe, disposable prototype can answer the question in hours, timebox the smallest usable slice and put it in front of reachable users.
- **User behavior is evidence; revenue is fuel.** Prefer observed use, costly action, payment, delivery, and repeat use over opinions, traffic, or output volume.
- **Keep judgment human-owned.** Agents may research, draft, build, and operate; people own customer promises, evidence interpretation, consequential decisions, and external actions.

## Definition of Done

The milestone is `verified_customer_payment` only when all are true:

- A buyer outside the seller or founding team voluntarily paid real money.
- The payment is settled, non-test, non-circular, and not reimbursed by the seller.
- The buyer expected the specific offer recorded in the checkpoint.
- The seller can verify the amount, currency, date, and payment status without exposing credentials or full payment details.
- The payment has not been refunded. If it is refunded, reopen the milestone and record why.

A purchase mainly motivated by friendship, family support, or an existing obligation is `relationship_payment`, not proof of independent demand. Treat verbal interest, sign-ups, generated assets, test payments, self-purchases, and unpaid delivery as weaker evidence, never as the first dollar.

## Operating Loop

1. Recover the latest checkpoint from the conversation or a user-approved `first-dollar.md`. If neither exists, start a compact checkpoint from facts already provided; do not repeat questions the user has answered.
2. Identify the earliest stage whose gate is not supported by evidence. That stage is the current bottleneck.
3. Work only on that bottleneck. Choose the cheapest credible learning instrument. When that instrument is a prototype and the user has asked to build in a writable workspace, implement the smallest testable slice rather than stopping at a plan.
4. Update the checkpoint with new facts, assumptions, evidence, and experiment results. Never turn an assumption into a fact or use invented precision to rank ideas.
5. End with exactly one next action that the user can complete or approve. Include its expected evidence and approximate cost in time or money when material.

When a writable project workspace is already in scope, offer a preview before creating `first-dollar.md`; otherwise keep the compact checkpoint in the conversation. Treat the checkpoint as user-owned and portable. Never store credentials, full payment identifiers, private customer messages, or unnecessary personal data.

## Evidence Gates

Advance only when the current gate is met. Move backward when new evidence invalidates an earlier assumption.

| Stage | Gate | Companion skill |
|---|---|---|
| `unscoped` | Starting state. Exit when one reachable community or buyer segment is specific. | `find-community` |
| `community_identified` | One reachable community or buyer segment is specific, and the user has a credible way to contact members. | `find-community` |
| `problem_observed` | The problem, current workaround, or consequence is supported by direct observation, buyer conversation, current spending, or behavior in a focused prototype test. | `validate-idea` |
| `offer_defined` | One buyer, result, boundary, delivery method, turnaround time, and initial price are explicit; a manual, agent-built, or hybrid version can be delivered now. | `processize`, `mvp` |
| `buyers_listed` | At least three named or precisely locatable prospects match the buyer definition and have a lawful contact path. | `first-customers` |
| `outreach_started` | At least one personalized message or sales conversation has actually reached a prospect. Drafting alone does not cross the gate. | `first-customers` |
| `interest_observed` | A prospect takes a costly action: detailed reply, call, requested proposal, checkout attempt, deposit, or equivalent. A like or compliment is insufficient. | `validate-idea`, `pricing` |
| `paid` | The Definition of Done is satisfied and minimally redacted evidence is recorded. | `pricing` |
| `delivered` | The promised result is delivered or the buyer receives the agreed remedy; feedback and process changes are recorded. | `processize`, `minimalist-review` |

Marketing and growth are downstream branches. Use `marketing-plan` only after repeatable sales evidence, `grow-sustainably` for real cost or scaling decisions, and `company-values` when operating principles or hiring become current constraints.

## Checkpoint

Maintain this structure, omitting empty optional detail rather than inventing it:

```yaml
goal: first verified customer payment
stage: unscoped # then community_identified, problem_observed, offer_defined, buyers_listed, outreach_started, interest_observed, paid, or delivered
customer:
  segment:
  reachability:
problem:
  situation:
  current_workaround:
  consequence:
offer:
  result:
  boundaries:
  delivery:
  turnaround:
  price:
buyer_candidates: []
assumptions: []
evidence: []
experiments: []
payment:
  classification: none # or interest, relationship_payment, verified_customer_payment
  amount:
  currency:
  date:
  status:
current_bottleneck:
next_action:
```

Each evidence entry records `date`, `claim`, `kind`, `source`, and `implication`. Use evidence kinds such as `user_report`, `direct_observation`, `buyer_words`, `current_spend`, `costly_action`, and `settled_payment`. Quote buyer words only with permission; otherwise summarize and mark the summary as such.

Each experiment records the riskiest assumption, learning instrument, target users, time or money budget, success and stop signals, offer or prototype shown, observed behavior, recurring objections, result, and next decision. For outreach, also record sent/replied/interested/paid counts. Zero responses, rejection, and prototype abandonment are evidence, not failure to report.

## Action Boundary

Research and drafting do not authorize external action. Before sending a message, publishing, submitting a form, creating a checkout, spending money, charging, deploying, or changing an account:

1. Show the exact target, content, cost, and reversible consequences.
2. Ask for explicit approval scoped to that single action.
3. Execute only the approved action and read back the result.

Use the cheapest credible experiment. Prefer an agent-built prototype over prolonged speculation when interaction with the product is the important unknown and the test is cheap, safe, reversible, and disposable. Prefer manual delivery when the unknown is whether the outcome itself is valuable. Invest in durable product infrastructure only after user behavior or repeated delivery reveals what deserves to survive. Do not create payment infrastructure merely to simulate demand; use the smallest lawful payment method the buyer can actually use.

## Response Contract

Keep each turn compact and action-oriented:

```markdown
Stage: <current stage>
Evidence: <strongest fact and its evidence kind>
Bottleneck: <earliest unmet gate>
Next action: <one action>
Success signal: <observable evidence that crosses or informs the gate>
```

If the user asks for analysis, explain the decision and still finish with one next action. If blocked, name the missing evidence and the smallest way to obtain it. Reaching `paid` is the first-dollar milestone; reaching `delivered` closes the ethical and operational loop.
