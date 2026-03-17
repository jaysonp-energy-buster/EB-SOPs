---
title: How to Use the EB-SOPs Repository
owner: Jayson P
created: 2026-03-16
last_reviewed: 2026-03-16
status: active
---

# How to Use the EB-SOPs Repository

## Purpose

This SOP explains how to create, upload, edit, and manage SOPs in the EB-SOPs GitHub repository so the team follows a consistent workflow.

## Scope

All Energy Buster team members who need to create or update SOPs.

## Prerequisites

- A GitHub account with access to the `jaysonp-energy-buster/EB-SOPs` repository
- Git installed on your computer ([download here](https://git-scm.com/downloads))
- Basic familiarity with Git commands (clone, branch, commit, push)

---

## Procedure

### 1. First-Time Setup (Clone the Repo)

```bash
git clone https://github.com/jaysonp-energy-buster/EB-SOPs.git
cd EB-SOPs
```

You only need to do this once. After cloning, you have a local copy to work from.

---

### 2. Creating a New SOP

**Step 1 — Pull the latest changes**

```bash
git checkout main
git pull origin main
```

**Step 2 — Create a new branch**

Name your branch after the SOP you're creating:

```bash
git checkout -b sop/your-sop-name
```

Example: `git checkout -b sop/client-onboarding`

**Step 3 — Copy the template**

Copy `TEMPLATE.md` into the appropriate folder and rename it using the naming convention `NNN-sop-name.md`:

```bash
cp TEMPLATE.md "SOPs/Deployment/002-your-sop-name.md"
```

Choose the right folder:
| Folder | Use for |
|--------|---------|
| `SOPs/Archive/` | Archived/retired SOPs |
| `SOPs/Automation/` | Automation procedures |
| `SOPs/C&I/` | Commercial & Industrial |
| `SOPs/C&I Training/` | C&I training materials |
| `SOPs/Deployment/` | Deployment procedures |
| `SOPs/Engineering Team Procedures/` | Engineering team processes |
| `SOPs/General Tutorials/` | General how-to guides & tutorials |
| `SOPs/iAuditor/` | iAuditor-related procedures |
| `SOPs/Monitoring/` | Monitoring procedures |
| `SOPs/Pricing/` | Pricing procedures |
| `SOPs/Project Resources/` | Project resource docs |
| `SOPs/PVWise/` | PVWise-related procedures |
| `SOPs/SAM/` | SAM-related procedures |
| `SOPs/SolarProof Eng & IT/` | SolarProof engineering & IT |
| `SOPs/Sustainable Savings Tool Development/` | Sustainable Savings Tool dev |

**Step 4 — Write your SOP**

Open the new file in your editor and fill in all sections: title, purpose, scope, prerequisites, and procedure. Update the frontmatter at the top (title, owner, created date, status).

**Step 5 — Commit and push your branch**

```bash
git add SOPs/operations/002-your-sop-name.md
git commit -m "Add SOP: your sop name"
git push -u origin sop/your-sop-name
```

**Step 6 — Open a Pull Request**

1. Go to the repo on GitHub
2. You'll see a prompt to create a PR for your recently pushed branch — click it
3. Add a short description of the SOP
4. Request a review from a teammate
5. Once approved, merge the PR into `main`

---

### 3. Updating an Existing SOP

1. Pull the latest `main`: `git checkout main && git pull origin main`
2. Create a branch: `git checkout -b update/sop-name`
3. Make your edits to the SOP file
4. Update the `last_reviewed` date in the frontmatter
5. Commit, push, and open a PR (same as steps 5–6 above)

---

### 4. Uploading an Existing Document as an SOP

If you have an SOP written outside of this repo (e.g., in Google Docs or Word):

1. Create a branch as described in Step 2 above
2. Convert the content to Markdown format
3. Paste it into a new file using the naming convention (`NNN-sop-name.md`)
4. Add the frontmatter from the template at the top of the file
5. Commit, push, and open a PR

---

### 5. Reviewing a Pull Request

1. Go to the **Pull Requests** tab on GitHub
2. Open the PR and read the changes
3. Leave comments if anything needs revision
4. Approve the PR when it's ready
5. The author (or reviewer) merges the PR into `main`

---

### 6. Finding an SOP

- **On GitHub:** Browse the `SOPs/` folders or use the search bar at the top of the repo
- **Locally:** Use your file explorer or run `ls SOPs/operations/` (or any subfolder)

---

## Quick Reference

| Action | Command |
|--------|---------|
| Clone the repo | `git clone https://github.com/jaysonp-energy-buster/EB-SOPs.git` |
| Pull latest | `git pull origin main` |
| Create branch | `git checkout -b sop/name` |
| Stage files | `git add SOPs/folder/file.md` |
| Commit | `git commit -m "Add SOP: name"` |
| Push branch | `git push -u origin sop/name` |
| Switch to main | `git checkout main` |

## Notes

- Never push directly to `main` — always use a branch and PR.
- Use the `TEMPLATE.md` as your starting point for every new SOP.
- Number your SOPs sequentially within each folder (001, 002, 003...).
- If you're unsure which folder to use, ask the team or default to `operations/`.
