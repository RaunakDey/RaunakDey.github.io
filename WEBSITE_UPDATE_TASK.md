# WEBSITE_UPDATE_TASK.md — Raunak Dey personal site

**Repo:** `RaunakDey/RaunakDey.github.io` · **Stack:** academic-jekyll (Jekyll-Now + Bootstrap)
**Goal:** Targeted content refresh. **Do NOT redesign or regenerate from scratch.** Preserve layout, structure, and CSS. Make minimal, surgical edits. All authoritative content is provided below — use it; do not invent facts, links, or metrics.

---

## 0. WORKING PROTOCOL (do this first)

1. **Read before editing:**
   - `index.html` (holds intro/bio, research cards, experience, talks, teaching, press)
   - `_config.yml` (name, description, social links)
   - **One existing file in `publications/_posts/`** — learn the exact front-matter schema (fields like title, authors, venue, year, image, pdf/link). Mirror it exactly for new entries.
   - `style.scss` and any inline styles in `index.html` (for the CSS-consistency pass)
2. **Preview locally** before committing: `bundle exec jekyll serve` → open `http://localhost:4000`. (Requires Ruby + bundler; run `bundle install` first if needed.)
3. **Commit granularly** — one commit per task below, clear messages (e.g. `Update intro/bio`, `Add Elanco experience`, `Add ISME Journal + in-review publications`). Work on a branch `site-refresh` and open a PR; do not force-push `main`.
4. **Guardrails:**
   - Truthful only. Do not add metrics, dates, or claims not in this file.
   - **NDA-safe (Elanco):** never name the species or the clinical condition. Use the provided wording.
   - Do not invent DOIs/URLs. For new entries, reuse existing link patterns or set the link to Google Scholar (`https://scholar.google.com/citations?user=2mI3Lx4AAAAJ`); leave a `<!-- TODO: add DOI -->` where a specific link is missing.
   - If a publication post needs a thumbnail and none exists, reuse a neutral existing image and leave a `<!-- TODO: replace thumbnail -->` note rather than blocking.
5. **Ask before deleting** any file or large block. Trimming a list (e.g. talks) is fine; deleting a whole section needs confirmation.

---

## 1. INTRO / BIO  (`index.html` bio section; also check `_config.yml` description)

Replace the current intro with this (adapt HTML tags to match the existing markup; keep the existing portrait, name heading, and social icons):

> I'm a Physics PhD candidate at the University of Maryland working at the intersection of **Bayesian machine learning, scientific AI, and inverse problems**. My work recovers what you can't directly observe — hidden parameters, states, and interactions — from noisy, indirect data: across biological interaction networks, population dynamics, time-series forecasting, and, most recently, behavioral phenotyping from video. I'm currently an **AI R&D intern at Elanco**, building computer-vision systems for pharmaceutical research, and I develop open-source scientific software (B², InvODE, PHAMILY) along the way. I'm moving into **applied / research scientist roles in scientific and health AI**.

**Tagline** (keep the existing one if present, or use): *"Recovering the unobserved from noisy data."* or keep *"Building quantitative models for science."*

---

## 1A. NEWS / RECENT  (new — short block near the top of `index.html`, just after the bio)

Add a compact **"News"** (or "Recent") list near the top of the page, after the intro and before the research cards, using the site's existing list/typography styling. Keep it to the ~4 most recent dated items; this list should be pruned over time so it always shows only recent highlights. Content:

- **2026** — First-author paper published in *The ISME Journal*: "Emergent higher-order interactions enable coexistence in phage–bacteria community dynamics."
- **2026** — Started as **AI R&D Intern at Elanco Animal Health** (computer vision for pharmaceutical research).
- **2026** — First-author manuscript *"Bayesian learning of traits from microbial time series"* (with J. Weitz and D. Talmy) under review.
- **2025** — Talk at **APS Global Summit** on multi-task inference of virus–microbe interaction networks.

