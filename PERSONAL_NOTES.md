# Personal Deployment Notes - Tree

**This file is gitignored and won't be included when people fork/template this repo.**

---

## Domain Setup

**Live URL:** https://littlelink.trenigma.dev

**DNS Provider:** Namecheap (trenigma.dev)

**DNS Record:**
```
Type:  CNAME
Host:  littlelink
Value: trenigma.github.io
TTL:   Automatic
```

**GitHub Pages Settings:**
- Custom domain: `littlelink.trenigma.dev`
- HTTPS: Enforced
- Source: GitHub Actions

---

## Deployment

**GitHub Repo:** https://github.com/trenigma/littlelink

**GitHub Actions Workflow:** `.github/workflows/static.yml`

**Deployment Process:**
```bash
cd ~/trenigma/littlelink-static

# Make changes to index.html, style.css, etc.

git add .
git commit -m "Update links/content"
git push

# Auto-deploys to littlelink.trenigma.dev in ~1 minute
```

---

## Analytics

### Plausible (Planned)

**Status:** Script commented out in index.html

**To Enable:**
1. Sign up at plausible.io
2. Add domain: `littlelink.trenigma.dev`
3. Uncomment script in `index.html`:
   ```html
   <script defer data-domain="littlelink.trenigma.dev" src="https://plausible.io/js/script.js"></script>
   ```

### Grafana Integration (Future)

**Plan:**
- Set up synthetic monitoring for uptime checks
- Track page load times
- Monitor button click events (if Plausible API allows)
- Add to existing Grafana dashboard (betatrenigma.grafana.net)

**Not urgent** - littlelink is static, no backend to monitor

---

## Button Links

**Current buttons (in order):**
1. BLOG → https://blog.trenigma.dev
2. BETA → https://beta.trenigma.dev
3. Calendly → https://calendly.com/trenigma
4. Rising Roots PNW → https://www.instagram.com/risingrootspnw/
5. Ko-fi → https://ko-fi.com/trenigma
6. Email → mailto:derek.ogletree@gmail.com
7. vCard Download → trenigma.vcf

**Social icons:**
- GitHub: https://github.com/trenigma
- Instagram: https://www.instagram.com/visceral_pnw
- LinkedIn: https://linkedin.com/in/trenigma/
- Signal: https://signal.me/#eu/NLY1a3uOiCc9D1TX8oOCgnsneYtgm-vrC89xIqxTSmcQHrI1Wj1BJJnpX1a23QLa

---

## Color Scheme

**Matching BETA gold accent:** `#E8A838`

**Button colors:**
- Blog: Purple `#5D3FD3` (white text)
- BETA: Gold `#E8A838` (black text) - matches BETA branding
- Calendly: Cyan `#5ECEEA` (black text)
- Rising Roots: Green `#537E32` (white text) - nature/climbing vibe
- Ko-fi: Blue `#13C3FF` (black text) - Ko-fi brand color
- Email: Orange `#FF6B35` (white text)
- vCard: Gray `#6C757D` (white text)

---

## Template Conversion

**Changes made for template:**
1. Rewrote README.md to be generic/forkable
2. Created SETUP.md with step-by-step instructions
3. This PERSONAL-NOTES.md for my deployment details
4. Added to `.gitignore`:
   ```
   PERSONAL-NOTES.md
   .DS_Store
   ```

**Wife's Fork:**
- She can fork/template this repo
- Won't get PERSONAL-NOTES.md (gitignored)
- Will get generic README + SETUP guide
- Can customize colors, links, content

---

## Migration History

**Original setup:**
- EC2 t3.micro instance (i-086d140f7c65bec38)
- Docker container: ghcr.io/techno-tim/littlelink-server:latest
- Traefik for SSL
- Cost: ~$10-15/month

**Current setup:**
- GitHub Pages (static HTML)
- Cost: $0/month
- Uptime: 99.9% SLA (better than EC2!)
- Deploy: git push

**Migration completed:** March 8, 2026

**EC2 instance:** Terminated March 8, 2026 (AMI backup created first)

---

## Future Enhancements

**Maybe:**
- Add GitHub Sponsors button (when I set that up)
- Add Resume download (JSONresume or PDF)
- Add "currently" section (job search status, projects, etc.)
- Integrate with BETA somehow? (current conditions widget?)

**Probably not:**
- Database/backend (defeats the purpose of static site)
- JavaScript frameworks (too much bloat)
- Build step (simplicity is the feature)

---

## Portfolio Value

**What this demonstrates:**
- Cost optimization ($10-15/month → $0)
- Migration skills (Docker → static)
- Template creation (making it forkable)
- Documentation (README, SETUP guide)
- Design skills (clean, modern aesthetic)
- GitHub Actions CI/CD

**LinkedIn/Resume mention:**
"Migrated personal link page from EC2/Docker to GitHub Pages, reducing costs from $10-15/month to $0 while improving uptime. Open-sourced as template for community use."

---

## Local Development

**Path:** `~/trenigma/littlelink-static/`

**Quick edits:**
```bash
cd ~/trenigma/littlelink-static
code .  # or vim index.html

# Preview in browser
open index.html

# Deploy
git add .
git commit -m "Update content"
git push
```

**No build step needed!** Just edit and push.

---

## Backup

**GitHub repo is the backup.** No need for separate backups since everything is:
- Version controlled (git history)
- Stored on GitHub (redundant infrastructure)
- Static files (no database to export)

**AMI backup of old EC2 instance:**
- AMI: `ami-0a9c2aeac777117d4`
- Name: `littlelink-backup-20260308`
- Cost: ~$0.05/month
- Can be deleted after 6 months if not needed

---

## Notes for Future Me

**When updating links:**
- Remember to test all buttons after pushing
- Check mobile view (Safari iOS, Chrome Android)
- Update vCard if contact info changes

**When helping others fork this:**
- Point them to SETUP.md (comprehensive guide)
- Remind them to update CNAME file with their domain
- Check that PERSONAL-NOTES.md is in .gitignore

**When adding new features:**
- Keep it simple (no build step)
- Test in multiple browsers
- Update README/SETUP if needed
- Consider if it's actually useful or just feature creep

---

Last updated: March 14, 2026 (after template conversion)