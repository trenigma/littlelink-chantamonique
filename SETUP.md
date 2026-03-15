# Setup Guide - Step-by-Step

Complete guide to set up your own link page using this template.

---

## Step 1: Get Your Own Copy

### Option A: Use This Template (Recommended)

1. Click **"Use this template"** button at the top of this repo
2. Name your new repo (e.g., `my-links`, `littlelink`, `links`)
3. Choose **Public** (required for free GitHub Pages)
4. Click **"Create repository"**

### Option B: Fork This Repo

1. Click **"Fork"** button at the top
2. Your fork will be created at `github.com/YOUR-USERNAME/littlelink`

---

## Step 2: Edit Your Profile Info

### Update Avatar

**Option 1: Use GitHub Avatar (Easy)**

Your GitHub avatar URL is:
```
https://avatars.githubusercontent.com/u/YOUR-USER-ID?v=4
```

Find your user ID at: https://api.github.com/users/YOUR-USERNAME

**Option 2: Use Custom Image**

Upload an image to your repo and reference it:
```html
<img src="avatar.jpg" alt="Your Name's Profile Picture" class="avatar">
```

Or use an external URL (Imgur, etc.)

### Edit Name & Bio

Open `index.html` and find:

```html
<h1 class="name">trenigma</h1>
<p class="bio">SRE/DevOps Engineer | Outdoor Enthusiast | Community Builder</p>
```

Replace with your info:

```html
<h1 class="name">Your Name</h1>
<p class="bio">Your job title | Your interests | Your vibe</p>
```

---

## Step 3: Update Buttons

### Remove Buttons You Don't Need

Find the button in `index.html` and delete the entire `<a>` tag:

```html
<!-- Delete this entire block if you don't need it -->
<a href="https://calendly.com/trenigma" 
   class="link-button" 
   style="--button-color: #5ECEEA; --text-color: #000000;">
    <i class="fas fa-calendar"></i>
    <span>Calendly</span>
</a>
```

### Edit Existing Buttons

Change the URL, text, and icon:

```html
<a href="YOUR-URL-HERE" 
   class="link-button" 
   style="--button-color: #5D3FD3; --text-color: #ffffff;">
    <i class="fas fa-blog"></i>  <!-- Change icon -->
    <span>YOUR TEXT</span>         <!-- Change text -->
</a>
```

**Common icons:**
- `fas fa-blog` - Blog
- `fas fa-briefcase` - Portfolio/Work
- `fas fa-envelope` - Email
- `fas fa-calendar` - Calendar/Scheduling
- `fas fa-coffee` - Ko-fi/Support
- `fas fa-download` - Download
- `fas fa-link` - Generic link
- `fab fa-youtube` - YouTube
- `fab fa-twitter` - Twitter/X
- `fab fa-linkedin` - LinkedIn

See all icons at: https://fontawesome.com/icons

### Change Button Colors

Each button has two color variables:

```html
style="--button-color: #5D3FD3; --text-color: #ffffff;"
```

**Popular color combos:**
- Purple: `#5D3FD3` (white text)
- Gold: `#E8A838` (black text)
- Cyan: `#5ECEEA` (black text)
- Green: `#537E32` (white text)
- Blue: `#13C3FF` (black text)
- Orange: `#FF6B35` (white text)
- Red: `#E63946` (white text)
- Pink: `#EA4AAA` (white text)

### Add New Buttons

Copy an existing button block and paste it where you want the new button to appear (order matters!):

```html
<a href="https://your-new-link.com" 
   class="link-button" 
   style="--button-color: #YOUR-COLOR; --text-color: #ffffff;"
   target="_blank"
   rel="noopener noreferrer">
    <i class="fas fa-YOUR-ICON"></i>
    <span>Button Name</span>
</a>
```

---

## Step 4: Update Social Icons

Find the social icons section:

```html
<div class="social-icons">
    <a href="https://github.com/YOUR-USERNAME">
        <i class="fab fa-github"></i>
    </a>
    <!-- ... more icons ... -->
</div>
```

**Add/remove/update URLs** for your social profiles.

**Common social icons:**
- `fab fa-github` - GitHub
- `fab fa-instagram` - Instagram
- `fab fa-linkedin` - LinkedIn
- `fab fa-twitter` - Twitter/X
- `fab fa-youtube` - YouTube
- `fab fa-facebook` - Facebook
- `fab fa-tiktok` - TikTok
- `fab fa-mastodon` - Mastodon
- `fab fa-discord` - Discord
- `fas fa-comment-dots` - Signal/Chat

---

## Step 5: Create Your vCard

### What is a vCard?

A `.vcf` file that lets people save your contact info to their phone/computer with one click.

### Edit `trenigma.vcf`

Open the file and replace with your info:

```
BEGIN:VCARD
VERSION:3.0
FN:Your Full Name
N:Last;First;;;
EMAIL;TYPE=INTERNET:your.email@example.com
TEL;TYPE=CELL:+1-555-123-4567
URL:https://yourwebsite.com
URL:https://github.com/yourusername
URL:https://linkedin.com/in/yourusername
NOTE:Your job title or tagline
END:VCARD
```

**Important:**
- Keep `BEGIN:VCARD` and `END:VCARD`
- Use your real info
- Delete lines you don't want to share

### Rename the vCard File (Optional)

If you rename `trenigma.vcf` to `yourname.vcf`, update the button in `index.html`:

```html
<a href="yourname.vcf" 
   class="link-button"
   download>
```

---

## Step 6: Update Meta Tags (SEO)

Open `index.html` and find the `<head>` section. Update:

