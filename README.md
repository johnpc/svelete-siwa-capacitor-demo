# SIWA Capacitor issue

## How this project was created:

```bash
npm create svelte@latest my-app
cd my-app
npm install
npm i @capacitor-community/apple-sign-in
```

Then usage of `@capacitor-community/apple-sign-in` was added to `src/routes/Header.svelte`.

## See the failure

To see the failure run

```bash
npm run build
```

The output is `SyntaxError: Cannot use import statement outside a module`

```bash
(base) ➜  my-app npm run build

> my-app@0.0.1 build
> vite build

vite v5.1.5 building SSR bundle for production...
"confetti" is imported from external module "@neoconfetti/svelte" but never used in "src/routes/sverdle/+page.svelte".
✓ 109 modules transformed.
vite v5.1.5 building for production...
✓ 99 modules transformed.
....
.svelte-kit/output/client/_app/immutable/chunks/entry.Cg3UxBo3.js                                  27.43 kB │ gzip: 10.80 kB
✓ built in 515ms
(node:1883) Warning: To load an ES module, set "type": "module" in the package.json or use the .mjs extension.
(Use `node --trace-warnings ...` to show where the warning was created)

node:internal/event_target:1083
  process.nextTick(() => { throw err; });
                           ^
/Users/xss/repo/my-app/node_modules/@capacitor-community/apple-sign-in/dist/esm/index.js:1
import { registerPlugin } from '@capacitor/core';
^^^^^^

SyntaxError: Cannot use import statement outside a module
    at internalCompileFunction (node:internal/vm:73:18)
    at wrapSafe (node:internal/modules/cjs/loader:1153:20)
    at Module._compile (node:internal/modules/cjs/loader:1205:27)
    at Module._extensions..js (node:internal/modules/cjs/loader:1295:10)
    at Module.load (node:internal/modules/cjs/loader:1091:32)
    at Module._load (node:internal/modules/cjs/loader:938:12)
    at cjsLoader (node:internal/modules/esm/translators:284:17)
    at ModuleWrap.<anonymous> (node:internal/modules/esm/translators:234:7)
    at ModuleJob.run (node:internal/modules/esm/module_job:217:25)
    at async ModuleLoader.import (node:internal/modules/esm/loader:316:24)
Emitted 'error' event on Worker instance at:
    at [kOnErrorMessage] (node:internal/worker:326:10)
    at [kOnMessage] (node:internal/worker:337:37)
    at MessagePort.<anonymous> (node:internal/worker:232:57)
    at [nodejs.internal.kHybridDispatch] (node:internal/event_target:807:20)
    at exports.emitMessage (node:internal/per_context/messageport:23:28)

Node.js v20.8.1
```