# Bug

To repro, run `tsc -b` from the root of this repro.

## Expected

There should be one `TS6307` error mentioning `packages/directImport/index.ts` due to the import in `packages/reprosTheBug/index.ts`.

## Actual

In addition to the expected error, there is a second `TS6307` error mentioning `packages/indirectImport/index.ts`. This will scale with the number of incorrect imports, both direct and indirect. 

## Explanation

Showing incorrect **indirect** imports increases noise and makes it harder to track down the direct import that caused the issue.
