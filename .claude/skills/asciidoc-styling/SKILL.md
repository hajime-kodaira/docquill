---
name: asciidoc-styling
description: AsciiDocが出力するHTMLのCSS対応。admonition, テーブル, ソースブロック等のスタイリング時に使用。
---

# AsciiDoc HTML出力のスタイリング

Asciidoctorが生成するHTMLはMarkdownとは異なるクラス名・構造を持つ。
テーマのCSSはこれらに対応する必要がある。

## Admonition
- ラッパー: `.admonitionblock` + タイプクラス (`note`, `tip`, `important`, `warning`, `caution`)
- 内部は `<table>` で `.icon` と `.content` が分かれる
- 各タイプを色・ボーダーで視覚的に区別する

## テーブル
- `.tableblock` クラス
- `frame-*`, `grid-*`, `stretch` のバリアント
- レスポンシブ対応として横スクロール wrapper を検討

## ソースコード
- `.listingblock > .content > pre.rouge.highlight > code[data-lang]`
- Rouge の monokai スタイル前提で配色

## その他
- `.quoteblock`, `.sidebarblock`, `.exampleblock`, `.literalblock`
- `.imageblock` — 画像 + キャプション
- `.conum`, `.colist` — コールアウト
- 目次は Hugo 側の `{{ .TableOfContents }}` を推奨

## 設計原則
- AsciiDocの出力HTMLは変更できないため、CSSで対応する
- `!important` の多用は避け、詳細度で対応する
