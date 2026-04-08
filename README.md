# docquill

AsciiDocで書くテックブログのHugoテーマ + 構築テンプレート。

## 構成

- **Hugo (extended)** + **Asciidoctor** で AsciiDoc を HTML に変換
- **GitHub Pages** にデプロイ、**PR Preview** 付き
- **Pagefind** によるクライアントサイド全文検索
- GitHub Actions は **コミットSHAピニング**、Dependabot で自動更新

## ローカル開発

```bash
cd exampleSite
hugo server -D
# http://localhost:1313/
```

## ディレクトリ

- `layouts/` — Hugoテンプレート
- `static/css/` — テーマCSS
- `archetypes/` — 記事テンプレート
- `exampleSite/` — テーマ動作確認用サンプルサイト
- `.github/workflows/deploy.yml` — デプロイ & PRプレビュー
- `.claude/skills/` — Claude Code用スキル

## 新規記事

```bash
cd exampleSite
hugo new posts/my-new-post.adoc
```

## 本番ビルド

```bash
cd exampleSite
hugo --minify --destination ../public
npx pagefind@1.3.0 --site ../public
```

## License

MIT
