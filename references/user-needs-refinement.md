# User Needs Refinement

A systematic approach to organizing, categorizing, and analyzing user needs to uncover insights and gaps.

## Why Refine User Needs?

Refinement transforms a collection of user needs into a structured knowledge base that:

- Reveals patterns and themes across research
- Identifies duplicates and gaps
- Makes needs easier to search, filter, and group
- Enables deeper analysis and insight discovery
- Creates consistency across projects and teams
- Facilitates stakeholder communication

## The Three-Part Refinement Process

### Part 1: Standardize the Structure

Focus on making all needs follow the consistent format:
**As a / Who is / I need to / So that**

**Tasks:**
1. Split combined "As a" fields into "As a" and "Who is" where appropriate
2. Ensure "I need to" focuses on needs, not wants
3. Verify "So that" articulates the ultimate goal, not just restating the need
4. Remove obvious non-needs (feature requests, implementation details)
5. Eliminate or merge duplicates

**Outcome:** All needs follow a consistent structure that makes them comparable and analyzable.

### Part 2: Tag and Categorize

Add metadata to enable grouping, filtering, and analysis.

**Key activities:**
1. Assign standardized user types
2. Create category groupings (epics)
3. Map needs to journey stages
4. Identify themes
5. Link to source projects/research

**Outcome:** Needs are enriched with metadata that enables multi-dimensional analysis.

### Part 3: Review for Insights

Analyze the structured, tagged needs to discover patterns and gaps.

**Analysis approaches:**
1. Group by outcome to find similar needs
2. Group by journey stage to identify coverage gaps
3. Group by user type to understand different perspectives
4. Count needs per category to spot imbalances
5. Look for orphaned or singleton categories

**Outcome:** Actionable insights about user needs coverage, gaps, and priorities.

## Database Structure

### Essential Fields

#### Unique ID
- Auto-generated identifier
- Enables consistent references even if the need text changes
- Useful when sharing needs across teams

#### User Type (dropdown)
High-level categorization of users:
- User researcher
- Team member
- Member of the public
- Project manager
- Service designer

**Why dropdown:**
- Prevents proliferation of similar but inconsistent types
- Makes filtering and grouping reliable
- Forces consistency while allowing new types as needed

#### As a (dropdown)
Standardized primary user role. Should have a limited, consistent set of options.

**Examples:**
- User researcher
- Lead user researcher
- Project member
- Library visitor

#### Who is (dropdown)
Secondary qualifier for cross-cutting characteristics.

**Examples:**
- Working in government
- With a login
- Without accessibility tools
- Unfamiliar with the system
- Leading a team

#### I need to (free text)
The specific action or capability. Free text because needs can be highly varied.

**Guidance:**
- Focus on the capability, not implementation
- Be specific but solution-agnostic
- Keep consistent language where possible

#### So that (dropdown)
After grouping, you'll discover that outcomes often fall into a limited set. Making this a dropdown:
- Highlights when needs share outcomes
- Makes duplicates easier to spot
- Enables grouping by outcome
- Reveals the most common user goals

**Example outcomes:**
- I can easily share research with others
- I can quickly and easily update records
- I don't have to wait for someone to add my team's work for me
- I can access the back end of the library
- We keep user data secure

#### Joined User Need (formula)
Automatically combines As a / Who is / I need to / So that into readable format for easy sharing and presentation.

### Organizational Fields

#### Theme (dropdown)
Categorizes what the need is about:
- Financial
- Motivational
- Technical
- Collaborative
- Security
- Efficiency

**Purpose:** Helps identify thematic patterns across different user types and journey stages.

#### Category User Need / Epic (dropdown)
Groups related needs into higher-level categories. Typically 8-12 epics for 60-80 needs.

**Benefits:**
- Easier to present to stakeholders
- Provides high-level view of project scope
- Helps organize work planning
- Enables progress tracking at epic level

**Examples of epics:**
- Finding and accessing research
- Adding and editing content
- Managing library structure
- Collaboration and sharing
- System access and permissions

#### Journey Stage (dropdown)
Maps the need to where it occurs in the user journey:
- Discovery
- Registration/Setup
- Creation
- Editing
- Review
- Library Management
- Sharing

**Value:**
- Identifies which parts of the journey have most needs
- Reveals stages with missing coverage
- Helps service designers understand touchpoints
- Enables journey-based filtering

#### Source Project (dropdown)
Which project or research effort identified this need.

**Uses:**
- Track which projects have contributed needs
- Identify projects with missing/incomplete needs
- Understand where needs are concentrated
- Credit research contributions

### Future Planning Fields

These fields are completed when needs are used in subsequent projects:

#### Projects This Applies To
Mark which future projects plan to address this need.

#### Failure Impact (free text)
What happens if this need isn't met. Helps with prioritization.

#### Success Impact (free text)
Benefits of meeting this need.

#### Success Measures
Where applicable, how success in meeting this need can be measured.

#### Acceptance Criteria (free text)
Specific, testable conditions that must be met for the need to be fulfilled.

**Format:** Bullet list of criteria

**Example:**
- Library can be accessed via clear URL
- Login/signup clearly displayed on homepage
- Users can authenticate via institutional credentials
- System handles failed authentication gracefully

## Standardization Through Dropdowns

After refining several hundred needs, certain fields naturally consolidate:

**Limited user types emerge**
Most organizations have 5-12 distinct user types across all projects.

