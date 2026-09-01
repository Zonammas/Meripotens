# Meripotens

Meripotens is an Obsidian vault system for interdisciplinary humanities research — though "research" is broader than it sounds here; see below. It moves raw, unstructured notes through a deliberate, staged process until they become either a live map of a discipline or a fully original piece of writing — without forcing structure onto material before it has earned it.

The name comes from Latin: *meritum* (earned) and *potentia* (latent potential). It names the system's two governing principles — structure is earned rather than assumed, and raw potential is respected, protected and unforced, until it earns its place. A link here stays dormant and unresolved until the material behind it has earned that place; nothing is promoted because it might matter, only because it already has.

This is a draft, shared as-is. It reflects one person's working system, not a finished product.

## Structure

The vault has six folders. Five form a processing pipeline; the sixth is a reference layer.

- `01_Essence` — the vault's own constitution. No content notes live here, only the rules, schema, and reasoning that govern everything else. Start reading here.
- `02_Power` — the entry point for every new note. Unstructured on purpose.
- `03_Balance` — MOCs, not flat notes, created by hand once a cluster of Power notes clearly represents one concept, theory, or school of thought.
- `04_Development` — one MOC per discipline, generated automatically from Dataview queries. Never edited by hand.
- `05_Revolution` — fully original work, built by hand, outside the automatic pipeline. The template ships with no query and none is ever added to it, but that doesn't mean Dataview is off-limits here: a user may write their own query, combining disciplines, sub-disciplines, or sources in a way no other layer can. What keeps this from becoming another automated layer is authorship — the system never supplies or suggests that query.
- `06_Source` — the bibliography. Every book, article, video, podcast, or course that feeds a note elsewhere in the vault, with citation tracking down to the page level. Also holds Figures — people studied as subjects in their own right, not consumed material — useful for History, Linguistics, and any field where who said something matters as much as what was said. A Figure note is earned, like a Balance MOC, not created automatically for every name in an `author` field — most authors never need one.

### Extending Templates & Source Types
The vault ships with baseline templates for common formats (books, articles, courses, videos, etc.). If you want to track source types that don't have a dedicated template — such as whole journal issues, patents, archival documents, or datasets — you don't need to alter the underlying core rules:

1. **Use or Adapt the Article / Source Template:** Copy an existing template (like `Article` or standard `Source`) and save it with your desired name in the `Templates/` folder.
2. **Preserve Core Frontmatter:** Keep the mandatory `category`, `type`, `status`, `disciplines`, and `citationKey` fields intact so Dataview queries can index them properly.
3. **Add Domain Fields:** Feel free to introduce custom properties (e.g., `volume`, `issue`, `issn` for journals) as needed. As long as your properties adhere to standard YAML key-value syntax, the vault will seamlessly ingest them.

Open `01_Essence/Start Here.md` first: it lays out the reading path through the documentation, ordered so the system is learned as a single flow. In short, that path runs `Vault Overview.md` → `Vision and Usage Guide.md` → `System Rules.md` → `Property Schema Reference.md` → `Dashboard.md` → `Manifesto.md`.

Several further documents in `01_Essence` sit outside that core path. `Why It Exists.md` makes the case for the whole system, and `The Layers as a Cosmos.md` offers a philosophical reading of the layers — both optional, neither needed to use the vault. `Design Decisions.md` records the reasoning behind the architecture, for anyone asking why it is built this way. `Team Collaboration.md` is an opt-in addendum for shared, multi-author use; a solo user can ignore it entirely.

## Requirements

- Obsidian, with the core Templates plugin enabled and its folder set to `Templates` (Settings → Templates → Template folder location).
- The Dataview community plugin, installed and enabled. Every automatic list in this vault (Development pages, Balance MOCs, the Source category MOCs, the Dashboard) depends on it.

These two are the only requirements — not a ceiling. This vault is not limited to the plugins listed here. If you want to extend it further (Templater for dynamic templates, a citation manager integration, graph or canvas tools, anything else Obsidian supports), that is entirely your own call to make. Nothing about the system depends on staying within this list; it only depends on Dataview and Templates working as described above.

## Getting Started

1. Open the vault in Obsidian and confirm Dataview and Templates are set up as above.
2. Create new notes with Command Palette → "Insert template" rather than typing frontmatter by hand, so the schema stays consistent.
3. Start in `02_Power`. Capture without editing. Everything else follows from what accumulates there.

## Customizing

The discipline list in `System Rules.md` reflects the original author's own fields of interest. It is a starting example, not a fixed requirement — replace or extend it to match your own subjects before relying on the vault.

None of the vocabulary in this vault — disciplines, `kind` values, naming patterns — is a mold your work has to fit. It exists so the vault can find its way back to what you made, not to decide what that work is allowed to be. This was not built only for formal academic research: a student organizing material for an exam, a researcher building toward a thesis, and someone following nothing but their own curiosity all use the same five layers correctly, even when what they name things looks nothing like an academic category.

## Status

Draft. Built and tested through use, not through a formal release process. Expect rough edges.

This repository ships as architecture and documentation, not example content. `02_Power`, `03_Balance`, `04_Development`, and `05_Revolution` hold only a placeholder note explaining what belongs there — that emptiness is the starting state, not something missing.

---

### Anticipated Experience

Two different people will meet this vault with two different reactions, and neither reaction is a sign that something is wrong.

Someone arriving from a rigid, folder-based system, where every note is filed the moment it is captured, will find Power unsettling. Nothing here asks to be categorized. Nothing here rewards immediate tidiness. That discomfort is not a bug to fix; it is the exact habit the layer is designed to interrupt. It will pass once enough Power notes accumulate and the first Balance MOC earns its place.

Someone arriving from no system at all, used to writing freely with no schema, no naming convention, no controlled vocabulary, will find the opposite friction. Balance's `kind` field, Development's fixed disciplines, Source's citation apparatus, the phantom-link rule itself, will feel like a great deal of ceremony for something that used to take no thought at all. That discomfort is not a bug either; it is the price of the traceability and honesty the rest of the vault depends on.

Revolution unsettles everyone, regardless of where they came from. It is the only layer with no scaffolding, no template field to fill in, no automatic query to lean on. Opening a blank Revolution note and being asked, implicitly, what you actually think, is uncomfortable by design. The discomfort is not something to fix or work around. It is the vault doing exactly what it was built to do: hand the question back to the person, instead of answering it for them.

This is why the system functions less like a tool and more like a mirror. It does not tell anyone what to think, what matters, or what they are capable of. It only reflects, with increasing clarity, how much real thought and real commitment the person using it has actually put in. Someone using it seriously will see that seriousness reflected back, layer by layer. Someone using it carelessly will see that too — not as a judgment, since the Dashboard describes rather than scores, but as an honest picture they cannot easily look away from.

## License
Distributed under the MIT License. See `LICENSE` for more information. 
If you use, modify, or distribute this vault architecture, please retain the original copyright notice and credit the author.
