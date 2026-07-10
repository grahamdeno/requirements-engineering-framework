# 01 – Requirements ID Convention

## The Format

```
PREFIX-G.C.R
```

| Segment | Meaning | Example |
|---|---|---|
| `PREFIX` | System or program identifier | `FMS` (Fleet Maintenance System) |
| `G` | Capability **Group** number | `3` = Work Order Management |
| `C` | **Capability** number within the group | `2` = Preventive Maintenance Scheduling |
| `R` | **Requirement** number within the capability | `4` = fourth requirement under that capability |

So `FMS-3.2.4` reads, at a glance: Fleet Maintenance System, Work Order Management group, Preventive Maintenance Scheduling capability, requirement four. Anyone on the program can locate it without opening a tool. Structure encoded in the designation, the way a library call number tells you the shelf, the section, and the book before you've moved a step.

## Rules

1. **Numbers are permanent.** A retired requirement's number is never reused. Reusing numbers destroys the audit trail, and the audit trail is the point.
2. **Group numbers are assigned once, at framework setup**, in a documented order. New groups append to the end; they never renumber existing groups.
3. **Capabilities number in order of creation within their group**, not alphabetically. Sorting is a tool's job; the ID's job is stability.
4. **One requirement, one ID.** If a shall statement needs two IDs, it was two requirements wearing one sentence. Split it (see [Doc 04](04-shall-statement-standards.md)).

## Why Hierarchical Beats Sequential

A flat sequence (`REQ-001` through `REQ-500`) tells you nothing at requirement 500. The hierarchical ID gives you three free capabilities:

- **Navigation.** Filter any tool by `FMS-3.*` and you're looking at all of Work Order Management.
- **Gap visibility.** If group 6 has forty requirements and group 7 has two, that's either a simple group or an under-decomposed one. The numbering makes the question visible.
- **Traceability at a glance.** In a defect report, a test case, or a heated stakeholder meeting, `FMS-3.2.4` locates the exact contested ground in seconds.