```html
<title>Your Name | Links</title>
<meta name="description" content="Your short bio here">
<meta name="author" content="Your Name">

<!-- Update all og: and twitter: meta tags too -->
<meta property="og:title" content="Your Name | Links">
<meta property="og:description" content="Your short bio here">
```

---

## Step 7: Test Locally (Optional)

### View in Browser

Just double-click `index.html` - it should open in your browser.

**Test checklist:**
- [ ] Profile shows your name and bio
- [ ] Avatar displays
- [ ] All buttons work (click each one)
- [ ] Social icons link correctly
- [ ] Theme toggle works (moon/sun icon)
- [ ] vCard downloads when clicked
- [ ] Mobile view looks good (resize browser)

---

## Step 8: Deploy to GitHub Pages

### Enable GitHub Pages

1. Go to your repo on GitHub
2. Click **Settings** tab
3. Scroll to **Pages** section (left sidebar)
4. Under **Source**, select:
   - Source: **GitHub Actions**
5. GitHub will auto-detect the static site and deploy it

### Create GitHub Actions Workflow

**If GitHub Actions isn't an option**, create `.github/workflows/static.yml`:

```yaml
name: Deploy static content to Pages

on:
  push:
    branches: ["main"]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      
      - name: Setup Pages
        uses: actions/configure-pages@v4
      
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: '.'
      
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

### Check Deployment

1. Push your changes to GitHub
2. Go to **Actions** tab - watch the workflow run
3. Once complete, your site is live at:
   ```
   https://YOUR-USERNAME.github.io/REPO-NAME/
   ```

**Takes about 1-2 minutes for first deployment.**

---

## Step 9: Add Custom Domain (Optional)

### Get a Domain

Buy a domain from:
- Namecheap
- Google Domains
- Cloudflare
- etc.

### Add CNAME File

Create a file called `CNAME` (no extension) in your repo with just your domain:

```
links.yourdomain.com
```

Commit and push this file.

### Configure DNS

**At your DNS provider** (Namecheap, Cloudflare, etc.), add a CNAME record:

```
Type:  CNAME
Host:  links (or whatever subdomain you want)
Value: YOUR-USERNAME.github.io
TTL:   Automatic or 300
```

**Example:**
- Domain: `yourdomain.com`
- Subdomain: `links`
- Result: `links.yourdomain.com` → your link page

### Enable HTTPS

1. Go to GitHub repo **Settings** → **Pages**
2. Under **Custom domain**, enter your domain: `links.yourdomain.com`
3. Click **Save**
4. Wait for DNS check (green checkmark)
5. Enable **Enforce HTTPS**

**DNS propagation takes 5-60 minutes.**

---

## Step 10: Optional Enhancements

### Add Analytics

**Plausible (Privacy-friendly):**

1. Sign up at https://plausible.io
2. Add your domain
3. Uncomment this line in `index.html`:
   ```html
   <script defer data-domain="YOUR-DOMAIN" src="https://plausible.io/js/script.js"></script>
   ```

**Google Analytics:**

Add before `</head>`:
```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Change Theme Colors

Edit `style.css` variables:

```css
:root {
    --bg-base: #0F1117;        /* Dark background */
    --bg-raised: #1E2535;      /* Buttons, cards */
    --text-primary: #E8E8E8;   /* Main text */
    --text-secondary: #A0A0A0; /* Bio text */
    --accent: #E8A838;         /* Gold accent */
}
```

### Add Favicon

1. Create a 512x512px image
2. Convert to favicon at https://favicon.io
3. Add to `<head>`:
   ```html
   <link rel="icon" href="favicon.ico" type="image/x-icon">
   ```

---

## Troubleshooting

### Site Not Deploying

**Check:**
1. Repo is **Public** (GitHub Pages requires this for free tier)
2. GitHub Actions workflow exists (`.github/workflows/static.yml`)
3. Check **Actions** tab for errors
4. Branch is `main` (or update workflow to match your branch name)

### Custom Domain Not Working

**Check:**
1. CNAME file exists with correct domain
2. DNS CNAME record is correct
3. DNS has propagated (use https://dnschecker.org)
4. GitHub Pages settings show green checkmark
5. Wait 5-60 minutes for DNS propagation

### Theme Toggle Not Working

**Check:**
1. JavaScript is enabled in browser
2. No browser errors (open DevTools console)
3. Theme toggle script is in `index.html` before `</body>`

### Buttons Not Centered

**Check:**
1. `.links` class exists on the container
2. No CSS conflicts from other stylesheets
3. Browser is modern (CSS Grid support)

---

## Example Workflows

### For Personal Branding
- Blog link
- Portfolio
- LinkedIn
- GitHub
- Email contact
- Resume download
- Social profiles

### For Content Creators
- YouTube channel
- Podcast
- Newsletter signup
- Patreon/Ko-fi
- Social media links
- Merch store

### For Small Business
- Website
- Booking calendar
- Email
- Phone (tel: link)
- Social media
- Reviews/testimonials link
- Location/maps

---

## Need Help?

1. Check [README.md](README.md) for features overview
2. Review this guide again (most issues are covered above)
3. Open an issue on GitHub
4. Search existing issues - someone might have had the same problem

---

## Next Steps

**After deploying:**
1. Share your link! Add it to:
   - Instagram/Twitter/TikTok bio
   - Email signature
   - Business cards
   - LinkedIn profile
2. Monitor analytics (if enabled)
3. Update links as needed (just edit and push)
4. Star this template repo if it was useful!

**That's it! You're live.** 🚀