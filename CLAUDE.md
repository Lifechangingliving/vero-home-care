# Vero Home Care Website

This is the website for **Vero Home Care LLC**, a non-medical home care agency in the Houston, Texas area, owned by **Markeisha Eaves, RN**. Markeisha is the person you are working with. She is a nurse and business owner, not a web developer.

## How to work with Markeisha

- Use plain, friendly language. Explain what you changed in terms of what visitors will see, not code.
- Before changing anything, look at the current page and confirm you are editing the right section.
- After making changes, run `open index.html` (or `open careers.html`) so she can preview the change in her browser **before** it goes live.
- **Do not push to the live site until Markeisha says it looks good.** Pushing is how changes go public.
- If a request is unclear (which page? which wording?), ask one short question rather than guessing.
- If she asks for something that conflicts with the content rules below (for example, medical claims or guaranteed coverage), explain the concern kindly and offer safe wording.

## The site at a glance

| | |
|---|---|
| Live site (today) | https://tammyamosley2018-hash.github.io/vero-home-care/ |
| Future domain | https://infoverohomecare.com (owned at Namecheap, **not connected yet**, see "Domain" below) |
| Hosting | GitHub Pages, served from the `main` branch, root folder |
| Tech | Plain HTML + CSS + a small JavaScript file. No build step, no frameworks, no package installs. |
| Phone | 832-892-9392 (`tel:8328929392`) |
| Email | contact@infoverohomecare.com (Google Workspace, works) |
| Office hours | Monday through Friday, 9 a.m. to 5 p.m. |
| License | Texas HCSSA License #025281 (shown in homepage footer) |

## Files

```
index.html         Homepage (all main content)
careers.html       Caregiver careers page
styles.css         Original base styles (minified onto one line, avoid editing; add overrides to mobile-fixes.css)
mobile-fixes.css   All newer styles, section styles, and responsive fixes. Put new CSS here.
script.js          Mobile menu, header background on scroll, fade-in on scroll, footer year
images/            caregiver-conversation.jpg, bedside-support.jpg, caregiver-careers.jpg
CLAUDE.md          This file
```

### Homepage sections (index.html, top to bottom)

| Section | id | What it is |
|---|---|---|
| Header / nav | | Logo, links, "Start a conversation" button, mobile hamburger menu |
| Hero | `#home` | Full-screen looping video (Streamable `xfst18`, muted, no controls) with headline "More support. More life at home." |
| Credentials bar | | Personal / Reliable / Dignified / Houston |
| Mission | `#about` | Mission statement, values chips, caregiver photo |
| Services | `#services` | Personal Care, Companionship, Household Support, Family Relief |
| Approach | `#approach` | "The Vero difference" principles |
| Who we serve | `#who-we-serve` | Audience copy, tags, bedside photo |
| Founder | | Markeisha Eaves, RN bio and specialties |
| Referrals | | For families and healthcare professionals |
| Standards | `#standards` | Privacy & HIPAA, caregiver standards, payment & benefit options |
| Contact | `#contact` | Phone, email, location, hours, "Request care online" + "Call to get started" buttons |
| Request care form | `#request-care` | Embedded Google Form (inside the Contact section) |
| Footer | | Logo, tagline, Careers link, year, license line |

### Careers page (careers.html)

Hero with photo, "Meaningful work" intro, "What we value" (Compassion, Dependability, Respect), and an `#apply` section. Applications currently go by email (a `mailto:` button to contact@infoverohomecare.com with subject "Caregiver Application - Vero Home Care").

**Important:** the navigation menu exists separately in `index.html` and `careers.html`, and each has both a desktop menu and a mobile menu. If you add, rename, or remove a nav link, update **all four** places.

## The care request form

- Google Form (client intake): https://forms.gle/qr6rai2WyUT3hkH97
- Full URL used in the page: `https://docs.google.com/forms/d/e/1FAIpQLSfLLAzWOMJUGEfnLSa4UJI4fyeAswZISxjFPuU65JHcm36Gbw/viewform` (embedded with `?embedded=true`)
- Questions: who needs care, living arrangements, hours per week, how they will pay, name, phone, preferred contact method, questions/comments.
- Responses go to Markeisha's Google Forms / Google Sheet, not to this website.
- Editing the form's questions happens in Google Forms. The website updates automatically; no code change needed.
- The embed has a fixed height (`.request-care-frame iframe` in `mobile-fixes.css`: 1900px desktop, 2150px under 900px wide). If questions are added or removed, the height may need adjusting so there is no extra blank space or inner scrollbar.
- The form must **not** require Google sign-in. In Google Forms → Settings → Responses, keep "Limit to 1 response" **off** and "Collect email addresses" set to **Responder input** (not "Verified"). If visitors report a sign-in screen, check these first.
- If Markeisha replaces the form with a new one, update the URL in **both** places in `index.html` (the iframe `src` and the "Open it in a new tab" link).

## Design system (keep changes consistent)

