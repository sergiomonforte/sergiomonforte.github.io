# Sergio Monforte — academic website

An 8-page static site (4 pages &times; 2 languages: English + Basque), built from your CVN record. No build step — just HTML/CSS.

## Files
- `index.html`, `research.html`, `publications.html`, `cv.html` — English pages
- `eu/index.html`, `eu/research.html`, `eu/publications.html`, `eu/cv.html` — Basque pages (mirror the English ones; publication/talk titles are left in their original language, as is standard — only the surrounding labels are translated)
- `style.css` — shared styling (used by both languages)
- `images/` — put a photo here if you want one

Each page has an EN / EU switch at the bottom of the sidebar.

## About the Basque translation
I did my best on the Basque text, including the job-title glosses on the CV page (irakasle agregatua, irakasle elkartua, irakasle laguntzaile doktorea, irakasle interinoa, doktoretza aurreko ikertzailea) — but this isn't proofread by a native speaker, and you're the actual syntactician here, so please read it over before publishing. Flag anything off and I'll fix it.

## About the colour
EHU's official corporate identity manual specifies Pantone Process Black + white as the only corporate colours. In practice, the university's 2025 rebrand introduced a vibrant green called **"Uniberdea"** as its lead colour — I couldn't find a published hex/Pantone code for it, so the site currently uses `#1a7a40` (a vibrant green in that spirit) as a stand-in. If you have the exact brand value, it's the `--accent` / `--link` variables at the top of `style.css` — one edit updates the whole site.

## To preview locally
Double-click `index.html`, or run a tiny local server from this folder:
```
python3 -m http.server 8000
```
then open http://localhost:8000

## To personalize
- **Photo:** drop a square-ish image into `images/` named `photo.jpg`. In each English page replace `<div class="avatar">SM</div>` with `<div class="avatar"><img src="images/photo.jpg" alt="Sergio Monforte"></div>`; in each `eu/` page use `<img src="../images/photo.jpg" alt="Sergio Monforte">` instead (note the `../`).
- **Links:** add Google Scholar / Academia.edu / institutional page links in the `.contact` block in the sidebar of each page.
- **CV as PDF:** if you'd rather link a downloadable PDF CV instead of (or alongside) the `cv.html` page, drop it in this folder and add a link — there's a commented example in `cv.html`.
- Personal identifiers from the CVN (ID number, date of birth, phone, nationality) were left off, since those aren't normally shown on a public academic page — add them back if you want.

## About the DOIs
I looked up DOIs via Crossref and the publishers' own pages and added one wherever I could verify it genuinely matches (title/authors/year). A handful of items are left without one because no DOI could be found — mostly small Basque-language venues and UEU/workshop proceedings that don't seem to assign DOIs (Uztaro item aside, which does have one). One exception worth your attention: I could not find "The Handbook of Non-Canonical Questions" (Oxford University Press, with your Larzabal chapter) indexed anywhere yet — that's most likely just because the volume hasn't been published/indexed yet, but it's worth double-checking that entry when you have a moment.

## Keeping "Recent highlights" current
On the About page, that section is just a plain `<ul>` list — there's a comment right above it in `index.html` (and `eu/index.html`) as a reminder. To update it, delete the oldest `<li>` and add a new one for your latest publication or news; nothing else on the site needs to change. I'm also happy to do this for you whenever you'd like — just tell me what to add.

## To publish (free options)
**GitHub Pages** (recommended, matches sites like billhaddican.github.io):
1. Create a new GitHub repo (e.g. `sergio-monforte.github.io` for a root domain, or any name for a project page).
2. Upload all files in this folder to the repo (keep the `eu/` subfolder structure as-is).
3. In the repo, go to Settings → Pages → set source to the `main` branch, root folder.
4. Your site will be live at `https://<username>.github.io/<repo>/` (or `https://<username>.github.io/` if you used the special repo name).

**Any other web host:** these are plain static files — upload them as-is via FTP/hosting panel, or use Netlify/Vercel by dragging the folder into their dashboard.

## Notes
Publication and CV data were compiled from your CVN (FECYT) export, August 2026. Let me know if you'd like a shorter "selected publications" list, DOI links throughout, a different font, or additional sections (e.g. Teaching page, News).
