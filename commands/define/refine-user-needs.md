# refine-user-needs

Organize, categorize, and analyze user needs to uncover patterns, duplicates, and gaps.

## Input

- Collection of user need `.md` files
- [[user-need]] template (for standardization)

## Instructions

### Phase 1: Standardize Structure

Review all existing needs for consistency:

1. **Check format compliance**
   - All files use the [[user-need]] template?
   - Filenames match "I need to" field?
   - Required fields are populated?
   - Wiki-links used for user types and journey stages?

2. **Refine "as a" / "who is" split**
   - Move qualifiers from "as a" to "who is" field
   - Example: "admin managing multiple workspaces" → as a: admin / who is: managing multiple workspaces
   - Standardize user type vocabulary

3. **Verify needs vs wants**
   - Ensure "I need to" focuses on capabilities, not solutions
   - Rewrite any solution specifications as capability needs
   - Example: "have a dashboard" → "view summary of my tasks"

4. **Check outcomes**
   - "So that" should be the ultimate goal, not just restating the need
   - Ensure action and outcome are at different levels
   - Example: Fix "I need to save work / so that work is saved" → "so that I don't lose progress"

### Phase 2: Tag and Categorize

Add metadata to enable analysis:

1. **Assign categories (epics)**
   - Group related needs into 8-12 high-level categories
   - Examples: "Access & Permissions", "Navigation", "Collaboration", "Content Creation"
   - Update `category:` field in each need's frontmatter

2. **Identify themes**
   - Look for conceptual threads across categories
   - Examples: findability, security, efficiency, autonomy
   - Update `theme:` field

3. **Verify journey stage mappings**
   - Ensure all needs link to appropriate `[[journey-stage]]`
   - Create stage notes if missing

4. **Note cross-cutting attributes**
   - Use "who is" field for common qualifiers
   - Examples: "with accessibility needs", "first-time user", "managing multiple workspaces"

### Phase 3: Analyze in Obsidian Bases

Use Bases to uncover insights:

1. **Set up analysis views**

   **View: By Journey Stage**
   - Group by: `user journey stage`
   - Purpose: See distribution across user journey
   - Question: Are some stages under-represented?

   **View: By User Type**
   - Filter by: `user type`
   - Purpose: Understand each user segment
   - Question: Have we captured all user types?

   **View: By Outcome**
   - Sort by: `so that` field
   - Purpose: Find needs with similar outcomes
   - Question: Are there duplicates or related needs?

   **View: By Category**
   - Group by: `category`
   - Purpose: See how needs cluster
   - Question: Are categories balanced or is something missing?

   **View: Unprocessed**
   - Filter: `category` is empty
   - Purpose: Track refinement progress
   - Question: Which needs still need categorization?

2. **Look for patterns**
   - **Duplicates:** Same outcome with different wording
   - **Related needs:** Different actions toward same outcome
   - **Gaps:** User types or stages with few/no needs
   - **Singletons:** Categories with only one need (may need research)
   - **Common outcomes:** Recurring "so that" statements

3. **Count and assess**
   - How many needs per journey stage?
   - How many needs per user type?
   - How many needs per category?
   - What's the ratio of categories to total needs? (Aim for 8-12 categories per 60-80 needs)

### Phase 4: Address Findings

Based on analysis, take action:

1. **Merge duplicates**
   - Combine needs with identical outcomes
   - Keep the clearest wording
   - Archive the redundant file or note both source projects

2. **Split overly broad needs**
   - If one need has multiple distinct outcomes, separate them
   - Create individual files for each specific need

3. **Research gaps**
   - Note journey stages or user types with sparse coverage
   - Plan targeted research to fill gaps
   - Create "research questions" note

4. **Standardize outcomes**
   - When many needs share outcomes, standardize wording
   - Makes filtering and grouping more effective
   - Example: "share with others" vs "make accessible to team" → choose one

5. **Validate singleton categories**
   - Categories with only 1-2 needs may need more research
   - Or may not warrant their own category (recategorize)

## Output

- Standardized need files with complete frontmatter
- Categories and themes assigned
- Obsidian Bases views configured for ongoing analysis
- List of insights:
  - Duplicates merged
  - Gaps identified
  - Patterns noted
  - Research questions for follow-up

## Analysis Questions

Use these to guide your review:

**Coverage:**
- Do we have needs for all key user types?
- Are all journey stages represented?
- Are there obvious missing scenarios?

**Quality:**
- Are needs clearly articulated?
- Can we validate each with users?
- Are outcomes specific and meaningful?

**Patterns:**
- Which outcomes appear most frequently?
- Which journey stages have most needs?
- Which user types have most/least needs?

**Balance:**
- Are categories roughly balanced or heavily skewed?
- Are some stages over/under-represented compared to their importance?
- Do singleton categories represent genuine distinct areas?

## Success Indicators

You've successfully refined when:

- ✓ All needs follow consistent format
- ✓ Duplicates are merged
- ✓ Categories assigned (8-12 categories for your set)
- ✓ Bases views enable easy filtering and analysis
- ✓ Gaps and patterns are documented
- ✓ Team can quickly find relevant needs
- ✓ Stakeholders understand scope via category summaries

## Common Refinement Scenarios

### Scenario: Duplicate with Different Wording

**Need A:** `find relevant information quickly.md`
- I need to: find relevant information quickly
- so that: I can complete my tasks efficiently

**Need B:** `search for what I'm looking for.md`
- I need to: search for what I'm looking for
- so that: I don't waste time hunting

**Action:** These serve the same outcome (efficiency). Merge into one need:
- I need to: find what I'm looking for quickly
- so that: I can complete tasks without wasting time
- Archive one file, note both sources

### Scenario: Vague Outcome

**Original:**
- I need to: manage team permissions
- so that: permissions are managed

**Problem:** Circular — outcome just restates the need

**Refined:**
- I need to: manage team permissions
- so that: sensitive data is only accessible to authorized members

### Scenario: Gap Identified

**Observation:** 15 needs for "registration" stage, only 2 for "offboarding"

**Actions:**
- Create note: "Research Question: Offboarding Experience"
- Plan research focused on account closure and data export scenarios
- May be appropriate gap (simpler flow) or missing needs

### Scenario: Outcome Proliferation

**Finding:** 30 needs with 28 different "so that" statements

**Problem:** Too much variation prevents useful grouping

**Action:** Review outcomes for similarity and standardize:
- "I can share with colleagues", "Others can see my work", "Team has access"
- All become: "I can collaborate with my team"

## Ongoing Maintenance

Refinement isn't one-time:

- **Project start:** Review relevant needs, note gaps
- **Project end:** Add new needs, merge duplicates, update categories
- **Quarterly:** Full review of consistency and patterns
- **As needed:** When needs grow significantly or new user types emerge

## Related Commands

- [[sketch-user-needs]] — Initial extraction of needs from research
- [[map-journey]] — Identify stages for journey stage mapping
- [[plan-exploration-and-sensemaking]] — Plan research to address gaps

## References

See [[user-needs-refinement-process]] and [[user-needs-best-practices]] in `references/` for detailed methodology and examples.
