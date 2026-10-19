> [!important] THIS FILE IS AN INSTRUCTION. WHEN REFERENCED IT IS MEANT TO BE TAKEN AS AN ACTION.

This skill belongs to the Guides shard. Ensure you have [[dev-init-gide]] in context before continuing.

# Skill: Create Guide

Create a simple single-page guide.

# Input

- Guide topic and purpose
- (Optional) Target audience

# Actions

1. **Get the next guide number.**
   - Run `flint helper type newnumber Guide`

2. **Create the guide file** using [[dev-tmp-gide-simple-v0.1]].
   - Path: `Mesh/Types/Guides/(Guide) NNN [Name].md`
   - Set status to `draft`
   - Write the guide content based on the provided topic

3. **Track the session** — stamp your session in `orb:` of the frontmatter: run `flint address me`, and append its `by` address (quoted) to `orb:`. Add nothing only when `orb:` or `orbh-sessions` already has an item that is exactly your `by` address, `@v1/<org>/session/<uuid>`, `[[<uuid>]]`, or your bare `<uuid>`. Old notes keep `orbh-sessions`: never remove it, and add no new item to it. See [[knw-f-artifacts]] § Session Tracking.

# Output

- New guide file at `Mesh/Types/Guides/(Guide) NNN Name.md`
- Status: `draft`
