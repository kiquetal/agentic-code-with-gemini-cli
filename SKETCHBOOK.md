# Sketchbook

## MCP PlantUML Integration Architecture

```
@startuml
!theme spacelab
skinparam backgroundColor #f8f9fa
skinparam classFontColor #000000

package "Ampcode" {
  [User Interface]
}

package "MCP Layer" {
  [.amprc.json Config]
  [MCP Server]
}

package "PlantUML" {
  [PlantUML Server]
  [Diagram Generator]
}

package "Output" {
  [SVG Format]
  [PNG Format]
  [PDF Format]
}

[User Interface] --> [.amprc.json Config]
[.amprc.json Config] --> [MCP Server]
[MCP Server] --> [PlantUML Server]
[PlantUML Server] --> [Diagram Generator]
[Diagram Generator] --> [SVG Format]
[Diagram Generator] --> [PNG Format]
[Diagram Generator] --> [PDF Format]

@enduml
```

## Features

- ✅ MCP Protocol Integration
- ✅ Multiple Output Formats
- ✅ Real-time Diagram Generation
- ✅ Ampcode Integration

---

*Co-authored by kiquetal*
