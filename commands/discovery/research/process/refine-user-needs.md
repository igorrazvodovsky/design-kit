Organise, categorise, and analyse user needs to uncover patterns, duplicates, and gaps.

## Input

- Collection of user need `.md` files
- User need template at `templates/user-need.md` for standardisation

## Instructions

### Phase 1: Standardize Structure

1. **Check format compliance**
   For each file:
   - Check frontmatter structure matches template
   - Verify required fields are populated
   - Verify filename matches "I need to" field

2. **Refine "as a" / "who is" split**
   - Move qualifiers from "as a" to "who is" field
   - Example: "admin managing multiple workspaces" → as a: admin / who is: managing multiple workspaces

3. **Verify needs vs wants**
   - Look for solution-oriented language
   - Rewrite as capability needs

### Phase 2: Tag and Categorise

1. **Assign categories (epics)**
   - Group needs by similar topics (use Grep to find patterns)
   - Identify high-level categories
   - Add `category:` field to each need

2. **Identify themes**
   - Find conceptual patterns
   - Add `theme:` field where appropriate

3. **Verify journey stage mappings**
   - Check for journey stage notes
   - Ensure all needs have `user journey stage:` field
   - Add missing stage links

### Phase 3: Analyse

1. Group by Journey Stage: Repeat for each stage to see distribution.
2. Group by User Type: Compare counts across user types.
3. Find Similar Outcomes: Identify needs with similar goals.
4. Find Needs by Category: Count needs per category.
5. Identify Duplicates: Look for variations expressing same need.

### Phase 4: Address Findings

1. **Merge duplicates**
   - Compare duplicate needs
   - Update one with best wording
   - Document both source IDs in comments
   - Delete redundant file

2. **Split overly broad needs**
   - Identify needs with multiple outcomes
   - Create separate files for each specific need
   - Update original or delete it

3. **Document gaps**
   - Create `example-1/outputs/research-questions.md`
   - List journey stages or user types needing research

1. **Standardise outcomes**
   - Find similar outcomes
   - Standardise wording across related needs
   - Example: "share with others" / "make accessible to team" → choose one consistently

5. **Validate singleton categories**
   - Count needs per category
   - For categories with 1-2 needs: research more or recategorise
   - Update category field as needed

### Phase 5: Create Analysis Report

Document findings in `example-1/outputs/needs-analysis.md`:

```markdown
# User Needs Analysis

## Summary Statistics

- Total needs: [count from Glob]
- User types: [count unique from Grep]
- Journey stages: [count unique from Grep]
- Categories: [list with counts]

## Distribution Analysis

### By Journey Stage
- Registration: X needs
- Onboarding: Y needs
- Daily use: Z needs
[etc.]

### By User Type
- User: X needs
- Admin: Y needs
[etc.]

## Patterns Identified

### Common Outcomes
[List frequent "so that" statements]

### Duplicates Merged
[List which needs were combined]

### Gaps Identified
[List under-represented areas]

## Recommendations

- Research needed for: [stages/types with few needs]
- Categories to split: [overly broad categories]
- Categories to merge: [singleton categories]
```

## Output

- Standardized need files with complete frontmatter
- Categories and themes assigned across all needs
- Analysis report: `example-1/outputs/needs-analysis.md`
- Research questions document: `example-1/outputs/research-questions.md`
- Archived duplicates: `example-1/outputs/needs/archived/`

## Common Refinement Scenarios

### Scenario: Outcome Proliferation

**Situation:** 50 needs with 40 different "so that" outcomes

**Problem:** Too much variation prevents useful grouping

**Process:**
1. Extract all outcomes: `Grep: pattern="so that:" output_mode="content"`
2. Identify similar goals with different wording
3. Decide on standard wording for each outcome category
4. Standardize across files

**Example:**
Outcomes to merge: "I can easily share research" / "Others can see my research" / "Research is accessible to the team"

Standard: "I can share research with others"

```
Edit:
  file_path="example-1/outputs/needs/make research visible.md"
  old_string="so that: Others can see my research"
  new_string="so that: I can share research with others"

Edit:
  file_path="example-1/outputs/needs/publish findings.md"
  old_string="so that: Research is accessible to the team"
  new_string="so that: I can share research with others"
```

### Scenario: Need vs Want (Solution Specification)

**Detection:**
```
Grep: pattern="I need to:.*button|dashboard|interface|screen|page" path="example-1/outputs/needs" output_mode="content" -n
```

**Example found:**
```
I need to: have a dashboard showing all my tasks
so that: I can see what to work on
```

**Problem:** Prescribes solution ("dashboard") instead of capability

**Process:**
```
Read: file_path="example-1/outputs/needs/have a dashboard showing all my tasks.md"

Edit:
  file_path="example-1/outputs/needs/have a dashboard showing all my tasks.md"
  old_string="I need to: have a dashboard showing all my tasks"
  new_string="I need to: see all my assigned tasks at a glance"

# Also update filename
Bash: command="mv 'example-1/outputs/needs/have a dashboard showing all my tasks.md' 'example-1/outputs/needs/see all my assigned tasks at a glance.md'"
```

### Scenario: as a / who is Split

**Detection:**
```
Grep: pattern="as a:.*managing|with|who" path="example-1/outputs/needs" output_mode="content" -n
```

**Example found:**
```yaml
as a: admin managing multiple workspaces
who is:
```

**Problem:** Qualifier in "as a" field should be in "who is"

**Process:**
```
Edit:
  file_path="example-1/outputs/needs/[need].md"
  old_string="as a: admin managing multiple workspaces\nwho is:"
  new_string="as a: admin\nwho is: managing multiple workspaces"
```

## Success Indicators

- ✓ Duplicates merged (verified via similarity searches)
- ✓ Categories assigned (no empty category fields)
- ✓ Analysis report created
- ✓ Gaps documented (research questions file exists)

## Related Commands

- [sketch-user-needs](commands/discovery/research/process/sketch-user-needs.md) — Initial extraction of needs from research
- [map-journey](commands/discovery/explore/map-journey.md) — Identify stages for journey stage mapping

## References

See [user-needs-refinement-process](references/user-needs-refinement-process.md) and [user-needs-best-practices](references/user-needs-best-practices.md) for detailed methodology and examples.
