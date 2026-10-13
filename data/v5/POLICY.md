# v5 change policy

Version 5 is a **draft under review**. It is not released, and its names, descriptions
and questions are expected to change.

Its **structure becomes permanent at release**. Until then, a domain that v5 *added* may
still be removed, and its number reused, because no released standard has ever
contained it.

> A v5 number becomes permanent the day v5 is released. From then on it can never be
> reused, renumbered, re-parented or deleted, exactly like a v4 number.

The release is recorded in one place, `V5_RELEASE_DATE` in
`scripts/lib/domain-rules.mjs`, and `scripts/validate.mjs` enforces the rule from it.

Draft numbers are still published on semdom.org and in `SemDom5-draft.xml`, so someone
may already have tagged words to one. That is why a removal is never silent. It needs an
`op: remove` entry in `data/v5/changes.yaml` that says why, and where anything already
tagged should go instead.

## Allowed

- **Add** a domain at the next free number under an existing parent
- **Revise** a name, description, question, example words or example sentence
- **Broaden** a domain's scope
- **Soft-deprecate**: mark a domain "prefer subdomains" in its description, and the
  domain stays
- **Before release only: remove** a domain that v5 added. Record it in `changes.yaml`:

  ```yaml
  - op: remove
    code: "4.6.8"
    name: "Elections, voting"
    migrate: "4.6.6.4"     # where words already tagged here should go
    rationale: >-
      Why the domain is being removed.
    date: "2026-10-13"
  ```

  Delete the domain file, then run `node scripts/validate.mjs --write-lock`. Once the
  removal merges, the number is free again and the next addition under that parent may
  take it.

## Forbidden — CI rejects these

- deleting or renumbering any domain that came from v4, at any time
- deleting a v5-added domain after release, or without an `op: remove` entry
- re-parenting a code
- changing a GUID
- narrowing a domain so that words already tagged to it become mis-tagged

The full reasoning is `docs/PRINCIPLES.md`. The short version is that every tagged sense
in every dictionary built on this standard references a domain number, in data this
project does not control and cannot migrate.

## How to propose a change

| You want to | Route |
|---|---|
| Change the wording of a v5 domain | The **Suggest a change** link on any domain page. No GitHub account needed. |
| Propose a **new** v5 domain | The same form, in "propose a new domain" mode. A maintainer assigns the number and GUID. |
| Change v4 text | See `data/v4/POLICY.md` first — v4 has its own, stricter, conditions. |

`docs/EDITING.md` walks through each route click by click.

### Why a new domain cannot be created in the browser alone

Three of the things a new domain needs cannot be done from a web editor:

1. **The number** must be the next free child of its parent, checked across *both* v4 and
   v5, because a number retired in v4 must never be handed out in v5.
2. **The GUID** must be minted and checked for collision against all 3,594 existing ones.
3. **`data/v5/structure.lock`** must be regenerated, which requires running Node.

So a new domain is *proposed* through the form and *applied* by a maintainer with
`node scripts/apply-proposal.mjs`. The proposal form shows a provisional number so you
can see where the domain would sit, but the real number is assigned at merge, from the
parent that review actually settled on. A proposal that gets re-parented during review
must not have burned a number on its way through.

### Numbering

A new child takes the **highest existing sibling number plus one**. Gaps are never
filled — a missing number may be missing because it was considered and discarded, and
nothing in the tooling can know that. v5 currently has no gaps at all. A removed draft
domain that was the *last* child leaves no gap, so its number is the next one handed out.
That reuse is deliberate, and it is safe only because the number was never released.

A tenth child would produce the first two-digit segment in the standard's history
(`1.7.10`). That is legal, and `validate.mjs` warns about it rather than failing, because
it is the exact case that YAML and XML parsers have historically coerced into a collision
with `1.7.1`. Treat the warning as a prompt to be sure, not as an obstacle.

### Rationale is required

Every added domain must have an `op: add` entry with a non-empty `rationale` in
`data/v5/changes.yaml`, and every removed one an `op: remove` entry. `scripts/validate.mjs`
rejects a v5 domain that has no add entry, and a removal that has no remove entry.

This is not paperwork. A domain number outlives the conversation that created it, or
removed it, and so must the reason. A GitHub issue is mutable, deletable and not part
of the repository, so the record lives here. `data/v5/history/*.yaml` holds the rationale for the ten
domains added during the original migration pass and is frozen; new entries go in
`changes.yaml`.

## Mirroring from v4

A v4 text fix must be mirrored here, unless v5 has already deliberately reworded that
passage. See `data/v4/POLICY.md` condition 3.

## See also

- `docs/PRINCIPLES.md` — the compatibility charter and the neutrality policy
- `docs/STYLE-GUIDE.md` — how an elicitation question has to be written to survive
  translation
- `docs/EDITING.md` — the mechanics, for someone who does not use Git
- `data/v4/POLICY.md` — the released version's rules
