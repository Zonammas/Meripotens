---
type: essence
purpose: Introduce the vault, its philosophy, and its overall structure
updated: 2026-08-11
---

# Vault Overview

Meripotens is a personal knowledge vault for interdisciplinary study across fields such as Art History, Philosophy, Politics, Literature, Military History, and many other humanities subjects.

## Name

This system is called Meripotens, from the Latin *meritum* (earned) and *potentia* (potential). The name binds its two central principles: structure is earned, not assumed, and the raw potential of unprocessed material is respected — left dormant and unforced — until it earns its place. A link stays unresolved until the material behind it has proven it deserves one, and the whole structure exists to protect that potential rather than to hurry it.

## Purpose

The vault is built to move raw, unstructured thinking through a deliberate process until it becomes either a structured map of a discipline or a fully original synthesis. Notes are never expected to be finished on arrival. Structure is earned through processing, not assumed at creation.

This is not built for one kind of user or one kind of goal. "Discipline" and "concept" are the words used throughout this documentation because the vault began as a research tool, but nothing about the mechanism requires formal research. The same five layers work equally well for a student organizing material for an exam, a researcher building toward a thesis, or someone with no institutional goal at all who is simply following their own curiosity and wants their scattered reading to eventually become something. What the vault offers everyone, regardless of purpose, is the same thing: a way to turn accumulated material into whatever the user is actually trying to make of it. Naming conventions and discipline labels exist to keep that material findable, not to decide what it is allowed to become.

## Structure

The vault has six folders. Five form a processing pipeline; the sixth is a supporting reference layer.

1. **Essence** — The root of the system. Contains no content notes, only the rules, schemas, and controlled vocabularies that govern how the vault operates.
2. **Power** — The entry point for all new notes. Unstructured, uncontrolled, but full of raw potential. Nothing is expected to be well-formed here.
3. **Balance** — A MOC layer, not flat notes. Each Balance MOC is created manually by the user to group a set of Power notes under one concept, theory, or school of thought, set through its `kind` field. The Power notes are connected to it through ordinary wikilinks, which a Dataview query then lists automatically.
4. **Development** — Discipline-based MOCs, one per discipline, that automatically list every Balance MOC and Source note linked to that discipline. Nothing is added to these pages by hand.
5. **Revolution** — Fully original MOCs, built by hand rather than derived from existing links. This is where discovery happens that the system itself cannot produce, only make possible.
6. **Source** — A reference layer, not part of the pipeline. Holds every book, article, video, podcast, course, or other material that feeds notes elsewhere in the vault. Each source belongs to one of three categories — Readable, Audible, Viewable — and links to both a broad discipline (Development) and, where relevant, a specific concept (Balance). Source also holds Figures: people studied as subjects in their own right, not consumed material, linked back from the Source notes written by or about them. Four fixed MOCs, one per category (Readable, Audible, Viewable, Figures), give a target-independent view of what has been consumed, researched, in progress, or queued.

## Organizing Principle

Beyond these six folders, no further folder hierarchy is used. Organization within and across folders is achieved entirely through frontmatter properties and links between notes. This keeps the vault flexible for interdisciplinary material that does not belong to a single category.

## Related Documents

[[System Rules]] defines the exact workflow and controlled vocabularies. [[Property Schema Reference]] lists every field and its type. [[Vision and Usage Guide]] explains the day-to-day workflow. [[Dashboard]] gives a live view of the vault's open work. [[Manifesto]] states the principles behind all of it.

New here? [[Start Here]] lays out the full reading path in order. Beyond the core: [[Team Collaboration]] is an optional addendum for shared, multi-author use; [[Why It Exists]] makes the case for the whole system; [[The Layers as a Cosmos]] offers a philosophical reading of the layers; and [[Design Decisions]] records the reasoning behind the architecture.
