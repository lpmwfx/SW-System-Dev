# SW-System Restructuring Plan

## Overview

This document outlines the plan for restructuring the `SW-System` repository to align with the defined SagasWeave architecture. The goal is to ensure `SW-System` functions purely as a core engine providing shared services, development automation, and foundational infrastructure, while moving development-specific documentation, project management artifacts, and remnants of previous applications to their appropriate locations, primarily within `SW-System-Dev`.

## Current State Analysis of SW-System

Based on the current directory listing, `SW-System` contains a mix of core system components, development-specific documentation, project management files, and potentially remnants from previous iterations.

### Key Observations:
- **Core System Files**: `package.json`, `package-lock.json`, `tsconfig.base.json`, `biome.json`, `vitest.config.e2e.ts`, `.ast-grep.yml`, `.comby.toml` are core configuration and tooling files.
- **Scripts**: The `scripts/` directory contains automation scripts, including `mcp-services`, which are central to `SW-System`'s role.
- **Documentation (Mixed)**: The `docs/` directory contains `contract`, `howto`, `prd`, `project`, and `techstack` subdirectories. Some of these, especially `prd` and `project/sprints`, seem more aligned with `SW-System-Dev`'s project management and documentation responsibilities rather than `SW-System`'s core engine function.
- **VSCode/Trae Configuration**: `.vscode/` and `.trae/` directories contain IDE-specific configurations, which are development environment concerns.
- **Reminiscences**: `README-naming-tools.md`, `SW-AIdriven.code-workspace`, `mcp-server.log`, `mcp-server.pid` might be temporary or specific to past development phases.

## Proposed Restructuring

### 1. Files/Folders to Remain in SW-System (Core Engine)

These are essential for `SW-System`'s role as the core engine and service provider:

-   `.ast-grep.yml`: Configuration for AST-based code analysis/transformation.
-   `.comby.toml`: Configuration for Comby code transformation.
-   `.gitignore`: Standard Git ignore file for the repository.
-   `biome.json`: Code formatting and linting configuration.
-   `package.json`, `package-lock.json`: Node.js project dependencies and metadata.
-   `scripts/`: Contains core automation scripts and MCP services.
    -   `auto-fix-naming.js`
    -   `auto-move-to-shared.js`
    -   `mcp-auto-start.sh`
    -   `mcp-services/` (and its contents, as these are core MCP services)
    -   `refactor-naming.js`
    -   `validate-naming.js`
-   `tsconfig.base.json`: Base TypeScript configuration for shared modules.
-   `vitest.config.e2e.ts`: End-to-end testing configuration for system services.

### 2. Files/Folders to Move to SW-System-Dev (Development Environment/Documentation)

These files and folders are related to project development, documentation, and IDE configuration, and should reside in `SW-System-Dev`.

-   `.trae/`: Move to `SW-System-Dev/.trae/`
    -   `rules/project_rules.md`
-   `.vscode/`: Move to `SW-System-Dev/.vscode/`
    -   `launch.json`
    -   `tasks.json`
-   `docs/`: This entire directory should be reviewed and its contents moved to appropriate places within `SW-System-Dev/docs/`.
    -   `contract/`: Move to `SW-System-Dev/docs/contract/`
        -   `code-quality-rules.md`
        -   `contract-rules.md`
    -   `howto/`: Move to `SW-System-Dev/docs/howto/`
    -   `prd/`: Move to `SW-System-Dev/docs/prd/`
        -   `01-dashboard.md`
        -   `02-editor.md`
        -   `03-version-control.md`
        -   `04-ui-ux-design.md`
    -   `project/`: Move to `SW-System-Dev/docs/project/` (or specific sub-folders like `building_docs`)
        -   `naming-automation.md`
        -   `sprints/` (all sprint-related documentation)
        -   `sw-naming-book.json`
    -   `techstack/`: Move to `SW-System-Dev/docs/techstack/`
        -   `01-techstack-toolbox.md`

### 3. Files/Folders to Delete or Re-evaluate (Reminiscences/Temporary)

These files appear to be temporary or remnants and should be removed or re-evaluated for their necessity.

-   `README-naming-tools.md`: Content should be integrated into relevant documentation in `SW-System-Dev/docs/project/` or `SW-System-Dev/docs/howto/`.
-   `SW-AIdriven.code-workspace`: This is a workspace file and should reside in the root of `SagasWeaveProject` or `SW-System-Dev` if it's a development-specific workspace.
-   `mcp-server.log`: Log files should typically be excluded from version control and managed by the application itself.
-   `mcp-server.pid`: PID files are temporary process identifiers and should not be version controlled.

## Action Plan (High-Level Steps)

1.  **Create Target Directories**: Ensure all necessary target directories exist in `SW-System-Dev` (e.g., `SW-System-Dev/.trae/`, `SW-System-Dev/.vscode/`, `SW-System-Dev/docs/contract/`, etc.).
2.  **Move Files/Folders**: Systematically move the identified files and folders from `SW-System` to their new locations in `SW-System-Dev`.
3.  **Delete Files**: Remove the identified temporary/reminiscent files from `SW-System`.
4.  **Update References**: Review any internal references within `SW-System` or `SW-System-Dev` that might point to the old locations of moved files.
5.  **Verify Functionality**: Ensure that `SW-System` still functions correctly as a standalone core engine and that the development environment in `SW-System-Dev` is complete and operational.

This restructuring will create a cleaner, more focused `SW-System` repository and consolidate development-specific concerns within `SW-System-Dev`, adhering to the principles of clear separation of concerns and maintainability.