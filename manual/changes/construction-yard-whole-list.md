---
title: Count every listed construction yard as one
category: fix
release: 0.2.0
targets:
- type: key
  id: BuildConst
  effect: changed
- type: system
  id: production
  effect: changed
credit: [ZivDero, AlexB]
---

A building of any type listed in `BuildConst` is now a construction yard: it joins its house's
yard tally, produces only for the country its own record names, and its loss or capture is
judged like entry 0's. A house whose yard was a later entry owned none as far as the engine was
concerned, so a computer house built no structures at all, a captured yard left the placement
cursor up, and a second yard type built for any country at all.

AlexB is credited for the ts-patches bundle that first read this list whole.
