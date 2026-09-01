---
type: essence
purpose: Optional addendum layering the minimal rules and metadata needed for shared, multi-author use onto the otherwise individual vault
updated: 2026-08-11
---

# Team Collaboration

This is an optional addendum. The base vault is written for a single author, but nothing in it forbids collaboration: the authorship principle that governs Revolution is *human versus system*, not *individual versus team*. A group of people is still "not the system," so a co-authored Revolution MOC satisfies the same rule a solo one does. This document adds only what shared use actually requires — a few conventions and a few optional fields. It changes none of the mechanics.

## What Does Not Change

The six folders, the five-layer pipeline, phantom links and their activation, the earned-structure principle, the controlled vocabularies, and every existing template stay exactly as they are. A shared vault runs the same queries a solo vault does; collaboration is additive, never a rewrite. If the additions below are ignored, the vault still works — it simply loses the ability to say *who* did what.

## Added Metadata

These fields are optional and meaningful only in a shared vault. They carry attribution and division of labor; a solo user never needs them, and omitting them breaks nothing.

| Field | Type | Applies to | Description |
|---|---|---|---|
| owner | Text | Power, Balance, Revolution | the single person accountable for this note — who captured it, maintains it, or is driving it. Answers "who do I ask about this." |
| contributors | List | Revolution | every person who authored part of the work, for genuinely co-authored Revolution MOCs. `owner` names the lead; `contributors` names everyone. |

`owner` values must be canonical member identifiers drawn from the roster below, for the same reason every other field is controlled: Dataview matches on exact strings, so "Alex" and "alex" are two different people to a query. Development pages need no ownership field — they are auto-generated and belong to no one; the same is true of Source category MOCs.

## Member Roster

Following the rule that vocabulary is defined before it is used, a shared vault lists its members' canonical identifiers before any `owner` or `contributors` field is filled in. Add them here first, then use them:

- (example) `Alex`, `Sam`, `Jordan` — replace with the actual team.

An identifier is whatever the team agrees on — first name, initials, a handle — as long as it is written identically everywhere. The list is the single source of truth; a name not on it will silently disappear from any by-owner view.

## Shared Vocabulary Becomes a Coordination Requirement

For a solo user, the controlled vocabularies in [[System Rules]] are a matter of being consistent with oneself. For a team they become a hard coordination requirement. Every Dataview query filters on exact string matches, so if one member writes the discipline `Politics` and another writes `Politika`, their work quietly splits into two invisible halves that never appear together. A team must therefore treat the vocabularies as strictly shared: one agreed spelling per discipline, `kind`, status, and category, documented in [[System Rules]] before anyone uses a new value. This is the same rule the solo vault already has — it simply carries more weight when more than one person can break it.

## Conventions, Not New Mechanics

The following are agreements a team makes among themselves. The system does not enforce them; it never forbids anything (see [[Manifesto]], principle 11). It only makes whatever the team does visible.

Creating a Balance MOC and activating a Development page stay exactly as defined — earned, deliberate, never automatic. In a group the only open question is *who* performs that act, and that is a social convention (any member may, or by agreement) rather than a mechanic. The earned threshold itself is unchanged, and is if anything a stronger signal in a team: when several people independently point a phantom link at the same prospective MOC, the concept has proven itself more convincingly than one person could prove it alone.

Citation keys need coordination that a solo vault rarely does. When two members log sources that would produce the same `citationKey`, the collision is resolved with the lowercase-suffix rule already in [[System Rules]] (`Weber1978a`, `Weber1978b`) — but in a team someone has to notice the collision, so shared sources are worth a quick check before a key is finalized.

## Reading the Mirror in a Team

In a solo vault the Dashboard and the Development pages are a mirror of one person's focus and honesty (see [[Manifesto]], principles 8 and 9). In a shared vault the same queries reflect the *group's* collective state instead. Nothing about the queries changes; only the reading does. "Unprocessed Power notes" stops meaning "my backlog" and starts meaning "our backlog"; a Development page stops describing one person's coverage of a discipline and starts describing the team's. This is still a description, not a verdict — it is a coordination surface, not a scoreboard. Adding `owner` simply lets the team slice that shared picture by person when it needs to (for example, a Dashboard query filtered `WHERE owner = "Alex"`), without turning the mirror into a ranking.

## Synchronization Is Out of Scope

Getting the same files onto several people's machines — Git, a shared sync service, or anything else — is the team's own infrastructure choice, exactly as plugin selection is (see the README). The vault architecture is sync-agnostic: it assumes only that whatever multiple people edit eventually reconciles into one set of files. How that happens, and the merge discipline it requires, is the user's responsibility, not the vault's.

## Related Documents

[[Vault Overview]] gives the top-level structure. [[System Rules]] defines the workflow and controlled vocabularies this addendum builds on. [[Property Schema Reference]] lists the base fields; the two fields above are additive and team-only. [[Manifesto]] states the principles behind all of it.
