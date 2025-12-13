# 🚀 GitHub Setup Guide - MacroMate

This guide will walk you through pushing your MacroMate project to GitHub step by step.

---

## 📋 Prerequisites

Before you begin, make sure you have:

- ✅ A GitHub account ([Sign up here](https://github.com/signup) if you don't have one)
- ✅ Git installed on your computer
  - Check by running: `git --version`
  - If not installed: [Download Git](https://git-scm.com/downloads)

---

## Step 1: Configure Git (First Time Only)

If you haven't configured git before on this computer, set your name and email:

```powershell
# Set your name (replace with your actual name)
git config --global user.name "Your Name"

# Set your email (use the same email as your GitHub account)
git config --global user.email "your.email@example.com"

# Verify configuration
git config --global user.name
git config --global user.email
```

> **Note**: This only needs to be done once per computer.

---

## Step 2: Initialize Git Repository

Open PowerShell in your project directory and run:

```powershell
# Navigate to your project directory (if not already there)
cd "c:\Users\Karan\Documents\Sem 9\Capstrone Project\macro_tracker_ai-main\macro_tracker_ai-main"

# Initialize git repository
git init
```

**Expected Output**: `Initialized empty Git repository in ...`

---

## Step 3: Review .gitignore

Your project already has a `.gitignore` file which prevents unnecessary files from being committed (like build files, IDE settings, etc.). This is good!

You can view it by running:
```powershell
cat .gitignore
```

---

## Step 4: Stage Your Files

Add all your project files to git:

```powershell
# Add all files to staging area
git add .

# Check what files are staged
git status
```

**Expected Output**: You'll see a list of files ready to be committed (in green).

---

## Step 5: Create Your First Commit

```powershell
# Create initial commit with a descriptive message
git commit -m "Initial commit: MacroMate AI-powered nutrition tracker"
```

**Expected Output**: Summary showing how many files were created/changed.

---

## Step 6: Create GitHub Repository

Now, go to GitHub in your browser:

1. **Go to GitHub**: [https://github.com/](https://github.com/)
2. **Sign in** to your account
3. Click the **"+"** icon in the top right → **"New repository"**
4. Fill in the details:
   - **Repository name**: `macro-tracker-ai` (or `MacroMate`)
   - **Description**: 
     ```
     🥑 Premium AI-powered nutrition tracker built with Flutter. Snap food photos for instant macro analysis using Google Gemini. 🚀
     ```
   - **Visibility**: Choose **Public** (recommended) or **Private**
   - **DO NOT** initialize with README, .gitignore, or license (we already have these)
5. Click **"Create repository"**

---

## Step 7: Connect Local Repository to GitHub

After creating the repository, GitHub will show you some commands. Use these:

```powershell
# Add GitHub as remote origin (replace YOUR_USERNAME with your actual GitHub username)
git remote add origin https://github.com/YOUR_USERNAME/macro-tracker-ai.git

# Verify remote was added
git remote -v
```

**Expected Output**: 
```
origin  https://github.com/YOUR_USERNAME/macro-tracker-ai.git (fetch)
origin  https://github.com/YOUR_USERNAME/macro-tracker-ai.git (push)
```

---

## Step 8: Push to GitHub

```powershell
# Rename the default branch to 'main' (if needed)
git branch -M main

# Push your code to GitHub
git push -u origin main
```

**What happens**:
- Git will ask for your GitHub credentials
- Use your GitHub **username** and **Personal Access Token** (not password)

### 🔑 If You Don't Have a Personal Access Token:

1. Go to [GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)](https://github.com/settings/tokens)
2. Click **"Generate new token"** → **"Generate new token (classic)"**
3. Give it a name (e.g., "MacroMate Development")
4. Select scopes: Check ✅ **repo** (full control)
5. Click **"Generate token"**
6. **Copy the token immediately** (you won't see it again!)
7. Use this token as your password when git asks

---

## Step 9: Verify on GitHub

1. Go to your repository on GitHub: `https://github.com/YOUR_USERNAME/macro-tracker-ai`
2. You should see all your files!
3. The README.md will be displayed on the main page

---

## Step 10: Add Repository Description & Topics (Optional but Recommended)

On your GitHub repository page:

1. Click **⚙️ Settings** (top right, near the repository name, or the gear icon next to "About")
2. In the **About** section (right sidebar), click **⚙️ (gear icon)**
3. Add:
   - **Description**: 
     ```
     🥑 Premium AI-powered nutrition tracker built with Flutter. Snap food photos for instant macro analysis using Google Gemini. 🚀
     ```
   - **Topics** (click "Add topics"):
     ```
     flutter, dart, firebase, gemini-ai, nutrition-tracker, artificial-intelligence, 
     health, computer-vision, mobile-app, windows, cross-platform, riverpod
     ```
4. Click **"Save changes"**

---

## 🎉 Success!

Your project is now on GitHub! Share the link with others:
```
https://github.com/YOUR_USERNAME/macro-tracker-ai
```

---

## 📝 Future Updates

When you make changes to your project and want to update GitHub:

```powershell
# 1. Check what changed
git status

# 2. Add the changes
git add .

# 3. Commit with a message
git commit -m "Description of what you changed"

# 4. Push to GitHub
git push
```

---

## 🔧 Common Issues & Solutions

### Issue 1: "Permission denied (publickey)"

**Solution**: Use HTTPS instead of SSH, or set up SSH keys.

For HTTPS, make sure your remote URL uses HTTPS:
```powershell
git remote set-url origin https://github.com/YOUR_USERNAME/macro-tracker-ai.git
```

### Issue 2: "Authentication failed"

**Solution**: 
- Make sure you're using a **Personal Access Token**, not your GitHub password
- Generate a new token if needed (see Step 8)

### Issue 3: "Updates were rejected"

**Solution**: Pull the latest changes first:
```powershell
git pull origin main --rebase
git push
```

### Issue 4: "Large files warning"

**Solution**: Some files might be too large for GitHub. Add them to `.gitignore`:
```powershell
# Open .gitignore and add the file pattern
echo "*.mp4" >> .gitignore
echo "*.mov" >> .gitignore
git add .gitignore
git commit -m "Update .gitignore for large files"
```

---

## 📚 Next Steps

1. ✅ Add a **LICENSE** file (MIT recommended)
2. ✅ Add **screenshots** to your README
3. ✅ Create a **demo video** and add to README
4. ✅ Set up **GitHub Actions** for automated testing (optional)
5. ✅ Enable **GitHub Pages** for documentation (optional)

---

## 🆘 Need Help?

- GitHub Documentation: [https://docs.github.com](https://docs.github.com)
- Git Command Reference: [https://git-scm.com/docs](https://git-scm.com/docs)
- Stack Overflow: [https://stackoverflow.com/questions/tagged/git](https://stackoverflow.com/questions/tagged/git)

---

**Good luck! 🚀**
