---
created: 2025-06-19 01:45
updated: 2025-06-19 01:45
tags:
  - obsidian
---
# 概要
メモツールであるObsidianを導入した。さらに必要なプラグインを導入し環境を整備した

# ディレクトリ構造
[Obsidian MCPサーバーをClaude Desktopで使ってみた \| DevelopersIO](https://dev.classmethod.jp/articles/obsidian-mcp-claude-desktop-integration-hands-on/)を参考にした。
Obsidianに限らずこういったメモツールは階層をあまり深くしすぎないほうが管理しやすい。

# プラグイン
[Obsidian MCPサーバーをClaude Desktopで使ってみた \| DevelopersIO](https://dev.classmethod.jp/articles/obsidian-mcp-claude-desktop-integration-hands-on/)と [ぼくがかんがえた最強のObsidian設定｜古村藍](https://note.com/indigo372/n/nae1e72203c5b) を主に参考にした。
Dailynoteは利用する予定がなかったので導入せず。現状は `Auto Link Title` `Dataview` `Temprater` くらいしか使っていない

[Obsidian Web Clipper × AI でWebページを自動要約＆ストックしてみた \| DevelopersIO](https://dev.classmethod.jp/articles/try-obsidian-web-clipper-ai-summary/)を参考に `Obsidian Web Clipper` を設定し、`gpt-4.1-mini` で要約してからObsidionにクリップする設定を実施した。

# CSS
[Obsidian-CSS-Snippets/Snippets at Collection · r-u-s-h-i-k-e-s-h/Obsidian-CSS-Snippets · GitHub](https://github.com/r-u-s-h-i-k-e-s-h/Obsidian-CSS-Snippets/tree/Collection/Snippets)に有用なCSSが多数紹介されているのでいくつか導入した。



## タグ関連ノート

```dataview
TABLE WITHOUT ID
  "[[" + file.name + "]]" as ノート,
  join(filter(file.tags, (t) => contains(this.file.tags, t)), ", ") as 共通タグ
FROM ""
WHERE file != this.file AND 
      length(filter(file.tags, (t) => contains(this.file.tags, t))) > 0
SORT file.name ASC
```

## リンク関連ノート

```dataview
TABLE WITHOUT ID
  "[[" + file.name + "]]" as 関連ノート,
  "via [[" + outgoing.path + "]]" as 経由
FROM ""
FLATTEN this.file.outlinks as outgoing
WHERE file != this.file AND 
      contains(file.inlinks, outgoing) AND
      !contains(this.file.outlinks, file.link)
SORT file.name ASC
```


