
<p align="center"> <img src="./images/ssh-guide-banner.png" alt="Git with Text Editors" width="700"> </p> 

## What Are SSH Keys?

SSH (Secure Shell) keys are a pair of cryptographic keys that 
<span style="background-color: yellow;">allow you to authenticate with GitHub without entering your username and password every time you push or pull.</span> allow you to authenticate with GitHub without entering your username and password every time you push or pull.Think of it like a secure key card that lets you access your repositories automatically.

## Why Use SSH Keys?

- **No more password prompts** - Push and pull without entering credentials
- **More secure** - GitHub no longer accepts regular passwords, only Personal Access Tokens or SSH keys
- **Faster workflow** - Seamless authentication for all your Git operations
- **Industry standard** - What most developers use

## Prerequisites

- A GitHub account
- Git installed on your computer
- Terminal/command line access

## Step 1: Generate Your SSH Key

Open your terminal and run:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```


FYI   `*The ed25519 is a high-speed high-securitypublic-key signature system*


**Important notes:**

- Replace `your_email@example.com` with your actual email
- If you use GitHub's "Keep my email private" feature, use your noreply email (found in GitHub Settings → Emails)
    - Format: `username@users.noreply.github.com`

**You'll be asked three questions:**

1. **"Enter file in which to save the key"**
    
    - Just press Enter to use the default location (`~/.ssh/id_ed25519`)
2. **"Enter passphrase"**
    
    - Press Enter to skip (no passphrase)
    - OR enter a passphrase for extra security (you'll need to enter it each time you use the key)
3. **"Enter same passphrase again"**
    
    - Press Enter again (or re-enter your passphrase)

## Step 2: Copy Your Public Key

Display your public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

This will show something like:

```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJl3dIeudNqd0DMRA... your_email@example.com
```

**Copy the ENTIRE output** - from `ssh-ed25519` all the way to your email at the end.

## Step 3: Add SSH Key to GitHub

1. Go to **GitHub.com** and log in
2. Click your **profile picture** (top right corner)
3. Click **Settings**
4. In the left sidebar, click **"SSH and GPG keys"**
5. Click the green **"New SSH key"** button
6. Fill in the form:
    - **Title:** Give it a descriptive name (e.g., "Ubuntu Laptop", "Work Computer")
    - **Key type:** Authentication Key (default)
    - **Key:** Paste your SSH key from Step 2
7. Click **"Add SSH key"**
8. GitHub may ask for your password - enter it to confirm

## Step 4: Test Your SSH Connection

Run this command to verify everything works:

```bash
ssh -T git@github.com
```

**First time only:** You'll see a message about authenticity. Type `yes` and press Enter.

**a success looks like this:**

```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

## Step 5: Switch Your Repository to Use SSH

For ==each== existing repository, you need to update the remote URL from HTTPS to SSH.

**Navigate to your repository:**

```bash
cd path/to/your/repository
```

**Update the remote URL:**

```bash
git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
```

Replace:

- `USERNAME` with your GitHub username
- `REPOSITORY` with your repository name

**Example:**

```bash
git remote set-url origin git@github.com:d4rumagit/Git-and-Github-Guide.git
```

**Verify it worked:**

```bash
git remote -v
```

You should see URLs starting with `git@github.com:` instead of `https://github.com/`

## Step 6: Test Your Setup

Try pushing to your repository:

```bash
git push
```

**No username or password prompt!** If it pushes successfully, you're all set! 🎉

## Troubleshooting

### Permission Denied Error

If you get "Permission denied (publickey)" when testing:

**Solution 1:** Start the SSH agent and add your key

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
ssh -T git@github.com
```

**Solution 2:** Make sure you added the key to GitHub (check Step 3)

**Solution 3:** Check if you have an old key conflicting

```bash
ls ~/.ssh/
```

If you see old keys, you might need to remove them or specify which key to use.

### Wrong Email or Want to Regenerate

To create a new key:

```bash
# Remove old key (optional)
rm ~/.ssh/id_ed25519*

# Generate new one
ssh-keygen -t ed25519 -C "new_email@example.com"
```

Then repeat Steps 2-6.

### Multiple GitHub Accounts

If you use multiple GitHub accounts, you'll need to configure SSH config files. That's beyond this guide, but search for "SSH config multiple GitHub accounts" for instructions.

## For New Repositories

When cloning a new repository, use the SSH URL instead of HTTPS:

**SSH URL format:**

```bash
git clone git@github.com:USERNAME/REPOSITORY.git
```

**Not HTTPS:**

```bash
# Don't use this
git clone https://github.com/USERNAME/REPOSITORY.git
```

## Summary

Once set up, your workflow is simple:

```bash
git pull    # No credentials needed
git add .
git commit -m "Your message"
git push    # No credentials needed
```

**You'll never need to enter your username and password again!**

## Additional Resources

- [GitHub SSH Documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)
- [Generating SSH Keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)