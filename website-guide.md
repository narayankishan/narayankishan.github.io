# How to Update Your Website

## Your Website Files Location
```
C:\Users\ecoki\Documents\GitHub\narayankishan.github.io
```

## Files You Can Edit

| File | Purpose |
|------|---------|
| `index.Rmd` | Home page (your bio, photo) |
| `CV.Rmd` | Your CV page |
| `research.Rmd` | Research projects & publications |
| `resources.Rmd` | Data resources page |
| `_site.yml` | Navbar links, site title, icons |
| `styles.css` | Custom styling (spacing, fonts) |
| `images/` folder | Your photos |

---

## Step-by-Step: Making Changes

### Step 1: Edit the file

Open the file you want to change:
```bash
notepad C:\Users\ecoki\Documents\GitHub\narayankishan.github.io\index.Rmd
```

Or open in RStudio: **File → Open File → select the .Rmd file**

Make your changes and **Save** (Ctrl + S).

---

### Step 2: Rebuild the website

Open **RStudio** and run this in the Console:
```r
rmarkdown::render_site()
```

This converts your `.Rmd` files to `.html` files.

---

### Step 3: Push to GitHub

Open **Command Prompt** and run these commands one by one:

```bash
cd C:\Users\ecoki\Documents\GitHub\narayankishan.github.io

git add .

git commit -m "Your message describing the change"

git push
```

**If push fails**, run:
```bash
git push --force
```

---

### Step 4: View your changes

1. Wait **1-2 minutes** for GitHub to deploy
2. Open your website: https://narayankishan.github.io/
3. **Hard refresh**: Press `Ctrl + Shift + R`

---

## Common Tasks

### Add a new research paper
1. Open `research.Rmd`
2. Add your paper details
3. Rebuild → Push

### Update your bio
1. Open `index.Rmd`
2. Edit the text inside `<div class="col2">`
3. Rebuild → Push

### Change your photo
1. Put new photo in `images/` folder
2. Open `index.Rmd`
3. Change the image filename in `<img src="images/YOUR_NEW_PHOTO.jpg">`
4. Rebuild → Push

### Add a new page to navbar
1. Create new file: `newpage.Rmd`
2. Open `_site.yml`
3. Add under `left:`:
   ```yaml
   - text: "New Page"
     href: newpage.html
   ```
4. Rebuild → Push

---

## Quick Reference Commands

```bash
# Navigate to your website folder
cd C:\Users\ecoki\Documents\GitHub\narayankishan.github.io

# Check what files changed
git status

# Add all changes
git add .

# Commit with message
git commit -m "describe your change"

# Push to GitHub
git push

# Force push (if normal push fails)
git push --force
```

---

## Troubleshooting

**"fatal: not a git repository"**
→ Run: `git init` then try again

**"Updates were rejected"**
→ Run: `git push --force`

**Website not updating?**
→ Hard refresh: `Ctrl + Shift + R`
→ Wait 2-3 minutes and try again

**render_site() error?**
→ Make sure `_site.yml` exists in your folder
→ Check for typos in your `.Rmd` files
