---
type: discipline-moc
discipline: 
scope: 
created: "{{date}} {{time}}"
---
# {{title}}

## Related Notes

### Balance Concepts

```dataview
TABLE definitionStatus AS "Status", updated AS "Updated"
FROM "03_Balance"
WHERE contains(disciplines, this.file.link)
SORT updated DESC
```

### Sources

```dataview
TABLE category AS "Category", type AS "Type", status AS "Status", rating AS "Rating"
FROM "06_Source"
WHERE contains(disciplines, this.file.link) AND type != "figure"
SORT status ASC
```
