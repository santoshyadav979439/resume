# Resume — single-file HTML → PDF

A clean, single-page-friendly résumé built as **one self-contained HTML file**
(`resume.html`). No build step, no dependencies, no internet required — the fonts are
system fonts and the icons are inline SVG. Open it in a browser, edit the text, and print
to PDF.

> This is a shareable template. Replace the content with your own and export your own PDF.

---

## Quick start

1. **Download** `resume.html` (or clone this repo).
2. **Open** it in Chrome (recommended) or any modern browser — just double-click the file.
3. **Edit** the text directly in the file (see below).
4. **Export to PDF:** `Cmd/Ctrl + P` → Destination **Save as PDF** → Save.

---

## How to edit

Open `resume.html` in any text editor (VS Code, Sublime, even TextEdit). All the content
lives in plain HTML near the bottom of the file; the styling is in the `<style>` block at
the top. You only need to touch the content unless you want to restyle.

### 1. Name, title & contact — the `<header>`
```html
<h1 class="name">Your Name</h1>
<p class="role">Senior Software Engineer — Frontend &amp; Full Stack</p>
```
Contact links live in `<div class="contact">`. Each is a `<a class="crow">` row:
- Email: `href="mailto:you@example.com"`
- Phone: `href="tel:+10000000000"` (no spaces in `tel:` — that's what makes it tappable on mobile)
- LinkedIn / Medium: update the `href="..."` to your profile URLs

To **remove** a contact item, delete its whole `<a>` (or `<span>`) block.

### 2. Summary
Edit the paragraph inside `<p class="summary">`. Wrap any phrase you want emphasized in
`<strong>...</strong>`.

### 3. Skills
Each row is a `<dt>` label + `<dd>` list inside `<dl class="skills">`:
```html
<dt>Languages</dt><dd>JavaScript · TypeScript · Golang</dd>
```
Use ` · ` (middot) between items.

### 4. Experience
Each role is a `<div class="job">` block:
```html
<div class="job">
  <div class="job-head">
    <p class="job-title">Company <span class="pos">— Your Title</span></p>
    <span class="dates">Mon YYYY — Mon YYYY</span>
  </div>
  <ul class="bullets">
    <li>What you did, with a number.</li>
  </ul>
</div>
```
Copy/paste a `.job` block to add a role. The connecting timeline rail and dot are automatic.

### 5. Highlight your metrics (the signature look)
Wrap any real number in `<span class="m">...</span>` to render it in the monospaced indigo
accent — this is what makes results like `$5M / year` or `5 engineers` pop:
```html
saved <span class="m">~1.5 months</span> of engineering effort
```

### 6. Placeholders to fill
Anything wrapped in `<span class="fill">[ ... ]</span>` shows up **orange** — these are
TODO metrics you should replace with real numbers before sharing. Search the file for `[`
to find them all, then swap in your figures and change `fill` to `m`.

---

## Export a clean PDF

From **Chrome** → `Cmd/Ctrl + P`:
- **Destination:** Save as PDF
- **Margins:** Default
- **Background graphics:** **ON** (so the indigo rail, dots, and accents print)
- Use Chrome's built-in *Save as PDF* — not the macOS print-dialog "PDF" button, which can
  flatten your clickable links.

The resulting PDF keeps the email, phone, and profile links **clickable**, including on
mobile.

---

## Customizing the look

All design tokens are CSS variables at the top of the `<style>` block:
```css
--indigo: #5A52E0;   /* the single accent color */
--ink:    #16171A;   /* main text */
--slate:  #5B6066;   /* secondary text */
```
Change `--indigo` to recolor every accent at once. Body font size lives in `body { font-size: ... }`.

---

## License

MIT — use it, edit it, share it.
