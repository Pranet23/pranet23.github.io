# How to Update Your Portfolio on GitHub (Step by Step)

Use this guide when you change `index.html` (or other files) and want to push the updates to GitHub so your live site (e.g. GitHub Pages or Vercel) shows the new version.

---

## Prerequisites

- Your portfolio code is in a folder on your computer (e.g. `pranet-portfolio`).
- You have a GitHub account and a repository for this project (e.g. `Pranet23/pranet-portfolio` or similar).
- Git is installed. To check: open **Command Prompt** or **PowerShell** and run `git --version`. If you see a version number, you’re good. If not, install from [git-scm.com](https://git-scm.com/).

---

## Option A: First Time – Connect This Folder to GitHub

Do this only once per project.

### 1. Open the project folder in the terminal

- **Windows:** Open File Explorer, go to your project folder (e.g. `Desktop\pranet-portfolio`), then in the address bar type `cmd` or `powershell` and press Enter.  
  Or: open Command Prompt / PowerShell and run:
  ```bash
  cd C:\Users\YourUsername\OneDrive\Desktop\pranet-portfolio
  ```
  (Replace with your actual path.)

### 2. Initialize Git (if this folder is not yet a Git repo)

Run:
```bash
git init
```

### 3. Create the repo on GitHub

1. Go to [github.com](https://github.com) and sign in.
2. Click the **+** (top right) → **New repository**.
3. Name it (e.g. `pranet-portfolio`).
4. Leave “Add a README” unchecked if you already have files.
5. Click **Create repository**.

### 4. Connect your folder to GitHub

GitHub will show commands; use these (replace `YOUR_USERNAME` and `REPO_NAME` with yours, e.g. `Pranet23` and `pranet-portfolio`):

```bash
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
```

### 5. First commit and push

```bash
git add .
git commit -m "Initial commit: portfolio site"
git branch -M main
git push -u origin main
```

If GitHub asks you to sign in, use your username and a **Personal Access Token** as the password (not your normal GitHub password). Create one: GitHub → Settings → Developer settings → Personal access tokens.

---

## Option B: You Already Have the Repo – Just Update the Website

Use this every time you change the site and want to update GitHub.

### 1. Open the project folder in the terminal

Same as in Option A, step 1 (e.g. `cd` into `pranet-portfolio`).

### 2. See what changed

```bash
git status
```

You’ll see modified files (e.g. `index.html`).

### 3. Stage all changes

```bash
git add .
```

Or stage only one file:

```bash
git add index.html
```

### 4. Commit with a short message

```bash
git commit -m "Update portfolio: new animations and back-to-top"
```

Use any message that describes what you did (e.g. “Fix contact email”, “Add new project”).

### 5. Push to GitHub

```bash
git push
```

If you get “branch not set”, use:

```bash
git push -u origin main
```

After this, GitHub has your latest code. If you use **GitHub Pages** or **Vercel**, they will pick up the push and update the live site in 1–2 minutes.

---

## Quick Reference (Copy-Paste)

When you’re already in the project folder and the repo is set up:

```bash
git add .
git commit -m "Describe your update here"
git push
```

---

## Troubleshooting

| Problem | What to do |
|--------|------------|
| `git` not found | Install Git from [git-scm.com](https://git-scm.com/) and restart the terminal. |
| `Permission denied` or `Authentication failed` | Use a Personal Access Token as password when Git asks. Create one in GitHub → Settings → Developer settings → Personal access tokens. |
| `Updates were rejected` | Someone else (or you on another machine) pushed first. Run `git pull` then `git push`. |
| Wrong folder | Use `cd` to go to the folder that contains `index.html` (your portfolio folder). |

---

## Enabling GitHub Pages (If You Haven’t Yet)

1. On GitHub, open your repo (e.g. `Pranet23/pranet-portfolio`).
2. Click **Settings** → **Pages** (left sidebar).
3. Under **Source**, choose **Deploy from a branch**.
4. Branch: **main**, folder: **/ (root)**.
5. Click **Save**. Your site will be at `https://YOUR_USERNAME.github.io/REPO_NAME/`.

If you use **Vercel** or **Netlify**, connect the same GitHub repo; they’ll deploy on every `git push`.
