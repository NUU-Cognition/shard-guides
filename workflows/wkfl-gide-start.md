This workflow belongs to the Guides shard. Ensure you have [[init-gide]] in context before continuing.

# Workflow: Start Guide

Design and create a multi-page guide with user review.

# Input

- Guide topic and purpose
- Target audience
- (Optional) Planned sections

# Actions

## Stage 1: Design

1. **Define the guide scope** — what will the reader learn? What's the end state?
2. **Plan the sections** — break the topic into logical, sequential sections
3. **Present the outline to the user:**
   - Guide title
   - Overview summary
   - Ordered list of planned sections with brief descriptions

Once the user confirms the outline, progress to the next stage.

## Stage 2: Create

1. **Create the guide folder** at `Mesh/Guides/(Guide) [Name]/`

2. **Create the root file** using [[tmp-gide-root-v0.1]].
   - Populate the `children:` frontmatter with all planned sections
   - Fill in the Sections table

3. **Create each section file** using [[tmp-gide-section-v0.1]].
   - Write the content for each section
   - Set `parent:` linking back to the root

4. **Track the session** — append your session ID to all created files.

Once all files are created, progress to the next stage.

## Stage 3: Review

1. Present the completed guide structure to the user
2. List all created files with a brief summary of each
3. Ask if any sections need revision or if additional sections should be added
4. Apply any requested changes
5. Confirm the guide is ready — suggest setting status to `review` or `published`

# Output

- Complete multi-page guide folder with root and all section files
- All files linked via `children:` / `parent:` frontmatter
- Status set per user preference
