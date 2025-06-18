---
created: <% tp.file.creation_date() %>
updated: <% tp.file.creation_date() %>
tags: []
---

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


