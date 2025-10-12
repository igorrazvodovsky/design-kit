# User Needs Best Practices

Practical guidance for managing user needs as a living practice, including team collaboration, timing, and common scenarios.

## Core Principles

### 1. User Needs Are a Living Document

User needs repositories should evolve continuously:

- Review at the start of every project
- Update at the end of every project
- Refine as understanding deepens
- Retire needs that become obsolete
- Split needs that prove too broad
- Merge needs revealed as duplicates

**Anti-pattern:** Creating a needs repository once and never touching it again.

### 2. Team Ownership Over Individual Control

While user researchers often do the bulk of refinement work, the team should be involved in:

- Reviewing groupings and categories
- Validating outcomes
- Identifying gaps
- Prioritizing needs
- Defining acceptance criteria

**Anti-pattern:** User researcher working in isolation, then presenting finished categorization to team.

### 3. This Is A Way, Not The Way

The methodology described here is one effective approach, not a rigid standard. Adapt it to:

- Your organization's scale
- Your team's workflow
- Your tool preferences
- Your project types

**Anti-pattern:** Forcing a method that doesn't fit your context.

## When to Refine User Needs

### Initial Repository Creation

**When:** First time building a user needs repository, or when consolidating needs from multiple legacy projects.

**Scope:** Often 100-1000+ needs to review.

**Effort:** Substantial—plan for significant dedicated time.

**Approach:**
1. Gather all existing user stories/needs
2. Initial pass to assess quality and consistency
3. Bulk standardization of format
4. Categorization and tagging
5. Analysis for insights and gaps

**Tip:** This is satisfying work but time-consuming. Block dedicated time rather than trying to fit it around other work.

### Project Start

**When:** Beginning a new project or sprint.

**Purpose:**
- Select which existing needs apply to this project
- Identify any obvious gaps in coverage
- Brief team on relevant needs
- Plan research to address gaps

**Effort:** Light—filtering and reviewing existing needs.

**Approach:**
1. Filter needs by relevant user types
2. Filter by relevant journey stages
3. Review for project relevance
4. Flag needs this project will address
5. Note any apparent gaps for research

### Project End

**When:** Completing a research phase or project.

**Purpose:**
- Add new needs discovered
- Update existing needs that research refined
- Remove duplicates
- Validate categorization

**Effort:** Medium—integrating new findings.

**Approach:**
1. Extract new needs from research
2. Check against existing needs for duplicates
3. Standardize format
4. Categorize and tag
5. Look for patterns or gaps
6. Consider whether new research invalidates old needs

**Critical timing:** Do this _toward_ the end with enough runway to address gaps, not _at_ the very end when it's too late to do follow-up research.

### Regular Review Cycles

**When:** Quarterly or semi-annually, independent of specific projects.

**Purpose:**
- Maintain consistency as repository grows
- Identify emerging patterns across projects
- Consolidate similar needs from different projects
- Update taxonomy as understanding evolves

**Effort:** Medium to substantial, depending on activity.

**Approach:**
1. Review needs added since last review
2. Check for drift in terminology or categorization
3. Update dropdowns if new patterns have emerged
4. Merge duplicates
5. Generate cross-project insights

## Team Collaboration

### Roles and Responsibilities

#### User Researcher (Lead)
- Owns the refinement process
- Does bulk of initial standardization
- Maintains consistency in repository
- Facilitates team reviews
- Synthesizes insights

**Time commitment:** Substantial during refinement phases.

#### Full Team (Participants)
- Reviews proposed groupings
- Validates outcomes and categorization
- Identifies gaps from their perspective
- Contributes to acceptance criteria
- Challenges assumptions

**Time commitment:** Focused sessions for input and validation.

#### Stakeholders (Recipients)
- Receive summarized findings (epics, not all needs)
- Provide strategic input on priorities
- Validate that needs align with business goals

**Time commitment:** Minimal—high-level presentations.

### Collaboration Workflow

**Phase 1: Solo Refinement (User Researcher)**
- Standardize format
- Initial categorization
- Identify obvious duplicates
- Prepare for team review

**Phase 2: Team Review (Full Team)**
- Present proposed groupings
- Discuss outcomes and themes
- Validate categorization
- Identify gaps as a group
- Assign priorities

**Phase 3: Refinement (User Researcher)**
- Incorporate team feedback
- Finalize categorization
- Complete analysis
- Generate insights

**Phase 4: Presentation (Full Team + Stakeholders)**
- Share key findings
- Present epics and themes
- Highlight gaps
- Propose research priorities

### Review Session Tips

**Prepare materials:**
- Summary of new/changed needs
- Proposed groupings in visual format
- Specific questions for team input
- Examples of unclear categorizations

**Structure the session:**
1. Context: Why we're reviewing (5 min)
2. Overview: What's changed (10 min)
3. Discussion: Groupings and categories (30 min)
4. Gaps: What are we missing? (15 min)
5. Next steps: Actions and timeline (10 min)

