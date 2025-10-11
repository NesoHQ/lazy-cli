### Feature: Project Setup Automation

## Problem Solved

Current project initialization requires multiple manual steps (folders, Git, config), slowing down developers and introducing inconsistencies.

## Solution Overview

Automates project creation by generating folders, initializing Git, and adding configuration files in one command.

## User Flow

1. Run `lazy node-js init` to start project setup.  
2. CLI asks if the user wants to install optional Node.js packages (express, dotenv, nodemon, zod, etc.):  
   - User answers `1` (YES) or `-1` (NO) for each package.  
   - User enters `0` to finish the package selection process.  
3. CLI asks if the user wants to apply a folder structure:  
   - `1` (YES) → user chooses **Modular**, **MVP**, or **Monorepo**.  
   - `0` (NO) → skips folder structure setup.  
4. CLI installs selected packages via npm and applies chosen folder structure from GitHub.  
5. Project is ready to run: simply use `npm start` to launch.  
6. Same workflow applies to Next.js, Vite, Go, Python, and planned future stacks.

## Technical Details

* **Implementation**: Modular Bash scripts.  
* **Dependencies**: Optional npm packages (express, dotenv, nodemon, zod, etc.).  
* **Non-Functional**: Packages come from npm; folder structures and templates are fetched from GitHub.

## Acceptance Criteria

* [ ] Users can select/deselect optional packages during init.  
* [ ] Users can apply Modular, MVP, or Monorepo folder structures from GitHub.  
* [ ] Initialized project is immediately runnable with `npm start`.  

## Status & Roadmap

* **Current**: Modular version published.  
* **Version**: v1.0.1
* **Next**: Add more language support and stabilize core init workflow with package suggestion.

## Contribution Notes

Help wanted? PRs for additional templates, folder structures, or new language support welcome. See CONTRIBUTING.md.

