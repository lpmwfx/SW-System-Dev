# Project Initialization

This document describes the process for initializing a new SagasWeave project, which involves setting up the repository structure and linking the core components (`SW-System`, `SW-Book`, `SW-App`) as Git submodules.

## Prerequisites

-   Git installed on your local machine.
-   Access rights to the SagasWeave GitHub repositories.

## Initialization Steps

1.  **Create the Root Project Directory**:
    Create a new directory for your project on your local machine. This will serve as the root for all the sub-repositories.

    ```bash
    mkdir MyNewSagasWeaveProject
    cd MyNewSagasWeaveProject
    ```

2.  **Initialize a Git Repository**:
    Initialize a new Git repository in the root directory. This will manage the submodules.

    ```bash
    git init
    ```

3.  **Add Core Repositories as Submodules**:
    Add the core SagasWeave repositories as submodules. This links them to your main project while keeping their Git histories separate.

    ```bash
    # Add the system engine
    git submodule add <URL_TO_SW_SYSTEM_REPO> SW-System

    # Add the book template
    git submodule add <URL_TO_SW_BOOK_REPO> SW-Book

    # Add the app template
    git submodule add <URL_TO_SW_APP_REPO> SW-App

    # Add the development/docs repository
    git submodule add <URL_TO_SW_SYSTEM_DEV_REPO> SW-System-Dev
    ```

    *Note: Replace `<URL_TO_..._REPO>` with the actual repository URLs.*

4.  **Commit the Submodules**:
    Commit the newly added submodules to your root repository. This saves the submodule configuration.

    ```bash
    git commit -m "Initial commit: Add SagasWeave core submodules"
    ```

5.  **Create a VSCode Workspace (Optional but Recommended)**:
    To make development easier, create a VSCode workspace file in the root directory (`.vscode/settings.json` or a `.code-workspace` file) to manage the multi-repository setup.

## Automated Initialization (`sw-init`)

The long-term vision is to automate this entire process with a single command, `sw-init`, provided by the `SW-System` repository. This script will handle:

-   Creating the directory structure.
-   Initializing the Git repository.
-   Adding the correct submodules.
-   Setting up default configuration files.

This will ensure that all new projects are set up consistently and correctly, following the architectural standards.