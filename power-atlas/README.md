# Power Atlas — prototype

Working concept: an evidence-first, time-aware knowledge graph for understanding how people, families, institutions, money, government, philanthropy, media, academia, and other systems connect.

This prototype is intentionally small. The goal is to prove the interaction model before building a giant database.

## Product thesis

Most public information about influence is scattered across biographies, filings, archives, corporate registries, foundation records, campaign-finance records, historical documents, and investigative datasets. Power Atlas should make those connections explorable without turning association into accusation.

A user should be able to:

- tap any person or institution and inspect its documented relationships;
- move through time and see only relationships that existed then;
- distinguish family, employment, ownership, funding, appointment, board, political, and other relationship types;
- open the source behind every consequential edge;
- see an evidence grade and whether a claim is direct, reconstructed, disputed, or merely proposed;
- search for paths between otherwise distant entities;
- switch between a readable article view and a visual graph;
- inspect competing interpretations without the platform deciding what political conclusion the user should reach.

## Core evidence rule

**An edge means only the relationship written on that edge.**

A shared board seat does not mean conspiracy. A donation does not mean control. A family connection does not establish coordination. Those stronger claims require their own evidence.

## Evidence grades

- **A — Primary:** original filing, contract, official register, archival letter, court record, contemporaneous minutes, etc.
- **B — Strong:** multiple high-quality independent secondary sources or a highly authoritative scholarly reconstruction.
- **C — Supported:** credible single-source secondary evidence.
- **D — Inference:** plausible reconstruction that is clearly labeled and not shown as an established fact.
- **E — Unverified:** user-submitted claim awaiting verification; never displayed as established fact.

## Sensitive background metadata

Historical background can be useful, but it must not become an explanation by default.

- Religion, ethnicity, ancestry, and similar attributes are descriptive metadata, not evidence of coordination.
- For living people, use explicit self-identification or strong authoritative documentation; do not guess sensitive traits from names, appearance, or associations.
- For deceased historical figures, a best-supported historical inference may be stored when clearly labeled with confidence and evidence.
- Every such field should carry provenance just like a graph edge.

## Data-source strategy

We should import public datasets as **source layers**, not erase their provenance.

- **Wikidata** — CC0; useful for baseline identity, dates, offices, family relations, identifiers.
- **LittleSis** — CC BY-SA 4.0 bulk entities/relationships and API; extremely useful for modern power relationships.
- **ICIJ Offshore Leaks** — ODbL database + CC BY-SA contents; useful for offshore entities, officers, intermediaries, and addresses.
- **OpenCorporates** — open/share-alike access for open-data projects; useful for legal-company identity and officers.
- **OpenSanctions / FollowTheMoney** — excellent graph ontology and PEP/sanctions data; free for non-commercial use, commercial use requires licensing.
- **Primary archives** — congressional records, SEC filings, nonprofit filings, court records, central-bank archives, family archives, historical newspapers, etc.

Each imported fact should retain `source_dataset`, `source_id`, `source_url`, `retrieved_at`, and license metadata.

### Important licensing implication

Several of the strongest source datasets use share-alike licenses. That fits a Wikipedia-like public knowledge project well, but it means the business model should focus on paid software/services (advanced analysis, private workspaces, alerts, saved investigations, exports, team tools) rather than trying to make imported public facts proprietary. Obtain legal review before a commercial launch.

## Why this should not simply be another LittleSis

LittleSis already proves that community-edited power mapping is useful. Power Atlas needs to be materially different:

1. **Time-native graph** — every relationship can have a start/end date and the whole network can be scrubbed through history.
2. **Evidence-native UI** — source and evidence strength are first-class visual objects, not buried notes.
3. **Historical continuity** — designed to trace families and institutions across generations and centuries.
4. **Multiple data layers** — modern corporate, political, offshore, archival, genealogical, philanthropic, academic, media, and other records in one graph.
5. **Self-skeptical design** — the interface explicitly separates fact, inference, interpretation, and absence of evidence.
6. **Mobile-first exploration** — engaging enough for a curious general user, rigorous enough for researchers.
7. **Readable knowledge layer** — each node can become a concise sourced article, not merely a graph vertex.

## Prototype files

- `index.html` — mobile-first graph UI
- `app.js` — graph rendering, filters, timeline, search, evidence drawer
- `data/sample-network.json` — a tiny historical finance/government network used only to test the product

## Next engineering steps

1. Move this prototype to a dedicated repository once the interaction model feels right.
2. Replace the static JSON with a versioned graph schema.
3. Build import adapters beginning with Wikidata and LittleSis.
4. Add canonical entity resolution and duplicate review.
5. Add shortest-path queries and source comparison.
6. Add contributor proposals/review instead of unrestricted live edits.
7. Add automated tests that reject unsourced production edges.

## Working name

`Power Atlas` is only a working title. Branding should be checked before public launch.