**Facilitate effectively:**
- Focus on areas where you're uncertain
- Don't ask team to rubber-stamp your work
- Encourage constructive challenge
- Document decisions and rationale
- Park tangent discussions for later

## Common Scenarios

### Scenario: Duplicate Needs from Different Projects

**Situation:** Two projects identified very similar needs with different wording.

**Approach:**
1. Examine both in detail—are they truly identical?
2. Look at the "So that" outcome—if it's the same, likely duplicates
3. Check if one is more specific than the other
4. If duplicates, merge and note both source projects
5. If one is more specific, make it a child or variation

**Example:**
- Need A: "I need to quickly add research to the library"
- Need B: "I need to easily add research without complex steps"
- **Resolution:** Merge to "I need to quickly and easily add research" noting both projects

### Scenario: Need vs Want

**Situation:** A user need sounds like a feature request.

**Original:** "As a user researcher, I want a search box on every page"

**Approach:**
1. Identify the underlying need behind the want
2. Ask: What would that feature enable?
3. Reframe as capability, not solution

**Refined:** "As a user researcher, I need to find relevant research from anywhere in the system so that I can quickly locate information"

### Scenario: Vague Outcome

**Situation:** The "So that" doesn't articulate a clear goal.

**Original:** "As a user, I need to login so that I can use the system"

**Problem:** "Use the system" is too vague.

**Approach:**
1. Ask: What specifically does system access enable?
2. Look at the user type for context
3. Consider what's different before vs after login

**Refined:** "As a user researcher who is authorized, I need to login so that I can access and contribute to the research repository"

### Scenario: Multiple Outcomes

**Situation:** One need seems to have multiple distinct outcomes.

**Original:** "As a user, I need to export data so that I can analyze it in other tools and share it with external stakeholders"

**Problem:** Two different outcomes bundled together.

**Approach:**
1. Split into separate needs with distinct outcomes
2. Keep "I need to" the same if the action is identical
3. Distinguish via different "So that" statements

**Refined:**
- Need 1: "...export data so that I can analyze it in specialized tools"
- Need 2: "...export data so that I can share findings with external stakeholders"

### Scenario: Gap in Journey Coverage

**Situation:** Analysis reveals 15 needs for "Creation" but only 2 for "Maintenance."

**Interpretation questions:**
- Is maintenance genuinely less complex?
- Did research focus disproportionately on creation?
- Are maintenance needs bundled into creation needs?
- Is maintenance a separate journey we didn't map?

**Response:**
1. Review with team to validate the gap
2. If genuine gap, plan targeted research
3. If needs are bundled, separate them
4. If journey mapping is incomplete, revisit it

### Scenario: Singleton Category

**Situation:** An epic/category has only one need in it.

**Possible interpretations:**
- This is a genuinely distinct area (keep it)
- This is under-researched (do more research)
- This need doesn't warrant its own category (recategorize)
- The need is too specific and should be split (refactor)

**Decision factors:**
- Strategic importance of the area
- Likelihood of finding more needs in this category
- Whether it makes sense standalone in presentations

### Scenario: Outcome Proliferation

**Situation:** You have 50 needs with 40 different outcomes.

**Problem:** Too much variation prevents useful grouping.

**Approach:**
1. Review outcomes looking for similarity
2. Identify higher-level outcome categories
3. Standardize wording where goals are similar
4. Create a standard dropdown list

**Example outcomes that should merge:**
- "I can easily share research"
- "Others can see my research"
- "Research is accessible to the team"

**Standardized:** "I can share research with others"

## Maintenance Strategies

### Preventing Drift

**Problem:** Over time, new needs get added without consistent categorization.

**Solutions:**
- Use dropdowns wherever possible
- Document categorization rationale
- Include examples for each category
- Regular review cycles to catch drift
- Brief new team members on standards

### Managing Growth

**Problem:** Repository grows to hundreds or thousands of needs.

