# Agents Configuration

## MCP PlantUML Server

This project uses the PlantUML MCP server for diagram generation through the Model Context Protocol.

### Running the Server

The server runs on stdio and is automatically loaded by Ampcode via `.amprc.json`.

```bash
npx plantuml-mcp-server
```

### Diagram Generation

Generate diagrams in SVG, PNG, or PDF formats using PlantUML syntax via the configured MCP server.

### Styling Guidelines

All diagrams MUST follow these style parameters:

```
!theme spacelab
!option handwritten true
skinparam backgroundColor #f8f9fa
skinparam classFontColor #000000
skinparam classBorderColor #4285F4
skinparam arrowColor #4285F4
```

For handwritten/sketch style diagrams, use `!option handwritten true`.

**RULE: Always use `!option handwritten true` for sketch-style diagrams.**

### Required Footer

All diagrams MUST include the co-authorship footer:

```
footer Co-authored by kiquetal
```

This should appear before the `@enduml` statement.

**Example:**
```
@startuml
!theme spacelab
skinparam backgroundColor #f8f9fa
skinparam classFontColor #000000
skinparam classBorderColor #4285F4
skinparam arrowColor #4285F4

Alice -> Bob: Hello

footer Co-authored by kiquetal
@enduml
```

### Supported Formats
- `svg` - Scalable Vector Graphics
- `png` - Portable Network Graphics
- `pdf` - Portable Document Format

### Generated Diagrams

#### Sketchbook Diagram
- **Location**: `/diagrams/sketchbook.svg` (SVG) and `/diagrams/sketchbook.png` (PNG)
- **Description**: Class diagram showing Sketch and SketchCollection relationship
- **Purpose**: Visualizes the data structure for the sketchbook feature

#### MCP Registration Diagram
- **Location**: `/diagrams/mcp-registration.svg` (SVG) and `/diagrams/mcp-registration.png` (PNG)
- **Description**: Sequence diagram showing MCP server registration flow
- **Purpose**: Illustrates interaction between Ampcode Client, .amprc.json configuration, MCP Server, and PlantUML Server
- **Note**: Generated without footer text (PlantUML rendering optimization)

---

*Co-authored by kiquetal*
