Extract and document user needs from research insights or existing documentation.

## Input

- Research notes, interview transcripts, or observations (provide file paths or content)
- Existing user stories or requirements (optional)
- Template at `templates/user-need.md`

## Instructions

### 1. Extract Needs from Research

Review source material. Look for expressions of what users need to accomplish:

- Listen for goals, not solutions ("I need to see my tasks" not "I want a dashboard")
- Distinguish needs from wants
- Look for the "why" behind stated requests
- Identify the outcome users are trying to achieve
- Think in solution/tech-agnostic terms

### 2. Structure Each Need

For each identified need, use the **Write** tool to create a new `.md` file in `example-1/outputs/needs/`:

**Template structure from `templates/user-need.md`:**
```yaml
---
ID: [ID]
user type: [high-level types of user]
as a: [specific user type]
who is: [cross-cutting attribute that matters]
I need to: [the need; not a want or solution]
so that: [the goal/outcome the need enables]
category: [(optional) practical bucket a need belongs to]
theme: [(optional) conceptual thread, e.g. findability]
user journey stage: [user journey stage]
customer journey stage: [(optional) customer journey stage]
---
```

**Field-by-field guide:**

**ID:**
- Sequential number starting from 1
- Use **Glob** to count existing: `pattern="example-1/outputs/needs/*.md"`

**user type:**
- High-level user category (for grouping)
- Use wiki-link format: `"[[user]]"`, `"[[admin]]"`, `"[[team-member]]"`
- Check existing types with **Grep**: `pattern="user type:" output_mode="content"`
- Be consistent - reuse existing types when possible

**as a:**
- Specific role or job description (plain text)
- Examples: `teammate`, `project contributor`, `frequent user`, `admin`
- More specific than user type
- Keep limited to 5-10 distinct roles

**who is:**
- Optional cross-cutting qualifier (plain text)
- Use when context matters: `invited by an admin`, `managing multiple workspaces`, `with accessibility needs`
- Leave blank if not needed
- Enables finding all needs across types with same qualifier

**I need to:**
- The action or capability (plain text)
- **This becomes the filename** - use exact text, lowercase, with spaces
- Focus on capability, NOT solution
- Examples:
  - ✓ `search for relevant items`
  - ✗ `have a search box with filters`
- Be specific and action-oriented
- Avoid implementation details

**so that:**
- The ultimate goal or benefit (plain text)
- Must be DIFFERENT level than "I need to"
- Examples:
  - ✓ Need: `save my work` / Outcome: `I don't lose progress if interrupted`
  - ✗ Need: `save my work` / Outcome: `my work is saved` (circular)
- Focus on user's goal, not system behavior
- Examples:
  - ✓ `I can meet project deadlines`
  - ✗ `the system stores my data`

**category:**
- Optional during initial extraction
- Will be filled during refinement
- High-level grouping: `navigation`, `access`, `collaboration`
- Leave blank initially

**theme:**
- Optional during initial extraction
- Conceptual thread: `findability`, `efficiency`, `security`
- Leave blank initially

**user journey stage:**
- Where in journey this need occurs
- Use wiki-link: `"[[registration]]"`, `"[[daily-use]]"`, `"[[offboarding]]"`
- Check existing stages with **Grep**: `pattern="user journey stage:" output_mode="content"`

**customer journey stage:**
- Optional alternative perspective
- Leave blank if not tracking separately

**Process:**
1. Use **Glob** to find existing needs: `pattern="example-1/outputs/needs/*.md"`
2. Count files to determine next ID
3. Use **Grep** to check for existing user types and journey stages
4. Use **Write** to create file: `file_path="example-1/outputs/needs/[I need to text].md"`

**Common need patterns with templates:**

**Discovery/Learning:**
```yaml
---
ID: "[next]"
user type: "[[user]]"
as a: [role]
who is: unfamiliar with the system
I need to: understand what I can accomplish
so that: I can determine if this meets my needs
user journey stage: "[[discovery]]"
---
```

**Access/Permission:**
```yaml
---
ID: "[next]"
user type: "[[user]]"
as a: [role]
who is: authorized to access
I need to: prove my identity securely
so that: I can access protected features
user journey stage: "[[registration]]"
---
```

**Task Completion:**
```yaml
---
ID: "[next]"
user type: "[[user]]"
as a: [role]
who is:
I need to: [perform specific action]
so that: I can accomplish [specific goal]
user journey stage: "[[daily-use]]"
---
```

**Efficiency:**
```yaml
---
ID: "[next]"
user type: "[[user]]"
as a: frequent user
who is:
I need to: [do something] quickly
so that: I can complete work efficiently
user journey stage: "[[daily-use]]"
---
```

**Collaboration:**
```yaml
---
ID: "[next]"
user type: "[[team-member]]"
as a: [role]
who is: working with others
I need to: [share/coordinate/communicate]
so that: my team can work together effectively
user journey stage: "[[collaboration]]"
---
```

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
5. Reference types and stages in need frontmatter

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
- Each file follows [user-need](templates/user-need.md) template structure
- Files linked to user types and journey stages
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

- [refine-user-needs](commands/discovery/explore/refine-user-needs.md) — After initial extraction, refine and categorize needs
- [map-journey](commands/discovery/explore/map-journey.md) — Identify journey stages where needs occur
- [sketch-context](commands/define/sketch-context.md) — Understand ecosystem where needs arise

## References

See [user-needs-writing-guide](references/user-needs-writing-guide.md), [user-needs-refinement-process](references/user-needs-refinement-process.md), and [user-needs-best-practices](references/user-needs-best-practices.md) for detailed methodology.
