---
key: BuildPower
summary: The power plants a computer house plans first, in order of preference.
see_also: ["system:ai-base-building"]
when_omitted:
  kind: value
  value: ""
---

The first entry the country this house acts as may own is queued immediately after the construction yard, and that seat skips [the base plan's](/systems/ai-base-building/#building-the-plan) candidate filter: a type carrying [`AIBuildThis=no`](/keys/aibuildthis/), or a [`TechLevel`](/keys/techlevel/) above the house's, is planned anyway. Nothing else reads the list, and in particular the power plant inserted ahead of a node that would outrun the base's output is chosen from the house's country name rather than from here.

A list holding no entry that country may own queues no power plant.
