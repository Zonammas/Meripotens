---
type: essence
purpose: Live overview of the vault's working queue across all layers
updated: 2026-08-11
---
# Dashboard

See [[Vault Overview]], [[System Rules]], [[Property Schema Reference]], and [[Vision and Usage Guide]] for the rules behind these queries, and [[Manifesto]] for the principles behind the rules.

## Unprocessed (Power)

```dataview
LIST
FROM "02_Power"
WHERE status = "raw"
SORT file.ctime DESC
LIMIT 5
```

## In Progress (Power)

```dataview
LIST
FROM "02_Power"
WHERE status = "in-progress"
SORT file.ctime DESC
LIMIT 5
```

## Activated (Power)

```dataview
LIST
FROM "02_Power"
WHERE status = "moved-to-balance"
SORT file.ctime DESC
```

## Draft Balance MOCs

```dataview
LIST
FROM "03_Balance"
WHERE definitionStatus = "draft"
SORT file.mtime DESC
```

## Reading / Watching / Etc. Queue (Source)

```dataview
TABLE category AS "Category", type AS "Type", status AS "Status"
FROM "06_Source"
WHERE (status = "planned" OR status = "in-progress") AND type != "figure"
SORT status ASC
```

By medium: [[Source_Readable_MOC]] · [[Source_Audible_MOC]] · [[Source_Viewable_MOC]] · [[Source_Figures_MOC]]

## Active Revolution MOCs

```dataview
LIST
FROM "05_Revolution"
WHERE status = "developing"
SORT created DESC
```
