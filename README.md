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
