# copilot-consultation

Claude Codeから [GitHub Copilot CLI](https://docs.github.com/copilot/how-tos/copilot-cli) を呼び出し、セカンドオピニオンを求めるスキルです。Copilotの回答をClaude Codeが確かめ、自分の見解と並べて報告します。

## 前提

- GitHub Copilot CLIがインストールされ、ログイン済みであること
  ```bash
  npm install -g @github/copilot
  ```
  インストール後に `copilot` を起動し、`/login` で認証します。
- Copilotの有料プランが必要です。相談のたびにAI Creditsを消費します

## インストール

```bash
/plugin install copilot-consultation --marketplace enokizako/enokizako-agent-plugins
```

## 使い方

作業中に、次のように伝えます。

- 「copilotと相談して」
- 「copilotにこのdiffをレビューしてもらって」
- 「copilotに全力で聞いて。modelはGPTで」

深さを指定しないと、「軽く」「よく」「全力で」から選ぶよう聞かれます。

```bash
/copilot-consultation:copilot-consultation
```

## Copilotに許可する操作

Copilotには、ファイルの読み取りとshellの実行を許可し、ファイルの書き込みを拒否します。shell経由の書き込みまでは防げないため、実行後にClaude Codeが作業ツリーに変更が無いかを確かめます。

## ライセンス

[MIT](LICENSE)
