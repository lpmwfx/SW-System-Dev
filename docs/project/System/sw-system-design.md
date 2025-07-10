# SW-System Design Document

## Overview

SW-System serves as the core engine and reusable infrastructure for the SagasWeave platform. It provides development automation, code quality tools, and service templates that other projects (SW-Book, SW-App) can leverage.

## Current Implementation

### Actual Directory Structure
```
SW-System/
├── scripts/                    # Development automation tools
│   ├── auto-fix-naming.js         # Automated naming convention fixes
│   ├── auto-move-to-shared.js     # Code refactoring automation
│   ├── refactor-naming.js         # Manual naming refactoring
│   ├── validate-naming.js         # Naming convention validation
│   └── mcp-services/              # MCP server implementations
│       ├── mcp-npm-services-server/
│       └── mcp-npm-test-server/
├── codemods/                   # Code transformation tools
│   └── sw-naming-transform.js     # JSCodeshift transformations
├── docs/                       # Documentation and specifications
│   ├── contract/                  # Code quality and contract rules
│   ├── prd/                      # Product requirement documents
│   ├── project/                  # Project management docs
│   └── techstack/                # Technology stack documentation
├── .ast-grep.yml              # AST-grep configuration
├── .comby.toml                # Comby transformation patterns
├── biome.json                 # Biome linter/formatter config
├── package.json               # NPM scripts and dependencies
└── vitest.config.e2e.ts       # E2E testing configuration
```

## Core Responsibilities

### 1. Development Automation
- **Naming Convention Enforcement**: Automated validation and fixing of naming conventions
- **Code Quality Tools**: Biome, AST-grep, and Comby integration
- **Refactoring Automation**: Automated code transformations and improvements
- **Testing Infrastructure**: E2E testing setup with Vitest

### 2. MCP Services
- **NPM Services Server**: Automated NPM script execution and management
- **Test Server**: Testing automation and validation services
- **Service Templates**: Reusable MCP server patterns

### 3. Code Transformation
- **JSCodeshift Codemods**: Automated code transformations
- **AST-grep Rules**: Structural code analysis and fixes
- **Comby Patterns**: Pattern-based code transformations

### 4. Configuration Management
- **Shared Configurations**: Biome, TypeScript, and testing configs
- **Naming Book**: Centralized naming convention definitions
- **Project Templates**: Standardized project structure patterns

## Technology Stack

### Core Technologies
- **Node.js** (LTS) - Runtime environment
- **TypeScript** - Type-safe development
- **Biome** - Code formatting and linting
- **Vitest** - Testing framework

### Development Tools
- **AST-grep** - Code transformation and analysis
- **Comby** - Structural search and replace
- **JSCodeshift** - JavaScript/TypeScript codemods
- **MCP Servers** - AI service integration

## Service Delivery Pattern

### Naming Convention Services
```bash
# Validate naming across project
npm run test:naming

# Auto-fix naming violations
npm run fix:naming

# Interactive naming fixes
npm run fix:naming:interactive
```

### Code Quality Services
```bash
# Run all quality checks
npm run naming:check-all

# Apply all automated fixes
npm run naming:fix-all

# Format code with Biome
npm run format:biome
```

### Refactoring Services
```bash
# Run JSCodeshift transformations
npm run refactor:jscodeshift

# Apply AST-grep fixes
npm run refactor:ast-grep:fix

# Move code to shared locations
npm run move:shared
```

## Integration with Other Projects

### SW-Book Integration
- Provides naming convention validation for content management
- Offers code quality tools for publishing automation
- Supplies MCP services for content processing

### SW-App Integration
- Delivers frontend code quality standards
- Provides component naming conventions
- Offers automated refactoring for UI components

## Future Enhancements

### Service Templates
- Create reusable service templates in `service-templates/`
- Develop initialization scripts in `init-scripts/`
- Build automation workflows in `automation/`

### Engine Components
- Implement core reusable components in `engine/`
- Create shared utilities and helpers
- Develop cross-project automation tools

### Configuration Expansion
- Centralize shared configurations in `shared-configs/`
- Create environment-specific overrides
- Implement project-specific customization patterns

## Benefits

### For Development Teams
- **Consistent Code Quality**: Automated enforcement of naming and coding standards
- **Rapid Development**: Pre-configured tools and automation scripts
- **Reduced Manual Work**: Automated refactoring and code transformations
- **Standardized Patterns**: Consistent project structure and conventions

### For AI Integration
- **Predictable Structure**: Standardized naming and file organization
- **Automated Workflows**: MCP services for AI-assisted development
- **Template-Based Generation**: Consistent patterns for code generation
- **Quality Assurance**: Automated validation and fixing of code issues

## Conclusion

SW-System successfully implements the core engine concept with robust development automation, code quality tools, and service integration. The current implementation provides a solid foundation for expanding into the full service template and initialization system envisioned in the architecture.