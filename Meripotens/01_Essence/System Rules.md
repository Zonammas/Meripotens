---
type: essence
purpose: Define layer rules, workflow, and controlled vocabularies for the vault
updated: 2026-08-11
---

# System Rules

## Layer Definitions and Workflow

**Power → Balance**
Every note begins in Power, uncontrolled and unstructured. A Balance MOC is created only when the user manually decides that a cluster of Power notes belongs together under one concept, theory, or school of thought, and sets that in the MOC's `kind` field. This step is never automatic and has no system-generated trigger. The user creates the Balance MOC, links the relevant Power notes into it with ordinary wikilinks, and the vault's Dataview query then lists those links under "Linked Power Notes." Balance notes are themselves MOCs, not flat content notes — they aggregate the Power notes that link to them, they do not summarize or restate them.

**Phantom Links and Activation**
A Power note may link to a Balance MOC that does not exist yet, by writing its prospective name (for example, `[[Balance_Stoicism_MOC]]`) before that note has been created. Obsidian renders this as an unresolved link, and it stays that way — passive — as long as every Power note pointing to it is still `raw` or `in-progress`. A Balance MOC should only actually be created, turning the phantom link into a real one, once at least one Power note pointing to it reaches `status: moved-to-balance`. Creating the MOC earlier than that builds structure around an idea that has not yet proven it deserves one, which is exactly what this rule prevents.

**Balance → Development**
Balance MOCs link outward to one or more discipline pages in Development through their `disciplines` field. A Balance MOC may belong to more than one discipline at once; this is expected for interdisciplinary ideas. When that field names a Development page that does not exist yet, it renders as a phantom link, the same as an unresolved Balance link inside a Power note — so the same activation pattern applies at this layer too, with one difference described below.

**Power + Balance → Development**
Development MOCs are built primarily from the links that accumulate between Power and Balance MOCs over time. They represent what the system's linking structure reveals about a discipline.

Creating a Development page is a deliberate act, not an automatic one: the user activates the page for a discipline when that discipline actually becomes a focus of their study, resolving the phantom links pointing to it.

What separates Development activation from Balance activation is that **Development carries no status threshold** — there is no requirement for associated Power or Balance notes to reach a specific status (such as `moved-to-balance` or `mature`). The page may be created the moment a discipline becomes an active target of study. Once created, its live Dataview queries fill it automatically from whatever Balance MOCs and Sources already link to it in their `disciplines` field. Until created, all underlying notes remain fully accessible through their own links.

**Revolution**
Revolution MOCs are built by hand, independent of what the link structure already shows. They represent original synthesis, not the output of a mechanical process. Because Revolution has no activation threshold, a Revolution MOC may be created at any point — including at the very outset, as a declared target, when the goal (a thesis, article, or blog post) is known in advance. Opening it early is a goal-directed use of the layer, not a violation of the earned principle; it remains a target that the pipeline feeds, never a substitute for it.

Revolution is the one layer with no structural limit. The user may build whatever folder and MOC arrangement the work calls for: sub-folders for separate theses or articles, guiding MOCs that index other Revolution MOCs, any nesting or cross-linking the project needs. Nothing in the layer constrains its shape, because its shape is part of the work being authored, not a schema imposed on it.

The layer has exactly one rule, and it is a negative one: a Revolution MOC must do something the other layers have not already done. Re-running a query Development or Balance already runs, restating what a Balance MOC already aggregates, or re-collecting links the pipeline already surfaces is not Revolution — it is duplication wearing the name. What qualifies a note as Revolution is that the connection, the framing, or the synthesis originated with the person and could not have been produced by the automatic pipeline on its own. This single constraint is what keeps a boundless layer from decaying into a lazy mirror of the layers beneath it.

**Revolution and Dataview**
The Revolution template ships with no query, and none should be added to the template — that is what keeps this layer free of system-provided scaffolding. This does not mean Dataview is forbidden inside a Revolution note. A user may write their own query there, combining disciplines, sub-disciplines, or sources in a way no other layer in the vault can — Development and Balance are each scoped to a single discipline or concept, so a cross-cutting view built for one specific piece of work is only possible here. What makes this legitimate rather than a violation is authorship: the system never supplies this query or suggests it; the user decides what to combine, and the query only executes a combination the user already conceived. The same is true whether the query stays as working scaffolding or gets replaced by prose — either way, the origin of the connection was the person, not the system.

**Source**
Source notes exist outside the pipeline. Any note in Power, Balance, Development, or Revolution may link to a Source note to preserve provenance.

Every Source note links back in two tiers via frontmatter: `disciplines` points to broad Development pages, and `subDisciplines` points to specific Balance MOCs. **This linking is set only on the Source note itself.** The corresponding Balance MOCs and Development pages do not manually link back; instead, their embedded Dataview queries dynamically pull and display every Source that references them, providing seamless two-way traceability without manual maintenance.

