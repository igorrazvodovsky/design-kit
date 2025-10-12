# User Needs Writing Guide

A reference for writing clear, actionable user needs based on research insights.

## Your Setup

This guide is adapted for use with:
- **Format:** Individual .md files per user need (one file per need)
- **Tool:** Obsidian with **Bases** plugin for database-like management
- **Structure:** YAML frontmatter with standardized fields
- **Links:** Wiki-links like `[[user]]` and `[[registration]]` to create relationships
- **Location:** Need files stored in `example-1/outputs/needs/`
- **Template:** Defined in `templates/user-need.md`
- **Management:** Bases provides filtering, sorting, and multiple views without code

## Terminology: User Needs vs User Stories

While both terms are used interchangeably, _user need_ is preferred over _user story_ because:

- User stories are used beyond user research contexts
- "Need" helps focus creation on what users actually need, not what they want
- The terminology reinforces a focus on fundamental requirements rather than feature requests

## The User Need Format

### Standard Structure

The traditional user need format is: **As a [role] / I need to [action] / So that [outcome]**

### Enhanced Structure with "Who is"

A more flexible approach splits the "As a" into two parts:

**As a [primary user type] / Who is [qualifier] / I need to [action] / So that [outcome]**

#### Why Split "As a"?

- **As a** — Keep consistent high-level user types (easier to group and filter)
- **Who is** — Capture cross-cutting secondary characteristics
  - Example: Users with accessibility needs
  - Example: Users without login credentials
  - Example: First-time users vs returning users

This separation allows you to:
- Maintain a limited, manageable set of primary user types
- Still capture important contextual variations
- Group needs by either primary type or secondary characteristics

### Component Breakdown

#### As a [user type]
The primary user role or persona. Keep this consistent and limited.

**Examples:**
- teammate
- admin
- external collaborator
- guest user

**In your Obsidian setup:**
- Stored in the `as a:` field in frontmatter
- The `user type:` field often uses wiki-links like `[[user]]` to link to user type definitions
- This creates a network of related needs by user type in your Obsidian graph

#### Who is [qualifier]
Optional additional context about the user's situation or characteristics.

**Examples:**
- invited by an admin _(from your [[accept an invite and land in the correct workspace]] example)_
- working in government
- with accessibility needs
- managing multiple workspaces

**In your Obsidian setup:**
- Stored in the `who is:` field in frontmatter
- Can be left blank when not needed
- Helps filter needs by cross-cutting concerns
- Use Obsidian queries to find all needs with specific qualifiers

#### I need to [action]
The specific action or capability the user requires. Focus on _needs_, not _wants_.

**Key distinction:**
- ✓ **Need:** "search for relevant research"
- ✗ **Want:** "have a fancy search interface with blue buttons"

**Guidelines:**
- Focus on the capability, not the implementation
- Avoid specifying solutions
- Be specific about what the user is trying to do
- Use concise, action-oriented language

**In your Obsidian setup:**
- Stored in the `I need to:` field in frontmatter
- **This becomes the filename** (e.g., "accept an invite and land in the correct workspace.md")
- Keep it concise enough for a readable filename
- Use lowercase and spaces for readability

#### So that [outcome]
The ultimate goal or benefit. This should articulate the higher-level purpose.

**Critical distinction from "I need to":**
- "I need to" describes the immediate action
- "So that" describes the ultimate goal or benefit

**Example:**
- I need to: get a passport
- So that: I can legally travel to another country

The passport is the need, but international travel is the outcome.

**In your Obsidian setup:**
- Stored in the `so that:` field in frontmatter
- Should be the user's goal, not a system feature
- Example from your repo: "I see the right data and teammates" (user outcome) not "the system displays the correct workspace" (implementation)

## Writing Principles

### 1. Focus on Needs, Not Wants

**Need** = fundamental requirement for accomplishing a goal
**Want** = desire for a specific solution or feature

Users need to accomplish goals. They may want specific features, but those are solutions, not needs.

### 2. Distinguish Actions from Outcomes

The "I need to" should never duplicate the "So that." They exist at different levels:

- **I need to:** Immediate action or capability
- **So that:** Higher-level goal or benefit

### 3. Be Goal-Oriented

Every user need should trace back to a meaningful user goal. If the "So that" feels trivial or circular, dig deeper to find the real outcome.

### 4. Avoid Solution Specification

❌ "I need to have a blue button on the homepage"
✓ "I need to quickly access my saved work so that I can resume tasks efficiently"

The first prescribes a solution. The second describes a need that designers can address in various ways.

### 5. Keep User Types Consistent

Standardizing user types makes it easier to:
- Group related needs
- Identify gaps in coverage
- Present findings to stakeholders
- Filter and analyze your research

## Common Patterns

### Discovery Needs
"As a [user type] who is [exploring/new], I need to [understand/learn/discover] so that [I can determine if this meets my needs]"

### Task Completion Needs
"As a [user type], I need to [perform action] so that [I can accomplish goal]"

### Access and Permission Needs
"As a [user type] who is [qualified], I need to [gain access/verify identity] so that [I can use protected features]"

### Efficiency Needs
"As a [user type], I need to [do something quickly/easily] so that [I can complete work efficiently]"

### Collaboration Needs
"As a [user type], I need to [share/coordinate/communicate] so that [team can work together effectively]"

