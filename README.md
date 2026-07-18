# Requirements Engineering Framework

A working methodology for decomposing EPICs into traceable, testable system requirements. Built from delivering enterprise and government software modernizations, where "we'll figure it out in sprint" is how programs die.

## The Problem This Solves

On a legacy system replacement, requirements chaos looks like this: capabilities scattered across EPICs with no numbering logic, "shall" statements that hide three requirements behind one sentence, and no way to prove the new system covers what the old one did. Then UAT arrives and the gaps announce themselves.

Requirements are the instructions a team builds from. When they're vague, the team improvises, and every improvisation is a decision the analyst never made and can't defend. This framework is the up-front discipline that prevents that.

## What's In It

| Doc | Covers |
|---|---|
| [01 – Requirements ID Convention](docs/01-id-convention.md) | Hierarchical numbering that encodes structure into every ID |
| [02 – Capability Grouping](docs/02-capability-grouping.md) | The category taxonomy, and the rules for when a new group earns its existence |
| [03 – EPIC Decomposition](docs/03-epic-decomposition.md) | The repeatable process: EPIC in, grouped shall statements out |
| [04 – Shall Statement Standards](docs/04-shall-statement-standards.md) | What makes a requirement singular, testable, and implementation-free |
| [05 – Legacy Capability Crosswalk](docs/05-legacy-crosswalk.md) | Proving coverage when replacing a legacy system through a verified handover |
| [06 – AI-Assisted Workflow](docs/06-ai-assisted-workflow.md) | Using AI to draft and red-team requirements without surrendering authority |

## Worked Example

[examples/worked-example-fleet-maintenance.md](examples/worked-example-fleet-maintenance.md) runs a full EPIC through the framework using a fictional municipal fleet-maintenance system replacing a legacy application. Real structure, invented content.

[examples/worked-example-epic-decomposition.md](examples/worked-example-epic-decomposition.md) runs one EPIC through the full six-step process for a fictional municipal fleet program. Real structure, invented content.

## Design Principles

1. **Every ID tells you where it lives.** `FMS-3.2.4` reads as: group 3, capability 2, requirement 4. Structure encoded in the designation, the same way a unit designation tells you the parent organization.
2. **Groups are earned, not invented.** New capability groups get created when content clearly warrants one, and the decision gets flagged and justified in writing. Discipline in the taxonomy is what keeps 500 requirements navigable at requirement 501.
3. **Flag the gaps, don't paper over them.** When a source document says "AI-enabled" with no mechanism behind it, the requirement gets written at the level the source supports, and the open questions get documented as an action item. Writing fiction to fill a source gap is how you baseline a lie.
4. **Traceability is accountability.** Every requirement traces to a source: an EPIC, a legacy capability, a stakeholder decision. If you can't say where a requirement came from, you can't defend it when it's challenged. And it will be challenged.

## Attribution

All examples use fictional systems and invented content. The methodology is original work; nothing here is derived from customer systems, government documents, or work product.

---

*Maintained by [Graham DeNoyer](https://github.com/grahamdeno). Part of a set covering the full delivery path: [Delivery Planning Framework](https://github.com/grahamdeno/delivery-planning-framework) · [User Engagement Playbook](https://github.com/grahamdeno/user-engagement-playbook) · [Decision Communication](https://github.com/grahamdeno/decision-communication) · [AI Delivery Toolkit](https://github.com/grahamdeno/ai-delivery-toolkit).*

## License

This work is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).
Share and adapt freely with attribution, for noncommercial use, under the same license.
For commercial licensing, contact me via [LinkedIn](https://www.linkedin.com/in/grahamdenoyer/).
