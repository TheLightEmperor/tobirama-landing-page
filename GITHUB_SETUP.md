# How to Commit Your Tobirama Landing Page to GitHub

## Prerequisites
- Git installed on your computer ([Download Git](https://git-scm.com/))
- GitHub account ([Create account](https://github.com/signup))

## Step-by-Step Guide

### 1. **Configure Git (First Time Only)**
Open PowerShell and run these commands to set your name and email:
```powershell
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### 2. **Create a New Repository on GitHub**
1. Go to [github.com](https://github.com) and log in
2. Click the **+** icon (top right) → **New repository**
3. Name it: `tobirama-landing-page`
4. Add description: "Tobirama Senju Anime Landing Page"
5. Choose **Public** or **Private**
6. **Don't** initialize with README, .gitignore, or license
7. Click **Create repository**

### 3. **Initialize and Commit Locally**
Open PowerShell in your project folder and run:

```powershell
# Navigate to your project
cd "c:\Users\customer\Desktop\landing page anime"

# Initialize git repository
git init

# Add all files to staging area
git add .

# Create initial commit
git commit -m "Initial commit: Tobirama landing page with blue theme, videos, and gallery"
```

### 4. **Connect to GitHub and Push**
After creating your repository on GitHub, you'll see instructions. Copy the commands or run:

```powershell
# Add remote repository (replace USERNAME with your GitHub username)
git remote add origin https://github.com/USERNAME/tobirama-landing-page.git

# Rename branch to main (if needed)
git branch -m main

# Push code to GitHub
git push -u origin main
```

### 5. **Authentication**
When prompted for password:
- **Option A**: Enter your GitHub password (if using HTTPS)
- **Option B**: Use Personal Access Token (more secure)
  1. Go to GitHub → Settings → Developer settings → Personal access tokens
  2. Generate a new token with `repo` scope
  3. Copy and paste as password

---

## Common Commands for Future Updates

### Make Changes and Commit
```powershell
# See what changed
git status

# Stage specific file
git add tobirama_landing_page.html

# Or stage all changes
git add .

# Commit with message
git commit -m "Your message describing changes"

# Push to GitHub
git push origin main
```

### View History
```powershell
# See all commits
git log --oneline

# See changes in last commit
git diff HEAD~1
```

### Create `.gitignore` File (Optional)
Create a file named `.gitignore` to exclude files from Git:
```
# Don't track node_modules
node_modules/

# Don't track OS files
.DS_Store
Thumbs.db

# Don't track environment files
.env
.env.local
```

---

## Project Files Structure
```
landing page anime/
├── tobirama_landing_page.html    (Main file)
├── images/                        (Image folder)
│   ├── header-bg.jpg
│   ├── image1.jpg
│   ├── image2.jpg
│   └── image3.jpg
├── videos/                        (Video folder)
│   ├── video1.mp4
│   └── video2.mp4
└── GITHUB_SETUP.md               (This file)
```

---

## Troubleshooting

### "fatal: not a git repository"
Make sure you ran `git init` in your project folder.

### "fatal: unable to access"
Check your internet connection or authentication (username/password/token).

### "branch rename failed"
Your branch is already named `main`.

### Need Help?
Visit: [GitHub Docs - Getting Started](https://docs.github.com/en/get-started)

---

## Quick Reference
| Command | Purpose |
|---------|---------|
| `git init` | Initialize new repository |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Commit with message |
| `git push origin main` | Push to GitHub |
| `git pull origin main` | Pull latest from GitHub |
| `git status` | See current status |
| `git log` | View commit history |

