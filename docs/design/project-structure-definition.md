# SagasWeave Project Structure Definition

## 1. Introduction

This document defines the mandatory folder and file structure for the SagasWeave ecosystem. Adherence to this structure is crucial for maintaining consistency, enabling automation, and ensuring the project remains scalable and maintainable. All AI-driven and manual development must follow these guidelines.

## 2. Root Project Structure

The SagasWeave project is a monorepo managed with Git submodules or as separate repositories. The root will contain the primary repositories:

```
SagasWeaveProject/
├── SW-System/       # Core engine, automation, and shared services
├── SW-Book/         # Narrative content, authoring tools, and publishing automation
├── SW-App/          # User-facing application (React)
└── SW-System-Dev/   # Centralized documentation and dev environment config (this repo)
```

## 3. `SW-System` Structure

```
SW-System/
├── .github/              # GitHub-specific files (e.g., workflows for CI/CD)
├── scripts/              # Automation scripts (e.g., project init, content processing)
│   ├── mcp-services/     # MCP (AI) services
│   └── ...
├── src/                  # Source code for shared services and utilities
│   ├── core/             # Core functionalities (logging, config)
│   ├── services/         # Business-logic services
│   └── utils/            # Shared utility functions
├── tests/                # Tests for the core system
├── .gitignore
├── biome.json            # Biome configuration for code quality
├── package.json          # Project dependencies and scripts
├── tsconfig.json         # TypeScript configuration
└── README.md
```

## 4. `SW-Book` Structure

```
SW-Book/
├── content/              # Narrative content source files
│   ├── chapters/         # Main story chapters in Markdown/MDX
│   ├── characters/       # Character profiles
│   └── world/            # World-building documents
├── assets/               # Static assets (images, fonts)
├── scripts/              # Scripts for content transformation and publishing
├── .gitignore
├── package.json          # Dependencies for content tooling
└── README.md
```

## 5. `SW-App` Structure

```
SW-App/
├── public/               # Static assets for the web app
├── src/
│   ├── api/              # API-related logic (fetching data)
│   ├── assets/           # App-specific assets (CSS, images)
│   ├── components/       # Reusable React components
│   │   ├── common/         # Generic components (Button, Input)
│   │   └── layout/         # Layout components (Header, Footer)
│   ├── hooks/            # Custom React hooks
│   ├── pages/            # Page components corresponding to routes
│   ├── services/         # Frontend services (state management)
│   ├── styles/           # Global styles
│   ├── types/            # TypeScript type definitions
│   └── App.tsx           # Main application component
├── .gitignore
├── package.json
├── tsconfig.json
└── README.md
```

## 6. `SW-System-Dev` Structure

```
SW-System-Dev/
├── docs/
│   ├── prd/              # Product Requirements Documents
│   ├── design/           # Architecture and design documents (this file is here)
│   ├── sprints/          # Sprint plans and contracts
│   └── howto/            # Guides and tutorials
├── .gitignore
└── README.md
```