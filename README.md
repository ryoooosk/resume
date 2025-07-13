# Resume Project

## 📄 職務経歴書はこちら

**🌐 <https://ryoooosk.github.io/resume/>**

このプロジェクトは職務経歴書をMarkdownで管理し、GitHub Pagesで公開、PDFとして出力するためのリポジトリです。

## 機能

- **Markdown形式での職務経歴書管理**: `index.md`で職務経歴書を管理
- **GitHub Pages対応**: Jekyll（minimaテーマ）を使用してWebサイトとして公開
- **PDF出力**: md-to-pdfを使用してPDF形式での出力が可能
- **品質管理**: textlintとmarkdownlintによる文書品質チェック

## ファイル構成

```
resume/
├── README.md              # プロジェクト概要（このファイル）
├── index.md              # 職務経歴書本体
├── _config.yml           # Jekyll設定ファイル
├── package.json          # Node.js依存関係とスクリプト
├── pdf-configs/          # PDF出力設定
│   ├── config.js         # md-to-pdf設定
│   └── style.css         # PDFスタイル
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

### PDF出力

```bash
# 職務経歴書をPDF形式で出力
npm run build:pdf
```

## GitHub Pages設定

このリポジトリはGitHub Pagesを使用してWebサイトとして公開されます。`_config.yml`でJekyllのminimaテーマが設定されており、`index.md`の内容が自動的にWebページとして表示されます。

## 使用ライブラリ

### textlint

日本語文書の校正ツール。以下のルールを適用して文章品質を向上させます：

- **@proofdict/textlint-rule-proofdict**: 辞書による校正
- **@textlint-ja/textlint-rule-no-dropping-i**: 「い」抜き言葉の検出
- **textlint-rule-ja-hiragana-hojodoushi**: 補助動詞のひらがな表記チェック
- **textlint-rule-ja-no-abusage**: 日本語の誤用検出
- **textlint-rule-ja-no-mixed-period**: 句読点の統一
- **textlint-rule-sentence-length**: 文の長さ制限
- その他多数の日本語校正ルール

### markdownlint-cli

Markdownの記法チェックを行い、一貫性のある文書フォーマットを維持します。

### md-to-pdf

MarkdownファイルをPDFに変換するツール。カスタムCSS（`pdf-configs/style.css`）を適用してスタイリングを行います。

### Jekyll (GitHub Pages)

静的サイトジェネレーター。`minima`テーマを使用してシンプルで読みやすいWebページを生成します。

## CI/CD

### Lint チェック (`.github/workflows/lint.yml`)

- **トリガー**: プルリクエスト、手動実行
- **処理内容**: textlint と markdownlint による文書品質チェック
- **実行環境**: Ubuntu Latest, Node.js 18

### PDF リリース (`.github/workflows/release-pdf.yml`)

- **トリガー**: `docs/README.md` が変更されたプルリクエスト、手動実行
- **処理内容**:
  - 職務経歴書のPDF生成
  - GitHub Releases へのドラフトリリース作成
  - PDF ファイルの自動アップロード
- **実行環境**: Ubuntu Latest, Node.js 18
