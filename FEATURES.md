### Feature: Project Setup Automation

## Problem Solved

Current project initialization requires multiple manual steps (folders, Git, config), slowing down developers and introducing inconsistencies across languages and frameworks.

## Solution Overview

Automates project creation by generating folders, initializing Git, adding configuration files, and optionally installing language-specific packages in one command.

## User Flow

1. Run `lazy <language> init` to start project setup (e.g., `lazy node-js init`, `lazy python init`).  
2. CLI asks if the user wants to install optional packages relevant to the chosen language/framework:  
   - User answers `1` (YES) or `-1` (NO) for each package.  
   - User enters `0` to finish the package selection process.  
3. CLI asks if the user wants to apply a folder structure:  
   - `1` (YES) → user chooses **Modular**, **MVP**, or **Monorepo**.  
   - `0` (NO) → skips folder structure setup.  
4. CLI installs selected packages via the appropriate package manager and applies chosen folder structure from GitHub.  
5. Project is ready to run: developer can use the standard command to start the project (e.g., `npm start`, `python manage.py runserver`, etc.).  
6. Same workflow applies to all supported stacks and languages.

## Technical Details

* **Implementation**: Modular Bash scripts with language-specific command modules.  
* **Dependencies**: Optional language/framework packages installed via package managers (npm, pip, etc.).  
* **Non-Functional**: Packages come from official package registries; folder structures and templates are fetched from GitHub.

## Acceptance Criteria

* [ ] Users can select/deselect optional packages during init.  
* [ ] Users can apply Modular, MVP, or Monorepo folder structures from GitHub.  
* [ ] Initialized project is immediately runnable with the appropriate start command.  

## Status & Roadmap

* **Current**: Modular version published.  
* **Version**: v1.0.1  
* **Next**: Add more language support and stabilize core init workflow with package suggestion.

## Contribution Notes

Help wanted? PRs for additional templates, folder structures, or new language support welcome. See CONTRIBUTING.md.
