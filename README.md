# Building Book - SDD Framework Harness

AI Harness for Specification-Driven Development (SDD).

## Overview

Building Book is a framework that guides development based on specifications defined in markdown documents. It provides a CLI, web server, and integration with opencode agents.

## Features

- **CLI Commands**: `bbook build`, `bbook open`, `bbook plan`
- **Web Server**: HTTP server with live reload for markdown and PlantUML
- **PlantUML Rendering**: Automatic SVG generation from `.puml` files
- **Status Tracking**: Document state management (pending/accepted/needs-work)
- **opencode Integration**: `.opencode/` directory for agent instructions

## Project Structure

```
docs/                    # Specification documents
├── Fundation.md         # General specification
├── status.yml           # Progress tracking
├── diagrams/            # Rendered SVG diagrams
└── plan/                # Planning documents
    ├── Plan.md
    ├── contract.yml
    ├── models.yml
    ├── business-rules.md
    └── adrs/

.opencode/               # opencode integration
├── agents.md            # Agent instructions
└── skills/
    └── building-book/
        └── SKILL.md

src/                     # Source code (future)
```

## Status

Currently in **Planning Stage** (GATE-001 passed, GATE-002 pending).

See [docs/Fundation.md](docs/Fundation.md) for full specification.

## Usage

```bash
bbook build              # Initialize project structure
bbook open               # Start web server
bbook plan status        # Show project state
```

## Architecture

Infrastructure → Domain ← Presentation

## License

MIT