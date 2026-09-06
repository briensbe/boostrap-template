# Agent Installation & Project Setup Guide

This guide is intended for AI coding agents. Read all instructions carefully and execute the steps sequentially to initialize and align the project repository.

---

## Agent Instructions & Persona

- Execute steps sequentially. And display the step title.
- Verify requirements and file contents after creation.
- Adhere strictly to the technical stack, zero-secret policy, and file path constraints.
- **Absolute Rule on Markdown Files:** In all generated Markdown files (`specs/`, `proposals/`, `tasks/`, `docs/`, `adr/`), **NEVER** write absolute file paths (e.g. `file:///...`, `C:\...`, or `/Users/...`). Always use **relative paths** from the repository root (e.g. `src/app/core/services/...`).

---

## Step : Prérequis de l'environnement
Vérifie que les pré-requis suivants sont installés

1. Node.js v22+
2. pnpm installé globalement (npm install -g pnpm)

3. Si ce n'est pas le cas : on s'arrête là. stop and tell the user to install or upgrade

## Step : Package Manager & Environment Setup

1. Use **`pnpm`** as the exclusive package manager. Do not use `npm` or `yarn`.
2. Ensure Node.js (LTS) and `pnpm` are properly configured in the workspace.


## Step: Angular 22 Project Initialization with pnpm

Ask the user for the project name (default: `my-angular-app`).

1. Prompt the user for `<PROJECT_NAME>`.
2. Check if a directory with this name already exists.
**If it does not exist:** Ask the user whether they want to create it (`[y/N]`)
3. Check if `<PROJECT_NAME>` already contains an Angular project (`angular.json` or `@angular/core` in `package.json`).
4. **If already an Angular project:** Inform the user, skip project creation, and navigate to the projetc directory.
5. **If directory exists but is NOT an Angular project:** Warn the user and ask for confirmation before scaffolding.
6. **If directory does not exist:**  Create an Angular app with Angular version 22 **mandatory**, Standalone components, native CSS, standard routing, no SSR, and `pnpm` as the package manager.
7. Navigate into the newly created directory.


## Step : Download Configuration Templates

<!-- Il n'y a plus besion de demander la création car c'est fait avec le projet Angular créé avant  -->
<!-- Ask the user for the target project directory path `<TARGET_DIR>` (default: `.`).
Check if the directory `<TARGET_DIR>` already exists
**If it does not exist:** Ask the user whether they want to create it (`[y/N]`) -->

For each target file:
1. Check if the file already exists in `<TARGET_DIR>`.
2. **If it exists:** Ask the user whether they want to overwrite it (`[y/N]`), keep the current version, or append missing sections.
3. **If it does not exist:** Download and create the file automatically.

### Target Files Map 

| Remote Source URL | Local Target Path |
| :--- | :--- |
| `https://raw.githubusercontent.com/briensbe/boostrap-template/refs/heads/main/.gitignore-template` | `<TARGET_DIR>/.gitignore` |
| `https://raw.githubusercontent.com/briensbe/boostrap-template/refs/heads/main/AGENTS-template.md` | `<TARGET_DIR>/.agents/AGENTS.md` |


<!--
 ## Step — Get the .gitignore
```bash
curl -fsSL https://raw.githubusercontent.com/briensbe/boostrap-template/refs/heads/main/.gitignore-template -o .gitignore
```

## Step — Get the AGENTS.md
### Créer le dossier .agents s'il n'existe pas et y télécharger AGENTS.md
```bash
mkdir -p .agents
curl -fsSL https://raw.githubusercontent.com/briensbe/boostrap-template/refs/heads/main/AGENTS-template.md -o AGENTS.md
``` -->

## Step : Initialiser OpenSpec avec les schémas ADR (openspec-with-adr).
Read this file: https://raw.githubusercontent.com/intent-driven-dev/openspec-schemas/refs/heads/main/AGENT_INSTALL.md and follow the instructions.

<!-- temporairement je désactive ça  -->
## Step: Git Repository Initialization

<!-- Il n'y a plus besoin de demander la création car c'est fait avec le projet Angular créé avant  -->
<!-- Ask the user for the project target directory (`TARGET_DIR`, default: `.`). -->

The agent must ensure that a Git repository is initialized in `<TARGET_DIR>`:

1. Check if a `.git` directory already exists.
2. If not initialized, run `git init` with the default initial branch set to `main`.


<!-- Pour l'instant on ne gère pas supabase dans l'installation de base. -->
<!-- ## Step X - Supabase CLI  et init
Vérifie que Supabase CLI est installé (pnpm add -g supabase ou via Scoop/Brew) -->
