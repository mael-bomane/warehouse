# warehouse

historical data from genesis up to now of some Solana DeFi protocols : perp funding rates, lending reserves, vault strategies.

## layout

```
funding-rates/      perp funding rate history
  SOL/
    drift/{v1,v2,v3}/data.{json,csv}
    hyperliquid/data.{json,csv}
    pacifica/data.{json,csv}

lending/            lending protocol reserve history
  kamino/sol/data.{json,csv}

lst/                liquid staking token APY history
  jito/data.{json,csv}
  marinade/data.{json,csv}

strategies/         vault/strategy performance history
  kamino/
    jitosol/data.{json,csv}
    msol/data.{json,csv}
```

## conventions

- one dataset per leaf dir. `data.json` canonical, `data.csv` mirror.
- path = `<domain>/<asset>/<protocol>/<version?>/data.*`.
- timestamps vary by source (unix sec, unix ms, ISO-8601) — check per-file.
- append-only snapshots. commits timestamped (see `git log`).
