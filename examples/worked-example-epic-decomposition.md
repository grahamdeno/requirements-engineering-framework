# Worked Example: EPIC Decomposition Run

This example runs one EPIC through the full six-step decomposition process (Docs 01 through 06). The program is a fictional municipal fleet-maintenance system, prefix `FMS`. Real structure, invented content.

## The Input EPIC

> **EPIC: Preventive Maintenance Scheduling.** The system will automatically schedule preventive maintenance for every fleet asset so services stop being missed. Supervisors need to create and approve PM work orders from the schedule, technicians need to know when a service comes due, and the system should reschedule around operational demand. Compliance reporting is required for the state fleet audit.

Source stories attached to the EPIC (abbreviated): schedule generation per asset, service-due notification, supervisor work-order creation from schedule, audit compliance view.

## Step 1: Read for Capabilities, Not Sentences

The EPIC contains **five capabilities**, not four. "Create and approve PM work orders" is two: creating a work order from the schedule and approving one are different behaviors with different actors and different test surfaces. The word "and" between two verbs is the tell. Split now, cheaply.

Identified capabilities: schedule generation, service-due notification, work-order creation from schedule, work-order approval, compliance view.

## Step 2: Assign Each Capability to a Group

Against the locked FMS taxonomy:

| Capability | Group | Reasoning |
|---|---|---|
| Schedule generation | 4. Preventive Maintenance | Core PM behavior |
| Service-due notification | 1. General Functionality | Notifications are cross-cutting; they serve every role and every module |
| Work-order creation from schedule | 2. Work Order Management | The work order is the object, PM is just the trigger |
| Work-order approval | 2. Work Order Management | Same object, different behavior |
| Compliance view | 6. Reporting | Output for an external audience |

No new group earned. Five capabilities distribute across four existing groups, which is normal: EPICs are written by theme, requirements live by structure.

## Steps 3 and 4: Draft and Number the Shall Statements

Each statement singular, testable, written at the altitude the source supports.

**Group 4, Capability 4.2 (Schedule Generation)**
- `FMS-4.2.1` The system shall generate a preventive maintenance schedule for each asset based on its assigned service interval.
- `FMS-4.2.2` The system shall support service intervals defined by elapsed time.
- `FMS-4.2.3` The system shall support service intervals defined by recorded usage.
- `FMS-4.2.4` The system shall recalculate an asset's next service date when a completed service is recorded.

**Group 1, Capability 1.6 (Service-Due Notification)**
- `FMS-1.6.1` The system shall notify the assigned technician when an asset's scheduled service comes due.
- `FMS-1.6.2` The system shall notify the depot supervisor when a due service remains unstarted past its scheduled date.

**Group 2, Capability 2.5 (Work Order Creation from Schedule)**
- `FMS-2.5.1` The system shall allow supervisors to create a work order from a scheduled service.
- `FMS-2.5.2` The system shall populate a schedule-created work order with the asset's identifier and due service tasks.

**Group 2, Capability 2.6 (Work Order Approval)**
- `FMS-2.6.1` The system shall allow supervisors to approve a preventive maintenance work order.
- `FMS-2.6.2` The system shall record the approving user and approval date on each approved work order.

**Group 6, Capability 6.3 (Compliance View)**
- `FMS-6.3.1` The system shall display completed and overdue preventive maintenance services for a user-selected date range.
- `FMS-6.3.2` The system shall allow users to export the compliance view in a document format.

Twelve statements. Decomposition stopped when each statement was singular and testable. No padding: fifty statements restating one behavior is not rigor.

## Step 5: Flag Source Gaps

One assertion in the EPIC is unsupported: **"the system should reschedule around operational demand."** The source defines no demand data, no rescheduling rule, and no authority for the change. Two actions, per the standard:

1. No requirement is written for automatic rescheduling. The behavior the source actually supports is manual: `FMS-4.2.5` The system shall allow supervisors to adjust an asset's scheduled service date.
2. Logged as a named action item: *What data source defines operational demand, and what rule governs automatic rescheduling? Owner: Fleet Operations Manager. On answer, FMS-4.2.5 gains a companion automatic-rescheduling requirement; until then it does not exist.*

Papering over that gap with an invented rescheduling rule would feel productive and would baseline a lie.

## Step 6: Final Review

Red-team pass complete: every statement singular and testable, every capability grouped against the locked taxonomy, one source gap flagged with a named owner. The set is ready to enter the baseline.

## What This Run Demonstrates

- One EPIC sentence hid two capabilities; the split happened at read time, not test time.
- A cross-cutting behavior (notifications) left its home EPIC for General Functionality, where every future EPIC can reuse it.
- The requirement count went down where the source was thin, not up. Altitude discipline is the difference between a baseline and a wish list.

---

*Fictional program. All identifiers, groups, and figures invented. Licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).*
