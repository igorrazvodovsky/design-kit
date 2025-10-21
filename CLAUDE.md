# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository overview

This is an _early-stage experimental project_ exploring how to deconstruct the design process into discrete, LLM-augmented tasks. The goal is to replace traditional design tools (like Figma) with an agentic system that supports the full spectrum of design work: discovery, synthesis, research, prototyping, and iteration.

**Current State**: Very early draft. Existing commands and templates are placeholders or early experiments testing the structure. _Do not treat current files as examples of the intended final form._ The repository represents goals and structural exploration, not working implementations.

## Core philosophy

- Design is non-linear and context-dependent, but follows a general flow
- The system is self-propelling: connections between tasks guide progression through the process
- Focus on facilitating conversation about goals and means rather than pure problem-solving
- Emphasize systems thinking and reflection-in-action
- Surface and question current framing, experiment with new frames

## Intended design process flow

**Define → Plan → Gather → Process → Explore → Focus → Construct → Refine → Reflect**

The vision is for commands and templates to map to steps in this process, with tasks referencing outputs from previous steps and generating inputs for subsequent ones. This flow is aspirational - current implementations are exploratory.

## Repository structure (experimental)

The repository separates concerns into three layers:

### `/commands/` - User-facing tasks
Executable design tasks organised by process stage (discovery, define, explore, etc.). Commands orchestrate skills to accomplish user goals. Users invoke commands directly (e.g., `/sketch-user-needs`).

**Structure:** `commands/[stage]/[activity-type]/[specific-task].md`

Example: `commands/discovery/research/process/sketch-user-needs.md`

### `/skills/` - Reusable capabilities
Claude Code skills providing specialised knowledge and workflows. Each skill is a self-contained package with:
- `SKILL.md` - Instructions and procedural knowledge
- `references/` - Documentation to load as needed
- `assets/` - Templates and files used in outputs
- `scripts/` - Executable code (when needed)

**Current skills:**
- `extract-needs-from-research` - Extract user needs from research materials
- `validate-need-quality` - Validate needs against quality criteria
- `identify-need-patterns` - Analyse patterns across needs collections
- `render-user-need` - Create properly formatted need files

Commands reference skills by name. Skills are automatically invoked by Claude when relevant to the task.

### `/agents/`
Multi-step autonomous agents for complex workflows (planned; none exist currently).

### `/references/`
Methodology documentation. Core references distributed to relevant skills.

### `/example-1/outputs/`
Working example applying the structure.

## Working with this repository

- This is a pure content/methodology repository with no build, test, or development commands
- **Commands** use kebab-case with action verbs (sketch-*, plan-*, map-*)
- **Skills** use kebab-case nouns describing capabilities (extract-needs-from-research, validate-need-quality)
- **Templates** use noun phrases describing artifact types
- Many files contain only single-line placeholders - this is intentional for testing structure
- When developing new commands or templates, focus on the _relationships between artifacts_ and how they flow through the process

### Design patterns

**Command → Skill → Output**
- Users invoke commands (e.g., `/sketch-user-needs`)
- Commands orchestrate one or more skills
- Skills use bundled resources (references, assets, scripts)
- Output follows template structures

**Skill reusability**
- Skills are domain-specific, not task-specific
- Multiple commands can use the same skill
- Skills reference each other when workflows connect
- Skills use progressive disclosure (metadata → SKILL.md → bundled resources)

**Example workflow:**
1. User runs `/sketch-user-needs` with research transcript
2. Command invokes `extract-needs-from-research` skill
3. Skill reads reference materials for quality standards
4. Command invokes `validate-need-quality` to check extracted needs
5. Command invokes `render-user-need` to create files
6. Skill reads template from `assets/user-need-template.md`
7. Command invokes `identify-need-patterns` for analysis
8. Skill reads refinement process reference
9. Output: Structured need files + analysis summary

### Writing style
- Use British spelling throughout (behaviour, organisation, colour, etc.)
- **Always use sentence case for headings and titles**
- **Prioritize conciseness** - Each sentence should add new information. Remove elaborative phrases that restate rather than extend. Trust reader comprehension—avoid over-explaining implications. Edit ruthlessly to remove redundancy.