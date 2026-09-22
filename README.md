# cricket-mobile (hop 3)

Mobile scorecard. **Three hops** from `cricket-protocol`. **One hop** from `cricket-live-gateway`.

```
protocol → scoring → live-gateway → mobile
```

Renders `last_event` only. Does not know `BallEvent`, `extras.type`, or `umpire_confirmed`. The gateway must strip those before this app sees the payload.

A protocol default that makes scoring count an unconfirmed LBW shows a wicket banner here without this file changing.

## Trap branch

`trap/banner-from-match-pack` — walk `snapshot.match.innings.latest_over.latest_delivery.wicket.umpire_confirmed` if the gateway passed the pack through. Tests stay green. Hop 3 talks to hop 0 through four strangers.

## Develop

```bash
npm test
```
