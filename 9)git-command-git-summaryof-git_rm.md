# Git RM — Complete Reference Guide

---

## What is `git rm`?

`git rm` removes a file from both the **working directory** and the **index (staging area)**, and stages that deletion so it can be committed.

```
HEAD (commit)  →  Index (Staging Area)  →  Working Directory
                        ❌ removed                ❌ deleted
```

---

## Command Variants

| Command | Removes from Index | Removes from Disk | Force Required? |
|---|---|---|---|
| `git rm file.txt` | ✅ Yes | ✅ Yes | Only if file has staged changes |
| `git rm --cached file.txt` | ✅ Yes | ❌ No (file stays on disk) | Only if file has staged changes |
| `git rm -f file.txt` | ✅ Yes | ✅ Yes | — (bypasses safety guard) |
| `git rm -r .` | ✅ Yes (recursive) | ✅ Yes (recursive) | Only if unrecoverable files exist |
| `git rm -r --cached .` | ✅ Yes (recursive) | ❌ No | Only if unrecoverable files exist |

---

## Does it Need a Commit After?

| Scenario | Example | Needs Commit After? | Reason |
|---|---|---|---|
| File was previously committed | `file6.txt` in HEAD | ✅ Yes | File exists in history — deletion must be recorded |
| File only in staging area, never committed | `file7.txt` only in index | ❌ No | Never entered history — nothing to record |
| File removed from index only (`--cached`) | Was committed before | ✅ Yes | Need to record untracking in history |

> **Simple Rule:** You can only "delete" something that officially exists in history.  
> If Git never recorded the file in a commit, there's nothing to officially delete.

---

## Git's Safety Guard

Git blocks `git rm` on files that **cannot be recovered**.

| File State | `git rm` | `git rm --cached` | `git rm -f` |
|---|---|---|---|
| Committed, no changes | ✅ Allowed | ✅ Allowed | ✅ Allowed |
| Committed, with unstaged changes | ❌ Blocked | ❌ Blocked | ✅ Force allowed |
| Staged only, never committed | ❌ Blocked | ❌ Blocked | ✅ Force allowed |
| Untracked (not in index at all) | ❌ Not applicable | ❌ Not applicable | ❌ Not applicable |

### Why does the safety guard exist?

```
Committed file → stored in Git history → always recoverable → Git allows rm
Staged-only file → never in history → permanently gone if deleted → Git blocks rm
```

---

## Recoverability Summary

| Command | File Was Committed? | Recoverable After? |
|---|---|---|
| `git rm file.txt` | ✅ Yes | ✅ Yes — restore from previous commit |
| `git rm file.txt` | ❌ No (staged only) | ❌ Blocked by Git |
| `git rm -f file.txt` | ❌ No (staged only) | ❌ **Gone forever** |
| `git rm --cached file.txt` | ✅ Yes | ✅ Yes — file still on disk |
| `git rm --cached file.txt` | ❌ No (staged only) | ❌ Blocked by Git |

---

## Common Use Cases

### 1. Delete a file and record it in history
```bash
git rm file.txt
git commit -m "remove file.txt"
```

### 2. Untrack a file without deleting it from disk
```bash
git rm --cached secrets.txt
# Add secrets.txt to .gitignore so it won't be tracked again
git commit -m "untrack secrets.txt"
```

### 3. Fix `.gitignore` not being respected
```bash
git rm -r --cached .       # Remove everything from index (files stay on disk)
git add .                  # Re-add everything, .gitignore now respected
git commit -m "fix: apply .gitignore correctly"
```

### 4. Force delete a file that was only staged (never committed)
```bash
git rm -f file7.txt        # ⚠️ Gone forever — no way to recover
```

---

## Quick Reference Card

```
git rm file.txt             → delete from disk + index, stage deletion
git rm --cached file.txt    → remove from index only, keep on disk
git rm -f file.txt          → force delete (bypasses safety guard)
git rm -r .                 → recursively remove all tracked files
git rm -r --cached .        → recursively remove from index only
```

---

## vs. Plain `rm` (OS delete)

| Action | Working Directory | Index | Needs Extra Step? |
|---|---|---|---|
| `rm file.txt` (OS) | ❌ Deleted | ✅ Still tracked | Yes — must run `git add -u` to stage deletion |
| `git rm file.txt` | ❌ Deleted | ❌ Removed | No — deletion already staged |