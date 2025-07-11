# SagasWeave Technology Stack

## 1. Introduction

This document outlines the official technology stack for the SagasWeave project. All development must adhere to this list of approved technologies, libraries, and tools to ensure consistency, maintainability, and interoperability across the ecosystem.

## 2. Core Technologies

| Category             | Technology / Tool                               | Purpose                                                                          |
| -------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------- |
| **Runtime**          | [Node.js](https://nodejs.org/) (LTS Version)    | The primary backend runtime for `SW-System` and all scripting.                   |
| **Language**         | [TypeScript](https://www.typescriptlang.org/)   | Enforces type safety across all repositories (`SW-System`, `SW-App`, `SW-Book`). |
| **Package Manager**  | [npm](https://www.npmjs.com/)                   | For managing project dependencies and running scripts.                           |

## 3. `SW-System` - Core Engine & Automation

| Category             | Technology / Tool                               | Purpose                                                                          |
| -------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------- |
| **Code Quality**     | [Biome](https://biomejs.dev/)                   | All-in-one tool for linting, formatting, and more. Replaces ESLint/Prettier.     |
| **Testing**          | [Vitest](https://vitest.dev/)                   | A fast and modern testing framework for unit and integration tests.              |
| **Code Transformation** | [AST-grep](https://ast-grep.github.io/)      | For structural search and replacement of code, ideal for large-scale refactoring. |
| **Code Transformation** | [Comby](https://comby.dev/)                     | For syntax-aware code search and replacement, useful for renaming and refactoring. |
| **AI Integration**   | Custom MCP Server                               | A custom-built server to facilitate communication between the system and AI agents. |

## 4. `SW-Book` - Content & Authoring

| Category             | Technology / Tool                               | Purpose                                                                          |
| -------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------- |
| **Content Format**   | [Markdown/MDX](https://mdxjs.com/)              | For writing narrative content. MDX allows embedding interactive components.      |
| **Authoring Tools**  | [Obsidian](https://obsidian.md/), [Textastic](https://www.textasticapp.com/) | Recommended mobile-first editors for a seamless writing experience.              |
| **Mobile Sync**      | [Working Copy](https://workingcopy.app/)        | A Git client for iOS to sync content from mobile devices to the repository.      |

## 5. `SW-App` - Frontend Application

| Category             | Technology / Tool                               | Purpose                                                                          |
| -------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------- |
| **Framework**        | [React](https://react.dev/)                     | The core library for building the user interface.                                |
| **Build Tool**       | [Vite](https://vitejs.dev/)                     | A fast and modern build tool for frontend development.                           |
| **Styling**          | CSS Modules / Styled Components                 | For scoped and maintainable component-level styling. **No inline styles.**       |
| **State Management** | [Zustand](https://zustand-demo.pmnd.rs/)        | A small, fast, and scalable state management solution.                           |
| **Routing**          | [React Router](https://reactrouter.com/)        | For handling navigation and routing within the single-page application.          |

## 6. Cross-Cutting Concerns

| Category             | Technology / Tool                               | Purpose                                                                          |
| -------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------- |
| **Version Control**  | [Git](https://git-scm.com/) & [GitHub](https://github.com/) | For source code management, collaboration, and versioning.                       |
| **CI/CD**            | [GitHub Actions](https://github.com/features/actions) | For automating testing, building, and deployment pipelines for all repositories.   |
| **Deployment**       | VPS / Static Hosting (e.g., Vercel, Netlify)    | `SW-System` is designed for a VPS. `SW-App` will be deployed to a static host.    |