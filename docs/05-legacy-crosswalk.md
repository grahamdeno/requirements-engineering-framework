# 05 – Legacy Capability Crosswalk

## The Situation

Replacing a legacy system is a controlled handover. The outgoing system carries work the incoming system must take over, and the handover fails if anyone assumes rather than verifies what that work actually is. The day the legacy system sunsets, every capability it provided is either covered by the new system, deliberately retired, or a surprise. The crosswalk exists to eliminate the third category.

This matters double when the sunset is contested. Legacy systems have defenders, usually the power users who mastered them, and "trust us, the new system does that" wins no arguments. A documented crosswalk converts a contested sunset debate into a line-by-line concurrence exercise. It's hard to argue with a table where every row has a disposition and a signature.

## The Method

### Step 1: Inventory the legacy system's capabilities

Not its screens. Its **capabilities**: the distinct things users can accomplish. Sources, in order of authority:

1. Official system documentation (user manuals, interface specs) where it exists
2. Observation of actual use, because how work is actually done and how the manual says it's done diverged years ago
3. Power-user interviews, specifically hunting the workarounds, because every workaround is an unstated requirement in disguise

Number the inventory with the same hierarchical convention (`LGCY-G.C.R`), grouped by the legacy system's own functional areas.

### Step 2: Assign every legacy capability a disposition

| Disposition | Meaning | Requires |
|---|---|---|
| **Migrate** | New system must provide it | A mapped new-system requirement ID |
| **Transform** | Need survives, mechanism changes | A mapped requirement + a change note |
| **Retire** | Deliberately not carried forward | A documented, stakeholder-endorsed rationale |
| **Defer** | Carried forward, later phase | A target phase and an owner |

The forcing function is the empty cell. Every legacy capability gets a disposition; "we haven't decided" is not a disposition, it's the surprise category with better manners.

### Step 3: Build the crosswalk table

```
Legacy ID    | Legacy Capability            | Disposition | New System ID(s) | Notes
LGCY-3.1.2   | Search work orders by vehicle | Migrate     | FMS-3.1.4        |
LGCY-3.4.1   | Print work order to form 24-B | Transform   | FMS-7.2.1        | Form retired; PDF export replaces
LGCY-5.2.3   | Manual stock-level override   | Retire      | —                | Endorsed 2026-03-12; audit risk
```

### Step 4: Take it to governance

The crosswalk is the document that turns opinions into decisions. Walk stakeholders through the Retire rows specifically; those are the contested ground. Concurrence on the record, before build, is what protects the program when someone resurrects the debate at UAT. Someone always resurrects the debate at UAT.

## The Payoff

Coverage becomes provable instead of asserted. Any auditor, stakeholder, or new team member can trace every legacy capability to its fate. And when the sunset date arrives, the handover is verified, not hoped for.
