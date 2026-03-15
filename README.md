# Static Link Page Template

A clean, modern link-in-bio page with dark/light theme toggle. Built with pure HTML/CSS/JavaScript - no frameworks, no dependencies, no bloat.

**[Live Demo →](https://littlelink.trenigma.dev)**

---

## Features

✨ **Dark/Light Theme Toggle** - Persistent preference using localStorage  
📱 **Mobile-Optimized** - Responsive design, touch-friendly buttons  
📇 **vCard Download** - Let people save your contact info  
⚡ **Fast** - Entire site is <50KB, loads instantly  
🎨 **Customizable** - Easy to modify colors, buttons, and layout  
🚀 **Easy Deploy** - GitHub Pages, Netlify, Vercel, or any static host  
♿ **Accessible** - ARIA labels, keyboard navigation, semantic HTML  

---

## Quick Start

### 1. Use This Template

Click **"Use this template"** button above, or fork this repo.

### 2. Edit Your Info

Open `index.html` and customize:
- **Profile**: Name, bio, avatar URL
- **Buttons**: Add/remove/reorder link buttons
- **Social Icons**: GitHub, Instagram, LinkedIn, etc.

### 3. Update vCard

Edit `trenigma.vcf` with your contact details.

### 4. Deploy

Push to GitHub and enable GitHub Pages, or deploy to any static host.

See **[SETUP.md](SETUP.md)** for detailed instructions.

---

## Customization

### Change Button Colors

Each button has inline CSS variables:

```html
<a href="https://example.com" 
   class="link-button" 
   style="--button-color: #5D3FD3; --text-color: #ffffff;">
    <i class="fas fa-icon"></i>
    <span>Button Text</span>
</a>
```

### Add New Buttons

Copy an existing button and modify:
1. Update `href` URL
2. Change icon (`fas fa-icon`)
3. Set colors (`--button-color`, `--text-color`)
4. Update text

### Change Theme Colors

Edit CSS variables in `style.css`:

```css
:root {
    --bg-base: #0F1117;
    --text-primary: #E8E8E8;
    /* ... */
}
```

---

## File Structure

```
littlelink/
├── index.html          # Main page
├── style.css           # All styles
├── trenigma.vcf        # Contact card (update with your info)
├── CNAME               # Custom domain (optional)
├── README.md           # This file
└── SETUP.md            # Detailed setup guide
```

---

## Tech Stack

- **HTML5** - Semantic markup
- **CSS3** - Modern layouts, animations, custom properties
- **JavaScript** - Theme toggle (vanilla, no frameworks)
- **Font Awesome** - Icons (loaded from CDN)

**No build step. No package.json. Just push and deploy.** 🚀

---

## Analytics (Optional)

Plausible Analytics is commented out in `index.html`. To enable:

1. Sign up at [plausible.io](https://plausible.io)
2. Add your domain
3. Uncomment the script tag in `index.html`

Other analytics platforms (Google Analytics, Fathom, etc.) can be added similarly.

---

## Custom Domain

1. Add a `CNAME` file with your domain:
   ```
   link.yourdomain.com
   ```

2. Configure DNS:
   ```
   link    CNAME    yourusername.github.io
   ```

3. Enable HTTPS in GitHub Pages settings

See [SETUP.md](SETUP.md) for detailed instructions.

---

## Examples

**Different use cases:**
- Personal portfolio landing page
- Link-in-bio for social media
- Digital business card
- Resume/contact page
- Event organizer links

**Sites built with this template:**
- [littlelink.trenigma.dev](https://littlelink.trenigma.dev) - Original version

*Using this template? Open a PR to add your site here!*

---

## Contributing

Found a bug? Want to add a feature? PRs welcome!

**Ideas for contributions:**
- Additional theme presets
- More icon sets
- Animation options
- Multi-language support
- Accessibility improvements

---

## License

MIT License - use freely, modify as needed, just keep it open source.

---

## Credits

Built by [trenigma](https://github.com/trenigma) as a replacement for Docker-based LittleLink server. Simplified, modernized, and made forkable for the community.

**Icons:** [Font Awesome](https://fontawesome.com)

---

## Support

Need help? Check [SETUP.md](SETUP.md) for detailed instructions.

Found this useful? Consider:
- ⭐ Star this repo
- 🍴 Fork and customize
- 📣 Share with others

Built something cool with this? Let me know!