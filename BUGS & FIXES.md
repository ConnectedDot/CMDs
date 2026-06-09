For SPFx 1.13.1 projects, newer TypeScript versions (5 or 6) are incompatible. 
E.g A Node 14 Project is tied to TypeScript 3.9 via `@microsoft/rush-stack-compiler-3.9`. 
To ensure proper compilation, confirm the TypeScript version using `npm ls typescript`. 
Configure VS Code to use the workspace's TypeScript version by adding the following to `.vscode/settings.json`:

```json
{
  "typescript.tsdk": "node_modules/@microsoft/rush-stack-compiler-3.9/node_modules/typescript/lib"
}
```

Then, in VS Code, Ctrl+Shift+P → TypeScript: Select TypeScript Version → Use Workspace Version

While `skipLibCheck: true` can skip type-checking `.d.ts` files, it won't resolve syntax errors caused by newer type packages incompatible with TypeScript 3.9.

For SPFx 1.13, avoid using loose `^` versions for packages that might introduce newer types. Instead, pin package versions (e.g., `"@pnp/sp": "2.13.0"`) to prevent compatibility issues. After adjusting package versions, perform a clean install:

(* ```bash
rm -rf node_modules package-lock.json
npm install
npm run build
``` *)

In summary, there is no TypeScript flag to enable newer TypeScript versions with SPFx 1.13. The solution involves locking VS Code and the build process to TypeScript 3.9.


Theop@Samuels MINGW64 /c/THEO/DEVELOPMENTS/LOTUS PROJECTS/MTNN/MTN-Workplan (production-fix3)
$ npm ls typescript
mtn-workpaper-v2@0.0.3 C:\THEO\DEVELOPMENTS\LOTUS PROJECTS\MTNN\MTN-Workplan
+-- @microsoft/rush-stack-compiler-3.9@0.4.47
| +-- @microsoft/api-extractor@7.15.2
| | `-- typescript@4.2.4 
| `-- typescript@3.9.10 
`-- spfx-fast-serve-helpers@1.13.7
  `-- react-refresh-typescript@2.0.2
    `-- typescript@4.2.4  extraneous

npm ERR! extraneous: typescript@4.2.4 C:\THEO\DEVELOPMENTS\LOTUS PROJECTS\MTNN\MTN-Workplan\node_modules\react-refresh-typescript\node_modules\typescript

Theop@Samuels MINGW64 /c/THEO/DEVELOPMENTS/LOTUS PROJECTS/MTNN/MTN-Workplan (production-fix3)
$ 
