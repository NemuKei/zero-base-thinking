# Native Codex CLI installation check — v0.1.2

The public-repository installation path worked in a fresh disposable local profile on macOS 26.6.2 with Codex CLI 0.153.4. The installed skill contained the expected five files, each matching the source bytes. The existing user's skill files and symlink matched their pre-test state afterward; the parent configuration also matched the recorded initial hash at the final check.

| Check | Result | Evidence |
| --- | --- | --- |
| User-wide installation from GitHub | pass | [Installer output](install-output.txt); five-file hash parity in [report.json](report.json) |
| Native discovery and selection | pass | The TUI's `/skills` list displayed **Zero-Base Thinking**. Selection injected the exact installed body from the user-scope path. [Record](direct-native.json) |
| Direct invocation and linked guide | pass | A request through `$zero-base-thinking` read `references/questions.md` and opened with a tentative purpose check. [Response](responses/direct-native.md) |
| Japanese request from another project | pass | A fresh `codex exec` session in project B selected the workflow from an explicit Japanese zero-base request and read both installed instruction files. No project-local skill was present. [Trace](natural-ja-project-b.json) |
| Ordinary edit | pass | A separate session replaced the requested README wording. It did not load Zero-Base Thinking or begin its dialogue. The resulting file contents were checked directly. [Trace](ordinary-edit-project-a.json) |

## Conditions

The installer was `skills@1.5.24` on Node.js 24.20.0. The command followed the README's public source and `--global` path, adding `--agent codex` and `--yes` for unattended selection and confirmation. Telemetry was disabled for the recorded installer run.

The test child processes used a disposable user directory and two fresh Git projects. A dedicated local app-server on a test-owned Unix socket served the native TUI. Separate non-interactive CLI sessions tested Japanese routing and the ordinary edit. The TUI reported `gpt-6-astra` with default reasoning; the exact backend build and effective default reasoning effort were not independently exposed.

A current ChatGPT login cache was reused locally, without copying the refresh credential. First-time account sign-in was outside the test. Existing account-synchronized plugins remained available; an unrelated MCP startup warning and a skill-description budget notice appeared without preventing these checks. This was a fresh local profile, not a new account or a plugin-free environment.

The native selector record was extracted from the test session's visible assistant messages and tool calls. The exec traces retain task messages, command/file events, and completion status. Credentials, system/developer instructions, reasoning records, account identifiers, and unrelated plugin output are excluded. Test directory paths are replaced with placeholders.

## Scope of the result

This verifies the recorded Codex CLI workflow on this macOS environment, including availability across the two projects. It does not verify the desktop app UI, IDE extension, Claude Code, Windows, Linux, or every combination of agent settings. Natural-language routing was observed once; it is not a guaranteed phrase parser.

The packaged `INSTALL.md` instructions remain compatible with this result. Its other host examples describe installation options, not additional native verification claims. The current [README](../../../README.md) and [distribution record](../../distribution.json) identify the verified scope.

The relevant official references describe [user-scope skill discovery](https://learn.chatgpt.com/docs/build-skills), [cached authentication](https://learn.chatgpt.com/docs/auth), and the [native `/skills` command](https://learn.chatgpt.com/docs/developer-commands?surface=cli). Observed results above come from the installed CLI, rather than from assuming that documentation guarantees a successful run.
