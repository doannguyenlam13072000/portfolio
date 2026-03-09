# SEO audit – portfolio components

Quick audit of keywords, content, and structure across `src/components` and layout.

---

## What was already in good shape

- **Layout.astro**: Strong base – unique `<title>`, meta description, keywords, author, Open Graph, Twitter Card, `robots`, `lang="en"`, and JSON-LD (Person + WebSite). Google Search Console verification present.
- **Keywords**: Meta keywords and hero copy use relevant terms (fullstack, Vue, React, Node.js, TypeScript, PostgreSQL, software engineer, portfolio).
- **Structured data**: Person and WebSite schemas in place.
- **Images**: Most have meaningful `alt` (words, abilities, skills, social icons). `loading="lazy"` used where appropriate.

---

## Issues found and fixes applied

### 1. Heading hierarchy (fixed)

- **Hero**: Had two `<h1>`s; the second (“I’m a Creative…”) was changed to a `<p>` with the same styling and an `aria-label` so the page has a single `<h1>`: “It’s me, Lam Doan.”
- **Contact**: Section title was `<h1>`; changed to `<h2>` so it’s a section heading under the main page topic.
- **Experiences / Project.astro**: Each project used `<h1>`; changed to `<h3>` so they are subsection titles under the Experiences `<h2>`.
- **TitleHeader**: Section titles (“What I Can Do”, “Professional Work Experience”) were in a `<div>`; changed to `<h2>` so the document outline is correct.
- **Skills**: “Frontend”, “Backend”, “Database”, “DevOps”, “Others” were `<h2>`; changed to `<h3>` so the section has one `<h2>` (from TitleHeader) and subsections as `<h3>`.
- **Features**: Had no section heading; added `TitleHeader` with “About me” / “What I bring” so the block has a proper `<h2>` and clearer SEO intent.

### 2. Semantic structure (fixed)

- **Main content**: Page content was in a generic `<div>`. Replaced with `<main id="main-content">` so screen readers and SEO see a clear main landmark.

### 3. Schema and branding (fixed)

- **Person `sameAs`**: Was empty; now populated from `socialLinks` (LinkedIn, GitHub, Facebook, Instagram) so search can associate your profiles.
- **Person `knowsAbout`**: Extended with more skills (e.g. Nuxt.js, Laravel, Spring Boot, Docker, AWS) to better match site content.
- **Navbar brand**: Label “Portfolio” changed to “Lam Doan” and link to `#hero` for consistent branding and relevance.

### 4. Image `alt` text (fixed)

- **Hero banner**: `alt="hero-image"` → `alt="Lam Doan, Full-stack Software Engineer - Portfolio illustration"`.
- **Contact illustration**: `alt="Contact"` → `alt="Get in touch with Lam Doan - Contact section"`.

---

## Current document outline (after fixes)

- **h1**: It’s me, Lam Doan (Hero)
- **h2**: About me (Features)
- **h2**: What I Can Do (Skills)
- **h3**: Frontend, Backend, Database, DevOps, Others (Skills subsections)
- **h2**: Professional Work Experience (Experiences)
- **h3**: Project titles (each experience card)
- **h2**: I’d love to hear from you! (Contact)

---

## Keyword usage by section

| Section   | Keywords / content notes |
|----------|---------------------------|
| **Layout** | title, description, meta keywords, OG/Twitter: fullstack, Vue, React, Node.js, TypeScript, PostgreSQL, software engineer, portfolio |
| **Hero** | “Senior Full-stack Engineer”, “4+ years”, “e-commerce, AI-assisted platforms, enterprise systems”, “React, Vue, TypeScript, Node.js”, “API design”, “international teams” |
| **Features** | Section title “About me” / “What I bring”; cards: Quick Learner, Problem Solver, On-Time Delivery, Effective Communication (soft skills, not tech keywords) |
| **Skills** | “What I Can Do”, “My skills”; tech names in labels and alts (JS, Vue, React, Nuxt, Angular, Astro, Node, Express, etc.) |
| **Experiences** | “Professional Work Experience”; project titles and descriptions in `dummy.js` are keyword-rich (e.g. e-commerce, AI, Laravel, React, Vue) |
| **Contact** | “I’d love to hear from you!” – generic; fine for a CTA |
| **Footer** | “Lam Doan”, “Copyright 2026”, social links with names in `alt` |

---

## Optional next steps

- **Features**: If you want this section to rank for “developer”/“engineer”, consider a short intro paragraph with 1–2 target phrases (e.g. “As a software engineer, I focus on…”).
- **Meta description**: Slightly different from OG description; you can align them or keep OG a bit shorter for social.
- **Canonical**: Add `<link rel="canonical" href={canonicalUrl} />` in Layout if you have multiple URLs (e.g. www vs non-www or different domains).

All applied changes are in the components and layout listed above; this file is for reference only.
