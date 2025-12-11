# Git & GitHub Guides

A comprehensive small collection of guides to help you learn Git and GitHub, from absolute beginner to confident user. 

I will add and update as time goes. :)) 

<p align="center"> <img src="./images/hero-banner.png" alt="Git & GitHub Guide" width="700"> </p>

---

## Navigation

- [>I have GIT, I Just Need a Repo<](Git%20It%20Now!%20Guide.md)
- [Full Guide](Git%20with%20Github%20Guide.md)
- [Quick Start Guide](Git%20Quickstart%20Guide.md)
- [Text Editors with Git Guide (limited)](Git%20with%20Text%20Editors%20Guide.md)
- [Github SSH Setup Guide](Github%20SSH%20Setup%20Guide.md)
- [Prerequisites](#prerequisites)
- [Resources](#resources)
- [License & Contributing](#license)

---

## Overview

A comprehensive collection of guides to help you learn Git and GitHub, from absolute beginner to confident user. Whether you need to push code in 15 minutes or want to deeply understand version control, these guides have you covered.

**Choose your path:**

- **Need results now?** → [Quick Start](#quick start)
- **Want deep understanding?** → [[Git with Github Guide]] (comprehensive)
- **Using specific editors?** → [[Git with Text Editors Guide]] (KATE/Obsidian)

---

## Prerequisites

**For all guides:**

- A computer running Windows, macOS, or Linux
- Basic familiarity with using a terminal/command line
- An internet connection
- A GitHub account

**No prior Git experience required!** These guides assume you're starting from zero and or have an idea and just need brushing up.

---

## Guide Contents

### Available Guides

1. **Quick Start Guide** - _15 minutes_
    
    - Get your first repository on GitHub TODAY
    - Skip the theory, just the essential commands
    - Perfect for: Time-pressed developers, quick reference
2. **Complete Beginner's Guide** - _Comprehensive_[Git Quickstart Guide]]
    
    - In-depth explanations of every concept
    - Privacy and security best practices
    - Troubleshooting common issues
    - .gitignore, workflows, and best practices
    - Perfect for: Those who want to truly understand Git
3. **Git with Text Editors** - _Tool-specific_
    
    - KATE editor integration
    - Obsidian vault tracking
    - Daily workflows for each editor
    - Perfect for: KATE/Obsidian users

---

## Full Guide

### Complete Learning Path

**Step 1: Installation & Setup**

- Install Git on your system
- Configure your identity (name and email)
- Choose authentication method (HTTPS or SSH)

**Step 2: Create Your First Repository**

- Initialize a local repository
- Create your first commit
- Understand Git's staging area

**Step 3: Connect to GitHub**

- Create a GitHub account
- Generate Personal Access Token or SSH keys
- Link your local repo to GitHub

**Step 4: Push Your Code**

- Add a remote repository
- Push your commits to GitHub
- Verify your code is online

**Step 5: Daily Git Workflow**

- Make changes to your files
- Stage and commit changes
- Push updates to GitHub
- Pull changes from collaborators

**Step 6: Best Practices**

- Write clear commit messages
- Use .gitignore files properly
- Protect your privacy
- Handle common issues

**For complete details on each step:** See the Complete Beginner's Guide

---

## Quick Start

**Want to push code to GitHub in 3 commands?**

```bash
# 1. Initialize and commit
git init
git add .
git commit -m "Initial commit"

# 2. Create repo on GitHub (github.com), then:
git remote add origin https://github.com/yourusername/repo-name.git

# 3. Push
git push -u origin main
```

**Don't know what these mean?** → Check the Quick Start Guide

**Want to understand WHY they work?** → Check the Complete Guide

---

## Resources

### Official Documentation

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [GitHub Skills](https://skills.github.com/)

### Community Help

- [Stack Overflow - Git](https://stackoverflow.com/questions/tagged/git)
- [GitHub Community](https://github.community/)
- [r/git subreddit](https://reddit.com/r/git)

### Useful Tools

- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [gitignore.io](https://www.toptal.com/developers/gitignore) - Generate .gitignore files
- [GitHub Desktop](https://desktop.github.com/) - GUI alternative to command line


---

## Choose Your Path

### Quick Start Guide - 15 Minutes

**"I just want to push code to GitHub NOW!"**

Perfect for:

- Complete beginners who want results fast
- Experienced developers who just need the commands
- Anyone who wants to get their first repo online today

**What you'll do:**

- Install Git
- Set up your first repository
- Push to GitHub in 15 minutes

**Skip the theory, get straight to action.**

---

### Complete Beginner's Guide - Comprehensive

**"I want to understand Git properly."**

Perfect for:

- Developers who want deep understanding
- Anyone planning to use Git professionally
- People who like to know _why_ things work

**What you'll learn:**

- Every command explained in detail
- Privacy and security best practices
- Troubleshooting common issues
- .gitignore, commit messages, and workflows
- Best practices for long-term success

**Take your time, learn it right.**

---

### Git with Text Editors - Tool-Specific

**"How do I use Git with KATE/Obsidian/my favorite editor?"**

Perfect for:

- KATE users who want terminal integration
- Obsidian users backing up their vaults
- Anyone using specific text editors with Git

**What you'll learn:**

- Setting up KATE's built-in terminal
- Backing up Obsidian vaults with Git
- Multi-device sync workflows
- Editor-specific tips and tricks

**Integrate Git into your existing workflow.**

---

## Recommended Learning Path

### New to Git? Start here:

1. **Day 1:** Follow the Quick Start Guide
    
    - Get your first repo on GitHub (15 minutes)
    - Learn the basic daily workflow
2. **Day 2-3:** Read the Complete Beginner's Guide
    
    - Understand what you did in the Quick Start
    - Learn best practices and troubleshooting
    - Set up privacy settings properly
3. **Day 4+:** Check out Git with Text Editors (if relevant)
    
    - Integrate Git with your favorite tools
    - Set up automated workflows

---

## What's Covered

### Installation & Setup

- Installing Git on Linux, macOS, and Windows
- Creating a GitHub account
- Configuring Git for the first time
- Email privacy settings

### Core Git Concepts

- Repositories (local and remote)
- Staging and committing
- Pushing and pulling
- Viewing history

### GitHub Integration

- Creating repositories on GitHub
- Personal Access Tokens (PAT)
- Connecting local repos to GitHub
- Basic collaboration

### Daily Workflows

- The standard add → commit → push cycle
- Checking status and viewing changes
- Writing good commit messages
- Using .gitignore files

### Troubleshooting

- Common error messages and solutions
- Undoing mistakes
- Handling merge conflicts
- Recovery strategies

### Tool Integration

- KATE editor setup
- Obsidian vault backup
- VS Code integration
- General editor workflows

---

## Quick Reference

### Essential Commands

```bash
git status              # What's changed?
git add .               # Stage all changes
git commit -m "msg"     # Save snapshot
git push                # Upload to GitHub
git pull                # Download updates
git log                 # View history
```

### First-Time Setup

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
```

### New Project Workflow

```bash
mkdir my-project && cd my-project
git init
echo "# My Project" > README.md
git add .
git commit -m "Initial commit"
git remote add origin <your-github-url>
git push -u origin main
```

---

## Need Help?

### Having Issues?

- Check Common Issues & Solutions in the Complete Guide

### Want More Resources?

- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Learn Git Branching](https://learngitbranching.js.org/) - Interactive tutorial
- [GitHub Skills](https://skills.github.com/) - Free hands-on courses

### Community Support

- [Stack Overflow - Git tag](https://stackoverflow.com/questions/tagged/git)
- [GitHub Community](https://github.community/)
- [r/git subreddit](https://reddit.com/r/git)

---

## About These Guides

These guides are designed to be:

**Beginner-Friendly**

- No assumptions about prior Git knowledge
- Plain language explanations
- Real-world examples

**Practical**

- Focus on what you'll actually use
- Copy-paste ready commands
- Tested workflows

**Complete**

- From installation to daily use
- Privacy and security included
- Troubleshooting built-in

---

## Learning Philosophy

**Git seems complicated at first**, and that's okay. Everyone feels confused when they start. These guides are built on a few principles:

1. **Get results first, understand later** - The Quick Start gets you working immediately
2. **Build on success** - Learn deeply after you've seen Git work
3. **Practice over theory** - You'll learn more by doing than reading or watching
4. **Mistakes are normal** - Everyone messes up. It's part of learning

**Start where you are. Use what you have. Do what you can. One Push at a time.**

---

## Which Guide Should I Use?

**"I have 15 minutes and need to push code today"**  
→ Quick Start Guide

**"I want to really dig inside of Git"**  
→ Complete Beginner's Guide

**"I use KATE/Obsidian and want Git integration"**  
→ Git with Text Editors

**"I'm not sure about this..."**  
→ Start with the Quick Start Guide, then explore the others

---

## TLDR

**Want to push your first repo in 3 commands?**

```bash
# 1. Initialize and commit
git init
git add .
git commit -m "Initial commit"

# 2. Create repo on GitHub (github.com), then:
git remote add origin https://github.com/yourusername/repo-name.git

# 3. Push
git push -u origin main
```

**You'll need:** Git installed, GitHub account, and a Personal Access Token (PAT).

**Don't know what those are?** → Quick Start Guide has you covered.

---

## Tips

- **Start simple:** Don't worry about branches, rebasing, or advanced features yet
- **Commit often:** Small, frequent commits are better than huge ones
- **Read the output:** Git's error messages are actually helpful
- **Use .gitignore:** Don't commit secrets, dependencies, or system files
- **Privacy matters:** Use GitHub's noreply email to protect your inbox

---



## License & Contributing

These guides are free to use, share, and modify. If you found them helpful, share them with others learning Git!

**Found an error?** Issues and improvements are welcome.

---

Good Luck!!!
