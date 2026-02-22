# LEARNING_GEMINI.md

This guide provides the essential commands and workflows for using Gemini CLI effectively, focusing on resolving bugs, starting projects from scratch, and understanding the different Gemini models.

---

## 1. Resolving a Bug

To resolve a bug efficiently, follow this structured workflow:

1.  **Analyze the Codebase**: Use `analyze` to understand the relevant files and logic.
    ```bash
    gemini-cli analyze [path/to/files]
    ```
2.  **Reproduce the Bug**: Write a test case or script to confirm the failure state.
3.  **Generate a Fix**: Ask Gemini CLI to propose and implement a solution.
    ```bash
    gemini-cli ask "Fix the bug where [description] in [file_path]"
    ```
    Alternatively, use the interactive chat for complex fixes:
    ```bash
    gemini-cli chat
    ```
4.  **Verify the Changes**: Review the differences and run your tests.
    ```bash
    gemini-cli diff
    gemini-cli status
    ```
5.  **Finalize**: If the fix is verified, commit your changes.

---

## 2. Creating a Project from Scratch

To start a new project from the ground up:

1.  **Initialize the Project**:
    ```bash
    gemini-cli init
    ```
2.  **Define Project Structure**: Ask Gemini CLI to suggest a layout.
    ```bash
    gemini-cli ask "Suggest a project structure for a [language] [application type]"
    ```
3.  **Generate Core Logic**: Progressively build out features.
    ```bash
    gemini-cli ask "Create a basic [language] application with [features]"
    ```
4.  **Iterate and Refine**: Use `chat` to refine the implementation based on your feedback.

---

## 3. Gemini Models

Gemini CLI leverages state-of-the-art models for different use cases. The latest generation is **Gemini 3**:

-   **Gemini 3 Pro**:
    *   **Best for**: Complex reasoning, massive context analysis (up to 2M+ tokens), multi-file bug fixing, and advanced agentic workflows.
    *   **Capabilities**: Superior at solving architectural problems and deep code analysis. It is the recommended model for "Pro" usage.
-   **Gemini 3 Flash**:
    *   **Best for**: Low-latency tasks, quick code edits, documentation, and high-volume automated scripts.
    *   **Capabilities**: Extremely fast and cost-efficient while maintaining high reasoning quality.

### How to Specify the Model
You can select or switch models using these methods:

-   **CLI Flag**: Use the `--model` (or `-m`) flag.
    ```bash
    gemini --model gemini-3-pro-preview
    ```
-   **Interactive Command**: Within a chat session, use:
    ```bash
    /model
    ```
-   **Configuration**: Manage standard settings using the interactive menu:
    ```bash
    /settings
    ```
-   **Preview Features**: To enable preview features (required for Gemini 3 access), manually edit your settings file (`~/.gemini/settings.json` for global or `.gemini/settings.json` for the workspace) to include:
    ```json
    {
      "experimental": {
        "previewFeatures": true
      }
    }
    ```
    Once enabled, the `auto` setting will resolve to Gemini 3 Pro by default.

---

## 4. Essential Commands & Tips

-   **Get Help**:
    *   `/help`: Lists available subcommands.
    *   `/tools`: Shows all tools Gemini CLI can execute (e.g., file operations, searches).
-   **Analyze Your Work**:
    *   `gemini-cli diff`: Shows changes made by the AI.
    *   `gemini-cli status`: Summarizes the current state of the workspace.
-   **Settings & Customization**:
    *   `/settings`: Opens the interactive settings editor for all configurations (Note: Use plural `/settings`; the singular `/setting` is not supported for feature management).
    *   `/skills list`, `/skills enable <name>`: Manage Agent Skills.
    *   `/hooks list`, `/hooks enable <name>`: Manage lifecycle hooks.
    *   `/ide enable`: Toggle IDE integration.
-   **Specialized Sub-Agents**:
    *   `codebase_investigator`: Use this for deep dives into unknown codebases.
    *   `cli_help`: Ask specific questions about Gemini CLI features.

---

*Stay efficient and build better with Gemini CLI.*
