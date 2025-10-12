



<p align="center"> <img src="./images/quickstart-banner.png" alt="Git & GitHub Quickstart Guide" width="700"> </p> 

Want to push code to GitHub **RIGHT NOW**? Follow these steps. This is the express lane.

> **New to Git?** This gets you pushing code FAST. For detailed explanations, privacy tips, troubleshooting, and best practices, see the [Complete Guide](Git%20In-Depth%20Guide.md).

---

## Prerequisites
- A computer (Linux/Mac/Windows)
- Internet connection

---

## Step 1: Install Git 

### Linux (Ubuntu/Debian)

Open terminal and run:

```bash
# Update package list
sudo apt update

# Install Git
sudo apt install git -y

# Verify installation
git --version
```

You should see something like: `git version 2.34.1`

### Linux (Fedora/RHEL)

```bash
sudo dnf install git -y
git --version
```

### macOS

**Option 1: Using Homebrew (recommended)**

```bash
# Install Homebrew first if you don't have it
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Git
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
3. Use default options (just keep clicking Next)
4. Open Git Bash (installed with Git)
5. Check version:

```bash
git --version
```

---

## Step 2: Create a GitHub Account
If you don't have a GitHub account:

1. Go to [github.com](https://github.com)
2. Click "Sign up"
3. Follow the registration process
4. Verify your email address

**Done!** Keep this browser window open, you'll need it soon.

>  **Important Privacy Note**
>
> Git embeds your **email address** into **every commit** you make, which becomes **publicly visible** on GitHub.
>
> **Recommendation:** Use GitHub's noreply email instead:
> ```bash
> git config --global user.email "12345678+yourusername@users.noreply.github.com"
> ```
>
> Find your noreply address under **GitHub → Settings → Emails → "Keep my email addresses private."**
>
> **For full privacy setup details, see the [Complete Guide](Git%20In-Depth%20Guide.md#part-2-creating-a-github-account).**

---

## Step 3: Configure Git 

```bash
# Set your name
git config --global user.name "Your Name"

# Set your email (use your GitHub noreply email if you set to hide your email)
git config --global user.email "youremail@example.com"

# Set default branch name to 'main'
git config --global init.defaultBranch main
```

**Check your config:**

```bash
git config --list
```

You should see your name and email listed.

---

## Step 4: Create Your First Repository

### If Starting a NEW Project:

```bash
# Create a directory
mkdir my-project
cd my-project
     
# Create a simple file
echo "# My Project" > README.md
```

### If You ALREADY Have a Project Folder:

```bash
cd path/to/your/project/folder
```

*It's safe to initialize Git inside an existing folder — it won't overwrite your files.  
Git will only add a hidden folder `.git/` to track changes.*

---

### Initialize Git

```bash
git init
```

You'll see: `Initialized empty Git repository in /path/to/my-project/.git/`

**What just happened?** Git created a hidden `.git` folder that tracks all your changes.

<p align="center">
  <a href="./images/git-init.png">
    <img src="./images/git-init.png" width="700" alt="Initialized Git Repo">
  </a>
</p>

---

### Check Status

```bash
git status
```

You'll see something like this (if you had files already in your project folder):

<p align="center">
  <a href="./images/git-status.png">
    <img src="./images/git-status.png" width="700" alt="git status">
  </a>
</p>

This means Git sees your file but isn't tracking it yet.

---

### Stage Your Files

"Staging" means telling Git which files you want to include in your next save (commit).

```bash
# Add specific file
git add README.md

# OR 

