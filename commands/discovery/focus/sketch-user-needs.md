# Sketch User Needs

Transform raw research into structured, validated user needs.

## When to Use

Use this command after conducting user research (interviews, observations, usability tests, feedback analysis) when you're ready to synthesize findings into structured needs statements.

**In the design process flow:** _Gather → **Process** → Explore_

This is a "Process" activity — you're transforming raw research data into actionable design inputs.

## What It Does

This command orchestrates multiple skills to process research into structured needs:

1. **Extracts** needs from your research materials
2. **Validates** each need against quality criteria
3. **Renders** needs as structured markdown files
4. **Identifies** patterns, themes, and gaps
5. **Suggests** next steps in the design process

## Input

- Research materials: interview transcripts, observation notes, feedback, survey responses
- File paths or direct content
- Existing needs collection (optional, for consistency)

## Output

- Individual need files: `example-1/outputs/needs/[need-text].md`
- Analysis summary: `example-1/outputs/user-needs-extraction-summary.md`
- Pattern insights and recommended next steps

## How It Works

This command uses four specialized skills:

**Extraction:** `extract-needs-from-research`
- Distinguishes needs from wants and solutions
- Identifies evidence-based capabilities
- Captures user context and goals

**Validation:** `validate-need-quality`
- Checks for capability vs solution
- Ensures need and outcome are different levels
- Verifies evidence basis and testability

**Rendering:** `render-user-need`
- Assigns sequential IDs
- Populates template structure
- Maintains consistency with existing needs

**Pattern Analysis:** `identify-need-patterns`
- Finds theme clusters and duplicates
- Analyzes coverage by user type and journey stage
- Surfaces strategic insights

## Template Structure

Each need follows the standard user-need template structure:

```yaml
---
ID: "[sequential-number]"
user type: "[[type]]"
as a: [specific role]
who is: [optional qualifier]
I need to: [capability statement]
so that: [goal/outcome]
category: [optional]
theme: [optional]
user journey stage: "[[stage]]"
customer journey stage: [optional]
---
```

## Example Usage

**Command:**
```
/sketch-user-needs
```

_Then provide research materials when prompted._

**What happens:**
1. Agent reviews your research
2. Extracts 5-15 candidate needs
3. Validates each against quality criteria
4. Creates need files with sequential IDs
5. Analyzes patterns across all needs
6. Generates summary with insights and next steps

## Quality Standards

The agent ensures each need:
- Describes a _capability_, not a solution
- Has evidence from research
- Is specific enough to validate
- Has outcome different from action (not circular)
- Is technology-agnostic
- Is testable

See `.claude/skills/validate-need-quality/SKILL.md` for detailed criteria.

## Related Commands

**Before:** [plan-interview](../plan/plan-interview.md), [sketch-study-plan](../plan/sketch-study-plan.md)
**After:** [refine-user-needs](refine-user-needs.md), [map-journey](../../explore/map-journey.md)
**Alternative path:** [combine-insights](../../explore/combine-insights.md)

## Behind the Scenes

This command uses Claude Code skills located in `.claude/skills/`:

- `extract-needs-from-research` — Extract needs from research materials
- `validate-need-quality` — Validate quality of extracted needs
- `render-user-need` — Create properly formatted need files
- `identify-need-patterns` — Analyze patterns across needs collection
