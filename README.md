# Design kit: deconstructing & augmenting the design process

Here I'm trying to deconstruct my design process into core tasks and look for opportunities for human-LLM co-creation. By dividing the tasks into discrete units, I'm re-evaluating and re-framing my work. The result I'm aiming for is a collection of tools and templates that can be used to augment design.

The kit uses a three-layer architecture—commands, skills, and agents—that separates what designers ask for (commands), how to do things (skills), and orchestration (agents).

Inspired by [spec-kit](https://github.com/github/spec-kit) & [amplifier](https://github.com/microsoft/amplifier).

> Current state: early-stage experiments.

## Objective

Replacing [Figma](https://www.figma.com/) as a main design tool with an agentic aid that can support both prototyping and earlier↔later stages of design work: discovery, synthesis, research, etc.

## Goals

- Build a self-propelling system where connections between tasks guide progression through the design process.
- ==Nudge a designer from viewing a design process as problem-solving towards facilitating a conversation about goals and means.== ^37066d
- Nudge a designer towards systemic worldviews and using mindset, methods, and tools of systems thinking
- Build in triggers for reflection-in-action – surfacing and questioning the current framing, trying new frames, probing them with experiments.

## Structure

The kit uses a three-layer architecture that separates concerns and enables intelligent, adaptive behaviour:

- Commands: triggers that designers type to start an activity. Each command maps to a step in the design process flow.
- Skills: Design methods and techniques.
- Agents: Autonomous processes that accomplish design goals by orchestrating skills.

Design is iterative, non-linear, and context-dependent, but there is still a sequence that underpins the general flow. Skills and commands are mapped to the most relevant step in this process.

**Define – Plan – Gather – Process – Explore – Focus – Build – Refine – Reflect**

## "Integration" with other tools

### Figma

TODO: Using Figma MCP server, integrating with Make prototypes, etc.

### User-research platform (e.g. Dovetail)

TODO: When research processing happens elsewhere, what, how, and how much should be exported/imported.

### Product analytics

TODO: Same as with research platforms.

## Using the kit with different types of design opportunities

TODO: feature/product, new/existing stuff; amount of unknowns, etc.

