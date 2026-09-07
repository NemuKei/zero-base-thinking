# Complete synthetic conversations — v0.1.2

Three paired cases produced six complete conversations, each reaching a direction or a bounded next check and then completing the requested ordinary edit. Both the control and skill arms followed changed intentions and fixed constraints. No material failure in these skill samples justified a runtime change.

The skill made independent alternatives and later comparison with the current arrangement more visible. The controls also produced useful proposals, including substantial resets. This small evaluation does not establish overall superiority or real-user usefulness.

| Case | What the pair shows | Control | With skill |
| --- | --- | --- | --- |
| Purpose recovery | Both explain the initial question, adopt workplace application as the revised purpose, offer options when requested, and close with a personal trial. The skill separates its mechanisms from current-state comparison; the control carries burden and evaluation pressure into the final check more explicitly. | [6 responses](transcripts/purpose-recovery-control.md) | [6 responses](transcripts/purpose-recovery-skill.md) |
| Sound current approach | Both support retaining the list and chat conditionally. The skill compares that arrangement with asking the chat each time; the control mainly examines the current arrangement's functional fit. | [3 responses](transcripts/sound-current-approach-control.md) | [4 responses](transcripts/sound-current-approach-skill.md) |
| Proposal first, fixed scope | Both provide options immediately, retain the verified rules and original data, incorporate the newly supplied mandatory format, and close with a representative-case check. | [3 responses](transcripts/proposal-first-scope-control.md) | [3 responses](transcripts/proposal-first-scope-skill.md) |

Response counts include the final ordinary edit. All six edits matched the requested visible text exactly, allowing terminal whitespace. This checks response behavior after an explicit task switch, not a real project edit or native UI routing.

## A detail to keep watching

In the skill recovery conversation, A4 discusses the effort of private notes and the possibility that consultation could still feel evaluative. A5 confirms the user's chosen one-attempt trial and explicitly checks application and obstacles, but does not separately revisit burden or evaluation pressure. The control's A5 includes both.

The narrower final check could matter because the earlier discomfort helped define an acceptable approach. It is a coverage difference in one sample, with benefit still unproven and the user having narrowed the trial at U5. It is not evidence of harm or a demonstrated need for another instruction. Retain the current runtime and look for explicit real-use feedback before expanding it around this observation.

## How the comparison was run

Each arm used a fresh assistant and a separate fresh simulated user. The assistant received shared initial facts and a request; the skill arm also loaded the frozen v0.1.2 workflow and question guide. User roles received the same case-specific facts and preferences, and replied to their own assistant's actual messages. The parent relayed their reply text without rewriting it.

The [case facts](../../conversation-cases.json), [protocol](protocol.md), [role instructions](role-prompts.md), and [setup](setup.json) describe the inputs and execution conditions. The source snapshot is revision `74b642f936efe260ad1f152b61805c5e8b5bdffe`; [report.json](report.json) records runtime and fixture hashes, per-criterion judgments, and run statistics. Complete exact messages are preserved in the paired Markdown and JSON transcripts.

All actors used the same model/effort inheritance mechanism with no overrides. The resolved backend build and effective settings were not independently exposed. Initial assistants started in this order: recovery control, recovery skill, sound skill, sound control, proposal control, proposal skill. Subsequent turns were interleaved as responses became available; no adaptive reply was copied between arms.

Inherited host instructions and catalogs were not removed, so the control is not a bare-model ablation. User roles were not given arm labels, but assistant announcements can reveal skill use. The recovery explanation request and later value discovery were scenario-defined events, not spontaneous human insight.

## Where the conversations diverged

- **Recovery:** both users revealed the same revised value and evaluation discomfort. Control U4 deferred choosing a concrete learning example; skill U4 explicitly could not identify the obstacle. Control U5 selected a two-week trial, while skill U5 selected one attempt.
- **Sound approach:** control U2 proposed asking participants once about maintenance effort. Skill U2 asked what to observe during the next loan, then supplied a separate decision in U3.
- **Proposal first:** both users disclosed one mandatory format and removable internal duplication. Control U2 requested a verification plan; skill U2 already selected two checks and left implementation open. The control's broader checklist therefore cannot be attributed to the absence of the skill alone.

These differences are part of adaptive conversation. They limit causal comparisons of output, length, and turn count. The longer sound-case skill response includes another viable mechanism and a fuller observation plan; whether that explanation is useful or burdensome to a person is unmeasured. Fewer questions or shorter answers are not success measures by themselves.

## Review and remaining work

The primary agent read all messages. A separate agent reviewed the six transcripts and comparison conditions; see the [independent review](independent-review.md). Neither review found a material conversational failure requiring a runtime change. The observation about the final burden check is retained above.

There is one pair per case, without repeated sampling or a statistical improvement estimate. All apparent understanding and agreement came from simulated users. No human-perceived insight, experienced effort, native question UI, global installation, or actual project execution was measured.

This supplies the automated complete-conversation evidence for [issue #1](https://github.com/NemuKei/zero-base-thinking/issues/1). Keep that issue open for explicit human usefulness/effort feedback and any follow-up that the evidence warrants. The runtime and its version remain unchanged.
