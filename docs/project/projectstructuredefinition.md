# Project Structure Definition for SagasWeave

This document defines the mandatory folder and file structure for the SagasWeave project. Adherence to this structure is crucial for maintaining consistency, facilitating collaboration, and ensuring the smooth operation of AI-driven development tools.

## 1. Root Directory (`SW-AIdriven`)
This is the core product directory. It should contain only essential files and folders required for the application to run and be deployed.

```
SW-AIdriven/
├── .vscode/                 # VSCode specific settings (launch.json, tasks.json)
├── docs/                    # Project documentation
│   ├── contract/            # Contract rules and templates
│   ├── howto/               # How-to guides
│   ├── prd/                 # Product Requirement Documents
│   ├── project/             # Project-specific documentation (this file, naming-automation, sprints)
│   └── techstack/           # Tech stack definitions
├── scripts/                 # Utility scripts (auto-fix-naming, mcp-services)
│   ├── mcp-services/        # MCP Server related scripts
├── src/                     # Source code (main application logic)
│   ├── assets/              # Static assets (images, fonts)
│   ├── components/          # Reusable UI components
│   ├── config/              # Configuration files (e.g., game.json, script-tags.json)
│   ├── core/                # Core logic and utilities
│   ├── data/                # Data models and interfaces
│   ├── features/            # Feature-specific modules
│   ├── hooks/               # React hooks
│   ├── layouts/             # Page layouts
│   ├── pages/               # Application pages/views
│   ├── services/            # API services, external integrations
│   ├── styles/              # Global styles, themes
│   ├── utils/               # General utility functions
│   └── index.ts             # Main entry point
├── tests/                   # Test files (separated from source code)
│   ├── unit/                # Unit tests
│   ├── integration/         # Integration tests
│   └── e2e/                 # End-to-end tests
├── .gitignore
├── package.json
├── package-lock.json
├── tsconfig.json
├── biome.json
├── vitest.config.ts
├── README.md
└── ... other essential config files
```

## 2. Development Directory (`SW-AIdriven-dev`)
This directory is intended for development-specific files, experimental features, and AI-generated content that is not yet ready for the main product. It helps keep the core product clean and focused.

```
SW-AIdriven-dev/
├── chatGpt/                 # AI-generated content, summaries, experimental prompts
├── experiments/             # Experimental code, proof-of-concepts
├── temp/                    # Temporary files, scratchpad
├── docs/                    # Development-specific documentation
│   ├── project/             # Project-specific documentation for dev environment
├── ... other development-related files
```

## 3. Naming Conventions
-   **Folders**: `kebab-case` (e.g., `my-feature-module`)
-   **Files**: `kebab-case` for general files (e.g., `my-component.tsx`), `PascalCase` for React components (e.g., `MyComponent.tsx`), `camelCase` for utility files (e.g., `myUtilityFunction.ts`).
-   **Components**: React components should be in their own file, named `PascalCase.tsx`.
-   **Tests**: Test files should mirror the structure of the `src` directory and end with `.test.ts` or `.spec.ts`.

## 4. File Content Guidelines
-   **Single Responsibility**: Each file should ideally have a single, well-defined purpose.
-   **Size Limits**: Keep files concise. Aim for under 300 lines of code (excluding comments and TSDoc). Max 500 lines including comments and TSDoc.
-   **No Inline Styling**: All styling must be done via external CSS/SCSS modules or styled-components, not inline.
-   **Unique Names**: Avoid generic names. Ensure unique names for variables, functions, classes, and imports within their respective scopes.

## 5. Documentation
-   All significant modules, functions, and components should have TSDoc comments.
-   Markdown files should be used for higher-level documentation, following the structure in the `docs/` directory.