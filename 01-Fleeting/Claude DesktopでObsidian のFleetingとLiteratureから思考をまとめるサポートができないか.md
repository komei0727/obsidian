---
created: 2025-06-19 02:00
updated: 2025-06-19 02:00
tags:
  - obsidian
  - claude-desktop
---
[[Obsidian MCPサーバーをClaude Desktopで使ってみた  DevelopersIO]] が使えそう
なぐり書きのアイデアと適当に取ってきた外部ソースを集約するのにClaude DesktopのAI機能を使えないかというアイデア
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


