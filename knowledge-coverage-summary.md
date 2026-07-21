# Knowledge coverage summary

Sibling to [management-overview.md](./management-overview.md), [project-summary.md](./project-summary.md), and [harness-flow.md](./harness-flow.md). This note is a shareable snapshot of **what each repo holds and how well covered it is** — high domains only, with note counts and sources where known.

Counts are markdown notes on disk (2026-07-21), excluding scratch harvest under `temp/`. Coverage is each vault's own scoreboard (`60-workflows/knowledge/common-case-coverage.md`).

Where a source was an earlier internal build it is listed as **previous project**; unattributed lived patterns are treated the same.

---

**Agent harness (control plane)**

The hub. Not a knowledge base — it holds the contracts and code that route work into the vaults.

| Component | Holds | Count |
| --- | --- | --- |
| Schemas | task / allocation / gate / escalation contracts | 4 JSON |
| Control-plane code | in-memory helpers, ephemeral task store, harness adapters | 6 Python modules |
| Entry skills | `harness-start`, `harness-task`, `harness-complete-task`, `harness-create-knowledge-base` | 4 skills |
| Docs | setup, source-control, charter, agent-ops, workflows | 8 docs |
| Tests | control-plane / task-store checks (CI gate on `main`) | 1 module |

Source: house-authored (this workspace); aligns with Cursor / model-provider agent guidance.

---

**Engineering knowledge base**

~410 doctrine + lab notes (196 lab examples/skeletons · 82 guidance · 36 principles · 21 standards · 16 patterns · 15 workflows · 14 atlases · 25 foundation). Scoreboard: **176 cells, ~94% at G4** (`status: canonical`). A further 142 harvest notes sit in `temp/` (not counted as doctrine).

| Domain | Cells | Coverage | Sources |
| --- | --- | --- | --- |
| Application languages (Python, C#) | 49 | ~90% G4 | PEP 8, official language docs; previous project |
| Data & SQL (T-SQL, Postgres, warehouse) | 41 | ~95% G4 | Kimball dimensional modeling, Postgres docs; previous project |
| Delivery & CI (GitHub Actions, gates) | 12 | 100% G4 | DORA; previous project |
| Containers & packaging (Docker, Compose) | 10 | 100% G4 | Docker docs; previous project |
| Infrastructure as code (OpenTofu, Helm, K8s) | 20 | 100% G4 | OpenTofu/Terraform, Helm, Kubernetes docs, Kubernetes The Hard Way (pedagogy), CNCF; previous project |
| APIs & contracts (OpenAPI, REST) | 12 | 100% G4 | OpenAPI / REST resource design; previous project |
| Security & auth | 10 | 100% G4 | OWASP (ASVS, Top 10, auth cheat sheets); previous project |
| Observability | 7 | ~86% G4 | DORA, SRE material, OpenTelemetry; previous project |
| Architecture & boundaries | 7 | 100% G4 | Fowler (microservices, Hard Parts), Evans/Vernon DDD, GoF; previous project |
| Orchestration (Argo) | 5 | 100% G4 | Argo Workflows docs; previous project |
| Agent craft | 6 | 100% G4 | Model-provider guidance; previous project |
| Shell & ML-trainer (thin) | 6 | 100% G4 | Tooling docs; previous project |

---

**Change knowledge base (PM / BA / TA)**

~400 doctrine + lab notes (161 lab worked exemplars/skeletons · 66 workflows · 55 guidance · 53 standards · 36 principles · 14 patterns · 11 foundation · 4 atlases). Scoreboard: **53 cells, 100% at G4** (`status: draft` — pending human dry-runs before promotion).

| Domain | Cells | Coverage | Sources |
| --- | --- | --- | --- |
| Business Analysis (BA01–12) | 12 | 100% G4 | BCS-aligned house method; previous project |
| Project Management (PM01–11) | 11 | 100% G4 | BCS-aligned house method; previous project |
| Test Analysis (TA01–09, analysis grain) | 9 | 100% G4 | BCS-aligned house method; previous project |
| Artefact pack (AR01–21, Tier-1 documents) | 21 | 100% G4 | BCS-aligned document suite; previous project |

Deliberately **not** a BABOK / PMBOK / ISTQB chapter mirror — frameworks are pressure, not vault structure.

---

**Systems knowledge base (domain systems & SoR)**

~176 notes (116 guidance · 15 foundation · 14 principles · 11 workflows · 10 atlases · 5 standards). Scoreboard scores **domain families × completeness** (`empty · seeded · partial · useful`; `status: draft`). "Useful" = an agent can answer role, use, cost/limits, failure/controls, and Gaps without inventing.

| Domain | Families | Coverage | Sources |
| --- | --- | --- | --- |
| Cloud platforms | DigitalOcean (P0), Azure | useful (interfaces partial) | Vendor docs; previous project (lived) |
| Databases | SQL Server (engine-deep), Postgres | useful | Vendor docs; previous project (lived) |
| DevOps & source control | Git, GitHub, Azure DevOps | useful | Vendor docs; previous project (lived) |
| CRM & ITSM | Zoho, ManageEngine ServiceDesk | useful | Vendor docs; previous project (lived) |
| Deferred (not started) | aryza-sentinel, tcs-bancs, tuum, virtual-cabinet | empty | — |

---

**How to read coverage**

| Scale | Used by | Meaning |
| --- | --- | --- |
| G1 → G4 | Engineering, Change | G1 law · G2 principle+source · G3 depth/craft · G4 worked exemplar |
| empty · seeded · partial · useful | Systems | up to "useful" = answerable without invention |

**Honest caveats**

- Only engineering's scoreboard is `canonical`; change and systems are `draft` (change awaits dry-runs; systems has P1 interfaces still partial and four deferred platforms).
- G4 proves *law + worked exemplar*, not unlimited depth — depth is tracked separately from cell counts.
- Sources marked *previous project* are internal lived patterns; named external sources (Kimball, OWASP, DORA, Fowler, BCS, vendor docs) are pressure, and the house note wins on house choices.
