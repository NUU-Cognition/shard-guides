This workflow belongs to the Guides shard. Ensure you have [[init-gide]] in context before continuing.

# Workflow: Update Guide

Revise an existing guide — update content, add or remove sections, and bring it back to current accuracy.

# Input

- Guide to update (name or link)
- What needs updating (specific sections, full refresh, or user will specify)

# Actions

## Stage 1: Assess

1. **Read the guide.** Load the root file (simple or multi-page).
   - For multi-page guides, also read all section files listed in `children:`
2. **Identify what's changed** — what's outdated, inaccurate, missing, or unnecessary.
3. **Present an update plan to the user:**
   - List of sections to revise, with a summary of proposed changes
   - Any new sections to add
   - Any sections to remove or merge
   - Whether the status should change (e.g., `published` → `draft` during revision)

Once the user confirms the plan, progress to the next stage.

## Stage 2: Revise

1. **Apply content changes** to each file identified in the plan.
2. **Add new sections** if planned — use [[sk-gide-add_section]] for multi-page guides.
3. **Remove or merge sections** if planned — delete files and update the parent's `children:` and sections table.
4. **Track the session** — append your session ID to `claude-sessions` in every edited file.

Once all changes are applied, progress to the next stage.

## Stage 3: Review

1. Summarize all changes made, file by file.
2. Ask the user to review the updates.
3. Apply any further revisions requested.
4. Confirm final status — suggest `review` if the guide was published, or keep as `draft` if still in progress.

# Output

- Updated guide with all planned revisions applied
- Session tracked on all edited files
- Status updated per user preference
