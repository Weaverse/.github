# Linear ↔ GitHub Conventions

We use **Linear** as the source of truth for all work tracking across Weaverse.
GitHub Issues are reserved for community/external bug reports on public repos; internal work lives in Linear.

---

## Workspace overview

**Teams** (Linear Free plan, capped at 2):

| Team | Key | Use for | Cycles |
|---|---|---|---|
| Engineering | `ENG` | All eng + cross-functional work today | 2-week cycles, Mondays |
| Design | `DES` | UI, brand, assets | No cycles |

> Non-engineering functions (Marketing, Sales, Ops, Product) file issues in `ENG` and tag with `area:*` labels until we upgrade.

**Projects** (group related work; one project per product line):

| Project | What it covers |
|---|---|
| **Weaverse** | Core platform: SDKs, app infra, dashboard, dev tooling |
| **Weaverse AI** | AI assistant, automation, provider routing |
| **Weaverse Hydrogen themes** | Branded themes (Pilot, Maison, Naturelle, Aspen, etc.) |
| **Studio** | Visual page builder (`Weaverse/builder`) |
| **Customer Projects** | Client engagement Hydrogen builds |
| **Marketing** | Content, tools, campaigns |
| **Operations** | Internal automation, team tooling |

See each project page in Linear for the repo list.

---

## Labels

**Type** (what kind of work):
`bug` · `feature` · `improvement` · `chore` · `docs`

**Source** (where it came from):
`customer` · `internal` · `community`

**Area** (function — use when filing non-eng work in the ENG team):
`area:design` · `area:product` · `area:marketing` · `area:sales` · `area:ops`

Don't use a separate `priority` label — Linear has a native priority field (Urgent / High / Medium / Low). Use that.

---

## GitHub ↔ Linear linking

Linear's native GitHub integration handles PR/branch/commit linking automatically.
Use any of these in a **branch name**, **PR title**, **PR description**, or **commit message**:

- `ENG-123` — links the PR to issue ENG-123
- `Fixes ENG-123` / `Closes ENG-123` / `Resolves ENG-123` — links **and** closes the issue when the PR merges
- `Ref ENG-123` — links without closing

### Branch naming

Easiest: open the Linear issue → click **"Copy git branch name"** → it gives you something like:

```
paul/eng-123-add-pagination-fix
```

That branch name auto-links to the issue on push.

If hand-rolling, the format is:
```
<username>/<identifier>-<short-kebab-description>
```

### Workflow automation

When you do this in GitHub… | …Linear does this:
---|---
Open a PR referencing `ENG-N` | Moves issue to **In Progress**
Mark PR ready for review | Moves issue to **In Review**
Merge the PR | Moves issue to **Done**
Close PR without merging | Moves issue back to **Todo**

---

## Filing a new issue

**From inside Weaverse (most work):**
File directly in Linear. Pick:
1. Team: `ENG` (or `DES` for pure design work)
2. Project: pick the right one (see table above)
3. Labels: at least one `type` label; add `area:*` if non-eng; add `source` if relevant
4. Assignee + priority

**From outside (community bug on a public repo):**
File on GitHub. Triagers will mirror critical ones into Linear manually.

---

## Saved views (recommended for everyone)

Create these in Linear sidebar → Views → New view, then star to pin:

- **My active work** — Assignee = me · State ≠ Done/Canceled
- **Needs my review** — State = In Review · Subscriber = me
- **Created by me** — Created by = me · State ≠ Done/Canceled
- **Current cycle** — Team = ENG · Cycle = current

---

## When we outgrow the Free plan

Triggers to upgrade to Standard:
- Need a 3rd team (Marketing or Sales getting their own workflow)
- Want Initiatives (cross-team multi-quarter themes)
- Want SLAs, Triage inbox, or Insights dashboards

When that happens, the `area:*` labels make it easy to split issues into proper teams.
