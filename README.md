# A module for javascript/typescript projects

This is a package-manager agnostic module for managing projects with a package.json

Supported package managers:
- npm
- yarn
- bun
- pnpm

By default, the module reads package manager hints from the standard `engines` field in
`package.json`, such as:

```json
{
  "engines": {
    "bun": "1.2.4"
  }
}
```

If no supported package manager engine is present, the module falls back to `npm`.
The default base image is selected from the resolved package manager: Bun uses
`oven/bun:<version>-alpine` when an exact Bun version is provided, and other
package managers use `node:25-alpine`.
