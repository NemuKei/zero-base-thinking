# Proactive opening evaluation — v0.1.1

The new default opens an explicit, open-ended zero-base request as a conversation, without requiring a separate request for questions. An explicit proposal-first request and ordinary-task boundaries remain intact.

Two baseline samples used v0.1.0. The mismatch case already opened with a useful question. With rich background, the other baseline said it could already produce a proposal and delivered a complete recommendation without opening a dialogue. The change makes the desired conversational default explicit; this does not establish that every v0.1.0 invocation was passive.

Five fresh-context candidate samples met their focused criteria. Actors were requested as `gpt-6-astra` with `medium` reasoning effort for both arms; the spawn interface accepted those requests. The exact backend build and effective runtime configuration were not independently exposed. Each actor saw only its case and the relevant skill snapshot, not scoring criteria or other outputs.

| Case | Result | Observation | Evidence |
| --- | --- | --- | --- |
| `open-existing` | pass | Opens with a short observation and one concrete question about the experience to change, with consequential options, selectable explanation help, and free response. This case already opened well in the baseline. | [response](responses/candidate-open-existing.md) |
| `bare-invocation` | pass | Helps locate a topic through one approachable entry question without demanding a completed problem statement or inventing a project. | [response](responses/candidate-bare-invocation.md) |
| `proposal-first` | pass | Provides an actual blank-sheet proposal and comparison using available information, marks assumptions, and does not require an opening question before the requested draft. | [response](responses/candidate-proposal-first.md) |
| `ordinary-edit` | pass | The loaded skill entry guard does not start a zero-base dialogue for an ordinary edit. This is a text-guard check, not native host discovery or an executed edit. | [response](responses/candidate-ordinary-edit.md) |
| `well-described-topic` | pass | Rich background no longer leads straight to a completed recommendation. The response begins inquiry with a discriminating question about actual handover experiences rather than repeating the settled purpose. | [response](responses/candidate-well-described-topic.md) |

See [report.json](report.json) for criterion-level judgments, source hashes, the baseline revision, and both baseline outputs. These are offline next-response samples. They do not close the complete-conversation and human-value work tracked in [issue #1](https://github.com/NemuKei/zero-base-thinking/issues/1), and they do not test native question UIs or host discovery.

## Follow-up probe

After the rich-context response, both actors received the same scripted user reply about having information but still being unable to judge. Both asked a further question to clarify that meaning. The [baseline](responses/baseline-followup-intent.md) first proposed another arrangement; the [candidate](responses/candidate-followup-intent.md) briefly reflected a tentative distinction and asked what the successor actually asks the previous owner. It offered examples and invited remembered wording, instead of treating the short selection as a complete account of intent.

This adds a paired two-response probe, not a completed conversation or evidence that a real person gained insight. The response burden and usefulness of the elicited language still require real-user evaluation.
