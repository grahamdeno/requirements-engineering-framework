# 04 – Shall Statement Standards

A shall statement succeeds only if it has exactly one possible interpretation. Every guess a developer makes about an ambiguous requirement is a decision the BA didn't make, and some of those guesses ship.

## The Standard

Every statement must pass all five checks:

### 1. Singular
One behavior per statement. The word "and" between two verbs is the tell.

- ❌ *The system shall allow users to create and approve work orders.*
- ✅ *The system shall allow users to create work orders.*
- ✅ *The system shall allow authorized approvers to approve submitted work orders.*

Two behaviors means two test cases, two possible defects, and eventually two different owners. Give each its own ID now.

### 2. Testable
A tester must be able to write a pass/fail test from the statement alone.

- ❌ *The system shall return search results quickly.*
- ✅ *The system shall return search results within 3 seconds for queries against up to 100,000 records.*

If the source document doesn't give you the threshold, that's a source gap to flag, not a blank to fill with optimism.

### 3. Unambiguous
Hunt the weasel words: *appropriate, user-friendly, support, seamless, robust, as needed, etc.* Each one is a different picture in every reader's head.

- ❌ *The system shall provide appropriate access to reports.*
- ✅ *The system shall restrict report access based on the authenticated user's assigned role.*

### 4. Implementation-Free
State **what**, not **how**. The requirement is the objective; the route belongs to the engineers.

- ❌ *The system shall use a dropdown populated from the vendors table to select a vendor.*
- ✅ *The system shall allow users to select a vendor from the list of active vendors.*

State the destination, not the turn-by-turn directions. Constrain the how only when a real constraint exists (compliance, integration contract), and then name the constraint as its own requirement.

### 5. Traceable
Every statement points back to a source: an EPIC, a legacy capability, a documented decision. An orphan requirement is indefensible the first time a stakeholder asks "who asked for this?" And someone always asks.

## Formula That Covers 90% of Cases

```
The system shall [verb] [object] [qualifier / condition].
```

- *The system shall allow users to search vehicle records by asset ID.*
- *The system shall restrict work order deletion to users with the Administrator role.*
- *The system shall generate a notification when a work order exceeds its scheduled completion date.*

Boring, uniform, and instantly parseable. In requirements, boring is a feature. Save the creativity for solving the problem, not describing it.
