# Traps for single-repo review

## `trap/banner-from-match-pack`

**The PR:** gateway sometimes forwards scoring's match pack. Drive the banner from `snapshot.match.innings.latest_over.latest_delivery` so overlays match the truck. Treat missing `umpire_confirmed` as a wicket.

**What a hop-3 review usually says:** uses a field the API already returns, Law of Demeter is a style nit, tests updated, LGTM.

**3 hops up (protocol):** the walk encodes hop-0 confirmation. A later default changes the banner without this file changing.

**2 hops up (scoring):** `wicket_counted` is ignored.

**1 hop up (gateway):** the firewall was the point of the gateway.

**Functional truth:** ScoreSnapshot (after the gateway) is a friend. `match.innings.latest_over.latest_delivery.wicket` is a 3-hop train wreck.
