# MCP PlantUML for Ampcode

Integration of Model Context Protocol (MCP) with PlantUML for diagram generation in Ampcode.

## Setup

### Prerequisites
- Node.js 18+
- PlantUML installed (`plantuml` command available)

### Installation

```bash
npm install
npm run build
```

### Configuration

Edit `.amprc.json` to customize:
- `outputFormat`: `svg`, `png`, `pdf`
- `diagramPath`: Directory for diagram files
- PlantUML JAR path (if using custom installation)

## Usage

```bash
npm start
```

This initializes the MCP PlantUML server and generates example diagrams.

## MCP Server Configuration

The `.amprc.json` file defines the MCP server settings for Ampcode:

```json
{
  "mcpServers": {
    "plantuml": {
      "command": "npx",
      "args": ["mcp-plantuml-server"],
      "env": {
        "PLANTUML_JAR_PATH": "/usr/local/bin/plantuml.jar"
      }
    }
  }
}
```

## Generate Diagrams

Use the TypeScript API to generate diagrams:

```typescript
const server = new MCPPlantUMLServer();
const output = await server.generateDiagram(plantUMLSource, "diagram-name");
```

## Directory Structure

```
.
├── .amprc.json          # MCP server configuration
├── index.ts             # MCP server implementation
├── package.json         # Dependencies
├── tsconfig.json        # TypeScript config
├── diagrams/            # Generated diagrams (auto-created)
└── README.md           # This file
```

## License

MIT
