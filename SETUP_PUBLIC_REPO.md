# Publishing `_showcase/` as a Standalone Public GitHub Repository

This guide provides the exact commands to initialize the `_showcase/` folder as its own completely independent Git repository with **zero commit history, source code, or secrets** from the parent private repository.

---

## Pre-Flight Security Check

1. **`_showcase/` is ignored by your private repo:**  
   `_showcase/` has been added to the root `.gitignore` of `k:\ginan`, so your private repository will not track this folder.
2. **Verify no sensitive files exist inside `_showcase/`:**  
   Only markdown documentation (`README.md`, `ARCHITECTURE.md`, `ASSETS_CHECKLIST.md`, `SETUP_PUBLIC_REPO.md`) and your curated public screenshots (`assets/`) should be inside `_showcase/`.

---

## Step-by-Step Git Commands (PowerShell / Terminal)

### Step 1: Create a New Empty Public Repository on GitHub
1. Go to [https://github.com/new](https://github.com/new).
2. Name the repository (e.g., `qasida-showcase` or `qasida-archive`).
3. Set visibility to **Public**.
4. **Do NOT** check "Add a README file", "Add .gitignore", or "Choose a license" (keep it completely empty).
5. Copy the new repository's HTTPS or SSH URL (e.g., `https://github.com/<your-username>/qasida-showcase.git`).

---

### Step 2: Initialize a Fresh Git Repository Inside `_showcase/`

Open PowerShell and navigate **directly into** the `_showcase/` directory:

```powershell
cd K:\ginan\_showcase
```

Initialize a brand-new Git repository (this creates a fresh `.git` folder inside `_showcase/` completely isolated from `K:\ginan\.git`):

```powershell
git init -b main
```

*(If your Git version is older and doesn't support `-b main`, run `git init` followed by `git checkout -b main`.)*

---

### Step 3: Verify Staged Files Before Committing

Stage all files inside `_showcase/` and inspect the status to confirm only showcase files are included:

```powershell
git add .
git status
```

Expected output:
```text
On branch main

No commits yet

Changes to be committed:
  new file:   ARCHITECTURE.md
  new file:   ASSETS_CHECKLIST.md
  new file:   README.md
  new file:   SETUP_PUBLIC_REPO.md
  new file:   assets/.gitkeep
```

---

### Step 4: Commit and Push to the Public Remote

Create the initial commit and push to your new public GitHub repository:

```powershell
git commit -m "docs: initial public architecture and showcase package"

# Replace with your actual public GitHub repository URL
git remote add origin https://github.com/Kashan-A1i/Qasida-Architecture.git

git push -u origin main
```

---

## Updating the Public Showcase Later

Whenever you capture your screenshots/GIFs (see `ASSETS_CHECKLIST.md`) or update the architecture docs:

```powershell
cd K:\ginan\_showcase
git add .
git commit -m "docs: add demo GIF and UI screenshots"
git push
```

Because `K:\ginan\_showcase` has its own `.git` directory and is listed in `K:\ginan\.gitignore`, all Git commands run inside `K:\ginan\_showcase` affect **only** the public showcase repository, while all Git commands run in `K:\ginan` affect **only** your private code repository.
