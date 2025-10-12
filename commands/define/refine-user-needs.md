# refine-user-needs

Organize, categorize, and analyze user needs to uncover patterns, duplicates, and gaps.

## Input

- Collection of user need `.md` files
- User need template at `templates/user-need.md` for standardization

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

### Phase 2: Tag and Categorize

1. **Assign categories (epics)**
   - Group needs by similar topics (use Grep to find patterns)
   - Identify 8-12 high-level categories
   - Add `category:` field to each need

2. **Identify themes**
   - Find conceptual patterns:
     ```
     Grep: pattern="so that:.*quick|fast|efficient" path="example-1/outputs/needs" output_mode="files_with_matches"
     ```
   - Add `theme:` field where appropriate

3. **Verify journey stage mappings**
   - Check for journey stage notes
   - Ensure all needs have `user journey stage:` field
   - Add missing stage links

### Phase 3: Analyze with Grep

**1. Group by Journey Stage**
```
Grep: pattern='user journey stage: "\[\[registration\]\]"' path="example-1/outputs/needs" output_mode="count"
```
Repeat for each stage to see distribution.

**2. Group by User Type**
```
Grep: pattern='user type: "\[\[user\]\]"' path="example-1/outputs/needs" output_mode="count"
```
Compare counts across user types.

**3. Find Similar Outcomes**
```
Grep: pattern="so that:.*share.*" path="example-1/outputs/needs" output_mode="content" -n
```
Identify needs with similar goals.

**4. Find Needs by Category**
```
Grep: pattern="category: access" path="example-1/outputs/needs" output_mode="files_with_matches"
```
Count needs per category.

**5. Find Unprocessed Needs**
```
Grep: pattern="^category:$" path="example-1/outputs/needs" output_mode="files_with_matches"
```
Identify needs missing categorization.

**6. Identify Duplicates**
```
Grep: pattern="I need to: find|search|locate" path="example-1/outputs/needs" output_mode="content" -n
```
Look for variations expressing same need.

### Phase 4: Address Findings

1. **Merge duplicates**
   - Compare duplicate needs
   - Update one with best wording
   - Document both source IDs in comments
   - Move redundant file to archive: `mv old.md archived/`

2. **Split overly broad needs**
   - Identify needs with multiple outcomes
   - Create separate files for each specific need
   - Update original or archive it

3. **Document gaps**
   - Create `example-1/outputs/research-questions.md`
   - List journey stages or user types needing research

4. **Standardize outcomes**
   - Find similar outcomes (Grep patterns)
   - Standardize wording across related needs
   - Example: "share with others" / "make accessible to team" → choose one consistently

5. **Validate singleton categories**
   - Count needs per category
   - For categories with 1-2 needs: research more or recategorize
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

## Tool Usage Examples

### Find all needs for a journey stage
```
Grep: pattern='user journey stage: "\[\[registration\]\]"' path="example-1/outputs/needs" output_mode="files_with_matches"
```

### Count needs per category
```
Grep: pattern="category: navigation" path="example-1/outputs/needs" output_mode="count"
```

### Find needs without categories
```
Grep: pattern="^category:$|^category:\s*$" path="example-1/outputs/needs" output_mode="files_with_matches"
```

### Find potential duplicates
```
Grep: pattern="I need to:.*save|store|persist" path="example-1/outputs/needs" output_mode="content" -n
```

### Update category for a need
```
Edit:
  file_path="example-1/outputs/needs/see my assigned work.md"
  old_string="category:"
  new_string="category: navigation"
```

### Create analysis report
```
Write:
  file_path="example-1/outputs/needs-analysis.md"
  content="# User Needs Analysis\n\n..."
```

## Analysis Questions

Use **Grep** to answer:

**Coverage:**
- Do we have needs for all key user types?
  ```
  Grep: pattern="user type:" path="example-1/outputs/needs" output_mode="content" | unique count
  ```

- Are all journey stages represented?
  ```
  Grep: pattern="user journey stage:" path="example-1/outputs/needs" output_mode="content" | unique count
  ```

