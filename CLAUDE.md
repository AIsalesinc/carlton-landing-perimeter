# Carlton Landing Digital Perimeter — RevFirma

Static landing page for the Carlton Landing Digital Perimeter project.

## Live URLs

- Production alias: https://carlton-site-ivory.vercel.app
- Latest deployment: https://carlton-site-8iwiwchn0-revfirmas-projects.vercel.app
- GitHub: https://github.com/AIsalesinc/carlton-landing-perimeter
- Vercel project: https://vercel.com/revfirmas-projects/carlton-site

## Project layout

```
carlton-site/
├── index.html          # Single-page site (≈33 KB). All CSS inline in <style>.
├── vercel.json         # Clean URLs + immutable cache on /assets/*
├── assets/
│   ├── logo-lightmode.svg
│   ├── logo-darkmode.svg
│   ├── RF-Logo-Black.svg
│   ├── RF-Logo-White.svg
│   ├── RF-Symbol.svg
│   └── perimeter.mp4   # 1.1 MB looping video used in FIG 02
├── .vercel/            # Vercel project link — DO NOT delete
└── CLAUDE.md           # This file
```

## Brand standards (DO NOT DRIFT)

Pulled from the official RevFirma styleguide. Keep edits inside these tokens.

| Token         | Value                          |
| ------------- | ------------------------------ |
| `--accent`    | `#26ACE8`  (brand blue)        |
| `--dark-blue` | `#20292C`                      |
| `--light-gray`| `#F9F9F9`                      |
| `--white`     | `#FFFFFF`                      |
| `--fg`        | `#1A1A1A`  (light-mode text)   |
| `--muted`     | `#666666`                      |
| `--border`    | `#CCCCCC`                      |

**Type:** Inter (body, headlines) + JetBrains Mono (buttons, eyebrows, nav).
**Type scale:** H1 72px / H2 48px / H3 36px / H4 28px / H5 20px / H6 16px, all weight 500.
**Buttons:** pill-shaped, `border-radius: 99px`, JetBrains Mono Bold, uppercase, 1px letter-spacing.

The full styleguide CSS lives inline in `index.html` `<style>`. Keep classes (`.t-h1`, `.btn-primary`, `.t-eyebrow`, etc.) — adding new components should follow the same naming.

## Page structure (13 sections, in order)

1. Hero — "Carlton Landing Protects Its Digital Space."
2. Built Here
3. 4-Stage Architecture (Perimeter → Saturation → Familiarity → Conversion)
4. What This Is
5. Visual Proof (FIG 01 phone mockup, FIG 02 perimeter video)
6. Live Metrics (16,844+ / 1.0 mi / 100%)
7. Services (3 reserved: Telehealth Doctor, Legal Services, Auto Brand)
8. Why It Matters
9. Protection + Control (includes "Fast alert system" + "Protects families and guests" bullets)
10. A Cleaner Digital Environment
11. The Future
12. Live Deployment (dark band, lists Y Combinator, Techstars, gener8tor, Rose Rock, Northwestern Mutual)
13. Final CTA

## Tone rules

- DO say: manage, protect, prioritize
- DO NOT say: control (in early sections), saturate ads, dominate (community-facing copy)
- Keep aggressive language only in: Services pills, scarcity in CTA
- Do NOT add slots beyond the 3 reserved — the line "Additional categories will be added as new local partners join" handles future growth without making residents feel passed over

## Deploy

**Manual (current setup):**

```powershell
cd $HOME\carlton-site
cmd /c "npx vercel --prod"
```

(`cmd /c` wraps it because PowerShell execution policy blocks `npx.ps1` on Windows by default.)

**Auto on git push (if Path A above is set up):**

```bash
git add . && git commit -m "..." && git push
```

Vercel rebuilds and ships within ~30 seconds of push.

## Common edits

- Hero copy → search `Protects Its` in index.html
- Service slots → search `class="services"` (each `<li class="taken">` is a reserved slot)
- Live metrics → search `class="metrics"` then change the `m-num` values
- Accelerator list → search `Y Combinator` in the Live Deployment section
- Phone mockup ad copy → search `TeleDirectMD` for the Facebook-ad block in FIG 01
- Map / video → `assets/perimeter.mp4`. Replace the file (keep the same filename) and redeploy.

## Things to avoid

- Don't break the `.vercel/project.json` link — that's how `vercel --prod` knows which project to ship to.
- Don't switch to a build framework (Next.js, etc.) unless asked. The whole point is the page is one HTML file with inline CSS — fast, portable, easy to hand off.
- Don't introduce localStorage / sessionStorage; not needed for this page.
- Don't add real telehealth / legal / financial advice copy without owner approval — RevFirma carries the regulatory risk.

## Open follow-ups

- [ ] Wire a real custom domain (e.g. `carlton.revfirma.com`). Owner picks the subdomain.
- [ ] Verify perimeter.mp4 plays on iOS Safari (autoplay + muted + playsinline are set, but worth a real-device check).
- [ ] If sponsor list grows, consider promoting the "Additional categories" line into a real expandable section.
