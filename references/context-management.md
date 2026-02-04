# Context Management (Progressive Disclosure)

## Window Discipline
- Avoid the last ~20% of context for big refactors or multi-file edits.
- If close to the limit, ask to `/compact` before continuing.

## Progressive Disclosure (3 Levels)
1. **Metadata always visible**: filenames, brief summaries, TODOs.
2. **Body on trigger**: load only the file/section needed.
3. **Bundled resources on demand**: schemas/docs moved to references or scripts.

## OpenClaw Practices
- Store large/static content under `references/` or scripts.
- Summarize and point instead of pasting full blocks.
- Batch related decisions in a single call.
