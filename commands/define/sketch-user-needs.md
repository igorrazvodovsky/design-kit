# sketch-user-needs

Extract and document user needs from research insights or existing documentation.

## Input

- Research notes, interview transcripts, or observations (provide file paths or content)
- Existing user stories or requirements (optional)
- [[user-need]] template at `templates/user-need.md`

## Instructions

### 1. Extract Needs from Research

Use **Read** tool to review source material. Look for expressions of what users need to accomplish:

- Listen for goals, not solutions ("I need to see my tasks" not "I want a dashboard")
- Distinguish needs (fundamental requirements) from wants (desired features)
- Look for the "why" behind stated requests
- Identify the outcome users are trying to achieve

### 2. Structure Each Need

For each identified need, use the **Write** tool to create a new `.md` file in `example-1/outputs/needs/`:

**Template structure:**
```yaml
---
ID: [sequential number - check existing with Glob to find next ID]
user type: "[[user-type]]"
as a: [specific role]
who is: [optional qualifier]
I need to: [action or capability]
so that: [ultimate goal/outcome]
category:
theme:
user journey stage: "[[stage]]"
customer journey stage:
acceptance criteria:
---
```

**Key principles:**

- **Filename = "I need to" field** — Use exact text with spaces, lowercase
- **Focus on needs, not wants** — "search for items" not "have a search box"
- **Separate action from outcome** — "I need to" describes action, "so that" describes why
- **Use wiki-links** — Link to `[[user-type]]` and `[[journey-stage]]` for relationships
- **Be specific** — Vague needs are hard to validate or design for

**Process:**
1. Use **Glob** to find existing needs: `Glob: pattern="example-1/outputs/needs/*.md"`
2. Count files to determine next ID
3. Use **Write** to create new file with frontmatter
4. Place in `example-1/outputs/needs/[need description].md`

### 3. Validate Need Quality

Check each need against these criteria before creating:

- [ ] Describes a capability, not a solution?
- [ ] "I need to" and "so that" are at different levels (not duplicates)?
- [ ] Based on research evidence, not assumptions?
- [ ] Specific enough to validate with users?
- [ ] Technology-agnostic (doesn't prescribe implementation)?
- [ ] Testable (could determine if it's met)?

### 4. Identify User Types and Journey Stages

As you document needs:

1. Use **Glob** to check for existing user type notes: `pattern="**/user types/*.md"`
2. Create notes for new types using **Write** if needed
3. Use **Glob** to check for journey stage notes: `pattern="**/journey stages/*.md"`
4. Create stage notes using **Write** if needed
5. Reference types and stages via wiki-links in need frontmatter

### 5. Watch for Patterns

Use **Grep** to identify patterns across needs:

**Find similar outcomes:**
```
Grep: pattern="so that:.*share" path="example-1/outputs/needs" output_mode="content"
```

**Find duplicates:**
```
Grep: pattern="I need to: [specific action]" path="example-1/outputs/needs" output_mode="files_with_matches"
```

**Check coverage by user type:**
```
Grep: pattern="user type:.*\\[\\[user\\]\\]" path="example-1/outputs/needs" output_mode="count"
```

**Identify gaps:**
- Use **Glob** to count needs per journey stage
- Compare counts to identify under-represented stages

### 6. Create Analysis Summary

After creating needs, use **Write** to create a summary file documenting:

- Total needs created
- User types identified
- Journey stages covered
- Patterns noticed
- Potential duplicates to review
- Gaps to address with future research

## Output

- Individual `.md` files in `example-1/outputs/needs/`
- Each file follows [[user-need]] template structure
- Files linked via wiki-links to user types and journey stages
- Summary file: `example-1/outputs/user-needs-extraction-summary.md`

## Common Pitfalls

**❌ Solution specification**
- "I need to have a blue button" → Prescribes solution

**✓ Capability description**
- "I need to quickly access my saved work so that I can resume tasks efficiently"

**❌ Vague outcomes**
- "so that I can use the system" → Too generic

**✓ Specific outcomes**
- "so that I can meet project deadlines" → Clear benefit

**❌ Duplicating action and outcome**
- "I need to: save my work" / "so that: my work is saved" → Circular

**✓ Different levels**
- "I need to: save my work" / "so that: I don't lose progress if interrupted"

## Tool Usage Examples

### Check for existing needs
```
Glob: pattern="example-1/outputs/needs/*.md"
```

### Find next available ID
```
Grep: pattern="^ID:" path="example-1/outputs/needs" output_mode="content"
```
Parse results to find highest number, add 1.

### Check for duplicates before creating
```
Grep: pattern="I need to: accept an invite" path="example-1/outputs/needs" output_mode="files_with_matches"
```

### Create new need file
```
Write:
  file_path="example-1/outputs/needs/accept an invite and land in the correct workspace.md"
  content="---\nID: \"8\"\nuser type: \"[[user]]\"\n..."
```

## Examples

### From Interview Quote

**Input:**
> "When I'm looking at projects, I just want to see the ones I'm actually working on, not everything in the whole system. It's overwhelming."

**Process:**
1. **Glob** to count existing needs → determine next ID (e.g., "23")
2. **Grep** to check for similar needs with "see" and "projects"
3. **Write** to create: `example-1/outputs/needs/see only my assigned projects.md`

**Output file:**
```yaml
---
ID: "23"
user type: "[[team-member]]"
as a: project contributor
who is: working on multiple projects
I need to: see only my assigned projects
so that: I can focus on my work without distraction
user journey stage: "[[daily-use]]"
category:
theme:
---
```

### From Observation

**Input:**
Observed: User repeatedly using browser back button to return to main list after viewing item details.

**Process:**
1. Interpret behavior → identify underlying need
2. **Grep** for similar navigation needs
3. **Write** need file

**Output file:**
```yaml
---
ID: "24"
user type: "[[user]]"
as a: frequent user
who is:
I need to: return to my previous view quickly
so that: I can efficiently browse multiple items
category: navigation
user journey stage: "[[daily-use]]"
---
```

## Related Commands

- [[refine-user-needs]] — After initial extraction, refine and categorize needs
- [[map-journey]] — Identify journey stages where needs occur
- [[sketch-context]] — Understand ecosystem where needs arise

## References

See [[user-needs-writing-guide]], [[user-needs-refinement-process]], and [[user-needs-best-practices]] in `references/` for detailed methodology.
