# @dazl/resolve-directory-context

[![npm version](https://badge.fury.io/js/%40dazl%2Fresolve-directory-context.svg)](https://badge.fury.io/js/%40dazl%2Fresolve-directory-context)

Helpers to get information about single/multi-package contexts.

## Features

Supports:

- single packages
- `"workspaces"` in `package.json` (yarn or npm@7)
- `lerna.json` defined workspaces

## API

- `resolveDirectoryContext`

```ts
import fs from 'fs';
import path from 'path';
import { resolveDirectoryContext } from '@dazl/resolve-directory-context';

const context = resolveDirectoryContext(basePath, { ...fs, ...path });
if (context.type === 'multi') {
  // context.rootPackage === {...}
  // context.packages === [{...}, {...}]
} else {
  // context.type === 'single'
  // context.npmPackage === {...}
}
```

### License

MIT
