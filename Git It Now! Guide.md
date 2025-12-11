
<p align="center"> <img src="./images/git-it-now.webp" alt="Git & GitHub Complete Guide" width="700"> </p> 

(You should already have Git installed. For installation instructions, see [Git Installation Guide](Git%20with%20Github%20Guide.md). )

When you want to copy a project from GitHub (or another Git provider) to your computer, use `git clone`. This command downloads the entire project including all files and history, and automatically sets everything up for you.

## Cloning an Existing Repository

**Step 1: Open your terminal and navigate to where you want to store projects**

**Mac/Linux:**
```bash
cd ~/Documents/my-projects
```

**Windows (Command Prompt):**
```bash
cd Documents\my-projects
```

**Windows (PowerShell):**
```powershell
cd ~/Documents/my-projects
```

**Step 2: Clone the repository**

All systems use the same command:
```bash
git clone https://github.com/username/project-name.git
```

Git will create a new folder with your project name and download everything into it. You're ready to work!



---

## Starting a New Project from Scratch

If you're creating a brand new project, start by initializing Git locally. Then you can create a repository on GitHub and push your code up.

**Step 1: Create a folder for your project**

**Mac/Linux:**
```bash
mkdir my-project
cd my-project
```

**Windows (Command Prompt):**
```bash
mkdir my-project
cd my-project
```

**Windows (PowerShell):**
```powershell
mkdir my-project
cd my-project
```

**Step 2: Initialize Git in that folder**

All systems use the same command:
```bash
git init
```

This creates a hidden `.git` folder that tracks your project's history.

**Step 3: Add your files and make your first commit**

All systems use the same commands:
```bash
git add .
git commit -m "Initial commit"
```

**Step 4: Connect to a GitHub repository**

First, create an empty repository on GitHub, then run these commands (same for all systems):

```bash
git remote add origin https://github.com/username/my-project.git
git branch -M main
git push -u origin main
```

Your project is now on GitHub and synchronized with your local folder!

---

## Key Takeaway

- **Use `git clone`** when copying an existing project from GitHub
- **Use `git init`** when starting a brand new project locally
- Most Git commands are the same across Mac, Windows, and Linux—only folder navigation differs slightly