# add all files at once
git add .
```

Check status again:

```bash
git status
```

Now it says:

<p align="center">
  <a href="./images/git-add.png">
    <img src="./images/git-add.png" width="700" alt="Git Add">
  </a>
</p>

---

### Make Your First Commit

A "commit" is like taking a snapshot of your project.

```bash
git commit -m "Initial commit"
```

**The `-m` flag** lets you add a message describing what you changed.

Check your commit history:

```bash
git log
```

<p align="center">
  <a href="./images/initial-commit.png">
    <img src="./images/initial-commit.png" width="700" alt="Initialized Commit">
  </a>
</p>

---

## Step 5: Create a GitHub Repository 

1. Go to [github.com](https://github.com)
2. Click the **"+"** icon (top right) then **"New repository"**

<p align="center"> <img src="./images/github-new-repo.png" width="500"> </p>

3. Fill in the details:
   - **Repository name:** `my-project`
   - **Description:** (optional)
   - **Public or Private:** Your choice
   - **Important:** **DO NOT** check "Initialize with README" if you already have files in your local project.

4. Click **"Create repository"**

<p align="center"> <img src="./images/create-new-repo.png" width="600"> </p>

### Copy the Repository URL

You'll see a page with "Quick Setup" instructions. Look for the URL that looks like:

```
https://github.com/yourusername/my-project.git
```

**For now, use HTTPS.** Copy the URL!

<p align="center">
  <a href="./images/git-url.png">
    <img src="./images/git-url.png" width="700" alt="git-url">
  </a>
</p>

---

## Step 6: Create a Personal Access Token

<p align="center">
  <a href="./images/PAT-personal-access-token.png">
    <img src="./images/PAT-personal-access-token.png" width="700">
  </a>
</p>

GitHub stopped accepting account passwords for pushing via HTTPS, so now you need a **Personal Access Token (PAT)** instead.

### Step 1: Navigate to the PAT Page
1. Click on your **Profile** (top right)
2. Go to **Settings**
3. **Developer settings** (bottom of sidebar)
4. **Personal access tokens → Tokens (classic)**
5. Click **"Generate new token"** → **"Tokens (classic)"**

### Step 2: Configure Your Token
**Give it a name:** `my-project`

**Set an expiration:** 
- 30 days, 90 days, or no expiration
- **Recommendation:** Use expiration dates and rotate regularly

**Pick permissions:**
- Check `repo` (full control of private repositories)

### Step 3: Generate and Save It
1. Click **"Generate token"**
2. **Copy it immediately** — you won't see it again!
3. Store it in a password manager

**Token format:** `ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx`

<p align="center">
  <a href=".images/PAT-copy.png">
    <img src="./images/PAT-copy.png" width="700">
  </a>
</p>

---

## Step 7: Push to GitHub

### Connect Your Local Repo to GitHub

In your terminal (still in your project folder):

```bash
# Add the remote repository (paste YOUR URL)
git remote add origin https://github.com/yourusername/my-project.git

# Verify it's added
git remote -v
```

You should see:

```
origin  https://github.com/yourusername/my-project.git (fetch)
origin  https://github.com/yourusername/my-project.git (push)
```

**What is "origin"?** It's just a nickname for your GitHub repository URL. You could call it "github" or "backup", but "origin" is the standard.

---

### Push Your Code

```bash
# Push your commits to GitHub
git push -u origin main
```

**First time?** You'll be asked to login:

- Enter your GitHub username
- For password, use a **Personal Access Token** (NOT your GitHub password)

**What's `-u origin main` mean?**

- `-u` = Set this as the default, so next time you can just type `git push`
- `origin` = The nickname for your GitHub repo
- `main` = The branch you're pushing to

---

## Done!  

Your code is now on GitHub! View it at:
```
https://github.com/yourusername/my-project
```

---

## Daily Workflow (What You'll Use Every Day)

### 1. Make Changes

Edit your files in KATE, Obsidian, VS Code, whatever you use.

```bash
# Example: Add a new file
echo "Look 'Ma! a Hello, world!" > hello.txt
```

### 2. Check What Changed

```bash
git status
```

### 3. Stage Your Changes

```bash
# Stage specific file
git add hello.txt

# OR stage all changes
git add .
```

### 4. Commit Your Changes

```bash
git commit -m "Add hello.txt file"
```

### 5. Push to GitHub

```bash
git push
```

That's it! Your changes are now on GitHub.

---

## What's Next?

### Want to understand what you just did?
Read the [Complete Beginner's Guide](Git%20In-Depth%20Guide.md) for detailed explanations of every command, best practices, and troubleshooting.

### Using KATE or Obsidian?
See [Git with Text Editors](Git%20with%20Text%20Editors.md) for editor-specific workflows.

### Quick Command Reference
```bash
git status      # Check what's changed
git add .       # Stage all files
git commit -m   # Save snapshot
git push        # Upload to GitHub
git pull        # Download from GitHub
git log         # View commit history
```

---

## Quick Troubleshooting

**"fatal: remote origin already exists"**
```bash
git remote remove origin
git remote add origin <your-url>
```

**"error: failed to push some refs"**
```bash
git pull
git push
```

**Accidentally committed wrong files?**
```bash
git reset --soft HEAD~1
```

**For more issues, see [Common Issues & Solutions](Git%20In-Depth%20Guide.md#part-11-common-issues-and-solutions)**

---
# Start From Scratch

"Oh No!!!!!!!!!"

"I've made a huge mistake and need to BURN everything"   ~Me


Do the following to WIPE everything while inside your project folder

~~~bash
# 1. Delete the .git folder (removes all history)
rm -rf .git

# 2. Start fresh
git init

# 3. Add everything
git add .

# 4. Make one clean commit
git commit -m "Initial commit"

# 5. Connect to your existing GitHub repo
git remote add origin https://github.com/yourusername/my-project.git

# 6. Force push (overwrites GitHub completely)
git push -u --force origin main
~~~


Refresh your repo in Github and you're all set.



**Remember:** Everyone gets confused at first. You'll make mistakes, push the wrong thing, or mess up a commit. That's normal! The best way to learn is by doing.
---

