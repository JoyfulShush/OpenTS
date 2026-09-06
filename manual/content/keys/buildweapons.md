---
key: BuildWeapons
summary: The war factories a computer house resolves a generic factory prerequisite to, in order of preference.
see_also: ["system:ai-base-building"]
when_omitted:
  kind: value
  value: ""
---

The first entry this house may own is what a [`Prerequisite=FACTORY`](/keys/prerequisite/) resolves to while [the base plan](/systems/ai-base-building/#building-the-plan) is assembled, and it is also moved to second place in the candidate list. The whole list answers whether the house owns a factory at all, which feeds the check on whether it can still earn, whether it keeps producing units while low on credits, and whether a house selling its base back can afford a harvester instead of a refinery; entry 0 supplies the factory price the first of those prices a replacement at.

The engine reads entry 0 without checking that the list has it, so an empty list is read past its end.
