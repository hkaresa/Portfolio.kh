# Karesa — portfolio site

A static, three-page portfolio for asset management & global macro roles. No build step, no dependencies — just HTML/CSS/JS. Deploys anywhere that serves static files.

## Pages

| File           | What it is                                                                 |
|----------------|----------------------------------------------------------------------------|
| `index.html`   | Home — about, fundamental work (Judgment), systematic work (Systems), the live IQ demo, Views teaser, contact. |
| `iq-demo.html` | The IQ decision-pipeline demo. **Sample data only** — no keys, no live positions. Embedded into the home page's Live section via `<iframe>`, and also reachable on its own. |
| `views.html`   | Dated macro views — a record of how the market view took shape, 2024→2026. |

The three pages are linked relatively (`index.html` ⇄ `views.html`, and `index.html` embeds `iq-demo.html`), so they travel together as one site.

## Run it locally

Any static server works. From this folder:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

(Opening `index.html` directly with `file://` mostly works, but the IQ `<iframe>` and fonts behave better over a local server.)

## Deploy (pick one)

**Netlify Drop — fastest.** Drag this whole folder onto https://app.netlify.com/drop. Live URL in seconds.

**Vercel via GitHub — what to keep.** Push this folder to a GitHub repo, import it at https://vercel.com (framework preset: *Other / static*). Every commit auto-redeploys. Add a custom domain under Project → Settings → Domains.

**GitHub Pages.** Push to a repo, then Settings → Pages → deploy from `main` / root.

All three serve `index.html` at the root automatically.

## Before you ship — fill in the `TODO`s

Search the files for `TODO` and `[ Surname ]`. The list:

- **Name** — `index.html` hero and footer (`[ Surname ]`), plus `views.html`/`iq-demo.html` if you want your full name there.
- **Contact** — email, LinkedIn, GitHub in `index.html` (the `#contact` section).
- **CV** — drop `Karesa-CV.pdf` into this folder; the contact link already points at `/Karesa-CV.pdf`.
- **Work links** — the five fundamental items (GE Vernova, Joby, Vistra, Rightmove, Novozymes/Chr. Hansen) and the signal-platform demo link currently point at `#`. Swap in real decks / PDFs / write-ups, and sharpen the one-line blurbs to match each.
- **Macro views** — `views.html` is drafted from your own theses; read it as *your* calls and tighten any wording you'd want to defend in a room.

## A note on the IQ demo

It mirrors the real architecture (four regimes, the gating matrix, the fragility overlay, the 0.78 confidence floor, the Claude trap filter) but every price, verdict, size and P&L figure is illustrative. It deliberately shows *reasoning*, not returns, and exposes no credentials or live positions. Present IQ as an engineering-and-analysis artifact rather than a live trading book — cleaner for compliance questions in interviews.
