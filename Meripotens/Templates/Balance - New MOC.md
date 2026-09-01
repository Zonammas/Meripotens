---
type: balance-moc
kind:
disciplines:
definitionStatus: draft
sources: []
created: "{{date}} {{time}}"
---

# {{title}}

## Linked Power Notes

```dataview
TABLE topic AS "Topic", locator AS "Locator"
FROM "02_Power"
WHERE contains(file.outlinks, this.file.link)
SORT file.ctime DESC
LIMIT 10
```

## Sources

```dataview
TABLE category AS "Category", type AS "Type", status AS "Status", rating AS "Rating"
FROM "06_Source"
WHERE (contains(subDisciplines, this.file.link) OR contains(subDisciplines, this.file.name)) AND type != "figure"
SORT status ASC
```
