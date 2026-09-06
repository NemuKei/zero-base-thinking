---
name: zero-base-thinking
description: >-
  Use when the user explicitly requests zero-base thinking, a blank-sheet reconsideration, or ゼロベースで考えて for a project, skill, business idea, or new concept. Do not infer this request from frustration, an ordinary improvement, a new-build task, or a mention of the skill alone.
license: MIT
metadata:
  version: "0.1.0"
---

# Zero-Base Thinking

Help the user discover what feels wrong, what is worth achieving, and which question deserves attention. **Complete at least one construction from a blank sheet before recommending a direction.** Keeping, changing, rebuilding, redirecting, pausing, and stopping are possible outcomes.

Work in the user's language. A conversation is sufficient; code, documents, a repository, memory, special UI, and other agents are optional.

## Entry and boundaries

Use this workflow only for an explicit request to think from zero. A quoted example, discussion of this skill, or “I'm stuck; fix this small bug” is not activation. If the host loads it for an unrelated task, continue the requested task without the interview.

Existing work enters through a concrete mismatch. A new concept enters through its hoped-for value; do not invent dissatisfaction or require an existing artifact. Honor the scope and constraints the user currently specifies, including a request to preserve particular logic.

Past decisions and documents are evidence of what was decided and why. Their assumptions, goals, and definitions can be wrong or outdated. Check their basis instead of granting them immunity. A recorded design preference is not automatically an external constraint. Reconsidering a design does not remove actual obligations or authorize changes to permissions, data, or live systems.

## 1. Locate the mismatch and the intended value

For existing work, find a specific moment: what happened, what the user expected, and what felt off. Separate that observation from an explanation of its cause. Trace plausible connections through presentation, behavior, approach, problem choice, and intended value. The cause may be upstream, but that is a hypothesis to examine.

Read only relevant material. Distinguish observed facts, user-stated intentions, actual constraints with their basis, and assumptions. Reopen a documented purpose when it no longer explains the value the user wants. Do not replace missing intentions with a confident interpretation.

For a new concept, start with who might benefit and what change would matter. The proposed product or technique is a candidate means, not a settled goal.

## 2. Use questions to reveal and organize thinking

Before asking substantive questions, read [the question guide](references/questions.md). Its rules cover understandable consequences, explanation help, recommendations, adaptation, and question UI limits.

Ask the next question whose answer can change the problem, value, or direction. Questions are prompts for discovery, not a form to complete. A rejection of the options, a mixed answer, hesitation, or a new thought may be the most useful result. Reflect your interpretation provisionally and let the user correct it. Rebuild the question sequence around new information instead of requiring answers to obsolete questions.

Obtain accessible facts yourself using authorized sources. User answers can settle their intentions and priorities; they do not prove market demand, causality, effectiveness, or feasibility. Keep those claims as hypotheses until supported.

Continue until the current value and scope support a meaningful blank-sheet attempt. Essential unknowns stay open: ask about them or offer clearly conditional scenarios. Do not imply that unanswered decisions are settled.

## 3. Construct from a blank sheet — required

Create a short brief containing:

- The value or purpose reconsidered in this conversation, with unresolved parts marked.
- Relevant observations and their basis.
- Current user-specified boundaries and verified constraints.
- Open assumptions that could change the direction.

Leave the inherited architecture, feature list, previous recommendation, and sunk effort out of the design brief. Bring in existing knowledge as observations, not as a requirement to preserve its implementation. Do not decide what is reusable yet.

From this brief, construct a positive account of what would make sense if no current solution existed: who receives what change, through what mechanism, and what the simplest useful arrangement would be. An arrangement can be a conversation, service, process, tool, or no new undertaking. Merely promising to “think from zero” or deleting features from the old backlog does not complete this step.

If isolated agent work is available and authorized, it can receive only this brief and relevant raw evidence to propose an independent construction. Otherwise perform the pass in the current conversation. Neither method guarantees freedom from anchoring; do not claim that context has been erased.

Make the construction visible in a concise proposal before comparing it with the current approach. If it converges on the current design, explain how the reconsidered value and constraints lead there. The pass remains required when the current solution looks adequate. If more user input is needed, leave it pending rather than claiming it is complete.

## 4. Compare the futures, then consider reuse

Compare the blank-sheet construction with the relevant existing approach and credible alternatives. Include a partial change, another means, pausing, or stopping when they are live alternatives; do not manufacture a fixed number of options.

For each consequential choice, make the anticipated result imaginable: what changes for whom, what they would do or experience next, what burden or opportunity is gained or lost, and why the result might follow. Connect that result to the user's stated intention. Mark uncertain outcomes and what would verify them. A method name or a generic advantage is not enough to support a choice.

Judge future work, verification, transition, ongoing effort, and expected value. Past effort does not make a design correct; a cheap rewrite does not make it valuable. Now identify which knowledge, logic, data, or implementation is useful to retain.

Recommendations are reasoned proposals that the user can reject or reshape. Choosing an option does not reveal an unspoken motive or prove comprehension. When the user expresses confusion, repair the explanation before treating their choice as settled.

## 5. Close with a useful decision or a useful uncertainty

Summarize only what matters:

- The mismatch or opportunity and the question now worth answering.
- The blank-sheet construction and which prior assumptions changed or held up.
- The selected or proposed direction, its expected consequences, and why it fits the intention.
- What remains uncertain and the smallest useful next verification or action.

Use concise prose or a compact comparison; omit empty or redundant fields. Separate a recommendation from a user-adopted decision. A pause or a targeted experiment can be a complete outcome; every branch need not be settled.

Detailed specification, implementation, or document revision follows the user's authorization and the host's normal workflow. This skill does not automatically start another skill, publish work, overwrite old decisions, or persist a personal profile. Preserve the reasoning in the conversation; write a durable artifact only when requested or already authorized.
