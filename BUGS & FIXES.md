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
