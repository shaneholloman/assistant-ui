---
"@assistant-ui/core": patch
---

fix: add typesVersions to support moduleResolution: node

Users with `moduleResolution: node` in their tsconfig were seeing `Property 'message' does not exist on type 'AssistantState'` because the `exports` map sub-paths (e.g. `@assistant-ui/core/react`) are ignored by legacy node module resolution. Adding `typesVersions` makes TypeScript resolve sub-path types correctly under all moduleResolution modes.