**Solutions:**
- Use filtering and views extensively
- Create project-specific subsets
- Sunset outdated needs (archive, don't delete)
- Consider splitting very large repositories by product area
- Maintain a "top 20" needs summary

### Tool Selection

**Considerations:**
- **Scale:** Will you have dozens or thousands of needs?
- **Collaboration:** How many people need access?
- **Analysis:** What grouping/filtering capabilities do you need?
- **Integration:** Does it need to connect to other tools?
- **Longevity:** Can you export if you switch tools?

**Options:**
- **Spreadsheet:** Simple, universal, limited grouping
- **Airtable:** Visual, collaborative, good filtering
- **Coda:** Powerful formulas, flexible views
- **Specialized tools:** Dovetail, Aurelius, UserQ
- **Custom database:** Maximum flexibility, requires maintenance

### Versioning

**Approaches:**
- **Living document:** Single repository that evolves (recommended for most)
- **Snapshots:** Freeze needs at project end, start fresh for next
- **Branching:** Main repository plus project-specific forks

**Recommendation:** Treat as living document with light versioning:
- Track date added and source project
- Flag needs when they change substantially
- Archive superseded needs rather than deleting
- Maintain changelog for major taxonomy changes

## Quality Indicators

### Signs Your Needs Are Well-Managed

✓ New team members can quickly find relevant needs
✓ Duplicates are caught before they're added
✓ Stakeholders grasp scope via epic summaries
✓ Gaps are obvious from journey/user type views
✓ Categorization decisions feel natural, not forced
✓ Repository is actively used in project planning
✓ Team references needs by ID in discussions
✓ Research validates and refines existing needs

### Signs You Need to Refactor

✗ People complain they can't find anything
✗ Same need appears multiple times with different wording
✗ Categorization feels arbitrary or contested
✗ Dropdowns have 30+ options
✗ Nobody uses the repository in actual work
✗ Major inconsistency between old and new needs
✗ Research keeps finding "new" needs already documented

## Getting Started: Minimum Viable Refinement

If you're starting from scratch or have limited time:

**Minimal structure:**
1. Standardize to As a / I need to / So that (skip "Who is" initially)
2. Create 3-5 user type categories
3. Identify 5-8 broad epics
4. Map to basic journey (Before/During/After or similar)

**Skip for now:**
- Detailed acceptance criteria
- Success/failure impacts
- Detailed theme taxonomy
- Cross-project tracking

**Iterate later:**
- Add complexity as repository proves useful
- Let patterns emerge before over-structuring
- Start with free text, convert to dropdowns when patterns stabilize

## Advanced Practices

### Acceptance Criteria as Sub-Needs

For complex needs, acceptance criteria can be detailed enough to function as sub-needs or implementation requirements.

**Example:**
- **Parent need:** "I need to securely access the system"
- **Acceptance criteria / sub-needs:**
  - Can authenticate via institutional login
  - Can use multi-factor authentication
  - Can recover forgotten password
  - Can see active sessions
  - Can revoke access from lost device

### Need Relationships and Dependencies

Track when needs relate to each other:
- **Prerequisites:** Need A must be met before Need B makes sense
- **Alternatives:** Needs that address the same outcome differently
- **Composites:** Need that combines several smaller needs
- **Conflicts:** Needs that may work against each other

### Impact Scoring

Quantify needs to aid prioritization:
- User impact (how many users affected)
- Frequency (how often needed)
- Severity (what happens if unmet)
- Alignment (strategic importance)

### Linking to Evidence

Connect each need to:
- Research sessions where it emerged
- Direct quotes from users
- Observational evidence
- Quantitative data supporting it

## Common Mistakes to Avoid

1. **Perfection paralysis:** Don't let pursuit of perfect categorization prevent using the repository
2. **Over-categorization:** Too many categories makes it harder to see patterns
3. **Solo work:** Team input is essential for accurate understanding
4. **One-time effort:** Needs repositories require ongoing maintenance
5. **Missing the forest:** Don't get so focused on individual needs you miss overall patterns
6. **Analysis without action:** Insights are only valuable if they inform decisions
7. **Rigid adherence:** If the structure isn't working, change it
8. **Ignoring duplicates:** Similar needs across projects are data, not errors

## Getting Buy-In

### For Teams

**Emphasize:**
- Reduces repeated research on same questions
- Makes research insights accessible when needed
- Provides structure for project planning
- Creates shared understanding of users

**Show:**
- Quick demos of finding relevant needs
- Examples of gaps identified through analysis
- How epics simplify scope communication

### For Stakeholders

**Emphasize:**
- Strategic view of user needs across products
- Evidence-based prioritization
- Visibility into research coverage
- Efficient use of research investment

**Show:**
- Epic-level summaries (not detailed needs)
- Gap analysis highlighting risks
- How needs inform roadmap decisions

### For Leadership

**Emphasize:**
- Organizational knowledge retention
- Consistency across teams
- Evidence-based decision making
- ROI on research investment

**Show:**
- Cross-project insights
- Coverage of strategic priorities
- Risk areas with gaps in understanding

## Measuring Success

### Usage Metrics
- How often is repository accessed?
- How many team members actively use it?
- Are needs referenced in project planning?
- Do new projects start by reviewing existing needs?

### Quality Metrics
- How often are duplicates caught?
- How quickly can relevant needs be found?
- How much does categorization change (stability)?
- Team confidence in using repository?

### Impact Metrics
- Does research build on previous findings?
- Are fewer redundant studies conducted?
- Do products address documented needs?
- Can team articulate user needs confidently?

## Summary: The Refinement Mindset

User needs refinement is not a one-time project but an ongoing practice:

- **Start simple:** Basic structure is better than no structure
- **Iterate:** Let sophistication evolve with usage
- **Collaborate:** Team involvement ensures accuracy and buy-in
- **Apply insights:** Analysis is only valuable if it informs action
- **Stay flexible:** Adapt the approach as you learn what works
- **Maintain:** Regular light maintenance prevents major overhauls

The goal is not a perfect taxonomy but a _useful_ one that helps teams understand and serve users better.

## References

Based on Jonathan Richardson's practical experience refining several hundred user needs and establishing user research repositories. Source: "User needs refinement — why and how to do it" (2020)
