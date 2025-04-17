# 📘 Version Control System (VCS) 

## 📌 What is a Version Control System?

A **Version Control System (VCS)** is a tool that helps developers manage and track changes to source code over time. It allows multiple people to work on the same codebase, keeps a history of changes, and facilitates collaboration and code recovery.

---

## 🎯 Why Use a Version Control System?

- ✅ Track changes and history
- ✅ Collaborate across teams
- ✅ Revert to previous versions
- ✅ Branch and experiment without affecting production
- ✅ Increase code quality and reliability
- ✅ Backup source code securely

---

## 🧰 Types of Version Control Systems

### 1. **Local VCS**
- Stores versions on a local machine
- Example: RCS (Revision Control System)

### 2. **Centralized VCS (CVCS)**
- Single central server stores all versions
- Developers check out and commit to this server
- Examples: CVS, Subversion (SVN), Perforce

### 3. **Distributed VCS (DVCS)**
- Every developer has a full copy of the repository
- Enables offline commits and full version history locally
- Examples: Git, Mercurial, Bazaar

---

## ✅ Advantages of VCS

- 🔄 Easy rollback and history tracking
- 👥 Supports team collaboration
- 🌿 Branching and merging support
- 🛡️ Backup and disaster recovery
- 📄 Detailed changelogs and auditing

---

## ❌ Disadvantages of VCS

- 🧠 Learning curve for new users
- ⚠️ Merge conflicts can be complex
- 💾 Large binary files may bloat repositories
- 🖥️ DVCS requires more local disk space

---

## 🔄 VCS Workflow (Git-based)

```mermaid
graph TD
A[Clone Repository] --> B[Create Branch]
B --> C[Make Changes]
C --> D[Stage Changes]
D --> E[Commit Changes]
E --> F[Push to Remote]
F --> G[Create Pull Request / Merge Request]
G --> H[Code Review]
H --> I[Merge to Main]

