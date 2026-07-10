# 03 – EPIC Decomposition

The repeatable process: an EPIC goes in, grouped and numbered shall statements come out. Run it the same way every time. Consistency is what makes the output trustworthy at scale; a process you only follow when convenient is a suggestion, not a process.

## Expected Input

A well-formed EPIC arrives with three parts. If any is missing, that's your first finding, not something to invent around.

- **Problem Statement** — what users need and why
- **Proposed Solution** — what the program intends to build
- **Acceptance Criteria** — how the program will know it worked

## The Process

### Step 1: Read for capabilities, not sentences

Identify the distinct *capabilities* the EPIC describes. An EPIC about "notifications" may actually contain two: the notification mechanism itself, and the contact-search logic that determines recipients. Different capabilities, different test surfaces, different IDs. Splitting them now is cheap; untangling them in a test plan is not.

### Step 2: Assign each capability to a group

Use the taxonomy from [Doc 02](02-capability-grouping.md). Cross-cutting capabilities that serve every role (notifications, search, authentication) belong in General Functionality. If nothing fits, apply the new-group rule and document the call.

### Step 3: Draft shall statements per capability

One statement per behavior, written to the standards in [Doc 04](04-shall-statement-standards.md). Decompose until each statement is singular and testable, then stop. Over-decomposition is real: fifty statements restating one behavior in fifty postures is padding, not rigor.

### Step 4: Number them

Apply the ID convention. New capability in an existing group takes the next capability number; requirements number sequentially beneath it.

### Step 5: Flag source gaps

When the EPIC asserts something it doesn't support (says "AI-enabled" with no mechanism, references an approval chain it never defines), do two things:

1. Write the requirement **at the altitude the source actually supports**
2. Log the open questions as a named action item: what's undefined, who owns the answer, what the requirement becomes once answered

These are the questions that must be answered before the set can be trusted. Papering over a gap with invented detail feels productive and baselines a lie.

### Step 6: Final review

Before the set moves forward, run it through a red-team pass (see [Doc 06](06-ai-assisted-workflow.md)) and confirm: every statement testable, every capability grouped, every gap flagged with an owner.

## Cadence Note

Decomposition works best as a steady drumbeat, one EPIC at a time, in the same session format. Batch-processing ten EPICs in one marathon produces inconsistent grouping decisions and numbering drift. Steady and repeatable beats fast and uneven, every time.
