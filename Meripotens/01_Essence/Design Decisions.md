---
type: essence
purpose: A living record of the design decisions behind the vault — the forks in the road, the alternatives, and why each was chosen
updated: 2026-08-11
---

# Design Decisions

The vault asks that every idea stay traceable to where it came from ([[Manifesto]], principle 6). This document applies that same rule to the vault's own design. It records the *reasoning* behind the structure, so that "why is it built this way" always has an answer to return to.

This is not a changelog. It does not log every edit. It records only genuine decisions — the points where a real alternative existed and one path was chosen for a reason. Each entry states the **decision**, the **alternative considered**, and the **rationale**. That filter is itself the discipline that keeps this document from bloating.

It is a living record. When a new design decision is made — one with a real alternative, not a routine change — it is added here, in the same form, before or as it takes effect. A choice that is never written down is, by this vault's own standard, only an impression of a decision.

## Layers and Pipeline

### Six folders, no deeper hierarchy
**Decision.** The vault uses exactly six folders; all further organization is done through frontmatter properties and links, not nested folders.
**Alternative considered.** A conventional topic-based folder tree.
**Rationale.** Interdisciplinary material rarely belongs to a single category. Links and properties let one idea live in many places at once; a folder tree would force a premature, single home.

### Structure is earned, not assumed
**Decision.** A Balance MOC is created only when a cluster of Power notes has earned it, signalled by a phantom link that stays passive until a Power note reaches `moved-to-balance`.
**Alternative considered.** Auto-promoting notes, or imposing structure at capture time.
**Rationale.** Structure imposed too early kills raw thinking before it develops; earned promotion keeps the map honest and prevents building around ideas that have not proven themselves.

### Development is gated by choice, not by a status threshold
**Decision.** A Development page's *content* is auto-generated, but its *existence* is a deliberate choice — activated when a discipline becomes a focus. It carries no earned status threshold.
**Alternative considered.** Giving Development the same status threshold as Balance, or letting it auto-exist on the first inbound link.
**Rationale.** Content is a pure mirror and should never be curated by hand; existence is a focus decision the user should own. Access is never gated either way — un-activated disciplines remain fully reachable through their own links.

### Revolution is scaffolding-free with a single negative rule
**Decision.** The Revolution template ships with no query and no structural limit. Its only rule is negative: it must do something the other layers have not. User-authored Dataview is allowed inside it.
**Alternative considered.** Forbidding Dataview in Revolution entirely, or giving it a template scaffold.
**Rationale.** The authorship that legitimizes Revolution is *human versus system*, not *individual versus team* and not *prose versus query*. Scaffolding or a system-supplied query would substitute the system's judgment for the person's, which is exactly what this layer exists to prevent.

### Raw notes may stay raw forever
**Decision.** The Power layer is a permanent, legitimate home, not a queue to be emptied. A note may remain `raw` indefinitely.
**Alternative considered.** The fleeting-to-permanent processing model (Ahrens) where raw notes are an inbox to clear.
**Rationale.** Maturity belongs to the *layer*, not to every note. Most thoughts should stay dormant; an unprocessed Power note is not a failure ([[Manifesto]], principle 9).

## Schema and Fields

### Vocabularies enforced by convention, not software
**Decision.** Controlled vocabularies (disciplines, statuses, kinds, categories) are enforced by documentation and Dataview's exact string-matching, not by any software constraint.
**Alternative considered.** A software-enforced enum or select type.
**Rationale.** Obsidian offers no enum type. A value outside the documented lists silently drops from the queries that depend on it, so the lists must be treated as real — the automation only works if the words match.

### `page` generalized to `locator`
**Decision.** The Power note's anchor field is `locator` (a page, a timestamp, or a section), not `page`.
**Alternative considered.** Adding a separate `timestamp` field alongside `page`.
**Rationale.** A note usually anchors to one source of one medium, so a single adaptive field beats two fields where one is always empty. `locator` is also the standards-aligned bibliographic term (CSL) covering page, section, and time alike.

### Provenance without a citation manager
**Decision.** Traceability is native: `sourceRef` + `locator` on the Power note, resolved to a `citationKey` and bibliographic fields on the Source note.
**Alternative considered.** Integration with an external citation manager (e.g. Zotero).
**Rationale.** The vault should be self-contained; a citation can be assembled on demand by following `sourceRef`, without a dependency the whole system would then rest on.

## Source and Figures

### Figures share the Source folder but are filtered out by type
**Decision.** Figure notes live in `06_Source` and share the `disciplines` / `subDisciplines` / `status` fields, but every source-oriented query excludes them with `type != "figure"`.
**Alternative considered.** A separate folder for Figures.
**Rationale.** A figure is a subject, not consumed material, yet belongs adjacent to the sources about them. Filtering by identity (`type`) rather than by location keeps them close without letting them leak into lists of consumed material.

### `author` and Figure notes are distinct, not substitutes
**Decision.** `author` records who wrote one work (free, automatic on every Source). A Figure note is a subject of research, created only when earned.
**Alternative considered.** Auto-creating a Figure note for every name in an `author` field.
**Rationale.** Most authors never become subjects of study. A Figure is earned, like a Balance MOC; reflexive creation would fill the vault with subjects no one is actually researching.

### The Readable / Audible / Viewable set is kept
**Decision.** Source categories stay Readable / Audible / Viewable.
**Alternative considered.** A noun set such as Text / Audio / Video.
**Rationale.** The three are a consistent set of "-able" capability adjectives (read / hear / view). Changing them would ripple through the four Source category MOC names and every category query for no real gain.

## Collaboration

### Team use is an optional addendum, not part of the core
**Decision.** Multi-author support (`owner`, `contributors`, a member roster) lives in an opt-in addendum; the core vault stays single-author by default.
**Alternative considered.** Baking collaboration fields and rules into the core schema.
**Rationale.** The authorship rule is human-versus-system, so teams are fully legitimate — but most users are solo. Keeping the core lean and collaboration opt-in serves both without imposing team ceremony on the individual.

### Synchronization is out of scope
**Decision.** How files are shared across machines (Git, a sync service) is left entirely to the user.
**Alternative considered.** Prescribing a sync or version-control method.
**Rationale.** The vault is sync-agnostic and only assumes files eventually reconcile. This is the same stance the README takes toward plugins — extension is the user's own call.

## Philosophy

### Permission, not prohibition
**Decision.** Every gate works by letting things stay passive, never by forbidding an action ([[Manifesto]], principle 11).
**Alternative considered.** Rule-enforcing gates that block actions until conditions are met.
**Rationale.** Because nothing stops the user from activating anything, what they do activate is authentically theirs, and what they leave passive is a true measure of focus. A system that prohibits records its own rules; a system that permits records the person. This is the root the other principles grow from.

### Goal-directed Revolution is documented alongside the emergent mode
**Decision.** Revolution may be opened at the very outset as a declared target, not only at the end as an emergent synthesis — with the caveat that an early Revolution MOC is a target, not a shortcut.
**Alternative considered.** Documenting only the emergent, end-of-pipeline path.
**Rationale.** Goal-driven users (thesis, article, blog) are among the strongest fit, and declaring a goal is itself an act of authorship. The caveat keeps the mode honest: the work still passes through the real layers, and the declared goal is best treated as a hypothesis the sources may overturn.

## Related Documents

[[Manifesto]] states the principles these decisions serve. [[System Rules]] and [[Property Schema Reference]] hold the mechanics they produced. [[Vault Overview]] gives the structure they shaped.
