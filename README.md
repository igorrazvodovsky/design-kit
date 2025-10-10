# Design kit: deconstructing the design process

Here I'm trying to deconstruct my design process into core tasks and look for opportunities for human-LLM co-creation. By dividing the tasks into discrete units, I'm re-evaluating and re-framing my work. The result I'm aiming for is a collection of tools and templates that can be used to augment design.

Inspired by [spec-kit](https://github.com/github/spec-kit).

## Objective

Replacing [Figma](https://www.figma.com/) as a main design tool with an agentic aid that can support both prototyping and earlier↔later stages of design work: discovery, synthesis, research, etc.

## Goals

- Build a self-propelling system where connections between tasks guide progression through the design process.
- Nudge a designer from viewing a design process as problem-solving towards the idea of facilitating a conversation about goals and means.
- Nudge a designer towards systemic worldviews and using mindset, methods, and tools of systems thinking
- Build in triggers for reflection-in-action – surfacing and questioning the current framing, trying new frames, probing them with experiments.

## Structure

Design is iterative, non-linear, and context-dependant, but there is still a sequence that underpins the general flow. Each task is mapped to the most relevant step in this process.

**Define – Plan – Gather – Process – Explore – Focus – Construct – Refine – Reflect**

For example, when preparing for user interviews, a designer might run a `/sketch-interview-protocol` command to help them create/edit an interview protocol. That command uses existing study plan under `.../discovery/research/plan` folder and/or related interview debriefs in `/process/` to generate a `user-interview-protocol.md` draft in `/execution/`.

Also, there are pick-and-choose commands (e.g. `/plan-exploration-and-sensemaking`) to take an output of the step and suggest the contents of the next step as not all of the available tasks are relevant in each situation. 

## Example

...