- **Fonts:** "Instrument Serif" for big headings (`.display`, `h1`, card titles), "DM Sans" for everything else. Loaded from Google Fonts in each page's `<head>`.
- **Colors** (CSS variables in `styles.css`): `--black #11100e`, `--black-2 #1a1815`, `--cream #f3eee4`, `--cream-2 #e6ded0`, `--muted #a9a197`. Sections alternate between dark (black) and light (cream/white).
- **Headings pattern:** a small uppercase `.kicker` label, then a `.display` heading where the second line is in `<em>` (italic), e.g. `Thoughtful care.<br><em>Every day.</em>`
- **Buttons:** `.button` plus `.button-light` (white), `.button-cream`, or `.button-outline` (currently styled only inside `.contact-card`).
- **Fade-in:** add class `reveal` to elements that should fade in on scroll (`delay-1/2/3` to stagger).
- **Layout width:** wrap content in `<div class="shell">`.
- **Mobile:** breakpoints at 900px and 600px. Always check that new sections stack correctly on a phone.
- Photos are real editorial images. Use descriptive `alt` text, and `loading="lazy"` for anything below the hero.

## Content rules (very important)

1. **Vero is NON-MEDICAL home care.** Never describe services as medical, skilled nursing, home health, nursing care, medication administration, wound care, or therapy. Markeisha is an RN, but the agency provides non-medical personal assistance. Her nursing background can be mentioned as experience that shapes the approach, not as a service.
2. **Never promise coverage or payment.** Payment sources (private pay, Medicaid, long-term care insurance, Veterans benefits, workers' compensation, Area Agency on Aging grants) are always "may include" and "eligibility varies." Keep the note that traditional Medicare generally does not cover ongoing non-medical personal care.
3. **Privacy:** keep the warning not to send medical records, diagnoses, Social Security numbers, or sensitive health information by email. Do not add website forms that collect diagnoses or health details.
4. **No em dashes (—) or en dashes (–) in sentences.** Markeisha's style removed them site-wide. Use periods, commas, or "and" instead. (Hyphens inside words like "long-term" are fine.)
5. Don't invent facts: testimonials, numbers of clients, awards, certifications, prices, or service areas beyond "Houston, Texas area." Ask Markeisha for real details.
6. Keep the license line "Texas HCSSA License #025281" in the homepage footer.
7. Tone: warm, calm, dignified, respectful. Speak to families and older adults. Keep sentences short and clear.

## Making a change: the routine

1. `git pull` first (in case anything changed on GitHub).
2. Make the edit.
3. **Cache busting:** the pages load CSS/JS with version tags like `mobile-fixes.css?v=20261015a`. When you change `mobile-fixes.css`, `styles.css`, or `script.js`, update that `?v=` value to today's date (format `YYYYMMDDa`, then `b`, `c` for more changes the same day) in **both** `index.html` and `careers.html`. Otherwise phones may keep showing the old look.
4. `open index.html` and let Markeisha review. Ask her to check on her phone after it is live as well.
5. When she approves:
   ```
   git add -A
   git commit -m "Short description of the change"
   git push
   ```
6. GitHub Pages updates in about 1 minute. Confirm with `gh run list -L 1` (should say `completed success`), then give her the live link to check. Remind her a hard refresh or a minute's wait may be needed.

If something breaks after a push, undo it safely with `git revert HEAD` then `git push` (never use `git reset --hard` or force-push).

## Domain (infoverohomecare.com): not connected yet

- The domain is registered at **Namecheap** and uses Namecheap's default DNS (`dns1/dns2.registrar-servers.com`).
- It currently has **no website records**, so typing infoverohomecare.com does not load the site. It **does** have Google Workspace email records (MX `smtp.google.com` and a `google-site-verification` TXT). **Never delete those**, or her email stops working.
- The pages' canonical and social tags already use `https://infoverohomecare.com/`.
- Plan: move this repo to Markeisha's own GitHub account first, then connect the domain.

**Steps to connect (when ready):**
1. In Namecheap → Domain List → Manage → Advanced DNS, add:
   - A record, Host `@`, Value `185.199.108.153`
   - A record, Host `@`, Value `185.199.109.153`
   - A record, Host `@`, Value `185.199.110.153`
   - A record, Host `@`, Value `185.199.111.153`
   - CNAME record, Host `www`, Value `<her-github-username>.github.io.`
   - Remove any Namecheap "parking" or URL redirect records for `@` and `www`. Leave MX and TXT records alone.
2. In the repo, create a file named `CNAME` (no extension) containing exactly `infoverohomecare.com`, commit and push. (Or set Custom domain in GitHub → repo Settings → Pages.)
3. Wait for DNS (minutes to a few hours). Check with `dig +short infoverohomecare.com`.
4. In GitHub → Settings → Pages, turn on **Enforce HTTPS** once the certificate is ready.
5. Update the "Live site" row at the top of this file.

## Moving the repo to Markeisha's GitHub

Currently at `github.com/tammyamosley2018-hash/vero-home-care` (Tammy's account). After transfer (GitHub → Settings → Transfer ownership, or a fresh push to a new repo in her account):
- Run `git remote set-url origin https://github.com/<her-username>/vero-home-care.git`.
- Turn on GitHub Pages in the new repo: Settings → Pages → Deploy from branch → `main` / root.
- The github.io address will change to `https://<her-username>.github.io/vero-home-care/`. Update the "Live site" row above.

## History notes

- Launched as a client preview 2026-08-25. Positioning corrected to non-medical care 2026-08-31.
- Hero video, editorial photos, standards section (privacy, caregiver standards, payment), and mobile menu fixes added through 2026-09-06.
- Care request Google Form embedded in the Contact section 2026-10-15.
- Built with help from Tammy Mosley, who set up this project and Claude Code for Markeisha.