If the template has no built-in news mechanism, implement it as a simple styled `<ul>` / `<div>` block in `index.html` consistent with the existing sections — do **not** add a new Jekyll collection or plugin.

---

## 2. EXPERIENCE  (`index.html` experience section)

**ADD this as the most recent entry, above the existing ones**, matching the existing entry markup/format:

- **AI Research & Development Intern — Elanco Animal Health** · Indianapolis, IN · May–Aug 2026
  Building an end-to-end computer-vision system to classify animal behavior from video for pharmaceutical efficacy studies — using foundation models (SAM2, Gemini), Bayesian and state-space/HMM priors, and large-scale data pipelines on Google Cloud (Vertex AI).

**Also verify/refresh existing entries** to match the current resume (do not rewrite heavily, just correct if stale):
- UMD Microbiome Center (UMIACS) — AI & Optimization Researcher · May 2024 – Dec 2025
- Graduate Research Assistant (Simons Foundation), Georgia Tech & UMD · Aug 2021 – Present
- IISER Kolkata — Research (Optimal Control & Stochastic Modeling) · 2017–2021

---

## 3. RESEARCH CARDS  ("contribution cards" in `index.html`)

The current cards read awkwardly. **Rewrite the copy of existing cards and add the two missing themes**, keeping the existing card HTML/CSS structure (same number of columns, same styling). Unify them under the inverse-problem theme. Target 4–6 cards, each a title + 1–2 sentences:

1. **Bayesian inference of microbial interaction networks** — Recovering interaction structure and traits from community time series with hierarchical Bayesian models and MCMC. *(ISME Journal 2026; Bayesian-traits primer in review.)*
2. **Behavioral phenotyping from video** *(new)* — Reading clinically meaningful behavior from raw video at scale, combining foundation models (SAM2, Gemini) with Bayesian location priors and state-space/HMM temporal structure. *(Elanco.)*
3. **Foundation-model & LLM time-series forecasting** *(new or rewrite)* — Tokenization schemes and LoRA fine-tuning for forecasting; probing the predictability limits of chaotic and stochastic systems.
4. **Network inference from population dynamics** — Multitask machine learning to reconstruct virus–microbe interaction networks from observed dynamics.
5. **Stochastic processes & signal extraction** — Inferring parameters and certified-random numbers from noisy Brownian trajectories; optimal-control sensing for broadband measurement *(patented)*.

Keep the existing card thumbnails/icons where they still fit; leave a `<!-- TODO: image -->` for the new cards.

---

## 4. PUBLICATIONS  (`publications/_posts/` — one markdown file per paper)

**First open an existing post to copy its exact front-matter schema.** Then ensure the following are present and correct. **ADD the ones marked NEW.** Group/label by type if the theme supports it; otherwise list by year.

**Journal (published):**
- **ISME Journal (2026)** — "Emergent higher-order interactions enable coexistence in phage–bacteria community dynamics." R. Dey, A. Coenen, M. Sullivan, J. Weitz, et al. *(first author)* — **verify this is present and marked published, not "in review."**
- Physical Review E (2022) — "Experimental verification of arcsine laws in mesoscopic nonequilibrium systems." R. Dey, A. Kundu, B. Das, A. Banerjee. *(first author)*
- Phys. Rev. Research (2022) — "Non-monotonic skewness of currents in non-equilibrium steady states." S. Manikandan, B. Das, A. Kundu, R. Dey, et al.
- Frontiers in Physics (2021) — "Simultaneous random number generation and optical-tweezers calibration employing a learning algorithm." R. Dey, S. Ghosh, A. Kundu, A. Banerjee. *(first author)*
- Phys. Rev. Fluids (2021) — "Single-shot wideband active microrheology using modulated optical tweezers." A. Kundu, R. Dey, S. Paul, A. Banerjee.
- Soft Matter (2021) — "Active microrheology using pulsed optical tweezers to probe viscoelasticity of lamin A." C. Mukherjee, K. Sengupta, A. Kundu, R. Dey, A. Banerjee.

