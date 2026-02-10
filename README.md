# 🚀 GitHub Pages Deployment Guide

Deploy your 360° product viewer to GitHub Pages in 5 minutes!

## 📋 What You'll Get

Once deployed, you'll have a URL like:
```
https://YOUR-USERNAME.github.io/lane3600-viewer/
```

This URL can be embedded in GitBook via iframely!

---

## 🎯 Quick Deployment Steps

### Step 1: Extract the Files

1. **Unzip** `lane3600-viewer-complete.zip`
2. You should see:
   ```
   deployment-package/
   ├── index.html
   ├── README.md
   └── frames/
       ├── frame_000.png
       ├── frame_001.png
       └── ... (60 frames total)
   ```

### Step 2: Create GitHub Repository

1. Go to **https://github.com/new**
2. **Repository name:** `lane3600-viewer` (or any name you want)
3. **Visibility:** ✅ **Public** (required for GitHub Pages)
4. **Do NOT** initialize with README
5. Click **Create repository**

### Step 3: Upload Files to GitHub

**Option A: Using GitHub Web Interface (Easiest)**

1. On your new repo page, click **uploading an existing file**
2. **Drag and drop** the entire `deployment-package` folder contents:
   - `index.html`
   - `frames/` folder (with all 60 images inside)
3. Scroll down and click **Commit changes**

**Option B: Using Git Command Line**

```bash
# Navigate to your deployment-package folder
cd path/to/deployment-package

# Initialize git
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit: 360 viewer"

# Add remote (replace YOUR-USERNAME and lane3600-viewer with yours)
git remote add origin https://github.com/YOUR-USERNAME/lane3600-viewer.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 4: Enable GitHub Pages

1. In your repo, go to **Settings** (top menu)
2. In the left sidebar, click **Pages**
3. Under **Source**, select:
   - Branch: **`main`**
   - Folder: **`/ (root)`**
4. Click **Save**

### Step 5: Wait & Get Your URL

1. Wait **1-2 minutes** for GitHub to deploy
2. Refresh the Pages settings page
3. You'll see: **"Your site is live at https://YOUR-USERNAME.github.io/lane3600-viewer/"**
4. Click the URL to test it!

---

## ✅ Testing the Deployment

Once live, test your viewer:

1. **Open the URL** in your browser
2. You should see the Ingenico Lane 3600 viewer
3. **Try dragging** to rotate - it should work smoothly
4. **Test on mobile** - it should be responsive

---

## 🔗 Embedding in GitBook

Once your GitHub Pages site is live:

### Method 1: GitBook Embed Block
1. In GitBook, add an **Embed** block
2. Paste your GitHub Pages URL: `https://YOUR-USERNAME.github.io/lane3600-viewer/`
3. iframely should auto-detect and embed it

### Method 2: Direct iframe
If Method 1 doesn't work, use a custom HTML block:

```html
<iframe 
  src="https://YOUR-USERNAME.github.io/lane3600-viewer/" 
  width="100%" 
  height="600" 
  frameborder="0"
  style="border: none; border-radius: 8px;"
>
</iframe>
```

---

## 🎨 Customization (Optional)

Want to change colors or behavior? Edit `index.html`:

**Change background gradient:**
Find this line (~line 20):
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```
Replace with your colors!

**Adjust momentum/physics:**
Find this section (~line 250):
```javascript
const CONFIG = {
    totalFrames: 60,
    framePathTemplate: 'frames/frame_{index}.png',
    friction: 0.92,        // Higher = more momentum (0-1)
    sensitivity: 0.5       // Higher = faster rotation
};
```

After making changes:
1. Save the file
2. Commit and push to GitHub
3. Wait 1-2 minutes for GitHub Pages to update

---

## 🐛 Troubleshooting

### ❌ "404 - Page not found"
- Wait 2-3 minutes after enabling Pages
- Check that branch is `main` and folder is `/ (root)`
- Verify `index.html` is in the root of your repo

### ❌ "Images not loading"
- Check that `frames/` folder is uploaded
- Verify all 60 frames are in the `frames/` folder
- Check browser console (F12) for errors

### ❌ "Viewer shows error"
- Check that frame files are named `frame_000.png` to `frame_059.png`
- Verify images uploaded correctly (check file sizes)

### ❌ "Not embedding in GitBook"
- Make sure your repo is **Public** (not Private)
- Try both the root URL and `/index.html`: 
  - `https://YOUR-USERNAME.github.io/lane3600-viewer/`
  - `https://YOUR-USERNAME.github.io/lane3600-viewer/index.html`
- Use direct iframe method if auto-embed doesn't work

---

## 📊 Performance Notes

- **Total size:** ~25MB (60 high-res frames)
- **Loading time:** 3-5 seconds on fast connection
- **Bandwidth:** GitHub Pages has no bandwidth limits for public repos

**To optimize loading:**
1. Compress images with [TinyPNG](https://tinypng.com/)
2. Or convert to WebP format for ~30% smaller files

---

## 🔄 Updating Your Viewer

To update frames or settings:

1. Edit files locally
2. Commit and push changes:
   ```bash
   git add .
   git commit -m "Update viewer"
   git push
   ```
3. Wait 1-2 minutes for changes to go live

---

## 🆘 Need Help?

- **GitHub Pages docs:** https://docs.github.com/en/pages
- **Check deployment status:** Settings → Pages
- **View build logs:** Actions tab in your repo

---

## ✨ Features Included

- ✅ Drag to rotate (mouse + touch)
- ✅ Momentum physics
- ✅ Loading progress bar
- ✅ Mobile responsive
- ✅ Beautiful gradient background
- ✅ Optimized for embedding
- ✅ Zero external dependencies

---

**Your URL will be:**
```
https://YOUR-USERNAME.github.io/lane3600-viewer/
```

**Share this URL to embed it anywhere!** 🎉
