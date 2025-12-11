

---

- Installing Git on your system
    
- Setting up Git for the first time
    
- Creating your first repository
    
- Connecting to GitHub
    
- Pushing your code to GitHub
    
- Basic Git workflow
    

---

## Part 1: Installing Git

### Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install git -y
git --version
```

### Linux (Fedora/RHEL)

```bash
sudo dnf install git -y
git --version
```

### macOS

**Option 1: Using Homebrew (recommended)**

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install git
git --version
```

**Option 2: Install Xcode Command Line Tools**

```bash
xcode-select --install
```

### Windows

1. Download Git from [git-scm.com/download/win](https://git-scm.com/download/win)
    
2. Run the installer
    
3. Use default options
    
4. Open Git Bash
    
5. Check version: `git --version`
    

---

## Part 2: Creating a GitHub Account

1. Go to [github.com](https://github.com)
    
2. Click "Sign up" and follow instructions
    
3. Verify your email
    

> **Important Privacy Note**  
> Git embeds your **email address** into every commit. To keep it private:

```bash
git config --global user.email "12345678+yourusername@users.noreply.github.com"
```

---

## Part 3: First-Time Git Setup

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"  # use noreply email
git config --global init.defaultBranch main
git config --global core.editor "nano"  # optional
```

Check configuration:

```bash
git config --list
```

Optional: create safe directories for Git:

```bash
# Example to add safe directory globally
git config --global --add safe.directory /path/to/project
```

---

## Part 4: Your First Local Repository

### Step 1: Create Project Folder

```bash
mkdir my-project
cd my-project
echo "# My Project" > README.md
```

Or navigate to an existing folder:

```bash
cd path/to/project
```

### Step 2: Initialize Git

```bash
git init
```

### Step 3: Check Status

```bash
git status
```

### Step 4: Stage Files

```bash
git add README.md  # or git add . for all
```

### Step 5: Make First Commit

```bash
git commit -m "Initial commit"
git log
```

---

## Part 5: Connecting to GitHub

### Create Repository

1. Click **+ → New repository** on GitHub
    
2. Name repository and leave it empty
    
3. Copy HTTPS URL
    

### Add Remote and Push

```bash
git remote add origin <your-github-url>
git remote -v
git push -u origin main
```

---

## Part 6: Creating a Personal Access Token (PAT)

1. Go to **Settings / Developer settings / Personal access tokens / Tokens (classic) / Generate new token**
    
2. Name it, set expiration, and select `repo` permissions
    
3. Copy token immediately
    

---

## Part 7: Pushing to GitHub

### Connect and Push

```bash
git remote add origin <your-github-url>
git push -u origin main
```

---

## Part 8: Daily Git Workflow

1. Make changes
    
2. Check status: `git status`
    
3. Stage changes: `git add .`
    
4. Commit: `git commit -m "message"`
    
5. Push: `git push`
    

---

## Part 9: Essential Git Commands Cheat Sheet

```bash
git config --global user.name  "Your Name"
git config --global user.email "you@exampl.com"
git init
git clone <url>
git status
git add <file>
git add .
git commit -m     "message"
git push
git pull
git log
git log --oneline
git log --graph
git restore <file>
git restore --staged <file>
git reset --soft HEAD~1
git reset --hard HEAD~1
git branch
git branch <name>
git checkout <name>
git checkout -b <name>
git merge <branch>
git remote -v
git remote add origin <url>
git remote remove origin
```

---

## Part 10: Using Git with KATE and Obsidian

### KATE

1. Edit files
    
2. Save
    
3. Terminal: `git add . && git commit -m "msg" && git push`
    

### Obsidian

1. Terminal in vault: `cd ~/Documents/ObsidianVault`
    
2. Initialize: `git init && git add . && git commit -m "Initial backup"`
    
3. Push to GitHub
    
4. Daily: add / commit / push
    

Use `.gitignore` for sensitive files:

```.obsidian/workspace.json
.trash/
private/
```

---

## Part 11: Quick Troubleshooting 

**fatal: remote origin already exists**

```bash
git remote remove origin
git remote add origin <your-url>
```

**Your branch is ahead of 'origin/ main' by X commits**

```bash
git push
```

**error: failed to push some refs**

```bash
git pull
git push
```

**Accidentally committed wrong files**

```bash
git reset --soft HEAD~1
git restore --staged .
git add file1 file2
git commit -m "Correct commit"
```

**Undo all local changes.**

```bash
git restore .
```

---

## Part 12: Start From Scratch (Embedded Quick Start)

```bash
rm -rf .git
git init
git add .
git commit -m "Initial commit"
git remote add origin <your-github-url>
git push -u --force origin main
```

---

## Part 13: Best Practices

- Commit often and push regularly
    
- Write clear commit messages
    
- Use `.gitignore`
    
- Never commit secrets
    

---

## Part 14: Quick Start Checklist 

1. Install Git
    
2. Configure Git
    
3. Create project folder
    
4. Initialize Git
    
5. Create README
    
6. First commit
    
7. Create GitHub repo
    
8. Connect and push
    

---

## Part 15: What's Next?

- Beginner: Branching, Pull Requests, Cloning
    
- Intermediate: Merge Conflicts, Stashing, Rebasing
    
- Advanced: Git Hooks, Submodules, Git LFS
    

---

## Useful Resources

- [Git Documentation](https://git-scm.com/doc)
    
- [GitHub Guides](https://guides.github.com/)
    
- [Learn Git Branching](https://learngitbranching.js.org/)
    
- [GitHub Skills](https://skills.github.com/)
    
- [Git Cheat Sheet PDF](https://education.github.com/git-cheat-sheet-education.pdf)
    
- [GitHub Git Cheat Sheet](https://training.github.com/downloads/github-git-cheat-sheet/)
    

---

## Conclusion

1. Make changes / `git add .` / commit / push
    
2. Practice on small projects
    
3. Everyone makes mistakes at first — absolutely normal!
    

---

**Communities for Help:**

- [Stack Overflow - Git](https://stackoverflow.com/questions/tagged/git)
    
- [GitHub Community](https://github.community/)
    
- [r/git subreddit](https://reddit.com/r/git)