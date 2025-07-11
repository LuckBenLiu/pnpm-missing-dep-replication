# pnpm-missing-dep-replication

replicate the "missing dep" issue that starts to happen from pnpm@10.12.2

# Replicate Steps

```
1. corepack enable pnpm && corepack install
2. pnpm fetch
3. pnpm install --offline
4. pnpm --filter some-e2e cypress:run
```

## Expected:

Cypress tests pass as what `pnpm<=10.12.1` does normally.

## Actual:

failed with `Error: You are attempting to run a TypeScript file, but do not have TypeScript installed. Ensure you have 'typescript' installed to enable TypeScript support.`
