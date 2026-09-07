<div align="center">

# Zero-Base Thinking

**Keep the purpose. Rethink the path.**

An Agent Skill for rethinking projects, workflows, and ideas from a blank sheet.

[Get started](#get-started) · [See a conversation](examples/team-meeting.md) · [日本語](README.ja.md)

[MIT](LICENSE) · [Experimental · v0.1.2](eval/README.md)

</div>

---

Projects accumulate decisions. Some still serve their purpose; others become assumptions nobody revisits.

Zero-Base Thinking helps you agree on what matters, then find ways to achieve it as if starting today. Use it when an existing approach feels wrong, or when a new idea is still taking shape.

## Get started

Install with the [skills CLI](https://github.com/vercel-labs/skills), then choose your agent when prompted. Requires Node.js 22.20 or later.

```sh
npx skills add NemuKei/zero-base-thinking --skill zero-base-thinking --global
```

File installation has been checked in isolated projects. Global installation and discovery inside native agent sessions are still awaiting end-to-end verification. [Installation checks →](eval/README.md#installation-checks)

In Codex, start a conversation with:

```text
$zero-base-thinking
This project has accumulated a lot of rules.
Let's rethink it from zero.
```

In Claude Code, use `/zero-base-thinking`. An explicit request such as “Think from a blank sheet” or “ゼロベースで考えて” can also select the skill where the host supports natural-language discovery.

## How it thinks

1. **Agree on what matters.** Check the purpose, intention, and value worth preserving. Old documents are evidence to examine.
2. **Start from a blank sheet.** Find different ways to deliver that value, including a substantial reset when it has a useful advantage.
3. **Make the tradeoffs clear.** Describe what each option would change, its benefits, its burden, and what remains uncertain.
4. **Place the current approach.** See which option it resembles, then consider what to retain and how to move forward.

Keeping what works, changing direction, trying a small experiment, pausing, and stopping can all be useful outcomes. The blank-sheet pass comes before the choice.

## A conversation you can steer

The assistant normally opens by checking its understanding:

> Is this the purpose and value you want to preserve?

If the purpose is unclear, it helps you find it. If you have already settled it in the conversation, it moves forward. You can correct the premise, combine options, ask for an example, or say you cannot decide yet. Your answers shape the next question.

Want a proposal first? Say so. The assistant can offer a draft with its assumptions visible. Questions have no answer deadline, and silence is never a decision.

Explore a fictional [team-meeting conversation](examples/team-meeting.md) or a [skill-design conversation in Japanese](examples/skill-redesign.ja.md).

<details>
<summary><strong>Installation options and host support</strong></summary>

Append `--agent codex` or `--agent claude-code` to choose an agent directly. For a project-only installation, run the command from that project and omit `--global`.

You can also give your agent the repository URL and ask it to install the skill. For a local checkout or extracted ZIP, use that folder's path in place of `NemuKei/zero-base-thinking`. See the [installation note](skills/zero-base-thinking/INSTALL.md) for manual installation.

The package follows the [Agent Skills format](https://agentskills.io/specification) and contains five files: the workflow, question guide, Codex metadata, installation note, and license. Its core is Markdown, with no required dependency on another skill, memory service, or background process.

Codex metadata enables natural-language discovery with `allow_implicit_invocation: true`. The workflow still requires an explicit zero-base request; routine edits continue as ordinary tasks. For selector-only activation, set `policy.allow_implicit_invocation` to `false` in the installed `agents/openai.yaml`. See the [Codex skills documentation](https://learn.chatgpt.com/docs/build-skills).

Question controls depend on the host. Plain-text dialogue is sufficient when no suitable question UI is available. The skill does not control host timers or default selections.

</details>

## Help it get better

This is an experimental skill. The [evaluation record](eval/README.md) contains synthetic cases, raw responses, and the limits of what has been checked. Its usefulness across real conversations is still being explored.

[Issues](https://github.com/NemuKei/zero-base-thinking/issues) and [pull requests](https://github.com/NemuKei/zero-base-thinking/pulls) are welcome. A small, anonymized example is especially useful: what you wanted, what the assistant did, and where the conversation helped or went off course. Include the agent and model when known.

The workflow lives in [SKILL.md](skills/zero-base-thinking/SKILL.md); question design lives in the [question guide](skills/zero-base-thinking/references/questions.md). For behavior changes, start with a concrete case and the [evaluation guide](eval/README.md).

---

[MIT License](LICENSE) · [NemuKei](https://github.com/NemuKei)
