# Agent Installation & Project Setup Guide

This guide is intended for AI coding agents. Read all instructions carefully and execute the steps sequentially to initialize and align the project repository.

---

## Agent Instructions & Persona

- Execute steps sequentially. And display the step title.
- Verify requirements and file contents after creation.
- Adhere strictly to the technical stack, zero-secret policy, and file path constraints.
- **Absolute Rule on Markdown Files:** In all generated Markdown files (`specs/`, `proposals/`, `tasks/`, `docs/`, `adr/`), **NEVER** write absolute file paths (e.g. `file:///...`, `C:\...`, or `/Users/...`). Always use **relative paths** from the repository root (e.g. `src/app/core/services/...`).

---

## Step 0: Prérequis de l'environnement
Vérifie que les pré-requis suivants sont installés

1. Node.js v22+
2. pnpm installé globalement (npm install -g pnpm)

3. Si ce n'est pas le cas : on s'arrête là. stop and tell the user to install or upgrade

## Step : Package Manager & Environment Setup

1. Use **`pnpm`** as the exclusive package manager. Do not use `npm` or `yarn`.
2. Ensure Node.js (LTS) and `pnpm` are properly configured in the workspace.

## Step — Get the .gitignore

```bash
curl -fsSL https://raw.githubusercontent.com/briensbe/boostrap-template/refs/heads/main/.gitignore-template -o .gitignore
```

## Step — Get the AGENTS.md
### Créer le dossier .agents s'il n'existe pas et y télécharger AGENTS.md
```bash
mkdir -p .agents
curl -fsSL https://raw.githubusercontent.com/briensbe/boostrap-template/refs/heads/main/AGENTS-template.md -o AGENTS.md
```

## Step 2: Initialize Git Configuration (`.gitignore`)


## Step X - Supabase CLI  et init
Vérifie que Supabase CLI est installé (pnpm add -g supabase ou via Scoop/Brew)
