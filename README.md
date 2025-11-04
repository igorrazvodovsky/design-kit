# Design kit: deconstructing & augmenting the design process

Here I'm trying to deconstruct my design process into core tasks and look for opportunities for human-LLM co-creation. By dividing the tasks into discrete units, I'm re-evaluating and re-framing my work. The result I'm aiming for is a collection of tools and templates that can be used to augment design.

Inspired by [spec-kit](https://github.com/github/spec-kit) & [amplifier](https://github.com/microsoft/amplifier).

> Current state: early-stage experiments.

## Main objective

Replacing [Figma](https://www.figma.com/) as a main design tool with an agentic aid that can support both prototyping and earlier↔later stages of design work: discovery, synthesis, research, etc.

## Supporting objectives

- Build a self-propelling system where connections between tasks guide progression through the design process.
- Nudge a designer from viewing a design process as problem-solving towards facilitating a conversation about goals and means.
- Nudge a designer towards systemic worldviews and using mindset, methods, and tools of systems thinking
- Build in triggers for reflection-in-action – surfacing and questioning the current framing, trying new frames, probing them with experiments.

## Building blocks

1. *Design assistant* sub-agents, skills, and commands
2. *Research repository* as a main source of context.
3. *Prototyping*: design system/-s, component libraries, templates, etc, backend integrations for real data, AI APIs for prototyping.

### 1. Design assistant

The assistant uses a three-layer architecture that separates concerns and enables intelligent, adaptive behaviour:

- Commands: triggers that designers type to start an activity. Each command maps to a step in the design process flow.
- Skills: Design methods and techniques.
- Agents: Autonomous processes that accomplish design goals by orchestrating skills.

### 2. Research repository

A knowledge base that serves as the primary context source for the design assistant. The [research repository boilerplate](https://github.com/igorrazvodovsky/research-repository-boilerplate) provides templates and tools for documenting research in a format that's human-readable and AI-processable, enabling the assistant to draw on accumulated insights, patterns, and domain knowledge when guiding design decisions.

### 3. Prototyping

- Concepts-based foundation
- A way for a designer to use their preferred AI toolkits that help with coding.
- TODO: Link [pattern playground](https://github.com/igorrazvodovsky/pattern-playground)
- TODO: LLM API/SDK

## Capabilities

### Knowledge synthesis
Transforming data and information into structured understanding

### Deeper and wider exploration
- Humans focus on important stuff; AI is researching long shots
- AI does boring stuff while humans consider second and third order consequences

### Memory and learning: avoiding repeating work and accumulate domain expertise

### Design playbook
Capturing and reusing complex design processes.

## Kit & design process it supports

Design is iterative, non-linear, and context-dependent, but there is still a sequence that underpins the general flow. Each component maps to relevant steps in the process.

**Define – Plan – Gather – Process – Explore – Focus – Build – Refine – Reflect**

### Using the kit with different types of design opportunities

TODO: feature/product, new/existing stuff; amount of unknowns, etc.

