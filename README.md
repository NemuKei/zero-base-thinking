# Zero-Base Thinking

[日本語](README.ja.md)

An instruction-only skill for moments when adding another improvement feels wrong, and for ideas that have not taken shape yet. Use dialogue to discover the actual intention, reconsider documented assumptions, and construct an approach from a blank sheet at least once.

Thinking from zero is mandatory. Rebuilding is one possible decision. A useful outcome may also be a small change, a different approach, an experiment, a pause, or stopping.

**Status: experimental, version 0.1.0.** Synthetic behavioral evaluations are described in [eval/README.md](eval/README.md). They do not establish effectiveness across models, users, or real projects.

## Use it

Invoke the skill explicitly using your host's skill selector or, where supported:

```text
$zero-base-thinking

Something feels wrong about this project. Help me work out what it is,
then reconsider the purpose and approach from zero.
```

Other requests include “ゼロベースで考えて” and “Think from a blank sheet; keep the calculation rules, but reconsider the workflow.” A new concept does not need an existing project or a feeling of dissatisfaction.

The skill asks questions to help the user discover and articulate thoughts. Options explain the consequences of choosing them, and provide a route to ask for an explanation. Free response, mixed answers, disagreement, and new insights are part of the process. There is no answer deadline. Explanation requests help adapt subsequent wording within the conversation; they do not become an expertise score or a persistent profile.

See a [team-meeting example](examples/team-meeting.md) or a [Japanese skill-design example](examples/skill-redesign.ja.md). The examples and evaluation fixtures are invented, rather than records of a particular person's projects or preferences.

## Install

With a coding agent that can install skills, ask:

```text
Install Zero-Base Thinking from https://github.com/NemuKei/zero-base-thinking
for my coding agent. Review any existing installation before replacing it,
then verify that the skill and its question guide are available.
```

Or, with Node.js 22.20 or later, run:

```sh
npx skills add NemuKei/zero-base-thinking --skill zero-base-thinking --global
```

**Verification scope:** file installation in isolated projects has been checked. User-wide (`--global`) installation and discovery/invocation inside native agent sessions have not yet been verified end to end. See the [installation checks](eval/README.md#installation-checks).

Select your agent if prompted. The [standard skills CLI](https://github.com/vercel-labs/skills) handles the destination. To target Codex directly, append `--agent codex`; for Claude Code, append `--agent claude-code`. To install only for one project, run the command from that project and omit `--global`. For a downloaded source or extracted skill folder, replace `NemuKei/zero-base-thinking` with that folder's path, or with `.` when running inside it.

The installable package lives in [`skills/zero-base-thinking/`](skills/zero-base-thinking/INSTALL.md). Its five files include all runtime instructions, metadata, the license, and a short installation note. Contributor documentation and synthetic evaluation records stay outside the installed skill. No custom installer or persistent background process is required.

Use your host's skill selector to confirm discovery. In Codex, invoke `$zero-base-thinking`; in Claude Code, invoke `/zero-base-thinking`. See the [short installation note](skills/zero-base-thinking/INSTALL.md) for the manual fallback.

## Activation and host support

The included Codex metadata permits prompt-based discovery (`allow_implicit_invocation: true`) so an explicit natural-language request can select the skill. The description and the entry guard restrict it to such requests: frustration, a routine improvement, or an ordinary new-build request is not sufficient. This is semantic routing, not a guaranteed phrase parser.

For command/selector-only activation in Codex, set `policy.allow_implicit_invocation` to `false` in the installed `agents/openai.yaml`. The natural-language phrase alone then does not provide that automatic discovery route; invoke the skill explicitly through the host. See [OpenAI's skills documentation](https://learn.chatgpt.com/docs/build-skills).

The format follows the [Agent Skills specification](https://agentskills.io/specification). Host-specific metadata and question interfaces are not part of a universal UI contract. A host without a suitable question tool can use permitted untimed text dialogue. The skill cannot remove a countdown or a default selection that a host does not allow it to control.

## What the skill does

1. Ground a mismatch or opportunity and reconsider the intended value.
2. Use understandable questions to reveal missing intentions and assumptions.
3. Construct an approach without inheriting the current solution as the premise.
4. Compare imaginable outcomes and future costs, then consider reuse.
5. Return the question worth answering, a proposed or chosen direction, and remaining uncertainty or a next verification.

Current user-specified boundaries still matter. Documents can be reassessed as design evidence; that does not erase actual obligations or grant permission to change live systems.

The skill has no mandatory dependency on a repository, memory system, model vendor, other skill, network connection, or subagent. Where available and authorized, a separate agent can construct an alternative using a brief with reconsidered intentions and evidence. A separate context reduces some shared context; it does not guarantee an unbiased result.

## Maintaining and evaluating

[`skills/zero-base-thinking/SKILL.md`](skills/zero-base-thinking/SKILL.md) owns the workflow. Its [`references/questions.md`](skills/zero-base-thinking/references/questions.md) owns the question design details and is loaded when asking questions. README files explain use and installation; they are not additional runtime instructions.

Use the [evaluation cases and rubric](eval/README.md) to check meaningful behavior after changes. Evaluate in fresh contexts, keep raw outputs, include a control without the skill, and distinguish an unfinished conversation from a completed decision. A response that asks an essential question is not required to invent a final design in the same turn.

Check frontmatter and relative links as well as behavior. Record the skill and reference hashes with evaluation results. Add a test when a new observed failure justifies it; avoid growing the skill around hypothetical edge cases.

The package is independent. It neither assumes another framing workflow is installed nor migrates other skills, personal settings, or memory stores.

## License and attribution

MIT; see [LICENSE](LICENSE). This skill was developed as an original instruction set. The copyright notice identifies the author; it does not encode a user's personal configuration or circumstances.
