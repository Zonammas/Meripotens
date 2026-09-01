---
type: essence
purpose: Reference for the frontmatter property schema used in every layer
updated: 2026-08-11
---
# Property Schema Reference

Property types are limited to what Obsidian natively supports: Text, List, Number, Checkbox, Date, Date & Time. Fields with fixed values use Text or List and draw only from the vocabularies in System Rules.

## Essence

| Field   | Type        | Description                       |
| ------- | ----------- | --------------------------------- |
| type    | Text        | fixed: essence                    |
| purpose | Text        | the note's function in the system |
| updated | Date & Time | last change                       |

## Power

| Field     | Type | Description                                                                                                                                                                                                                              |
| --------- | ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type      | Text | fixed: power                                                                                                                                                                                                                             |
| created   | Date |                                                                                                                                                                                                                                          |
| topic     | List | loose, unsettled tags                                                                                                                                                                                                                    |
| status    | Text | raw / in-progress / moved-to-balance                                                                                                                                                                                                     |
| sourceRef | List | optional, link(s) to the Source note(s) this idea or quote came from                                                                                                                                                                     |
| locator   | Text | optional, the exact position the note anchors to, whatever the medium: page or page range for print (e.g. "45", "45-46"), episode name or timestamp for audio/video (e.g. "12:45", "12:45-13:30"), or section for a web page (e.g. "§2") |

When a Power note is built around a direct quote, the quote itself goes in the note body, not in frontmatter — frontmatter only carries the pointer back to the source and the locator. The citation itself is assembled later from `sourceRef` → the Source note's `citationKey` and bibliographic fields.

A Power note carries no identity, only signposts: its frontmatter holds only backward pointers (`sourceRef`, `locator`) and transient state (`status`, loose `topic`), so any forward link to a Balance MOC belongs in the note body — under `# Discovered Signs` in the template — as a gesture, never in frontmatter as a claim about what the note is.

## Balance

Balance notes are MOCs, not flat content notes. Each one aggregates the Power notes that link into it.

| Field            | Type        | Description                                         |
| ---------------- | ----------- | --------------------------------------------------- |
| type             | Text        | fixed: balance-moc                                  |
| kind             | Text        | concept / theory / school-of-thought / subDicipline |
| disciplines      | List        | reference to one or more Development disciplines    |
| definitionStatus | Text        | draft / mature                                      |
| created          | Date & Time |                                                     |

Includes two Dataview blocks (see template): one listing Power notes that link to it, one listing Source notes whose `subDisciplines` point to it.

## Development

| Field      | Type        | Description                              |
| ---------- | ----------- | ---------------------------------------- |
| type       | Text        | fixed: discipline-moc                    |
| discipline | Text        | single value from the discipline list    |
| scope      | Text        | short description of what the MOC covers |
| created    | Date & Time |                                          |

## Revolution

| Field              | Type | Description                                                                     |
| ------------------ | ---- | ------------------------------------------------------------------------------- |
| type               | Text | fixed: revolution-moc                                                           |
| created            | Date |                                                                                 |
| relatedDisciplines | List | optional                                                                        |
| status             | Text | developing / submitted / revising / published / complete — see [[System Rules]] |

## Source — Core Fields (all types)

| Field          | Type   | Description                                                                                                               |
| -------------- | ------ | ------------------------------------------------------------------------------------------------------------------------- |
| category       | Text   | Readable / Audible / Viewable                                                                                             |
| type           | Text   | Book, Article, Academic Article, Web Page, Podcast, Audiobook, Video, Documentary, Course                                 |
| disciplines    | List   | link(s) to one or more Development pages — the broad discipline(s) this source belongs to                                 |
| subDisciplines | List   | optional, link(s) to one or more Balance MOCs — the specific concept(s), theory, or school of thought this source informs |
| status         | Text   | planned / in-progress / complete                                                                                          |
| link           | Text   | URL, ISBN, or DOI                                                                                                         |
| rating         | Number | 1-5                                                                                                                       |
| citationKey    | Text   | canonical citation key for this source, format defined in [[System Rules]]                                                |
| relatedFigures | List   | optional, link(s) to Figure notes this source is written by or about                                                      |

