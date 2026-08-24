# Renovate Configs

This repo contains configurations for Renovate. These settings are set to my liking and may change at any time, so I don't recommend using them on your own projects. That said, feel free to use this as a reference if you're trying to configure Renovate yourself.

## Default

Use this config for JS/TS applications.

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>bachman-dev/renovate-config"]
}
```

## `jslib`

Use this config with JS/TS libraries.

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>bachman-dev/renovate-config:jslib"]
}
```

## `oxlint-tsgolint`

Oxlint uses `tsgolint` when it's configured to do type-aware linting. This config establishes a Custom Manager that keeps a repository's TypeScript version matched to the current `tsgolint` version, as their versions are derived from their supported TS version + a small patch incrament (e.g. a version for TypeScript 7.0.2 may look like 7.0.2001).

For projects that are using `tsgolint`, extend the `oxlint-tsgolint` config *in addition to* the default or `jslib` config.

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>bachman-dev/renovate-config", "github>bachman-dev/renovate-config:oxlint-tsgolint"]
}
```

# Development

We use mise-en-place for tool and environment management. Create a `mise.local.toml` in the project's directory, set a `RENOVATE_TOKEN` with the [correct permissions as described in the Renovate docs](), and use the test commands to evaluate changes -- either `test:local` for package rule evaluations, or `test:gitHub` for PR and other GitHub specific integration.

```shell
mise install
```

```shell
pnpm test:local
```

```shell
pnpm test:github
```
