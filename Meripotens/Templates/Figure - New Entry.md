---
type: figure
professions: []
birthDate: 
deathDate: 
birthplace: 
travels: []
languages: []
workCount: 
disciplines: []
subDisciplines: []
status: planned
---

# {{title}}

## Related Sources

```dataview
TABLE category AS "Category", type AS "Type", status AS "Status"
FROM "06_Source"
WHERE contains(relatedFigures, this.file.link)
SORT status ASC
```
