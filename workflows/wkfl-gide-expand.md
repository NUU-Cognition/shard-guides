This workflow belongs to the Guides shard. Ensure you have [[init-gide]] in context before continuing.

# Workflow: Expand Guide

Expand a guide by answering inline `%%? question%%` markers, replacing each with authored content that flows naturally into the surrounding text. See the Philosophy section in [[init-gide]] for the on-topic vs prerequisite distinction.

# Input

- Guide to expand (name, path, or link)
- (Optional) Additional context or references to inform the answers
- (Optional) --forced mode, where there is no approval between stages and directly confirms and moves on to stages. 

# Actions

## Stage 1: Scan

1. **Read the guide.** Load the full document.
   - For multi-page guides, read the root and all section files listed in `children:`
2. **Extract all `%%?...%%` markers.** For each marker, capture:
   - The question text
   - Its location (file and heading context)
   - Surrounding content (text before and after the marker)
3. **Present the expansion plan** — list every question with its context so the user can see what will be answered.

Once the user confirms the plan (or adjusts which questions to answer), progress to the next stage.

## Stage 2: Expand

1. **Classify each question** as either **on-topic** or **prerequisite**:
   - **On-topic**: The question is directly about the guide's subject matter. It belongs in the guide.
   - **Prerequisite**: The question is about background knowledge the guide assumes. It helps the reader but isn't part of the guide's core narrative.

2. **Answer every question in one pass.** For each `%%?...%%` marker:
   - **On-topic questions** — write content that directly answers the question. Match the tone, depth, and style of the surrounding guide text. Flow naturally into the existing prose — the reader should not be able to tell where expansion happened. Replace the marker entirely with the authored content.
   - **Prerequisite questions** — replace the marker with an aside callout:
     ```markdown
     > [!info] Aside: [Topic]
     > [Explanation of the prerequisite concept]
     ```
     Place the aside near the point where the prerequisite knowledge is first needed.

3. **Remove all answered `%%` markers** from the document. Leave no traces.
4. **Track the session** — append your session ID to `claude-sessions` in every edited file.

Once all markers are expanded, progress to the next stage.

## Stage 3: Review

1. Present the expanded guide to the user for review.
2. Apply any revisions requested — tone adjustments, more detail, less detail, restructuring.
3. Confirm final status with the user.

# Output

- Guide with all `%%?...%%` markers replaced by authored content
- No `%%` markers remaining in the document
- Session tracked on all edited files