**Conference / proceedings:**
- SPIE Nanoscience + Engineering (2021) — "Random number extraction from an optically trapped Brownian oscillator using an iterative algorithm." R. Dey, A. Kundu, S. Ghosh, A. Banerjee. *(first author, oral + proceedings)*

**In review / in preparation (NEW — add these, clearly labeled):**
- **"Bayesian learning of traits from microbial time series."** R. Dey, J. Weitz, D. Talmy, et al. *(first author, in review)* — **this is missing; add it.** List the authors as shown; it is fine to name this paper publicly. If Raunak supplies the full co-author list, replace "et al." with the complete names — do not invent any names.
- First-author manuscript on virus–microbe network inference *(in preparation)*.
- Two co-authored manuscripts *(in review/preparation)* — optional; add a single line if the layout supports an "in prep" note, otherwise skip.

**Patent:**
- Indian Patent No. 539208 (2024) — "A system for carrying out active microrheology to probe viscoelasticity of protein." K. Sengupta, C. Mukherjee, A. Kundu, R. Dey, et al.

After adding posts with images, run `_make_thumbnails.sh` if thumbnails are required by the template.

---

## 5. TALKS  (`index.html` talks section)

**Trim to key external talks only.** Remove internal/university-level seminars. Keep:
- APS Global Summit 2025 — Multi-task inference of virus–microbe interaction networks from population dynamics
- NetSci-2024 (Canada) — Statistical inference of network models
- SPIE Photonics 2021 (oral) — ML extraction of random numbers from stochastic trajectories
- (Optional) Simons Foundation SCOPE

---

## 6. SOFTWARE  (`index.html` software section)

**Leave as-is** — it's good. Only verify links resolve: B² (`https://b2-bayesian-for-biology.github.io/MCMCwithODEs_primer/`), InvODE (`https://raunakdey.github.io/InvODE/`), PHAMILY. Fix a broken link if found; otherwise no changes.

---

## 7. TEACHING & PRESS / MEDIA

**Leave as-is** — confirmed fine. No edits unless a link is broken.

---

## 8. CSS / STYLE CONSISTENCY PASS  (`style.scss`, inline styles)

Light pass only — do **not** restyle the site:
- Make card spacing, fonts, heading sizes, and link colors consistent across sections (use the values already dominant in the file; don't introduce new ones).
- Remove obviously dead/duplicated rules if certain they're unused.
- Verify mobile layout still works (Bootstrap grid intact) after edits.

---

## DEFINITION OF DONE

- [ ] Intro rewritten; reads as Bayesian ML / scientific AI / inverse problems with Elanco mentioned.
- [ ] News/Recent block added near the top with ~4 recent dated items (ISME J published, Elanco, in-review paper, APS talk).
- [ ] Elanco experience entry added (NDA-safe wording).
- [ ] Research cards rewritten + behavioral-phenotyping and forecasting cards present; unified theme.
- [ ] ISME Journal shows as published; "Bayesian learning of traits" added as in-review; all listed pubs present & correct.
- [ ] Talks trimmed to key external talks.
- [ ] Software / teaching / press unchanged (links verified).
- [ ] CSS consistent; mobile layout intact.
- [ ] `bundle exec jekyll serve` builds clean with no errors; site previewed.
- [ ] Granular commits on a `site-refresh` branch; PR opened. No `main` force-push.
- [ ] All `TODO` placeholders (images, missing DOIs) listed in the PR description for Raunak to fill.

---

## KICKOFF PROMPT (paste this to the agent)

> Read `WEBSITE_UPDATE_TASK.md` in the repo root and execute it. First read `index.html`, `_config.yml`, and one existing file in `publications/_posts/` to learn the publication schema. Then make minimal, targeted edits per the TODO sections, preserving the existing layout and CSS. Use only the content provided in the task file — do not invent facts, metrics, or links. Build with `bundle exec jekyll serve` to verify, commit each section separately on a `site-refresh` branch, and ask me before deleting any file or whole section. List any image/DOI TODOs at the end.
