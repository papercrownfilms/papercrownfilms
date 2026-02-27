# Paper Crown Films Website - Deployment Guide

## What You Have

Your complete website is ready to deploy! This folder contains:
- `index.html` - Your website
- `logo.png` - Paper Crown Films logo
- `all_i_cee.jpg` - All I Cee poster
- `stan.jpg` - Stan poster
- `de_thierry_plains.jpg` - De Thierry Plains poster
- `intro.mp4` - Intro video
- `CNAME` - Custom domain configuration

## Step 1: Create GitHub Account (if you don't have one)

1. Go to https://github.com
2. Sign up for a free account
3. Verify your email

## Step 2: Create Repository

1. Go to https://github.com/new
2. Repository name: `papercrownfilms` (or any name you want)
3. Set to **Public**
4. **Do NOT** initialize with README, .gitignore, or license
5. Click "Create repository"

## Step 3: Upload Files

**Option A: Using GitHub Web Interface (Easiest)**

1. On your new repository page, click "uploading an existing file"
2. Drag and drop ALL files from this folder into the upload area
3. Scroll down and click "Commit changes"

**Option B: Using Git Command Line**

If you have Git installed:

```bash
# Navigate to the website_deploy folder
cd path/to/website_deploy

# Initialize git
git init

# Add all files
git add .

# Commit
git commit -m "Initial website deployment"

# Add your GitHub repository as remote (replace YOUR-USERNAME)
git remote add origin https://github.com/YOUR-USERNAME/papercrownfilms.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Step 4: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" (top right)
3. Click "Pages" in the left sidebar
4. Under "Source", select "Deploy from a branch"
5. Under "Branch", select "main" and "/root"
6. Click "Save"
7. Wait 2-3 minutes for deployment

Your site will be live at: `https://YOUR-USERNAME.github.io/papercrownfilms/`

## Step 5: Configure Custom Domains

### For papercrownfilms.com:

1. Go to your domain registrar (where you bought the domain)
2. Find DNS settings
3. Add these records:

**A Records** (point to GitHub Pages):
```
Type: A
Name: @
Value: 185.199.108.153

Type: A
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153
```

**CNAME Record** (for www):
```
Type: CNAME
Name: www
Value: YOUR-USERNAME.github.io
```

### For papercrownfilms.com.au:

**Option 1 - Redirect** (Recommended):
Set up a redirect from papercrownfilms.com.au to papercrownfilms.com in your domain registrar's settings.

**Option 2 - Same DNS Setup**:
Use the same A and CNAME records as above, but you can only have ONE domain in the CNAME file at a time. GitHub Pages works best with one primary domain.

## Step 6: Verify Domain in GitHub

1. Back in your GitHub repository settings → Pages
2. Under "Custom domain", enter: `papercrownfilms.com`
3. Click "Save"
4. Wait for DNS check (can take 24-48 hours, usually faster)
5. Once verified, check "Enforce HTTPS"

## Troubleshooting

**Site not loading?**
- Wait 5-10 minutes after enabling Pages
- Check that all files uploaded correctly
- Make sure repository is Public

**Domain not working?**
- DNS changes can take 24-48 hours
- Double-check DNS records match exactly
- Try clearing browser cache
- Check GitHub Pages shows "DNS check successful"

**Intro video not playing?**
- Large video files may take time to load
- Users can click "Skip Intro" to bypass

## Updating Your Site

To make changes:
1. Edit files locally
2. Go to repository → "Upload files" 
3. Drag updated files (will overwrite old ones)
4. Commit changes
5. Wait 2-3 minutes for site to update

## Need Help?

- GitHub Pages Docs: https://docs.github.com/en/pages
- GitHub Support: https://support.github.com

---

**Your domains:**
- papercrownfilms.com (primary)
- papercrownfilms.com.au (redirect to .com)

**Free forever!** GitHub Pages is completely free for public repositories.
