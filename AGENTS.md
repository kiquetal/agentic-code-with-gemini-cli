# Agents Configuration

## Git Push Rules

**RULE: Never push by yourself! Always wait for user confirmation before pushing.**

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

Choose the appropriate theme based on the desired output.

#### Light Mode (Default)

```
!theme spacelab
!option handwritten true
skinparam backgroundColor #f8f9fa
skinparam DefaultFontColor #000000
skinparam textFontColor #000000
skinparam classFontColor #000000
skinparam sequenceActorFontColor #000000
skinparam sequenceParticipantFontColor #000000
skinparam sequenceArrowFontColor #000000
skinparam noteFontColor #000000
skinparam classBorderColor #4285F4
skinparam arrowColor #4285F4
```

#### Dark Mode

```
!theme spacelab
!option handwritten true
skinparam backgroundColor #212121
skinparam DefaultFontColor #ffffff
skinparam textFontColor #ffffff
skinparam classFontColor #ffffff
skinparam sequenceActorFontColor #ffffff
skinparam sequenceParticipantFontColor #ffffff
skinparam sequenceArrowFontColor #ffffff
skinparam noteFontColor #ffffff
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
skinparam DefaultFontColor #000000
skinparam textFontColor #000000
skinparam classFontColor #000000
skinparam sequenceActorFontColor #000000
skinparam sequenceParticipantFontColor #000000
skinparam sequenceArrowFontColor #000000
skinparam noteFontColor #000000
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

#### MCP Registration Diagram (Dark)
- **Location**: `/diagrams/mcp-registration-dark.svg` (SVG) and `/diagrams/mcp-registration-dark.png` (PNG)
- **Description**: Dark-themed sequence diagram showing MCP server registration flow
- **Purpose**: High-contrast dark mode version of the MCP registration flow

#### Skill Management Diagram
- **Location**: `/diagrams/skill-management.svg` (SVG) and `/diagrams/skill-management.png` (PNG)
- **Description**: Sequence diagram showing the flow of enabling/disabling a skill
- **Purpose**: Illustrates the interaction between the User, Gemini CLI, Settings, and Skill Registry

#### Skill Management Diagram (Dark)
- **Location**: `/diagrams/skill-management-dark.svg` (SVG) and `/diagrams/skill-management-dark.png` (PNG)
- **Description**: Dark-themed sequence diagram for skill management
- **Purpose**: High-contrast dark mode version of the skill management flow

#### Osquery Usage Diagram
- **Location**: `/diagrams/osquery_usage.svg` (SVG) and `/diagrams/osquery_usage.png` (PNG)
- **Description**: Architecture diagram explaining how osquery works
- **Purpose**: Visualizes the flow from SQL queries to system APIs and raw data retrieval

---

*Co-authored by kiquetal*