## File Organization in Obsidian

### File Naming Convention
The filename should match the "I need to" field for easy reference:
- `accept an invite and land in the correct workspace.md`
- `find what I'm looking for.md`
- `see my assigned work.md`

This makes it easy to reference needs by their core action using wiki-links.

### Frontmatter Structure
Your template at `templates/user-need.md` defines the standard structure:

```yaml
---
ID: [unique identifier]
user type: [can use wiki-link like [[user]]]
as a: [specific role]
who is: [optional qualifier]
I need to: [the need]
so that: [the outcome]
category: [optional grouping]
theme: [optional conceptual thread]
user journey stage: [can use wiki-link like [[registration]]]
customer journey stage: [optional]
acceptance criteria: [optional]
---
```

### Using Wiki-Links for Relationships
Wiki-links create connections that power Obsidian's graph view:

- `user type: "[[user]]"` — links to user type definition
- `user journey stage: "[[registration]]"` — links to journey stage
- These create a navigable graph showing relationships
- Enables finding all needs for a user type or journey stage via backlinks

### Example from Your Repository

`example-1/outputs/needs/accept an invite and land in the correct workspace.md`:

```yaml
---
ID: "8"
user type: "[[user]]"
as a: teammate
who is: invited by an admin
I need to: accept an invite and land in the correct workspace
so that: I see the right data and teammates
category:
theme:
user journey stage: "[[registration]]"
customer journey stage:
acceptance criteria:
---
```

**What makes this well-formed:**
- Clear user role: "teammate"
- Important qualifier: "invited by an admin" (distinguishes from self-signup)
- Specific action: "accept an invite and land in the correct workspace"
- Clear outcome: "I see the right data and teammates"
- Linked to journey stage: `[[registration]]`

## More Examples

### Before Refinement
"User researcher wants to add their research to the library when they finish doing a project"

### After Refinement (as .md file)

Filename: `quickly and easily add research to the library.md`

```yaml
---
ID: "42"
user type: "[[user researcher]]"
as a: user researcher
who is:
I need to: quickly and easily add research to the library
so that: I can share my research with others
category:
theme:
user journey stage: "[[contribution]]"
---
```

### Another Example

**Before:** "help to name my projects in a clear, consistent way"

**After:**

Filename: `name my projects in a clear consistent way.md`

```yaml
---
ID: "43"
user type: "[[user researcher]]"
as a: user researcher
who is:
I need to: name my projects in a clear, consistent way
so that: I don't make mistakes that are seen publicly
category:
theme:
user journey stage: "[[creation]]"
---
```

## Validation Checklist

Use this checklist to validate each user need:

- [ ] Does it describe a need rather than a want or solution?
- [ ] Is the user type consistent with other needs in the repository?
- [ ] Does "I need to" describe a specific action or capability?
- [ ] Does "So that" articulate the higher-level goal or outcome?
- [ ] Are "I need to" and "So that" at different levels (not duplicates)?
- [ ] Is it based on research evidence rather than assumptions?
- [ ] Could different solutions potentially address this need?
- [ ] Does the filename match the "I need to" field exactly?
- [ ] Are wiki-links used correctly for user types and journey stages?
- [ ] Is the frontmatter YAML properly formatted?
- [ ] Does the file have a unique ID?

## Working with Needs in Obsidian

### Using Obsidian Bases

You're using **Obsidian Bases** to manage your user needs. Bases is a core plugin (introduced in 2025) that turns your notes into an interactive database without requiring programming knowledge.

**Why Bases for user needs:**
- Filter needs by properties (user type, journey stage, category)
- Create multiple views (e.g., "Registration needs", "All teammate needs")
- Edit properties inline without opening files
- Sort and organize visually
- No code required (unlike Dataview)

**Setting up a Base for your needs:**
1. Enable the Bases core plugin in Obsidian settings
2. Create a new Base (`.base` file)
3. Point it to your `example-1/outputs/needs` folder
4. Add filters for properties like `user type`, `user journey stage`, `category`
5. Create different views for different perspectives

**Example views you might create:**
- **By Journey Stage:** Filter to show needs at `[[registration]]`, `[[onboarding]]`, etc.
- **By User Type:** Filter to show all `[[user]]` needs vs `[[admin]]` needs
- **Unprocessed:** Show needs where `category` is empty
- **High Priority:** Filter by priority field if you add one

### Finding Related Needs

**Using Bases (recommended):**
- Create filtered views by user type or journey stage
- Sort by any property
- See counts and summaries
- Edit properties inline

**Using Backlinks (alternative):**
1. Navigate to a user type note (e.g., `[[user]]`)
2. View backlinks to see all needs referencing that type

**Using Search:**
```
path:example-1/outputs/needs "user type: [[registration]]"
```

### Creating New Needs

1. Use your template: `templates/user-need.md`
2. Fill in the frontmatter fields
3. Name the file to match the "I need to" field
4. Place in `example-1/outputs/needs/`
5. Use wiki-links for user types and journey stages
6. Assign a unique ID (sequential numbering works well)
7. The need will automatically appear in your Bases views

## References

- Based on GDS (Government Digital Service) principles for user needs
- Adapted from Jonathan Richardson's user needs refinement methodology
- Source: "User needs refinement — why and how to do it" (2020)
