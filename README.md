# A module for javascript/typescript projects

This is a package-manager agnostic module for managing projects with a package.json

Supported package managers:
- npm
- yarn
- bun
- pnpm

By default, the module reads the standard `packageManager` field from
`package.json`, such as:

```json
{
  "packageManager": "bun@1.2.4"
}
```

If the field is absent, the module falls back to `npm`. The default base image
is selected from the resolved package manager: Bun uses `oven/bun:<version>-alpine`
when a Bun version is provided, and other package managers use `node:25-alpine`.
