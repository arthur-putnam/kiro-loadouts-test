# Example Loadouts

This directory contains example loadouts that demonstrate the structure and organization of Kiro loadouts.

## Available Loadouts

### react-fullstack

Complete React fullstack development environment with TypeScript, testing, and best practices.

**Includes:**
- React patterns and component best practices
- Jest testing guide with React Testing Library
- TypeScript configuration for React
- File system tool permissions
- Pre-commit linting hook
- PostgreSQL MCP server configuration

**Dependencies:** javascript-base

### javascript-base

Base JavaScript/Node.js development environment with ESLint and Prettier.

**Includes:**
- ESLint rules and standards
- Prettier formatting configuration
- Format-on-save hook

**Dependencies:** None

### python-data-science

Python data science environment with pandas, numpy, and Jupyter best practices.

**Includes:**
- Pandas best practices and patterns
- Jupyter notebook guidelines
- Python tool permissions
- Data analysis skill

**Dependencies:** None

## Loadout Structure

Each loadout follows this structure:

```
loadouts/<loadout-name>/
  manifest.json                    # Loadout metadata and artifact references
  steering-documents/              # Steering documents
    <category>/                    # Optional category subdirectory
      *.md                         # Markdown documents
    *.md                           # Flat structure also supported
  tool-permissions/                # Tool permission configurations
    *.json
  hooks/                           # Agent hooks
    *.json or *.md
  powers/                          # Kiro powers
    *.md or *.json
  skills/                          # Agent skills
    *.md
  mcp-configs/                     # MCP server configurations
    *.json
```

## Manifest File

The `manifest.json` file defines the loadout metadata and references all artifacts:

```json
{
  "name": "loadout-name",
  "version": "1.0.0",
  "description": "Description of what this loadout provides",
  "dependencies": ["other-loadout-name"],
  "artifacts": {
    "steeringDocuments": [
      {
        "path": "steering-documents/example.md",
        "inclusionMode": "always"
      }
    ],
    "toolPermissions": [
      {
        "path": "tool-permissions/permissions.json"
      }
    ],
    "hooks": [
      {
        "path": "hooks/example-hook.json",
        "enabled": true
      }
    ],
    "mcpConfigs": [
      {
        "path": "mcp-configs/server.json",
        "enabled": true
      }
    ]
  }
}
```

## Installation Targets

When installed, artifacts are placed in these locations:

- **Steering Documents** → `.kiro/steering/`
- **Tool Permissions** → `.kiro/settings/tool-permissions.json` (merged)
- **Hooks** → `.kiro/hooks/`
- **Powers** → `.kiro/powers/`
- **Skills** → `.kiro/skills/`
- **MCP Configs** → `.kiro/settings/mcp.json` (merged)

## Creating Your Own Loadouts

1. Create a directory under `loadouts/` with your loadout name
2. Add a `manifest.json` file with metadata
3. Organize artifacts in their respective directories
4. Reference artifacts in the manifest
5. Test the loadout structure

