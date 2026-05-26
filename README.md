# 習慣トラッカー

毎日の習慣を記録・分析するPWAアプリです。

## ファイル構成

```
habit-tracker/
├── index.html        # メインアプリ
├── vercel.json       # Vercel設定
├── api/
│   └── ai.js         # AnthropicAPIプロキシ（サーバーサイド）
└── README.md
```

---

## デプロイ手順（Vercel）

### 1. GitHubリポジトリを作成

[github.com](https://github.com) にログインして「New repository」で新しいリポジトリを作成。
このフォルダの中身をすべてアップロード（または git push）します。

### 2. Vercelにデプロイ

1. [vercel.com](https://vercel.com) にアクセスしてGitHubでログイン
2. 「Add New Project」→ 先ほど作ったリポジトリを選択
3. 設定はデフォルトのまま「Deploy」をクリック

### 3. APIキーを設定（重要）

デプロイ後、Vercelのダッシュボードで：

1. プロジェクトの「Settings」タブを開く
2. 「Environment Variables」を選択
3. 以下を追加：
   - Name: `ANTHROPIC_API_KEY`
   - Value: `sk-ant-...`（Anthropic ConsoleのAPIキー）
4. 「Save」したあと「Redeploy」

### 4. iPhoneでホーム画面に追加

1. Safariで発行されたURLを開く（例：`https://your-app.vercel.app`）
2. 画面下の共有ボタン（□↑）をタップ
3. 「ホーム画面に追加」を選択
4. アイコンがホーム画面に追加されてアプリとして使える

---

## APIキーの取得方法

1. [console.anthropic.com](https://console.anthropic.com) にアクセス
2. 「API Keys」→「Create Key」
3. 発行されたキー（sk-ant-...）をコピーしてVercelに設定

---

## 注意

- データはブラウザの `localStorage` に保存されます
- アプリを削除するとデータも消えます
- 複数端末での同期が必要な場合は別途データベース連携が必要です
