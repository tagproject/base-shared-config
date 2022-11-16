<p align="center"><img src="https://cdn.jsdelivr.net/gh/tagproject/art/packages/base-shared-config/banner.svg" alt="Package logo"></p>

<p align="center">
    <a href="https://github.com/tagproject/base-shared-config/actions"><img src="https://github.com/tagproject/base-shared-config/actions/workflows/build.yml/badge.svg" alt="Build Status"></a>
    <a href="https://www.npmjs.com/package/@tagproject/base-shared-config"><img alt="npm" src="https://img.shields.io/npm/v/@tagproject/base-shared-config.svg"></a>
    <a href="https://github.com/keindev/standard-shared-config"><img src="https://img.shields.io/badge/standard--shared--config-config-green?logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAfCAYAAACh+E5kAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAJQSURBVHgB1VftUcMwDFU4/tMNyAZ0A7IBbBA2CExAmIBjApcJChO0TFA2SJkgMIGRyDNV3TSt26RN353OX/LHUyTZIdoB1tqMZcaS0imBDzxkeWaJWR51SX0HrJ6pdsJyifpdb4loq3v9A+1CaBuWMR0Q502DzuJRFD34Y9z3DXIRNy/QPWKZY27COlM6BtZZHWMJ3CkVa28KZMTJkDpCVLOhs/oL2gMuEhYpxeenPPah9EdczLkvpwZgnQHWnlNLiNQGYiWx5gu6Ehz4m+WNN/2i9Yd75CJmeRDXogbIFxECrqQ2wIvlLBOXaViuYbGQNSQLFSGZyOnulb2wadaGnyoSSeC8GBJkNDf5kloESAhy2gFIIPG2+ufUMtivn/gAEi+Gy4u6FLxh/qer8/xbLq7QlNh6X4mbtr+A3pylDI0Lb43YrmLmXP5v3a4I4ABDRSI4xjB/ghveoj4BCVm37JQADhGDgOA+YJ48TSaoOwKpt27aOQG1WRES3La65WPU3dysTjE8de0Aj8SsKS5sdS9lqCeYI08bU6d8EALYS5OoDW4c3qi2gf7f+4yODfj2DIcqdVzYKnMtEUO7RP2gT/W1AImxXSC3i7R7rfRuMT5G2xzSYzaCDzOyyzDeuNHZx1a3fOdJJwh28fRwwT1QY6Xzf7TvWG6ob/BIGPQ59ymUngRyRn2El6Fy5T7G0zl+JmoC3KRQXyT1xpfiJKIeAemzqBl6U3V5ocZNf4hHg61u223wn4nOqF8IzvF9IxCMkyfQ+i/lnnhlmW6h9+Mqv1SmQhehji4JAAAAAElFTkSuQmCC" alt="Standard Shared Config"></a>
</p>

[Standard Shared Config](https://github.com/keindev/standard-shared-config) for `tagproject` packages with **shared configs**

## Install

```console
npm install @tagproject/base-shared-config --save-dev
```

## Usage

- Add `"prepare:config": "base-shared-config"` to `scripts` property in your `package.json`
- Rename your `prepare` scripts to `prepare:[NAME]`
- Add `"prepare": "npm-run-all prepare:*"`
- Run `npm run prepare`

> use `node --experimental-specifier-resolution=node node_modules/.bin/base-shared-config` while [ESM](https://nodejs.org/api/esm.html) is in `Experimental`

## Configs

### extract actions and hooks:

- `.github`
- `.husky`

### merge files:

- `.gitignore`
- `.npmignore`
- `.husky/commit-msg`

### append to `package.json`:

#### scripts:

- `build` - build shared config
- `generate` - run all `generate:*`
  `generate:changelog` - generate changelog
  `prepare` - run all `prepare:*`
- `prepare:config` - rebuild local configs
  `prepare:husky` - install husky hooks
  `release` - lint, build config, generate changelog and bump package version

#### other

```json
{
  exports: "./lib/index.js"
  manager: "npm"
  type: "module"
  types: "./lib/index.d.ts"
}
```

### check and install dependencies:

- [changelog-guru](https://www.npmjs.com/package/changelog-guru): `latest`
- [husky](https://www.npmjs.com/package/husky): `8.x`
- [npm-run-all](https://www.npmjs.com/package/npm-run-all): `latest`
