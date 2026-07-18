# Worked Example: Fleet Maintenance System

One EPIC run through the full framework, end to end, using a **fictional** municipal fleet-maintenance system (`FMS`) replacing a fictional legacy application (`LegacyFleet`). Real structure, invented content.

## The Incoming EPIC

> **Problem Statement**
> Shop supervisors and technicians need reliable notifications inside FMS. Today, work order status changes are communicated by email and word of mouth, and assignments get missed.
>
> **Proposed Solution**
> Implement a standardized notification capability that functions across all roles, including refined logic for how the recipient field produces search results, ensuring accurate recipient identification and consistent delivery.
>
> **Acceptance Criteria**
> All roles can send and receive notifications in FMS; the recipient field returns accurate, predictable search results; notifications route correctly to intended recipients.

## Step 1 – Read for Capabilities

The EPIC says "notifications," but it contains **two capabilities** with different test surfaces:

1. **Notifications** — the delivery mechanism itself
2. **Recipient Search** — the logic that determines who a notification can reach

One sentence in the solution, two capabilities in reality. Splitting now is cheap. Untangling them in a test plan is not.

## Step 2 – Assign to a Group

Both serve every role in the system. Cross-cutting capabilities belong in **Group 1: General Functionality**. No new group is warranted; the new-group rule is not close to being met.

## Step 3 & 4 – Draft and Number

| Requirements ID | Capability | System Requirement |
|---|---|---|
| FMS-1.4.1 | Notifications | The system shall allow users to send notifications to other system users. |
| FMS-1.4.2 | Notifications | The system shall allow users to receive notifications within the application. |
| FMS-1.4.3 | Notifications | The system shall route each notification to the recipients selected by the sender. |
| FMS-1.4.4 | Notifications | The system shall retain a record of sent notifications, including sender, recipients, and timestamp. |
| FMS-1.5.1 | Recipient Search | The system shall allow users to search for notification recipients by last name. |
| FMS-1.5.2 | Recipient Search | The system shall allow users to search for notification recipients by assigned role. |
| FMS-1.5.3 | Recipient Search | The system shall support partial-match searches when identifying notification recipients. |

Capabilities 1.4 and 1.5 take the next open capability numbers in Group 1. Every statement passes the five checks: singular, testable, unambiguous, implementation-free, traceable to this EPIC.

## Step 5 – Flag Source Gaps

The EPIC leaves real questions unanswered. They get logged, not invented around:

> **⚠️ Source Gaps — Action Required (Owner: Product Owner, before sprint commitment)**
> - **Delivery channels undefined.** In-app only, or email as well? FMS-1.4.2 is written in-app-only at the altitude the source supports; expands if email is confirmed.
> - **"All roles" untested against read-only accounts.** Can auditor-role users *send*, or only receive? Affects FMS-1.4.1.
> - **No retention period stated** for the notification record in FMS-1.4.4. Compliance may have an opinion. Compliance always has an opinion.

Note what did *not* happen: nobody wrote "the system shall send email notifications" because email seemed likely. Likely is not sourced. Writing fiction to fill a source gap baselines a lie, and baselined lies get built.

## Step 6 – Final Review

The set went through a red-team pass (per [Doc 06](../docs/06-ai-assisted-workflow.md)). One finding: the original draft of FMS-1.4.3 read "route notifications correctly," which is untestable. "Correctly" is a weasel word; it was rewritten to the observable behavior. The reviewer advises, the BA decides, and this time the reviewer was right.

## Crosswalk Tie-In

LegacyFleet had no notification capability; users worked around it with email. Under the [crosswalk method](../docs/05-legacy-crosswalk.md), that workaround was captured in the legacy inventory as an unstated requirement, which is exactly what seeded this EPIC. Every workaround is an unstated requirement in disguise. The inventory is where you spot them.
