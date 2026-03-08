# Trenigma Link Page

Modern, responsive link-in-bio page built with pure HTML/CSS. Deployed on GitHub Pages at **littlelink.trenigma.dev**.

## Features

✨ **Modern Design**
- Dark/light theme toggle with smooth transitions
- Smooth hover animations and icon effects
- Mobile-optimized and responsive
- Fast loading (<50KB total)
- Accessibility-focused (keyboard navigation, reduced motion support)

🔗 **Custom Buttons**
- BLOG → blog.trenigma.dev
- BETA Weather Tool → beta.trenigma.dev  
- Calendly → Schedule time
- Rising Roots PNW → Community Instagram
- Ko-fi → Support my work
- Email Me → Direct mailto link
- Download vCard → One-click contact save

📱 **Social Links**
- GitHub
- Instagram  
- LinkedIn
- Signal

## Setup Instructions

### 1. Initial Deployment

```bash
# From the project directory
git add .
git commit -m "Initial commit: Trenigma link page"

# Create GitHub repo (trenigma/links or trenigma/littlelink)
# Then push
git remote add origin https://github.com/trenigma/links.git
git branch -M main
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to: https://github.com/trenigma/links/settings/pages
2. **Source:** Select "GitHub Actions" (not "Deploy from a branch")
3. Custom domain will be handled by CNAME file automatically

### 3. Configure DNS (Namecheap)

Add CNAME record:
```
link    CNAME    trenigma.github.io
```

DNS propagation: 5-30 minutes

### 4. Enable HTTPS in GitHub Pages

Once DNS is verified:
- Go to Pages settings
- Check **☑ Enforce HTTPS**

---

## Analytics Setup (Optional)

### Plausible + Grafana Integration

**Step 1: Set up Plausible**

1. Sign up at https://plausible.io (free for hobby projects)
2. Add site: `link.trenigma.dev`
3. Copy the script snippet
4. In `index.html`, uncomment the Plausible script tag (line 35)
5. Verify data is flowing in Plausible dashboard

**Step 2: Connect to Grafana**

1. Install Plausible datasource plugin in Grafana Cloud
2. Configure datasource with your Plausible site ID
3. Import dashboard or create custom panels:
   - Total visits
   - Unique visitors
   - Top referrers
   - Button click tracking (advanced - requires event goals)

**Alternative:** If you want full control, implement a CloudFlare Worker → PostgreSQL/InfluxDB pipeline.

---

## Customization Guide

### Update Links

Edit `index.html`:
- Each button has `href`, `style` (colors), and icon class
- Colors use CSS custom properties: `--button-color` and `--text-color`

### Change Theme Colors

Edit `style.css` `:root` variables:
```css
--gold: #E8A838;  /* BETA gold */
--bg-void: #09090E;  /* Background */
```

### Add/Remove Buttons

Copy an existing `.link-button` block:
```html
<a href="https://example.com" 
   class="link-button" 
   style="--button-color: #HEXCODE; --text-color: #HEXCODE;"
   target="_blank">
    <i class="fas fa-icon-name"></i>
    <span>Button Text</span>
</a>
```

Icons: Browse at https://fontawesome.com/icons

---

## Future Enhancements

### GitHub Sponsors (Placeholder Ready)

**When ready to activate:**

1. Set up GitHub Sponsors: https://github.com/sponsors
2. In `index.html`, uncomment the GitHub Sponsors button (around line 120)
3. Push changes

**Why:** Great for passive income on open source work like BETA. No platform fees.

### Advanced Analytics

**Event tracking** (track which buttons get clicked):
- Add Plausible goals for each button
- Add `data-plausible-event` attributes to links
- See which links drive the most traffic

### Resume Hosting

**When you want to re-add Resume button:**

Options:
1. Host PDF on GitHub: `/resume.pdf`
2. Use GitHub Gist with rendered HTML
3. Use read.cv or similar service
4. Self-host on blog.trenigma.dev/resume

---

## File Structure

```
littlelink-static/
├── index.html          # Main page
├── style.css           # Styles and theme
├── trenigma.vcf        # vCard contact file
├── CNAME               # Custom domain config
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

---

## Deployment

Every `git push` to `main` will auto-deploy to https://link.trenigma.dev

**No build step needed** - pure HTML/CSS served directly by GitHub Pages.

---

## Maintenance

### Update Links
Edit `index.html` → commit → push

### Update vCard
Edit `trenigma.vcf` → commit → push

### Monitor Uptime
GitHub Pages SLA: 99.9% uptime

### Cost
**$0/month** forever (GitHub Pages is free for public repos)

---

## License

Personal project - all rights reserved to Derek Ogletree (trenigma).

---

## Credits

- Built by Derek Ogletree (trenigma)
- Icons: Font Awesome
- Inspiration: LittleLink Server theme
- Color scheme: Matches BETA weather tool aesthetic

---

**Questions?** Email derek.ogletree@gmail.com or open an issue.