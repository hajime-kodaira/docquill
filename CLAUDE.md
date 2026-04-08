# docquill

AsciiDocで書くテックブログの静的サイトジェネレーター構成。

## Tech Stack
- SSG: Hugo (extended)
- Markup: AsciiDoc (.adoc) + Asciidoctor
- Hosting: GitHub Pages
- CI/CD: GitHub Actions (SHAピニング必須)
- Search: Pagefind

## Commands
- `cd exampleSite && hugo server -D` — テーマのローカルプレビュー
- `hugo --minify` — 本番ビルド
- `npx pagefind@1.3.0 --site public` — 検索インデックス生成

## Directory Structure
- `layouts/` — Hugoテンプレート (Go template)
- `static/css/` — テーマCSS
- `archetypes/` — 記事テンプレート
- `exampleSite/` — 単体動作確認用サンプルサイト
- `exampleSite/content/posts/` — サンプル記事 (.adoc)
- `.claude/skills/` — Claude Code用スキル

## Code Conventions
- テンプレートはGoテンプレート構文
- CSSはカスタムプロパティ (CSS Variables) でテーマ管理
- ダークモードは `prefers-color-scheme` で対応
- AsciiDocが生成するHTML要素のクラス名に合わせたCSS設計

## Important Rules
- GitHub Actionsは必ずコミットSHAでピニング（タグ禁止）
- Hugo, Asciidoctor, Pagefindはバージョン固定
- テーマのCSS設計時は `.claude/skills/hugo-theme-design/` のスキルを参照
- AsciiDocのHTML出力スタイリング時は `.claude/skills/asciidoc-styling/` を参照
