This skill belongs to the Guides shard. Ensure you have [[init-gide]] in context before continuing.

# Skill: Create Guide

Create a simple single-page guide.

# Input

- Guide topic and purpose
- (Optional) Target audience

# Actions

1. **Get the next guide number.**
   - Run `flint helper type newnumber Guide`

2. **Create the guide file** using [[tmp-gide-simple-v0.1]].
   - Path: `Mesh/Types/Guides/(Guide) NNN [Name].md`
   - Set status to `draft`
   - Write the guide content based on the provided topic

3. **Track the session** — append your session ID to `claude-sessions` in the frontmatter.

# Output

- New guide file at `Mesh/Types/Guides/(Guide) NNN Name.md`
- Status: `draft`
