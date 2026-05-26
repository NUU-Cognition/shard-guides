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

4. **Track the session** — append your session ID to `claude-sessions` in both the new section and the updated parent.

# Output

- New section file at `Mesh/Guides/(Guide) [Parent Name]/(Guide) [Parent Name] . [Section Name].md`
- Parent root file updated with new child reference
