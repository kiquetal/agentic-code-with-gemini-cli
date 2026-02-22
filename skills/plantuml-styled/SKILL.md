---
name: plantuml-styled
description: Generate PlantUML diagrams with specific project styling, including theme, skinparams, and mandatory co-authorship footer. Use when creating or updating architectural, sequence, or class diagrams.
---

# PlantUML Styled

## Overview

This skill ensures all PlantUML diagrams generated for the project adhere to a consistent visual style and include required attribution.

## Styling Guidelines

All diagrams MUST follow these style parameters:

```plantuml
!theme spacelab
!option handwritten true
skinparam backgroundColor #f8f9fa
skinparam classFontColor #000000
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
skinparam classFontColor #000000
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
