# 02 – Capability Grouping

## What Groups Are

Capability Groups are the top tier of the taxonomy: broad functional areas that every requirement in the system rolls up under. For a fictional fleet-maintenance system, the initial set might be:

| # | Group | Scope |
|---|---|---|
| 1 | General Functionality | Cross-cutting: authentication, roles, notifications, search, help |
| 2 | Data Management | Records lifecycle, imports, data quality, retention |
| 3 | Work Order Management | Creating, assigning, tracking, and closing maintenance work |
| 4 | Asset Management | Vehicle records, assignments, lifecycle status |
| 5 | Inventory & Parts | Stock levels, ordering, consumption tracking |
| 6 | Administrative | Configuration, reference data, user management |
| 7 | Reporting Functions | Queries, dashboards, exports, scheduled reports |

Define the initial set **before** decomposition begins, from the legacy system's functional areas and the program's known scope. This is groundwork done once, deliberately. Skipping it means inventing taxonomy under time pressure, and taxonomy invented under pressure is taxonomy you'll be apologizing for at requirement 300.

## The New-Group Rule

Content will eventually show up that fits no existing group. A new group is **earned** when all three are true:

1. The content represents a genuinely new functional area, not a variation of an existing one
2. It will plausibly accumulate multiple capabilities over the program's life, not just one
3. Forcing it into an existing group would mislead anyone navigating by group

When those hold, create the group, append it to the end of the numbering, and **flag the decision in writing with your reasoning**. A one-paragraph justification today saves a forty-five-minute argument in a governance meeting later.

**The canonical example:** a modernization program encounters its first AI-driven capability. AI-enabled functionality is not a flavor of Reporting or General Functionality; it's a new functional area that will grow. It earns `Group 8: AI-Enabled Capabilities`, and every future ML or predictive capability rolls up under it as `8.2.x`, `8.3.x`, and so on. One decision, made once, keeps the whole future category coherent.

## Anti-Patterns

- **The junk drawer.** If "General Functionality" is absorbing everything hard to classify, the taxonomy is failing. Groups exist to make location predictable.
- **Premature splitting.** One requirement does not justify a group. Park it in the nearest fit with a note, and promote it when siblings arrive.
- **Renaming mid-program.** Group names appear in every export, test plan, and stakeholder deck ever produced. Rename only with a documented decision and a migration note. Better yet, name them right the first time by borrowing the legacy system's own functional vocabulary; it's the language your stakeholders already speak.
