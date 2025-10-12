# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is an _early-stage experimental project_ exploring how to deconstruct the design process into discrete, LLM-augmented tasks. The goal is to replace traditional design tools (like Figma) with an agentic system that supports the full spectrum of design work: discovery, synthesis, research, prototyping, and iteration.

**Current State**: Very early draft. Existing commands and templates are placeholders or early experiments testing the structure. _Do not treat current files as examples of the intended final form._ The repository represents goals and structural exploration, not working implementations.

## Core Philosophy

- Design is non-linear and context-dependent, but follows a general flow
- The system is self-propelling: connections between tasks guide progression through the process
- Focus on facilitating conversation about goals and means rather than pure problem-solving
- Emphasize systems thinking and reflection-in-action
- Surface and question current framing, experiment with new frames

## Intended Design Process Flow

**Define → Plan → Gather → Process → Explore → Focus → Construct → Refine → Reflect**

The vision is for commands and templates to map to steps in this process, with tasks referencing outputs from previous steps and generating inputs for subsequent ones. This flow is aspirational - current implementations are exploratory.

## Repository Structure (Experimental)

### `/commands/`
Intended to be executable design tasks organized by process stage. Currently contains structural placeholders.

### `/templates/`
Intended to define output formats for design artifacts. Currently minimal placeholders testing the concept.

### `/example-outputs/`
Early experiments applying the structure to scenarios. These are tests, not reference implementations.

## Working with This Repository

- This is a pure content/methodology repository with no build, test, or development commands
- Commands use kebab-case with action verbs (sketch-*, plan-*, map-*)
- Templates use noun phrases describing artifact types
- Many files contain only single-line placeholders - this is intentional for testing structure
- When developing new commands or templates, focus on the _relationships between artifacts_ and how they flow through the process

### Wiki-Link Resolution

This repository uses Obsidian for knowledge management. Files contain wiki-links like `[[user]]` that reference other documents.

- **Link mappings** are defined in [.claude/link-mappings.json](.claude/link-mappings.json)
- Common entity types include:
  - User types (user, admin)
  - User journey stages (registration, access, onboarding, setup)
  - Needs categories (navigation)
- When encountering `[[entity-name]]`, resolve it using the mappings file
- Obsidian uses "shortest path" resolution by default, so `[[user]]` finds `example-1/outputs/user types/user.md`
- Update the mappings file when adding new entity types to maintain alignment between Obsidian and Claude Code
