# 06 – AI-Assisted Workflow

AI drafts fast and reviews tirelessly. It does not own the baseline. The division of labor is simple: the AI produces drafts and reviews, the BA owns the requirement set. Get that relationship right and the framework runs at twice the speed with better quality. Get it backwards and you've automated the production of confident nonsense.

## Where AI Earns Its Place

### 1. First-draft decomposition

Give the AI a standing brief once per session, then feed it EPICs one at a time. The brief establishes the framework as the fixed standard for everything that follows:

```
STANDING BRIEF — REQUIREMENTS DECOMPOSITION

You will draft system shall statements from EPICs I provide.

STANDARDS:
- Each statement singular, testable, unambiguous, implementation-free
  (I will reject statements with "appropriate," "user-friendly," "quickly," or hidden "and"s)
- Format: "The system shall [verb] [object] [qualifier]."

STRUCTURE:
- Assign each statement a Requirements ID: [PREFIX]-Group.Capability.Requirement
- Group under these categories: [paste your group taxonomy]
- If content clearly fits no group, propose a new group, flag it, and justify it. Do not force a bad fit.

SOURCE GAPS:
- Where the EPIC asserts something it doesn't define, write the requirement at the
  altitude the source supports and list the open questions as an action item.

Confirm you understand the format, then I'll paste the first EPIC.
```

Two things make this work. The **example statements of "good"** you add from your own accepted set (show, don't tell), and the **explicit permission to flag gaps** rather than invent detail. An AI ordered to produce complete-looking output will produce complete-looking fiction. Order it to surface the gaps instead, and it becomes your best source-document critic.

### 2. Red-teaming the set

Before any baseline, run the full set through a hostile review: testability, ambiguity, singularity, completeness, conflicts. This is the rehearsal before the event that counts. The AI is exceptionally good at the tedious passes a human reviewer fatigues on, like checking statement 340 against statement 12 for conflict. (A ready-made prompt for this lives in the companion [AI Delivery Toolkit](https://github.com/grahamdeno/ai-delivery-toolkit).)

### 3. Crosswalk gap hunting

Paste the legacy inventory and the new requirement set, and ask one question: *which legacy capabilities have no plausible new-system coverage?* Treat the answer as leads to verify, not findings to accept.

## The Non-Negotiables

- **The AI proposes, the BA disposes.** Every statement gets human review before it enters the set. No exceptions, no matter how clean the output looks. Especially when the output looks clean.
- **Verify against source, not against fluency.** AI output is confident by default. Confidence is not evidence. Check drafted requirements against the actual EPIC text, every time, the same way you'd check any secondhand report against the source.
- **Data sensitivity applies.** Never paste customer or program source material into any AI tool your organization hasn't approved for that data classification. Sanitize first or don't paste.
- **The AI never talks to stakeholders.** Drafts, reviews, and gap lists are internal working products. What goes to governance carries your name and your judgment.