**Source Category MOCs**
`Source_Readable_MOC`, `Source_Audible_MOC`, `Source_Viewable_MOC`, and `Source_Figures_MOC` sit in 06_Source and query their category's notes by status, independent of discipline. They exist to audit consumption and research by medium rather than by topic, and to serve as a record for choosing future direction from what has already been read, listened to, watched, or studied.

**Figures**
Not every subject of research is consumed material — people are studied, not read or watched. Figure notes live in 06_Source alongside Source notes but are their own entity: `type: figure`, no `category`, no `citationKey`. A Source note may point to the Figure(s) it is written by or about through `relatedFigures`; the Figure note's own Dataview query then lists every Source pointing to it, the same mirrored-linking pattern used everywhere else in the vault.

The `author` field (on Source notes) and a Figure note answer different questions and are not substitutes for each other: `author` records who wrote one specific work, free and automatic on every Source note. A Figure note is earned, not automatic, following the same principle as Balance MOCs — it is created only when the person themselves becomes an unavoidable subject of the research, not by reflex for every name that appears in an `author` field. Most authors never get a Figure note, and that is correct, not incomplete.

## Controlled Vocabularies

Obsidian property types do not include an enum or select type, so every field that should carry a fixed value must be entered manually as Text or List. The lists below are the only valid values for those fields. New values may be added here first, then used in notes — never the reverse.

Nothing technically stops a note from using a value outside these lists — Obsidian will accept it without complaint. The lists exist because every Dataview query in this vault filters on exact string matches against them (`WHERE status = "planned"`, `WHERE contains(disciplines, ...)`, and so on); a value that isn't documented here will simply fail to match those queries and quietly disappear from the automatic views that depend on it. Using this vault well means treating the lists as real, not because the software enforces them, but because the automation only works if the words match.

None of this is a mold to fit your work into: the vocabulary exists so the vault can find its way back to what you made, not to decide what that work may be or who may make it (see [[Manifesto]], principle 10). In practice this means you extend it. Add to the Disciplines list, or use a `kind` the list does not yet cover, and the vault adapts — the only rule is documenting the new value here first, so the automation keeps matching it.

### Disciplines (used in Development, Balance, Source)

Philosophy, Psychology, History, Religion, Science, Art, Literature, Linguistic, Technology, Finance, Politics, State, Military, Sociology, Law, News, Etc... The limit is up to the user's preference.

### Source Categories

Readable, Audible, Viewable

### Source Types

- Readable: Book, Article, Academic Article, Web Page
- Audible: Podcast, Audiobook
- Viewable: Video, Documentary, Course

### Balance Kind (used only in Balance)

concept, theory, school-of-thought, subDicipline

### Status Values

- Power: raw, in-progress, moved-to-balance
- Balance: draft, mature
- Revolution: developing, submitted, revising, published, complete (`submitted` / `revising` / `published` exist for work headed toward peer review or publication; `complete` remains for work finished with no publishing intent)
- Source: planned, in-progress, complete
- Figure: planned, researching, complete

## Naming Conventions

- Source notes are named with `unique note` feature. The metadata section will contain the necessary information, so including information labeled “note” in the naming convention is a waste of time.
- Balance and Development notes, since they are both MOCs, are named `Balance_<Topic>_MOC` and `Development_<Discipline>_MOC` (for example, `Balance_Stoicism_MOC`,`Development_Philosophy_MOC`).
- For “Power” notes, the `unique note` feature can be used to enter them into the system without wasting time on custom naming.
- The four Source category MOCs are named `Source_Readable_MOC`, `Source_Audible_MOC`, `Source_Viewable_MOC`, and `Source_Figures_MOC` — fixed names, not created per-topic.
- Figure notes are named directly after the person's name and include the date like (YYYYMMDDHHMM)`unique note` attribute (for example, `Ferdinand de Saussure - 202611221034`).
- Every Source note's `citationKey` follows `LastnameYear` (for example, `Weber1978`). If there is no individual author, use the organization or channel name in place of the surname. If more than one sources share the same key, disambiguate with a lowercase letter suffix (`Weber1978a`, `Weber1978b`). 

## Quote and Citation Traceability

A Power note that is anchored to a specific passage, rather than a general reaction, should set `sourceRef` to link back to the originating Source note and `locator` to the exact position it anchors to — a page or page range for print, a timestamp for audio or video, a section for a web page. The quoted text itself belongs in the body of the Power note, not in frontmatter. This keeps every idea traceable back to a citable location without requiring a citation manager: to write a footnote later, follow `sourceRef` to the Source note and read off its `citationKey` and bibliographic fields.

## Duration Fields

All duration fields (for podcasts, audiobooks, videos, documentaries) are recorded in minutes as a Number, so they remain sortable.

## Related Documents

[[Vault Overview]] gives the top-level structure. [[Property Schema Reference]] lists every field and its type. [[Vision and Usage Guide]] explains the day-to-day workflow. [[Dashboard]] gives a live view of the vault's open work. [[Manifesto]] states the principles behind all of it.
