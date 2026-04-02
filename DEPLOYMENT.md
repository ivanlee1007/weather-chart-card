# Deployment Notes

This repository is published to HACS as **UNiNUS Weather Chart Card**.

## Canonical identifiers

- Repository: `ivanlee1007/weather-chart-card`
- HACS name: `UNiNUS Weather Chart Card`
- Canonical Lovelace type: `custom:weather-chart-card`
- Published frontend filename: `weather-chart-card.js`

## Release workflow

```bash
cd /path/to/weather-chart-card
npm install
npm run build
git add .
git commit -m "Describe the change"
git push origin master
```

Then create a tag and GitHub release:

```bash
git tag -a vX.Y.Z -m "vX.Y.Z"
git push origin vX.Y.Z
```

Attach these build artifacts to the release when needed:

- `dist/weather-chart-card.js`
- `dist/weather-chart-card-ha.js`

## HACS expectations

`hacs.json` currently points to:

- `filename: weather-chart-card.js`

So if you change build output names, update `hacs.json` and README together.

## Before calling a release done

- version bumped in `package.json`
- `npm run build` passed
- repo contains updated docs for user-visible changes
- runtime bundle on the target HA instance matches the release
- hard-refresh browser test passed
- GUI editor changes were verified in a fresh browser context

## Recent documentation corrections

These docs now intentionally reflect the current fork behavior:

- card picker name is **UNiNUS Weather Chart Card**
- canonical type is `custom:weather-chart-card`
- GUI editor uses HA-native `ha-form` selectors
- text sensor title/content font sizes are configurable
