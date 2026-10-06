# Softer Strategies — website

One-page site for **Softer Strategies LLC**: a brand, product + experience strategy studio based in Washington, DC.

`index.html` is the whole site in one file: HTML, CSS, JavaScript, and all photos. Open it in a browser and it works. No build step and no dependencies, except Google Fonts (Fraunces + Hanken Grotesk).

---

## For Dahnaya: building it out

**Hosting.** The file works as-is on GitHub Pages, Netlify, Vercel, or any static host. Rename nothing; `index.html` is the homepage.

**Recommended first cleanup: move the images out.** All 13 photos are embedded as base64 (`src="data:image/jpeg;base64,..."`), which makes the file ~2 MB. For speed and SEO:
1. Save each image into an `/images` folder as a compressed `.webp` or `.jpg`.
2. Replace each `src="data:image/..."` with `src="images/filename.webp"`.
3. Keep the `alt` text and the `style="object-position:..."` on each image; those control the crop.

**Search the file for these comments.** Every editable spot is marked:
- **Contact form → hello@softerstrategies.com.** Submissions are delivered through FormSubmit (`FORM_ENDPOINT` near the bottom of the script). **One-time activation:** once the site is live, submit the form once, then click *Activate* in the email FormSubmit sends to hello@softerstrategies.com. Inquiries arrive with the subject "New inquiry — Name" or "Pilot inquiry — Name", and Reply goes straight to the sender. If sending ever fails, the form opens a pre-filled email to hello@ as a backup. To switch services (Formspree, Netlify Forms), replace the `FORM_ENDPOINT` URL.
- `UPDATE EMAIL`: hello@softerstrategies.com and partnership@softerstrategies.com in the footer, plus hello@ for the form + contact links ( every "Let's build something" / "Let's work" / "Start a conversation" button opens the form).
- `UPDATE METRIC`: the four numbers in the Mahogany Pages section.
- `UPDATE EVENT LIST`: the event weekends list.
- `ADD SOCIAL LINKS`: commented-out Instagram/LinkedIn lines in the footer.
- `CLIENT WORK`: where a "Selected work" section can go once a client approves being featured.

**How the page is organized.** Each section is wrapped in a comment banner, e.g. `<!-- ============ 13 · FOUNDER ============ -->`. Order: Hero → What we do (circle reveal) → Positioning → Capabilities (horizontal scroll on desktop) → Experiences → Digital concierge phone → Who it's for → Partnerships → Capture the story → Experience intelligence → Soft Queer Wealth + The Mahogany Pages → Technology → The softer method → Founder → Team → Contact → Footer → Inquiry form (dialog).

**Section tabs.** A floating pill at the bottom of the screen (`<nav class="tabbar">`) appears after the hero and lets visitors jump between sections; the active tab highlights as they scroll. To add or rename a tab, edit its `<li>` and make sure the `href` matches a section `id`.

**Design tokens.** All colors and fonts are CSS variables at the top of the `<style>` block (`--cream`, `--espresso`, `--blush`, `--rose`, etc.). Dark mode is handled automatically from the same tokens.

**Motion.** The scroll effects are hand-written vanilla JS (no GSAP or libraries) and switch off automatically for visitors with "reduce motion" turned on. Everything stays readable with JS disabled.

**Checks before launch.**
- Test on a real iPhone (Safari) and Android (Chrome); most traffic will come from social on mobile.
- Confirm the pinned scroll sections (phone mockup, horizontal capabilities) feel smooth on older phones.
- Run Lighthouse; after moving images out, aim for 90+ on Performance and Accessibility.

---

## For Davina: SEO

**Already in place:** semantic HTML (`header`, `main`, `section`, `footer`), one `h1`, logical `h2`/`h3` order, descriptive `alt` text on every photo, a meta description, and basic Open Graph title/description.

**To add:**
- **Domain + canonical:** `<link rel="canonical" href="https://softerstrategies.com/">` once the domain is live.
- **Share image:** `og:image` (1200×630) plus `twitter:card` tags; there's an `UPDATE` comment where it goes.
- **Favicon + touch icons:** `favicon.ico`, `apple-touch-icon.png`.
- **Structured data:** JSON-LD `ProfessionalService` / `Organization` schema (name, url, email, `areaServed`, Washington, DC address/region, founder: Briana).
- **Search Console + sitemap:** a `sitemap.xml` and `robots.txt`, then submit to Google Search Console and Bing Webmaster Tools.
- **Analytics:** privacy-conscious and consent-based, to match the site's own promise in the "Experience intelligence" section (e.g. Plausible or Fathom, or GA4 with a consent banner).
- **Keywords to support in copy/meta:** brand strategy DC, experience strategy, digital concierge for events, conference/summit guest experience, Black-owned strategy studio, The Mahogany Pages.
- **Performance:** moving images out of the HTML (see Dahnaya's section) is the single biggest SEO/performance win.

---

## Content notes
- **Soft Queer Wealth** and **The Mahogany Pages** are separate entities from Softer Strategies (sister company and its product). Keep them presented that way.
- Team bios (Rae, Davina, Briana, Dahnaya) should be reviewed by each person before launch.
- Get permission for any photo you didn't take yourselves before launch.
- The three Beach Club / Dining / Sailing images on the phone mockup are generated graphics; swap in licensed photos any time.