**Quality:**
- How many needs lack categories?
  ```
  Grep: pattern="^category:$" path="example-1/outputs/needs" output_mode="count"
  ```

**Patterns:**
- Which outcomes appear most frequently?
  ```
  Grep: pattern="so that:" path="example-1/outputs/needs" output_mode="content"
  ```
  Parse and count frequency.

**Balance:**
- Which journey stage has most needs?
  Compare counts from stage-by-stage Grep queries.

## Common Refinement Scenarios

### Scenario: Duplicate with Different Wording

**Process:**
1. Find similar needs: `Grep: pattern="I need to:.*find|search" output_mode="content"`
2. Compare full needs
3. If same outcome, update one need with best wording
4. Archive duplicate: `mv duplicate.md archived/`

### Scenario: Vague Outcome

**Process:**
1. Find circular outcomes: `Grep: pattern="so that:.*manage" output_mode="content"`
2. Review each flagged need
3. Replace with specific outcome

**Example:**
```
Edit:
  file_path="example-1/outputs/needs/manage team permissions.md"
  old_string="so that: permissions are managed"
  new_string="so that: sensitive data is only accessible to authorized members"
```

### Scenario: Gap Identified

**Process:**
1. Count needs per stage (Grep)
2. Identify stages with few needs
3. Document gap:

```
Write:
  file_path="example-1/outputs/research-questions.md"
  content="# Research Questions\n\n## Offboarding Experience\n\nOnly 2 needs identified for offboarding stage vs 15 for registration.\n\nInvestigate:\n- Account closure process\n- Data export needs\n- Transition planning\n"
```

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

### Scenario: Multiple Outcomes

**Situation:** One need has multiple distinct outcomes bundled together

**Original need:**
```yaml
I need to: export data
so that: I can analyze it in other tools and share it with external stakeholders
```

**Problem:** Two different outcomes in one need

**Process:**
1. Identify needs with "and" in outcome field
2. Determine if outcomes are truly distinct
3. Create separate needs for each outcome
4. Archive or update original

**Tool sequence:**
```
Grep: pattern="so that:.*and.*" path="example-1/outputs/needs" output_mode="files_with_matches"

Read: file_path="example-1/outputs/needs/export data.md"

Write:
  file_path="example-1/outputs/needs/export data for analysis.md"
  content="---\nID: \"45\"\n...I need to: export data\nso that: I can analyze it in specialized tools\n---"

Write:
  file_path="example-1/outputs/needs/export data for sharing.md"
  content="---\nID: \"46\"\n...I need to: export data\nso that: I can share findings with external stakeholders\n---"

Bash: command="mv 'example-1/outputs/needs/export data.md' 'example-1/outputs/needs/archived/'"
```

### Scenario: Singleton Category

**Situation:** Category has only 1-2 needs

**Detection:**
```
Grep: pattern="category: offboarding" path="example-1/outputs/needs" output_mode="count"
```

**Possible actions:**

**If under-researched:**
```
Write:
  file_path="example-1/outputs/research-questions.md"
  content="## Category: Offboarding\n\nOnly 1 need found. Research questions:\n- What happens when users leave?\n- Data export needs?\n- Account cleanup?\n"
```

**If should recategorize:**
```
Edit:
  file_path="example-1/outputs/needs/close account cleanly.md"
  old_string="category: offboarding"
  new_string="category: account management"
```

**If genuinely distinct:**
Keep as-is, document rationale in analysis report

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

- ✓ All needs have complete frontmatter (no empty required fields)
- ✓ Duplicates merged (verified via similarity searches)
- ✓ Categories assigned (no empty category fields)
- ✓ Analysis report created
- ✓ Gaps documented (research questions file exists)

## Related Commands

- [[sketch-user-needs]] — Initial extraction of needs from research
- [[map-journey]] — Identify stages for journey stage mapping

## References

See [[user-needs-refinement-process]] and [[user-needs-best-practices]] in `references/` for detailed methodology and examples.
