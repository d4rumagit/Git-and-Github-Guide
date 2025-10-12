



<p align="center"> <img src="./images/complete-guide-banner.png" alt="Git & GitHub Complete Guide" width="700"> </p> 

If you're reading this, you probably want to start using Git to save your code, track changes, and push projects to GitHub. This guide will walk you through everything from installation to your first push. No fluff, just the stuff you need to know.



---
<h1 style="text-align: center";> <u>!!  This guide will unfortunately only have examples being performed from a Linux Machine  !! </u></h1>



## What You'll Learn

- Installing Git on your system
- Setting up Git for the first time
- Creating your first repository
- Connecting to GitHub
- Pushing your code to GitHub
- Basic Git workflow



---
---
## <h1 style="text-align: center;"> Part 1: Installing Git </h1>


---
---

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
---
## Part 2: Creating a GitHub Account





If you don't have a GitHub account:

1. Go to [github.com](https://github.com)
2. Click "Sign up"
3. Follow the registration process
4. Verify your email address

**Done!** Keep this browser window open, you'll need it soon.





>  **Important Privacy Note (Don’t Skip This!)**
>
> If you care about your privacy or security — **like I do** — this part is **critical**.  
> <b>Many</b> people forget that Git embeds your **email address** into **every commit** you make.
>
> That email becomes **publicly visible** on GitHub or any shared repository.  
> For privacy-conscious users, that’s a major **red flag** 
>
> **Recommendation:**  
> Use GitHub’s noreply email instead of your real one:
> ```bash
> git config --global user.email "12345678+yourusername@users.noreply.github.com"
> ```
>
> You can find your noreply address under  
> **GitHub → Settings → Emails → “Keep my email addresses private.”**
>
> This keeps your real email hidden while still linking commits to your GitHub profile.



<p align="center">
  <a href="./images/keep-my-email-private.png">
    <img src="./images/keep-my-email-private.png" width="750" alt="Kepp My Email Private">
  </a>
</p>



Now that your email is now private, go ahead and untik  "Block command line pushes that expose my email"

if this is ON, then pushes will be blocked




<p align="center">
  <a href="./images/block-push-with-email.png">
    <img src="./images/block-push-with-email.png" width="700" alt="Block Push">
  </a>
</p>





<p align="center">
  <a href="spam-meme.png">
    <img src="spam-meme.png" width="400" alt="Spam EVERYWHERE!">
  </a>
</p>

In open source, sharing your email is mostly a courtesy.

> **For most of us, though, the reason to avoid using your real personal or work email is simple:** you don’t want spam showing up in your inbox.  
> Use a GitHub noreply email instead to stay safe while keeping your commits linked to your account.


<p style= "text-align: center";>I digress..</p>



---
---
## <h1 style="text-align: center;">Part 3: First-Time Git Setup</h1>






```bash
# Set your name
git config --global user.name "Your Name"

# Set your email (use your GitHub email)
git config --global user.email "youremail@example.com" <-- noreply email 

# Set default branch name to 'main'
git config --global init.defaultBranch main

# Optional: Set your default editor (replace with your preferred editor)
git config --global core.editor "nano"
# For VS Code: git config --global core.editor "code --wait"

```



**Check your config:**

```bash
git config --list
```

You should see your name and email listed.


By default Git doesn't create a "Safe Directory"

The `safe.directory` setting allows users to explicitly list directories that Git should consider safe, even if they don't meet the default ownership criteria. This can be done on a per-repository basis, or globally for all repositories.

this is good security housekeeping 

optional but you can create them at anytime, like I did below.

<p align="center">
  <a href="./images/safe-directory.png">
    <img src="./images/safe-directory.png" width="750" alt="Safe Directory">
  </a>
</p>




---
---
## <h1 style="text-align: center;">Part 4: Your First Local Repository</h1>






Let's create a simple project and turn it into a Git repository.

### Step 1: Create a Project Folder

```bash
# Create a directory
mkdir my-repositories
cd my-project
     
# Create a simple file
echo "# My Project" > README.md
```

or
If you already have a project folder with files


~~~ bash
cd path/to/your/project/folder

~~~


*It’s safe to initialize Git inside an existing folder — it won’t overwrite your files.  
Git will only add a hidden folder `.git/` to track changes.


### Step 2: Initialize Git

This turns your folder into a Git repository:

```bash
git init
```

You'll see: `Initialized empty Git repository in /h/to/my-project/.git/`

**What just happened?** Git created a hidden `.git` folder that tracks all your changes.



<p align="center">
  <a href="./images/git-init.png">
    <img src="./images/git-init.png" width="700" alt="Initialized Git Repo">
  </a>
</p>



### Step 3: Check Status

```bash
git status
```

You'll see something  like this :

If you had files already in your project folder

<p align="center">
  <a href="./images/git-status.png">
    <img src="./images/git-status.png" width="750" alt="Git Status">
  </a>
</p>

This means Git sees your file but isn't tracking it yet.

### Step 4: Stage Your Files

"Staging" means telling Git which files you want to include in your next save (commit).

```bash
# Add specific file
git add README.md

# OR 

# add all files at once
git add .
```


I will  'Stage'  all my files


Check status again:

```bash
git status
```

Now it says:

<p align="center">
  <a href="./images/git-add.png">
    <img src="./images/git-add.png" width="750" alt="Git Add">
  </a>
</p>

### Step 5: Make Your First Commit

A "commit" is like taking a snapshot of your project.

```bash
git commit -m "Initial commit"
```

**The `-m` flag** lets you add a message describing what you changed.

**What's a good commit message?**

**Good:**

- "Add README file"
- "Inital commit"
- "Fix login bug"
- "Update homepage design"

**Bad:**

- "stuff"
- "changes"
- "idk"    

Check your commit history:

```bash
git log
```


<p align="center">
  <a href="./images/inital-commit.png">
    <img src="./images/initial-commit.png" width="750" alt="Inital Commit">
  </a>
</p>


---
---


<h1 style="text-align: center;">Part 5: Connecting to GitHub</h1>







Now let's put your code on GitHub so others can see it (and so you have a backup).

### Create a GitHub Repository

1. Go to [github.com](https://github.com)
2. Click the **"+"** icon (top right) then **"New repository"**

<p align="center"> <img src="./images/github-new-repo.png" width="500"> </p>

3. Fill in the details:
- **Repository name:** `my-project`
- **Description:** (optional)
- **Public or Private:** Your choice
- **Important:** **DO NOT** check "Initialize with README"  
  if you already have files in your local project.

>  **Warning:** If you plan to push an existing local repository, **don’t create the initial README on GitHub**.

- Always create the repository **completely empty**, then add your remote and push your local commits first.
- **( This will be covered shortly in Part 6 Step 1)**


3. Click **"Create repository"**

<p align="center"> <img src="./images/create-new-repo.png" width="600"> </p>


### Copy the Repository URL

You'll see a page with "Quick Setup" instructions. Look for the URL that looks like:

```
https://github.com/yourusername/my-project.git
```

**There are two URL types:**

**HTTPS** (easier, recommended for beginners):

```
https://github.com/yourusername/my-project.git
```

**SSH** (more secure, requires setup):

```
git@github.com:yourusername/my-project.git
```

**For now, use HTTPS.** Copy the URL!


<p align="center">
  <a href="./images/git-url.png">
    <img src="./images/git-url.png" width="750" alt="Git URL">
  </a>
</p>


---
---

<h1 style="text-align: center;">Part 6: Creating a Personal Access Token (PAT)</h1>




<p align="center">
  <a href="./images/-personal-access-token.png">
    <img src="./images/PAT-personal-access-token.png" width="700">
  </a>
</p>

GitHub stopped accepting account passwords for pushing via HTTPS, so now you need a **Personal Access Token (PAT)** instead. Don't worry, it's pretty simple.

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
  <a href="./images/PAT-copy.png">
    <img src="./images/PAT-copy.png" width="700">
  </a>
</p>



---
---

# Part 7: Pushing to GitHub





### Step 1: Connect Your Local Repo to GitHub

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



### Step 2: Push Your Code

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
---
If you did not create a default global config, then you will get an error if you try to push...

Because, IF you didn't configure the "gobal init.defaultBranch" to <b> Main</b>, by default it will set to <b>Master</b>

---
---

# Part 8: The Basic Git Workflow

Now that everything is set up, here's your daily workflow:

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

Shows:

```
Untracked files:
        hello.txt
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

# Part 9: Essential Git Commands Cheat Sheet

```bash
# Setup
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Creating Repositories
git init                          # Initialize a new repo
git clone <url>                   # Clone an existing repo

# Basic Workflow
git status                        # Check status
git add <file>                    # Stage specific file
git add .                         # Stage all files
git commit -m "message"           # Commit with message
git push                          # Push to GitHub
git pull                          # Get latest changes from GitHub

# Viewing History
git log                           # View commit history
git log --oneline                 # Compact view
git log --graph                   # Visual graph

# Undoing Things
git restore <file>                # Discard changes in file
git restore --staged <file>       # Unstage file
git reset --soft HEAD~1           # Undo last commit, keep changes
git reset --hard HEAD~1           # Undo last commit, delete changes (careful!)

# Branching (Advanced)
git branch                        # List branches
git branch <name>                 # Create new branch
git checkout <name>               # Switch to branch
git checkout -b <name>            # Create and switch to new branch
git merge <branch>                # Merge branch into current branch

# Remote Repositories
git remote -v                     # List remotes
git remote add origin <url>       # Add remote
git remote remove origin          # Remove remote
```

---




# Part 10: Using Git with KATE and Obsidian


### For KATE Users

KATE is just a text editor, so your workflow is:

1. Edit files in KATE
2. Save them
3. Open terminal in your project folder
4. Run git commands:

```bash
git add .
git commit -m "Update documentation"
git push
```

**tip:** Open KATE's built-in terminal:

- KDE shoudl have 'Konsole' preinstalled alongside KATE, but if its not, just install it through the setting of KATE
- `Settings` then `Configure Kate` then `Plugins` then Enable `Terminal`
- To toggle  press `F4`

### For Obsidian Users

If you're tracking an Obsidian vault with Git:

1. Open terminal in your vault folder:

```bash
cd ~/Documents/ObsidianVault
```

2. Initialize Git (first time only):

```bash
git init
git add .
git commit -m "Initial vault backup"
```

3. Create GitHub repo and connect it:

```bash
git remote add origin https://github.com/yourusername/obsidian-vault.git
git push -u origin main
```

4. Daily backup routine:

```bash
cd ~/Documents/ObsidianVault
git add .
git commit -m "Daily notes update"
git push
```

# **Warning:** Be careful about pushing personal notes to public repos!



**Pro tip:** Create a `.gitignore` file to exclude certain files:

```bash
nano .gitignore
```

Add:

```
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.trash/
private/
```

---

<a id="part-11-common-issues-and-solutions"></a>
# Part 11: Common Issues and Solutions


### Issue: "fatal: remote origin already exists"

**Solution:**

```bash
# Remove the existing remote
git remote remove origin

# Add it again
git remote add origin <your-url>
```

### Issue: "Your branch is ahead of 'origin/main' by X commits"

**Solution:**

```bash
# Just push!
git push
```

### Issue: "error: failed to push some refs"

Someone else pushed changes before you did.

**Solution:**

```bash
# Get the latest changes
git pull

# Then push your changes
git push
```

### Issue: Accidentally committed the wrong files

**Solution:**

```bash
# Undo the last commit, keep the changes
git reset --soft HEAD~1

# Unstage everything
git restore --staged .

# Now add only what you want
git add file1.txt file2.txt
git commit -m "Correct commit"
```

### Issue: Want to undo all local changes

**WARNING: This deletes your changes!**

```bash
git restore .
```

---

# Part 12: Best Practices

### Commit Often, Push Regularly

**Do:**

- Commit after completing a feature
- Commit when you fix a bug
- Push at the end of your work session

**Don't:**

- Wait days to commit
- Commit half-finished work

### Write Good Commit Messages

**Good:**

```
Add user authentication
Fix database connection timeout
Update README with installation steps
```

**Bad:**

```
fixed stuff
changes
updates
asdfasdf
```

### Use .gitignore

Always create a `.gitignore` file to exclude:

- System files (`.DS_Store`, `Thumbs.db`)
- Dependencies (`node_modules/`, `vendor/`)
- Build outputs (`dist/`, `build/`)
- Secrets (`.env`, `config.local.js`)
- Personal notes (`TODO.md`, `NOTES.md`)

### Never Commit Secrets

**NEVER EVER EVER** commit:

- Passwords
- API keys
- Access tokens
- Private keys
- Database credentials

Use environment variables or config files (and add them to `.gitignore`). 

---

# Part 13: Quick Start Checklist

Starting a new project? Follow this checklist:

**Step 1: Install Git**

```bash
git --version
```

**Step 2: Configure Git**

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

**Step 3: Create Project Folder**

```bash
mkdir my-project
cd my-project
```

**Step 4: Initialize Git**

```bash
git init
```

**Step 5: Create README**

```bash
echo "# My Project" > README.md
```

**Step 6: Make First Commit**

```bash
git add .
git commit -m "Initial commit"
## Part 6: Pushing to GitHub

### Step 1: Connect Your Local Repo to GitHub

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
```

**Step 7: Create GitHub Repo**

- Go to github.com
- Click "+" then "New repository"
- Copy the URL

**Step 8: Connect and Push**

```bash
git remote add origin <your-github-url>
git push -u origin main
```

**Done!** You're now using Git and GitHub!

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


## What's Next?

You now know the basics of Git! Here's what to explore next:

### Beginner Topics

- **Branching** - Work on features without breaking main code
- **Pull Requests** - Collaborate with others
- **Cloning** - Download other people's projects

### Intermediate Topics

- **Merge Conflicts** - Resolve conflicts when code changes overlap
- **Stashing** - Temporarily save uncommitted changes
- **Rebasing** - Alternative to merging

### Advanced Topics

- **Git Hooks** - Automate tasks before/after git actions
- **Submodules** - Include other repos in your project
- **Git LFS** - Handle large files efficiently

---

## Useful Resources

**Official Documentation:**

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)

**Interactive Learning:**

- [Learn Git Branching](https://learngitbranching.js.org/) - Visual, interactive tutorial
- [GitHub Skills](https://skills.github.com/) - Free hands-on courses

**Cheat Sheets:**

- [Git Cheat Sheet (PDF)](https://education.github.com/git-cheat-sheet-education.pdf)
- [GitHub Git Cheat Sheet](https://training.github.com/downloads/github-git-cheat-sheet/)

---

## Conclusion

Git seems complicated at first, but the basic workflow is simple:

1. Make changes to your files
2. `git add .`
3. `git commit -m "describe your changes"`
4. `git push`

That's 90% of what you'll do with Git. Start with these basics, practice with small projects, and you'll be comfortable in no time.

**Remember:** Everyone was confused by Git at first. You'll make mistakes, push the wrong thing, or mess up a commit. That's normal! The best way to learn is by doing.

Now go create something and push it to GitHub!

---

**Questions or stuck?** The Git and GitHub communities are very helpful:

- [Stack Overflow - Git tag](https://stackoverflow.com/questions/tagged/git)
- [GitHub Community](https://github.community/)
- [r/git subreddit](https://reddit.com/r/git)

Good Luck!!!
