# misoclub web

misoclub の公式サイト。素の HTML / CSS で作られた静的サイトで、GitHub Pages で公開します。

## 構成

```
.
├── index.html              # ランディングページ
├── apps.html               # アプリ一覧（リリース済みアプリ専用ページ）
├── contact.html            # お問い合わせ（mailto 中心）
├── dl/                     # アプリDL専用ページ（シェアからの遷移先）
│   ├── nihon-tabinikki.html
│   └── memoria.html
├── privacy/
│   └── sample-app.html     # 各アプリ用テンプレート（複製して使う）
├── css/
│   └── style.css           # 共通スタイル（色は :root の変数で調整）
├── assets/
│   ├── logo.png            # ロゴ（logo-source.png から切り抜き済み）
│   ├── logo-source.png     # ロゴ原本（再クロップ用）
│   └── google-play-badge.png
└── .nojekyll               # GitHub Pages の Jekyll 処理を無効化
```

## アプリのダウンロードページ（`dl/`）

アプリのシェア機能などから飛ばす遷移先。iOS / Android を選んでダウンロードしてもらうための最小ページで、misoclub の他アプリ一覧（`apps.html`）以外のリンクは置いていません。

新しいアプリを追加するときは `dl/` のファイルを複製し、アプリ名と各ストアの URL（`href="#"` の箇所）を差し替えてください。

## ローカルで確認する

ビルド不要。ファイルをブラウザで開くだけでも見られますが、相対リンクを正しく確認するには簡易サーバーが便利です。

```sh
python3 -m http.server 8000
# → http://localhost:8000 を開く
```

## 新しいアプリのプライバシーポリシーを追加する

1. `privacy/sample-app.html` を `privacy/<アプリ名>.html` という名前で複製
2. アプリ名・更新日・各項目を編集
3. アプリ側からそのページの URL を直接リンク

## GitHub Pages で公開する

リポジトリの Settings → Pages で、Source を `main` ブランチのルート (`/`) に設定すると公開されます。

## TODO

- [x] お問い合わせ先メールアドレス（`misoclubsupport@gmail.com`）を設定
- [ ] 各DLページのストアURL（App Store / Google Play）を差し替え（現在は `href="#"`）
- [ ] App Store の公式バッジ画像を用意（現在は自作バッジ。Apple のガイドライン準拠の公式バッジ推奨）
- [ ] ランディングページのキャッチコピー・「私たちについて」を実際の内容に
- [ ] OGP 画像・favicon の追加
- [ ] （必要なら）お問い合わせフォームの実送信対応
