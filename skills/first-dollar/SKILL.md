---
name: first-dollar
description: Guide a solopreneur from a reachable customer problem to a first verified customer payment. Use when someone wants their first online revenue, needs the next step from idea to sale, or wants one evidence-tracked journey across community, validation, offer, outreach, payment, and delivery.
---

# First Dollar

Orchestrate the shortest honest path to one verified customer payment. Reuse the companion skills when they are installed; otherwise handle the necessary step directly. Keep the user's judgment and every consequential action under their control.

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
3. Work only on that bottleneck. Ask one focused question or produce one concrete artifact that can cross its gate.
4. Update the checkpoint with new facts, assumptions, evidence, and experiment results. Never turn an assumption into a fact or use invented precision to rank ideas.
5. End with exactly one next action that the user can complete or approve. Include its expected evidence and approximate cost in time or money when material.

When a writable project workspace is already in scope, offer a preview before creating `first-dollar.md`; otherwise keep the compact checkpoint in the conversation. Treat the checkpoint as user-owned and portable. Never store credentials, full payment identifiers, private customer messages, or unnecessary personal data.

## Evidence Gates

Advance only when the current gate is met. Move backward when new evidence invalidates an earlier assumption.

| Stage | Gate | Companion skill |
|---|---|---|
| `unscoped` | Starting state. Exit when one reachable community or buyer segment is specific. | `find-community` |
| `community_identified` | One reachable community or buyer segment is specific, and the user has a credible way to contact members. | `find-community` |
| `problem_observed` | The problem, current workaround, and consequence are supported by direct observation, buyer conversation, or current spending. | `validate-idea` |
| `offer_defined` | One buyer, result, boundary, delivery method, turnaround time, and initial price are explicit; a manual version can be delivered now. | `processize`, then `mvp` only if building is justified |
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

Each experiment records the hypothesis, target prospects, offer shown, channel, sent/replied/interested/paid counts, recurring objections, result, and next decision. Zero responses and rejection are evidence, not failure to report.

## Action Boundary

Research and drafting do not authorize external action. Before sending a message, publishing, submitting a form, creating a checkout, spending money, charging, deploying, or changing an account:

1. Show the exact target, content, cost, and reversible consequences.
2. Ask for explicit approval scoped to that single action.
3. Execute only the approved action and read back the result.

The default validation offer is manual and reversible. Build software only when repeated delivery reveals a stable step worth automating. Do not create payment infrastructure merely to simulate demand; use the smallest lawful payment method the buyer can actually use.

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
