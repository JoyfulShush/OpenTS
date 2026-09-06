---
key: ActsLike
summary: The country a scenario's house plays as, whose things its construction yard builds.
see_also: [Owner, GDIHunterSeeker, NodHunterSeeker, MultiplayPassive, "system:production"]
when_omitted:
  kind: computed
  note: The house's own country, or no country at all for a country that takes no part in the multiplayer contest.
---

The value names a country, by its identifier or by its position in the rules country list, and `<none>` names no country at all. A value naming no country is logged and leaves the default standing. Only a campaign mission reads its house records, so this is a campaign setting; outside a campaign every house acts for its own country.

```ini title="scenario map file"
[Special] ; a house record in the scenario's own house list
ActsLike=Nod ; play as Nod; ActsLike=1 names the same country by position in the stock rules
```

Three things consult it, and two of the three can tell apart only the first two countries.

- Every object the house creates copies the value into a record of its own, which is what survives a capture. A construction yard can only put up a BuildingType whose [`Owner`](/keys/owner/) list includes the country its own copy names, so a captured yard keeps building for the country it was built by.
- A hunter-seeker discharge creates [`GDIHunterSeeker`](/keys/gdihunterseeker/) when the value is the first country and [`NodHunterSeeker`](/keys/nodhunterseeker/) for anything else.
- An AI trigger restricted to one side runs only for a house whose value matches: the first country for its GDI restriction, the second for its Nod restriction.

The default is the house's own country whatever it is called: a country named `GDI-Reserve` no longer inherits a country from its name. The stock `Neutral` and `Special`, and any other [`MultiplayPassive=yes`](/keys/multiplaypassive/) country, act for no country at all unless the record says otherwise.
