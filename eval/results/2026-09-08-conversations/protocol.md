# Complete conversation evaluation protocol

This evaluation compares one pair of synthetic conversations for each of three cases. It evaluates the existing v0.1.2 instructions without changing them in response to intermediate results.

## Roles and conditions

- Each arm uses a fresh assistant actor and a separate fresh simulated-user actor. Roles retain only their own dialogue across turns. No conversation or adaptive reply is shared between arms.
- Control assistants receive the shared case context and initial request with no skill files intentionally supplied or loaded. Skill assistants also read the frozen runtime and question guide. Inherited host instructions and catalogs are not removed by this test, so the control is not a bare-model ablation.
- Both user actors receive the same case-specific facts and preferences. They are not given the arm assignment, rubric, or other dialogue. An assistant may identify the skill in its reply, so masking is not guaranteed.
- The parent relays the simulated user's exact reply. User-role metadata and unreleased scenario facts are withheld from the assistant. The parent does not write or revise adaptive user replies.
- All assistant and user actors inherit the calling session's model and reasoning effort without overrides. The exact resolved backend build and effective settings are not independently exposed.
- This is offline text dialogue. Actors do not browse, operate the native question UI, execute the simulated project, or contact a real user. The final ordinary edit is performed as a text response.

## Cases and branching

The purpose-recovery case includes a scenario-defined request for a concrete explanation and a later change in the user's account of the desired value. The wording and subsequent turns depend on the assistant's actual response. The change is a preauthored simulation event, not evidence of spontaneous human insight.

The sound-current-approach case permits a fresh construction to support retaining a simple, apparently adequate arrangement. The user remains open to an alternative with a reasoned benefit and does not insist on preservation.

The proposal-first-scope case begins with a request for options using incomplete facts, preserves verified rules and source data, and later supplies a delivery constraint. A bounded next check may be the useful outcome.

After a direction or bounded verification has been discussed, the user asks for an ordinary wording edit. Successful completion of that edit is checked separately from the quality of the preceding discussion.

There are at most seven assistant responses in the recovery case and five in each other case. These are evaluation ceilings, not user answer deadlines. Reaching a ceiling without closure is recorded as incomplete; it is not converted into agreement.

Initial facts are comparable across arms, but adaptive replies can supply different details at different times. The results must disclose those differences, dispatch order, and the absence of cross-arm carryover. This is one sample per case and arm, without a statistical improvement estimate.

## Semantic review

Review complete transcripts with pass, partial, fail, or not_applicable judgments and cite the relevant turns. Consider:

1. Whether the intended value is established or revisited where necessary, and current explicit constraints remain intact.
2. Whether a positive construction from that value is visible, with useful mechanisms beyond inherited assumptions.
3. Whether explanation requests produce a concrete repair, and new concerns or changed answers actually alter the inquiry and proposals.
4. Whether requested proposals appear with uncertainty visible, and the discussion reaches a reasoned direction or a useful bounded next check.
5. Whether a sound current arrangement is considered on its merits without a reflexive preference for preservation or replacement.
6. Whether repeated questions, ignored answers, invented facts, premature conclusions, or excessive interviewing occur.
7. Whether the later ordinary edit is completed without restarting the zero-base dialogue.

Record conversational effort as observed turns and response length, without treating smaller counts as success. Judge the relation between proposals and the user's expressed value, not only literal instruction compliance. Simulated agreement and AI judgments do not establish real-user insight or acceptable effort.

## Evidence and follow-up

Retain initial case facts, user-only scenario briefs, role instructions, complete exact transcripts, file hashes, conditions, and unavailable metadata. Public cases and transcripts contain synthetic material only.

If a material defect appears, prepare a focused reproduction before recommending runtime changes. If the observed differences do not justify a change, retain the current instructions. Human-perceived usefulness and effort require explicit human feedback; that part remains unmeasured in this automated evaluation.
