# Skill-1: Git Version Control

| Field   | Details                                             |
|---------|-----------------------------------------------------|
| Student | Ch. Venkata Sai Nikesh                              |
| ID      | 2400080138                                          |
| Section | 51                                                  |
| GitHub  | https://github.com/NIkesh7474/FSAD-Skill-1          |

---

## Aim

To manage a software project using Git version control by simulating a real-world workflow — creating files, staging and committing changes, pushing to GitHub, working with multiple branches, and resolving merge conflicts.

---

## What is This Project?

This experiment simulates how developers use Git in real projects.

- Create project files and track changes
- Push code to GitHub as remote storage
- Work on separate branches for features and bug fixes
- Merge branches and resolve conflicts

---

## Key Git Commands

| Command                  | Purpose                                              |
|--------------------------|------------------------------------------------------|
| git init                 | Initialize a new Git repository                      |
| git config               | Set global username and email                        |
| git status               | Check state of working directory and staging area    |
| git add .                | Stage all modified and new files                     |
| git commit -m            | Record staged changes with a message                 |
| git remote add origin    | Link local repo to remote GitHub repository          |
| git push                 | Upload local commits to remote repository            |
| git checkout -b          | Create and switch to a new branch                    |
| git merge                | Integrate changes from one branch into current       |
| git log --oneline        | Display compact history of commits                   |

---

## Project Structure
```
FullStack-Skill-1/
├── main.java       (Java file with feature and bug fix changes)
├── notes.txt       (Project notes updated across branches)
└── README.md       (Project documentation)
```

---

## Branch Workflow

| Branch         | Action Performed                                  | Status           |
|----------------|---------------------------------------------------|------------------|
| main           | Initial commit — main.java and notes.txt created  | Active           |
| feature-update | Login module added to main.java and notes.txt     | Merged           |
| bug-fix        | Null pointer exception fix applied to main.java   | Merged (conflict resolved) |

---

## Step by Step Procedure

### Task 1 — Initialize Git Repository
```cmd
mkdir MyProject
cd MyProject
git init
git config --global user.name "VenkataSaiNikesh"
git config --global user.email "nikesh@email.com"
```

---

### Task 2 — Create Files and Stage
```cmd
echo public class Main {} > main.java
echo Project notes - v1.0 > notes.txt
git status
git add main.java notes.txt
git status
```

---

### Task 3 — Commit Files
```cmd
git commit -m "Initial commit: add main.java and notes.txt"
git log --oneline
```

**Output:**
```
a1b2c3d (HEAD -> main) Initial commit: add main.java and notes.txt
```

---

### Task 4 — Push to GitHub
```cmd
git remote add origin https://github.com/NIkesh7474/FSAD-Skill-1
git branch -M main
git push -u origin main
```

---

### Task 5 — Create Branch: feature-update
```cmd
git checkout -b feature-update
echo Feature: login module added >> main.java
echo Updated feature notes >> notes.txt
git add .
git commit -m "feature-update: added login module"
```

---

### Task 6 — Create Branch: bug-fix
```cmd
git checkout main
git checkout -b bug-fix
echo Bug fix: null pointer resolved >> main.java
git add .
git commit -m "bug-fix: resolved null pointer exception"
```

---

### Task 7 — Merge Both Branches into Main
```cmd
git checkout main
git merge feature-update
git merge bug-fix
```

**Output:**
```
CONFLICT (content): Merge conflict in main.java
Automatic merge failed; fix conflicts and commit.
```

---

### Task 8 — Resolve Merge Conflict
Conflict seen in main.java:
```
<<<<<<< HEAD
Feature: login module added
=======
Bug fix: null pointer exception resolved
>>>>>>> bug-fix
```

After manually editing to keep both changes:
```cmd
git add main.java
git commit -m "Merge bug-fix: resolved conflict in main.java"
```

---

## Git Log After All Merges
```
*   m1n2o3p (HEAD -> main) Merge bug-fix: conflict fix
|\
| * i7j8k9l (bug-fix) bug-fix: null pointer fix
* | e3f4g5h (feature-update) feature-update: login
|/
* a1b2c3d  Initial commit: add main.java and notes.txt
```

---

## Tasks Completed

- [x] Task 1 - Initialized Git repo and configured username and email
- [x] Task 2 - Created main.java and notes.txt, staged files
- [x] Task 3 - Committed staged files with meaningful message
- [x] Task 4 - Connected to GitHub and pushed commits
- [x] Task 5 - Created feature-update branch with login module
- [x] Task 6 - Created bug-fix branch with null pointer fix
- [x] Task 7 - Merged both branches into main
- [x] Task 8 - Resolved merge conflict manually and committed fix

---

## Git Commands to Push to GitHub
```cmd
cd C:\Users\HP\MyProject

git remote add origin https://github.com/NIkesh7474/FSAD-Skill-1
git branch -M main
git push -u origin main --force
