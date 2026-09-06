# Install Zero-Base Thinking / 導入

This folder is a complete skill. It contains no account configuration, personal memory, or dependency on another skill.

ファイルを扱えるAIエージェントへ、このフォルダーまたはZIPを渡して「このSkillを導入して」と依頼できます。既存の導入がある場合は、上書き前に差分を確認してください。

With Node.js 22.20 or later, run this from the extracted folder:

```sh
npx skills add . --skill zero-base-thinking --global
```

Choose your agent if prompted. Use `--agent codex` or `--agent claude-code` to select one directly. The [skills CLI](https://github.com/vercel-labs/skills) also accepts a Git repository URL in place of `.`.

For manual installation, copy this complete folder into the skill directory supported by your agent, keeping its name `zero-base-thinking`. For example, Codex supports `~/.agents/skills/zero-base-thinking/`; Claude Code supports `~/.claude/skills/zero-base-thinking/`. Other hosts may use different directories or an upload interface. Check the host's skill selector after installation.

After installation, use `$zero-base-thinking` in Codex or `/zero-base-thinking` in Claude Code. See the [Codex](https://learn.chatgpt.com/docs/build-skills) and [Claude Code](https://code.claude.com/docs/en/skills) documentation for host-specific discovery.

「ゼロベースで考えて」という明示依頼も対象です。導入後の選択方法は、使うAIエージェントに合わせてください。
