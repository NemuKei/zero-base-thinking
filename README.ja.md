<div align="center">

# Zero-Base Thinking

**目的を確かめる。手段を、白紙から考える。**

プロジェクト、仕事の進め方、まだ形のないアイデアを考え直すためのAgent Skill。

[使ってみる](#使ってみる) · [対話を読む](examples/skill-redesign.ja.md) · [English](README.md)

[MIT](LICENSE) · [実験版 · v0.1.2](eval/README.md)

</div>

---

プロジェクトには、決めごとが積み重なります。今も役立つものもあれば、いつの間にか疑わなくなった前提もあります。

Zero-Base Thinkingは、まず何を大切にしたいかを確かめ、今から始めるならどうするかを一緒に考えます。今のやり方に違和感があるときにも、まだ形のない構想にも使えます。

## 使ってみる

[skills CLI](https://github.com/vercel-labs/skills)で導入し、表示された選択肢から使うエージェントを選びます。Node.js 22.20以上が必要です。

```sh
npx skills add NemuKei/zero-base-thinking --skill zero-base-thinking --global
```

プロジェクト内へのファイル配置は検証済みです。全プロジェクト共通の導入と、各AIアプリでの認識・呼び出しは、まだ通しでは検証していません。[導入の検証記録 →](eval/README.md#installation-checks)

Codexでは、こんな一言から始められます。

```text
$zero-base-thinking
このプロジェクト、決めごとが増えてきた。
ゼロベースで考えて。
```

Claude Codeでは `/zero-base-thinking` を使います。自然文からSkillを選べる環境では、「ゼロベースで考えて」という明示的な依頼も入口になります。

## 考える順序

1. **大切にしたいことを確かめる。** 維持したい目的・意図・価値を言葉にします。古いDocsに書かれた目的も、今の意図と照らして見直します。
2. **白紙から組み立てる。** その価値を実現する方法を考えます。役立つ理由があれば、思い切った案も候補に入れます。
3. **選んだ先を見えるようにする。** 各案で何が変わり、どんな利点や負担があり、何がまだ分からないかを比べます。
4. **現状を位置づける。** 「今のやり方は、この案に近い」と整理してから、何を残し、どう移るかを考えます。

今の良さを残す、別の道へ進む、小さく試す、保留する、やめる。どれも結論になり得ます。選ぶ前に、一度は白紙から考えることを大切にしています。

## 自分の言葉で、対話を進める

通常は、AIが仮に捉えた目的を一問で確かめるところから始まります。

> 維持したい目的・意図・価値は、この理解で合っていますか？

目的がまだ見えていなければ、一緒に探すところから。その対話で確認済みなら、次へ進みます。前提を訂正する、複数の案を組み合わせる、例を求める、まだ決められないと伝える。その返答から、次の問いが変わります。

先に案を見たいときは、そのまま伝えてください。仮定を明らかにした提案から始められます。回答期限は設けず、返事がないことを同意として扱いません。

架空の[Skill設計の対話](examples/skill-redesign.ja.md)と、[チーム会議の対話（英語）](examples/team-meeting.md)で、進み方を読めます。

<details>
<summary><strong>導入オプションと利用環境</strong></summary>

エージェントを直接指定するなら、導入コマンドに `--agent codex` または `--agent claude-code` を追加します。一つのプロジェクトだけに導入する場合は、そのフォルダーで実行し、`--global` を外します。

AIエージェントにリポジトリのURLを渡して、導入を頼む方法もあります。手元のソースや展開したZIPから導入する場合は、`NemuKei/zero-base-thinking` をそのフォルダーのパスに置き換えます。手動配置は[導入案内](skills/zero-base-thinking/INSTALL.md)を参照してください。

パッケージは[Agent Skills形式](https://agentskills.io/specification)の5ファイルです。対話手順、質問ガイド、Codex用設定、導入案内、ライセンスを含みます。本体はMarkdownで、他のSkill、メモリーサービス、常駐処理への依存はありません。

Codex用設定の `allow_implicit_invocation: true` は、自然文からの発見を可能にします。対話を始めるのは、ゼロベースで考えるよう明示的に依頼されたときです。通常の編集依頼は、そのまま通常の作業として扱います。Skill選択機能からだけ呼び出す場合は、導入先の `agents/openai.yaml` で `policy.allow_implicit_invocation` を `false` にします。[CodexのSkill案内](https://learn.chatgpt.com/ja-JP/docs/build-skills)

質問の表示方法は利用環境によって異なります。適した質問UIがなければ、通常のテキストで対話できます。アプリ側のタイマーや初期選択を、このSkillが制御することはできません。

</details>

## 一緒に育てる

現在は実験版です。[評価記録](eval/README.md)には、合成事例、実際に生成された応答、確認できた範囲を残しています。実際の対話でどれだけ役立つかは、引き続き確かめています。

[Issue](https://github.com/NemuKei/zero-base-thinking/issues)や[プルリクエスト](https://github.com/NemuKei/zero-base-thinking/pulls)を歓迎します。目的、AIの応答、考えが進んだ点や引っかかった点を、個人情報を含まない短い例で共有してもらえると助かります。分かる範囲で、使用したエージェントとモデルも添えてください。

対話手順は[SKILL.md](skills/zero-base-thinking/SKILL.md)、問いの組み立て方は[質問ガイド](skills/zero-base-thinking/references/questions.md)にあります。振る舞いを変える提案は、具体的な事例と[評価ガイド](eval/README.md)から始められます。

---

[MIT License](LICENSE) · [NemuKei](https://github.com/NemuKei)
