# SagasWeave Project Overview

## 1. Vision
SagasWeave is an AI-driven narrative development system designed to empower creators to build rich, interactive, and dynamic story experiences. It bridges the gap between high-level narrative concepts and executable code, leveraging AI as a co-editor and enabler throughout the development lifecycle.

## 2. Purpose
The primary purpose of SagasWeave is to provide a robust, text-based Domain Specific Language (DSL) for authoring scenes, user interfaces, game logic, and world-building elements. It aims to streamline the creation process by automating repetitive tasks, enforcing consistency, and facilitating rapid prototyping and iteration.

## 3. Core Principles
-   **AI as Co-Editor/Fallback**: AI is integrated not just for content generation, but as a tool for validation, correction, and optimization. It acts as a "fallback" mechanism, ensuring quality and adherence to project standards.
-   **Text-First Development**: All core content and logic are defined in Markdown files with semantic `::TAGs::`, making the project highly readable, version-controllable, and accessible.
-   **File-Based System**: "Everything is a file." This principle ensures modularity, portability, and ease of management.
-   **Automated Naming & Consistency**: Strict naming conventions, enforced by `sw-naming-book.json` and automated tools, ensure a consistent and maintainable codebase.
-   **KISS (Keep It Simple, Stupid)**: Prioritize simplicity and clarity in design and implementation.
-   **DRY (Don't Repeat Yourself)**: Avoid redundant code and content through modular design and reusable components.
-   **SOLID & SPR (Single Responsibility Principle)**: Adhere to established software design principles for maintainability and scalability.

## 4. Key Components & Workflow
SagasWeave's workflow involves authoring Markdown files, which are then parsed, validated, and transformed into executable code. Key components include:
-   **Markdown Authoring**: Creators write narratives, UI definitions, and game logic using a custom Markdown syntax with semantic tags.
-   **`sw-naming-book.json`**: A central configuration for enforcing naming conventions across the project.
-   **`script-tags.json`**: Defines custom semantic tags used within Markdown for specific functionalities.
-   **`game.json`**: Global game configuration.
-   **Compiler (`sw-compile`)**: Processes Markdown files, validates structure, and generates platform-specific code.
-   **AI Task Runner (`ai-task-runner.ts`)**: Orchestrates AI operations for tasks like content generation, validation, and refactoring.
-   **Automated Tools**: Biome, AST-grep, JSCodeshift, and Comby are used for code formatting, linting, and automated refactoring, especially for naming consistency.
-   **MCP Server**: Provides a terminal-first interface for interacting with the SagasWeave system, enabling automated tasks and development workflows.

## 5. Target Platforms
SagasWeave aims to support a wide range of platforms, including:
-   Web (React)
-   iOS/Android (React Native)
-   Desktop (macOS, Windows via Tauri)
-   Terminal Preview

## 6. Development Environment
The project emphasizes a clean separation between the core product (`SW-AIdriven`) and development-related files (`SW-AIdriven-dev`) to ensure a streamlined deployment and maintenance process.