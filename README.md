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


## Usage

```bash
bbook build              # Initialize project structure
bbook open               # Start web server
bbook plan status        # Show project state
```

## License
MIT