`disciplines` and `subDisciplines` give Source two levels of linking: broad (Development) and specific (Balance). A Balance MOC's Sources block (see template) queries `subDisciplines` to show every Source pointing to it, so the link works in both directions without manual upkeep. `relatedFigures` works the same way with Figure notes: set it on the Source, and the Figure note's own query picks it up automatically.

## Figure

Figure notes are not Source entries — a person is not consumed the way a book or a video is. They live in 06_Source as a separate entity because most research (especially in History and Linguistics) is about people as much as it is about material.

| Field | Type | Description |
|---|---|---|
| type | Text | fixed: figure |
| professions | List | e.g. linguist, historian, ruler |
| birthDate | Text | not Date — historical dates are often approximate (e.g. "c. 470 BCE") |
| deathDate | Text | same reasoning; blank if living or unknown |
| birthplace | Text | |
| travels | List | cities or countries the figure lived in or traveled to |
| languages | List | languages the figure worked or wrote in |
| workCount | Number | known number of works |
| disciplines | List | link(s) to one or more Development pages |
| subDisciplines | List | optional, link(s) to Balance MOCs (a school of thought the figure founded or belonged to) |
| status | Text | planned / researching / complete |

Figure notes do not have a `citationKey` — a Figure is a subject, not a citable source. The note body is otherwise unrestricted: add whatever else is relevant about the person. Includes a Dataview block (see template) listing every Source note whose `relatedFigures` points to it.

## Source Category MOCs

| Field    | Type        | Description                             |
| -------- | ----------- | --------------------------------------- |
| type     | Text        | fixed: source-category-moc              |
| category | Text        | Readable / Audible / Viewable / Figures |
| created  | Date & Time |                                         |

Four fixed notes — `Source_Readable_MOC`, `Source_Audible_MOC`, `Source_Viewable_MOC`, `Source_Figures_MOC` — live in 06_Source alongside the Source and Figure notes themselves. Each queries its category's notes grouped by status, independent of discipline or project. This gives a target-independent audit view and, over time, a record for spotting future directions from what has already been consumed, rated, or researched.

Note the `Figures` value here labels the category-MOC only; it is not a Source note `category`. Source notes remain Readable / Audible / Viewable, while Figure notes carry no `category` at all (a Figure is a subject, not consumed material). Because Figure notes share the 06_Source folder and the `disciplines` / `subDisciplines` / `status` fields with Source notes, every source-oriented Dataview query in the vault (Development and Balance `Sources` blocks, the Dashboard reading queue) filters with `AND type != "figure"` so Figures never leak into a list of consumed material.

## Source — Type-Specific Fields

| Type                       | Additional Fields and Types                                                       |
| -------------------------- | --------------------------------------------------------------------------------- |
| Book                       | author (List), publisher (Text), isbn (Text), pageCount (Number)                  |
| Article / Academic Article | author (List), journal (Text), doi (Text), pageRange (Text)                       |
| Web Page                   | author (List, optional), siteName (Text), accessed (Date)                         |
| Podcast                    | host (List), guest (List, optional), episodeNumber (Number), durationMin (Number) |
| Audiobook                  | author (List), narrator (Text), durationMin (Number)                              |
| Video / Documentary        | directorOrChannel (Text), durationMin (Number), platform (Text)                   |
| Course                     | instructor (Text), institution (Text), platform (Text)                            |
_Note on Templates:_ `Article` and `Academic Article` share the exact same frontmatter structure. To minimize friction, a single `Article` template may be used in the `Templates` folder. The `type` property can simply be set to `Academic Article` inside the note whenever formal research papers are logged, keeping both data types clean for Dataview queries without duplicating template files.
## Related Documents

[[Vault Overview]] gives the top-level structure. [[System Rules]] defines naming conventions and controlled vocabularies (including the `Balance_<Topic>_MOC` / `Development_<Discipline>_MOC` naming pattern, deliberately kept out of this document to separate "what a field is" from "how a note is named"). [[Vision and Usage Guide]] explains the day-to-day workflow. [[Dashboard]] gives a live view of the vault's open work. [[Manifesto]] states the principles behind all of it.
