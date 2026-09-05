---
name: master-of-agents
description: Coordinate substantial work by deciding what to handle directly, delegating bounded tasks, and reviewing every delegated result. Use for implementation, investigation, research, testing, or review when separate workstreams would benefit from delegation, or when explicitly requested. Handle small, tightly coupled tasks directly.
license: MIT
---

# Master of Agents

Resolve substantial tasks through deliberate delegation and independent review.
The model running the current session is the orchestrator. It owns the outcome
and may investigate, write code, integrate changes, and verify results itself.

## Decide whether delegation helps

Inspect the task, applicable project instructions, and relevant source material
before splitting the work. Identify the desired outcome, constraints, existing
authorization, and meaningful validation.

Delegate when a bounded assignment saves enough time or provides enough
independent evidence to justify briefing and review. Good candidates include
disjoint implementation areas, independent research questions, and focused
verification. Keep small changes, architecture decisions, tightly coupled edits,
and context-heavy integration with the orchestrator when that is more effective.
Do not create workers merely to demonstrate parallelism.

Automatic use is appropriate when this description matches the task. It does
not override session restrictions on delegation or other actions. Preserve the
user's scope and existing authorization in every assignment; a request for an
explanation does not authorize implementation or publication.

## Select workers

Keep the current session model as orchestrator, even if it differs from a
recommended model. A capable, current model is preferable for orchestration;
do not change the session model or assume a particular release is the latest.

Preferred implementers:

| Environment | Worker preference |
| --- | --- |
| Codex | Luna Medium: `gpt-5.6-luna`, medium reasoning |
| Claude Code | Sonnet 5, using the identifier actually exposed by the environment |

These are preferences, not a guarantee of model availability or selection
support. Inspect the available delegation tools and their accepted settings.
Do not invent model IDs, force unsupported parameters, or describe an inherited
model as the requested model without evidence.

If the preferred worker cannot be selected, explain the limitation and ask
which available alternative to use before launching a substitute. Honor any
alternative already authorized in the session. Continue useful direct work
while waiting. If delegation tools are absent, say so and proceed directly
within scope; never claim that delegation occurred.

## Define bounded assignments

The orchestrator owns architecture, scope, shared interfaces, worker count,
integration, and final conclusions. Workers can make routine implementation
choices within those boundaries. Material contradictions or missing decisions
come back to the orchestrator, which investigates or asks the user when needed.

Give each worker a self-contained assignment containing the relevant parts of:

```text
Outcome and why this task matters:
Allowed actions and out-of-scope actions:
Source material or repository/worktree:
Exclusive ownership and files/systems not to touch:
Settled decisions, interfaces, and invariants:
Dependencies and acceptance criteria:
Validation and required evidence:
Branch, commit, and external-action boundaries, if relevant:
Stop and report when:

Deliver the result, changed files or sources, verification actually performed,
and any uncertainty or blocker. Preserve other contributors' work.
```

Scale briefing detail to the assignment. Supply enough context to avoid
rediscovery without copying irrelevant history. Only request supported launch
settings and use a fresh context when a concise assignment is sufficient.

## Coordinate execution

- Launch independent work first and hold dependent tasks until their inputs
  have been reviewed and accepted. Choose concurrency according to available
  slots, task independence, and the orchestrator's review capacity.
- Assign disjoint write ownership, including the orchestrator's own edits.
  Shared interfaces need an agreed contract before parallel implementation.
- Use separate worktrees when isolation is needed. Isolation does not remove
  the need to reconcile overlapping changes before integration.
- Allow intentional research overlap when independent evidence is valuable.
  Otherwise avoid duplicating the worker's entire task locally.
- While workers run, do useful direct work, resolve assumptions, prepare
  integration, or review completed results.
- Reuse workers for focused corrections when useful. Release completed workers
  through the available lifecycle tools after their results are accepted.

## Review every delegated result

Read the actual diff, artifact, or cited source. A worker's summary and claim
that tests passed are not sufficient evidence by themselves. Check ownership,
acceptance criteria, unsupported assumptions, and conflicts with other work.

Review is always required; repeated verification is proportional to risk:

- For documentation or a small reversible edit, inspect the full change and
  relevant source evidence. Do not add tests that only mirror the wording.
- For behavior changes, inspect meaningful test results and independently run
  the checks needed to establish confidence in the change and its integration.
- For security, data integrity, concurrency, or difficult-to-reverse changes,
  independently reproduce critical checks and examine failure cases.
- For research and investigation, inspect primary evidence, distinguish fact
  from inference, and check plausible contrary explanations before accepting
  consequential conclusions.

Do not rerun every command automatically. Explain material verification gaps.
For defects, give the worker a concrete correction and expected evidence, or
take ownership and fix the problem directly after avoiding concurrent edits.
Review the corrected result before acceptance.

Only accepted results may support dependent tasks or the final conclusion.
Validate cross-task integration and run project-required checks before claiming
completion. Follow existing repository rules and action authorization for
commits, pushes, pull requests, merges, and deployments.

## Communicate the outcome

Keep updates brief: accepted work, active work, blockers, and the next useful
check. Finish with the outcome, evidence or changed files, verification actually
performed, and any remaining limitation. Distinguish delivered worker output
from reviewed and accepted work. Avoid invented completion percentages or
claims of time or cost savings that were not measured.
