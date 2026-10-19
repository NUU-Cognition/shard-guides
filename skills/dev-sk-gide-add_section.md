> [!important] THIS FILE IS AN INSTRUCTION. WHEN REFERENCED IT IS MEANT TO BE TAKEN AS AN ACTION.

This skill belongs to the Guides shard. Ensure you have [[dev-init-gide]] in context before continuing.

# Skill: Add Section

Add a sub-guide page to an existing multi-page guide.

# Input

- Parent guide name (the multi-page guide folder)
- Section name and content topic

# Actions

1. **Verify the parent guide exists.**
   - Check that `Mesh/Guides/(Guide) [Parent Name]/(Guide) [Parent Name].md` exists
   - Read it to understand the guide's scope and existing sections

2. **Create the section file** using [[dev-tmp-gide-section-v0.1]].
   - Path: `Mesh/Guides/(Guide) [Parent Name]/(Guide) [Parent Name] . [Section Name].md`
   - Set `parent:` to link back to the root guide
   - Set status to match the parent's status (or `draft` if the parent is `published`)

3. **Update the parent root file.**
   - Add the new section to the `children:` frontmatter list
   - Add a row to the Sections table in the body

4. **Track the session** — stamp your session in `orb:` of the new section and of the updated parent: run `flint address me`, and append its `by` address (quoted) to `orb:`. Add nothing only when `orb:` or `orbh-sessions` already has an item that is exactly your `by` address, `@v1/<org>/session/<uuid>`, `[[<uuid>]]`, or your bare `<uuid>`. Old notes keep `orbh-sessions`: never remove it, and add no new item to it. See [[knw-f-artifacts]] § Session Tracking.

# Output

- New section file at `Mesh/Guides/(Guide) [Parent Name]/(Guide) [Parent Name] . [Section Name].md`
- Parent root file updated with new child reference
