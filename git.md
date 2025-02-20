# Git

## Basic Commands
```bash
git init                	# Initialize a new Git repository
git clone <repo_url>    	# Clone an existing repository
git status              	# Check the status of changes
git add <file>          	# Stage a specific file
git add .               	# Stage all changes
git commit -m "Message" 	# Commit changes with a message
git push origin main    	# Push changes to remote repository
git pull origin main    	# Pull latest changes from remote
```

## Branching
```bash
git branch <branch-name>    # Create a new branch
git branch                  # List all branches
git checkout <branch>       # Switch to a branch
git switch <branch>         # Alternative to checkout
git merge <branch>          # Merge a branch into current
git branch -d <branch>      # Delete a branch (only if merged)
git branch -D <branch>      # Force delete a branch
```

## Undoing Changes

```bash
git reset --soft HEAD~1   # Undo last commit, keep changes staged
git reset --hard HEAD~1   # Undo last commit and discard changes
git revert HEAD           # Create a new commit that reverts the last commit
git checkout HEAD~1 file.txt  # Restore a file from previous commit
```

### Reset vs Revert vs Checkout
| Command | Effect | Use Case |
|---------|--------|----------|
| `git reset --soft <commit>` | Moves HEAD back, **keeps changes staged** | Undo last commit but keep staged |
| `git reset --mixed <commit>` *(default)* | Moves HEAD back, **unstages changes** but keeps them | Undo last commit and edit files |
| `git reset --hard <commit>` | Moves HEAD back, **deletes all changes** | Completely discard changes |
| `git revert <commit>` | Creates a new commit that **undoes** the specified commit | Undo a commit without rewriting history |
| `git checkout <commit> -- <file>` | Restore file to an older state | Undo changes to a specific file |

## Viewing History
```bash
git log                  # Show commit history
git log --oneline        # Show history in one-line format
git log --graph --decorate --oneline  # Pretty log with branch info
git diff                 # Show unstaged changes
git diff --staged        # Show staged changes
git show <commit>        # Show changes of a commit
```

## Remote Repositories
```bash
git remote -v               # Show remote URLs
git remote add origin <url> # Add a new remote repository
git push origin <branch>    # Push changes to remote branch
git pull origin <branch>    # Fetch and merge latest changes
git fetch                   # Download changes without merging
git merge origin/main       # Merge remote changes into current branch
```

### Pull vs Fetch vs Fork
| Concept | Description |
|---------|-------------|
| **Pull (`git pull`)** | Downloads changes from remote **and merges** them into the current branch. |
| **Fetch (`git fetch`)** | Downloads changes from remote **without merging** them. You can later inspect and merge them manually. |
| **Fork** | A **copy of a repository** made in your own GitHub account. It allows you to make changes independently from the original repository. |

#### Example Usage:
- **`git pull`** → You want to **update** your branch with the latest changes from `origin/main`:
  ```bash
  git pull origin main
  ```
- **`git fetch`** → You want to **check for updates** without merging them:
  ```bash
  git fetch
  ```
  Then, you can view remote changes:
  ```bash
  git log origin/main --oneline
  ```
  If you decide to merge them:
  ```bash
  git merge origin/main
  ```
- **Forking** → You want to contribute to an open-source project:
  1. Fork a repository on GitHub.
  2. Clone your fork locally:
     ```bash
     git clone <your-fork-url>
     ```
  3. Make changes and push to your fork.
  4. Create a **pull request** to propose changes to the original project.

## Tags
```bash
git tag                     # List all tags
git tag <tag-name>          # Create a new tag
git tag -a <tag-name> -m "Tag message"  # Create annotated tag
git push origin <tag-name>  # Push a tag to remote
```

## Stashing (Save Changes Temporarily)
```bash
git stash                # Stash current changes
git stash list           # Show stashed changes
git stash apply          # Reapply last stash
git stash drop           # Delete last stash
git stash pop            # Apply and remove last stash
```

## Advanced Git Commands
```bash
git cherry-pick <commit>    # Apply a commit from another branch
git rebase <branch>         # Reapply commits on top of another branch
git bisect start            # Start a binary search for bugs
git reflog                  # View history of HEAD movements
```

---
### Reset vs Revert vs Checkout Explained
- **`reset`** moves the branch pointer back, **changing history** (use cautiously).
- **`revert`** creates a new commit **without deleting history**.
- **`checkout`** allows switching to a different commit **without modifying history**.

#### Example Scenario:
1. You made a wrong commit and **want to undo it completely**:  
   `git reset --hard HEAD~1`
2. You want to **undo a commit but keep the changes in working directory**:  
   `git reset --soft HEAD~1`
3. You **want to keep history intact but remove a commit**:  
   `git revert HEAD`

---
## Git Workflow Examples

### 1️ Standard Workflow (Cloning, Editing, and Pushing)
```bash
git clone <repo-url>        # Clone repository
git checkout -b feature-x   # Create and switch to a new branch
# Make changes...
git add .                   # Stage changes
git commit -m "Added feature X"
git push origin feature-x   # Push to remote
```

### 2️ Syncing with Remote
```bash
git pull origin main        # Get latest changes
git merge main              # Merge into current branch
```

### 3 Forking & Contributing (Open-Source)
```bash
# Fork a repository on GitHub, then:
git clone <your-fork-url>   # Clone fork
git remote add upstream <original-repo-url> # Link to original repo
git fetch upstream          # Get latest changes from original repo
git merge upstream/main     # Merge latest changes into forked repo
git push origin main        # Push updated fork
```

---

