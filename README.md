# Resume Project

## 📄 職務経歴書はこちら

**🌐 <https://ryoooosk.github.io/resume/>**

このプロジェクトは職務経歴書を Markdown で管理し、GitHub Pages で公開するためのリポジトリです。

## 機能

- **Markdown 形式での履歴書管理**: `index.md` で履歴書を管理
- **GitHub Pages 対応**: Jekyll（minima テーマ）を使用して Web サイトとして公開
- **品質管理**: textlint と markdownlint による文書品質チェック

## ファイル構成

```sh
resume/
├── README.md              # プロジェクト概要（このファイル）
├── index.md              # 職務経歴書本体
├── _config.yml           # Jekyll設定ファイル
├── package.json          # Node.js依存関係とスクリプト
└── node_modules/         # Node.js依存関係
```

## セットアップ

```bash
# 依存関係のインストール
npm install
```

## 使用方法

### 文書品質チェック

```bash
# textlintとmarkdownlintを実行
npm run lint
```

## GitHub Pages 設定

このリポジトリは GitHub Pages を使用して Web サイトとして公開されます。
`_config.yml` で Jekyll の minima テーマが設定されており、`index.md` の内容が自動的に Web ページとして表示されます。

## 使用ライブラリ

### textlint

日本語文書の校正ツール。次のルールを適用して文章品質を向上させます。

- **@proofdict/textlint-rule-proofdict**: 辞書による校正
- **@textlint-ja/textlint-rule-no-dropping-i**:「い」抜き言葉の検出
- **textlint-rule-ja-hiragana-hojodoushi**: 補助動詞のひらがな表記チェック
- **textlint-rule-ja-no-abusage**: 日本語の誤用検出
- **textlint-rule-ja-no-mixed-period**: 句読点の統一
- **textlint-rule-sentence-length**: 文の長さ制限
- その他多数の日本語校正ルール

### markdownlint-cli

Markdown の記法チェックを行い、一貫性のある文書フォーマットを維持します。

### Jekyll (GitHub Pages)

静的サイトジェネレーター。`minima` テーマを使用してシンプルで読みやすい Web ページを生成します。

## CI/CD

### Lint チェック (`.github/workflows/lint.yml`)

- **トリガー**: プルリクエスト、手動実行
- **処理内容**: textlint と markdownlint による文書品質チェック
- **実行環境**: Ubuntu Latest, Node.js 18