**Outcomes converge**
Despite varied needs, users typically have 15-25 distinct ultimate outcomes within a system.

**Journey stages stabilize**
User journeys typically have 6-10 consistent stages.

**Themes cluster**
Needs tend to fall into 8-15 thematic areas.

**Benefits of dropdowns:**
- Prevent future inconsistency
- Make filtering fast and reliable
- Force consideration of whether a "new" type is truly distinct
- Enable consistent analysis over time
- Still flexible—you can add new dropdown options when genuinely needed

## The Refinement Workflow

### Initial Setup (One-time)
1. Create database structure with fields
2. Import existing user needs
3. Do initial pass to understand scope

### Bulk Refinement
1. **First pass:** Standardize format (As a/Who is/I need to/So that)
2. **Second pass:** Split "As a" into "As a" and "Who is"
3. **Third pass:** Identify and merge duplicates
4. **Fourth pass:** Standardize user types into dropdown
5. **Fifth pass:** Group similar outcomes and create dropdown
6. **Sixth pass:** Create and assign themes
7. **Seventh pass:** Create and assign epics/category needs
8. **Eighth pass:** Map to journey stages
9. **Ninth pass:** Review groupings to identify patterns

### Ongoing Maintenance
- Review needs at project start to select relevant ones
- Add new needs from research at project end
- Update existing needs if research refines understanding
- Periodically review for new duplicates or gaps

## Analysis Techniques

### Grouping by Outcome
Group needs by their "So that" field to find:
- Needs that serve the same ultimate goal
- Potential duplicates with different wording
- Related needs that could be addressed together

**Insight example:** "19 outcomes for 32 needs—many needs share common goals"

### Grouping by Journey Stage
View needs by where they occur to find:
- Stages with heavy need concentration
- Stages with few or no identified needs (potential gaps)
- Whether research has covered the full journey

**Insight example:** "9 needs for Creation, 11 for Library Management, but only 3 for Editing and 1 for Review—are we missing needs in later stages?"

### Grouping by User Type
Filter to single user types to understand:
- Unique needs of each user group
- Whether certain user types dominate (potential bias)
- Gaps in research coverage

**Insight example:** "All but 3 needs are for user researchers—have we adequately captured other user types?"

### Category Need Analysis
Review your epics/categories:
- How many needs fall into each category?
- Are there singleton categories (only one need)?
- Are categories balanced or heavily skewed?

**Insight example:** "3 category needs only have one user need each—are these categories appropriate, or should we research further?"

**Insight example:** "11 category needs for 39 user needs—good ratio for stakeholder digestion"

### Cross-tabulation
Combine multiple groupings:
- Which user types need what at which journey stages?
- Which themes appear across all user types vs. specific ones?
- Do certain outcomes correlate with journey stages?

## Example: Hackney Library Project Analysis

From refining 32 needs on an open library project:

**Outcomes:** Only 19 distinct "so that" outcomes despite 32 needs—many needs share ultimate goals

**Journey distribution:**
- Creation: 9 needs
- Library Management: 11 needs
- Editing: 3 needs
- Review: 1 need

**Question raised:** Are we missing needs in Editing and Review stages?

**User type distribution:** All but 3 needs are for user researchers

**Question raised:** Have we captured needs of other user types adequately?

**Category distribution:** 11 category needs for 39 refined user needs

**Assessment:** Good ratio for stakeholder presentations

**Singletons:** 3 categories with only one need each

**Question raised:** Are these legitimate distinct categories, or should we research further?

## Tools and Formats

### Database Options
- **Airtable:** Visual, easy to share, good filtering/grouping
- **Coda.io:** More flexible formulas, good for complex views
- **Spreadsheet:** Simple, universal, but less powerful grouping
- **Specialized tools:** Dovetail, Aurelius, etc.

### Key Requirements
Whatever tool you use should support:
- Dropdown fields
- Formulas (for joining fields)
- Grouping and filtering
- Multiple views
- Easy sharing with team

## Output Artifacts

### For Stakeholders
- **Epic summary:** List of 8-12 category needs
- **Journey map:** Needs mapped to stages
- **User type comparison:** Key needs per user group

### For Team
- **Full needs database:** Filterable and searchable
- **Gap analysis:** Stages/types with missing coverage
- **Duplicate list:** Candidates for merging

### For Future Projects
- **Reusable needs library:** Searchable repository
- **Acceptance criteria bank:** Examples of well-defined criteria
- **Outcome list:** Standard outcomes to check against

## Common Pitfalls

1. **Not standardizing early enough:** Harder to fix inconsistency in large repositories
2. **Too many categories:** Keep epics/categories to 8-12 for clarity
3. **Forcing dropdowns too early:** Let patterns emerge before constraining
4. **Ignoring duplicates:** Similar needs with different wording hide insights
5. **Solo refinement:** Team input crucial for accurate categorization
6. **One-and-done:** Needs repositories should be living documents

## Success Indicators

You've successfully refined user needs when:

- ✓ Duplicates are easily spotted by outcome similarity
- ✓ Filtering by user type instantly shows relevant needs
- ✓ Stakeholders can grasp scope via 8-12 epics
- ✓ Journey gaps are visually obvious
- ✓ New needs can be quickly categorized using existing taxonomy
- ✓ Team confidently references specific needs by ID
- ✓ Cross-project patterns become visible

## References

Based on Jonathan Richardson's methodology from refining several hundred user stories for a research repository project. Source: "User needs refinement — why and how to do it" (2020)
