# User Needs Writing Guide

A reference for writing clear, actionable user needs based on research insights.

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
- As a user researcher
- As a team member
- As a member of the public
- As a library visitor

**Best practice:** Use a dropdown list of standardized user types to maintain consistency.

#### Who is [qualifier]
Optional additional context about the user's situation or characteristics.

**Examples:**
- who is working in government
- who has a login
- who has accessibility needs
- who is unfamiliar with the system

#### I need to [action]
The specific action or capability the user requires. Focus on _needs_, not _wants_.

**Key distinction:**
- ✓ **Need:** "I need to search for relevant research"
- ✗ **Want:** "I want a fancy search interface"

**Guidelines:**
- Focus on the capability, not the implementation
- Avoid specifying solutions
- Keep free-text format as needs can be wide-ranging
- Be specific about what the user is trying to do

#### So that [outcome]
The ultimate goal or benefit. This should articulate the higher-level purpose.

**Critical distinction from "I need to":**
- "I need to" describes the immediate action
- "So that" describes the ultimate goal or benefit

**Example:**
- I need to: get a passport
- So that: I can legally travel to another country

The passport is the need, but international travel is the outcome.

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

## Examples

### Before Refinement
"User researcher wants to add their research to the library when they finish doing a project"

### After Refinement
- **As a:** User researcher
- **Who is:** (not specified)
- **I need to:** Quickly and easily add research to the library
- **So that:** I can share my research with others

### Another Example
**Before:** "help to name my projects in a clear, consistent way"

**After:**
- **As a:** User researcher
- **Who is:** (not specified)
- **I need to:** Name my projects in a clear, consistent way
- **So that:** I don't make mistakes that are seen publicly

## Validation Checklist

Use this checklist to validate each user need:

- [ ] Does it describe a need rather than a want or solution?
- [ ] Is the user type consistent with other needs in the repository?
- [ ] Does "I need to" describe a specific action or capability?
- [ ] Does "So that" articulate the higher-level goal or outcome?
- [ ] Are "I need to" and "So that" at different levels (not duplicates)?
- [ ] Is it based on research evidence rather than assumptions?
- [ ] Could different solutions potentially address this need?

## References

- Based on GDS (Government Digital Service) principles for user needs
- Adapted from Jonathan Richardson's user needs refinement methodology
- Source: "User needs refinement — why and how to do it" (2020)
