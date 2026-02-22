---
name: plantuml-styled
description: Generate PlantUML diagrams with specific project styling, including theme, skinparams, and mandatory co-authorship footer. Use when creating or updating architectural, sequence, or class diagrams.
---

# PlantUML Styled

## Overview

This skill ensures all PlantUML diagrams generated for the project adhere to a consistent visual style and include required attribution.

## Styling Guidelines

Choose the appropriate theme based on the desired output.

### Light Mode (Default)

```plantuml
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

### Dark Mode

```plantuml
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

For handwritten/sketch style diagrams, always use `!option handwritten true`.

## Required Footer

All diagrams MUST include the co-authorship footer before the `@enduml` statement:

```plantuml
footer Co-authored by kiquetal
```

## Example

```plantuml
@startuml
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

Alice -> Bob: Hello

footer Co-authored by kiquetal
@enduml
```

## Supported Formats
- `svg` - Scalable Vector Graphics (Preferred)
- `png` - Portable Network Graphics
- `pdf` - Portable Document Format
