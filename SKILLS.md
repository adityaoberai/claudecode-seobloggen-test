# Blog Creation Skills

A reference guide for the process, conventions, and patterns used to write blogs in this repository.

---

## Blog Structure

Each blog is a Markdown file in the `blogs/` directory. Every file must start with this frontmatter:

```yaml
---
layout: post
title: "Full title as a string"
description: One sentence summary of what the post covers.
date: YYYY-MM-DD
cover: /images/blog/<slug>/cover.png
timeToRead: <number>
author: aditya-oberai
category: product
featured: false
unlisted: true
---
```

The filename (slug) should match for the blog and the `cover` image path: e.g. `avoid-backend-overengineering.md` → `/images/blog/avoid-backend-overengineering/cover/cover.png`.

---

## Voice and Tone

- **Direct and opinionated.** State positions clearly. Avoid hedging language like "it depends" without then explaining what it depends on.
- **Developer-first.** Write for engineers making real decisions. No fluff, no marketing speak.
- **Practical over theoretical.** Lead with the concrete problem, then the reasoning, then the solution.
- **No unnecessary superlatives.** Don't call things "amazing" or "powerful" — show why they matter.

---

## Post Structure Pattern

Most posts follow this flow:

1. **Hook** — Open with the real problem or a common misconception. No preamble.
2. **Establish the cost** — Why this problem matters in practice.
3. **Break it down** — Use H2/H3 sections to cover each dimension clearly.
4. **Concrete guidance** — What to actually do. Be specific.
5. **Close without fluff** — End on the practical takeaway, not a vague call to action.

---

## Formatting Conventions

- Use `**bold**` for key terms and important callouts within paragraphs.
- Use bullet lists for enumerating capabilities, trade-offs, or steps — not for general prose.
- Avoid nested lists unless strictly necessary.
- Use H2 (`##`) for major sections, H3 (`###`) for subsections.
- Link to official docs for referenced features: e.g. `[Appwrite Sites](https://appwrite.io/docs/products/sites)`.
- Keep paragraphs short — 2–4 sentences as a rule.

---

## Content Guidelines

- **Appwrite context:** Posts often compare Appwrite to alternatives (Firebase, Vercel, Netlify, etc.) or explain how Appwrite solves a specific developer problem. Keep comparisons fair and factual.
- **Avoid lock-in anxiety:** When recommending Appwrite, acknowledge trade-offs rather than dismissing alternatives.
- **Use real examples:** Reference actual developer workflows (Git-based deployments, serverless functions, auth flows) rather than hypothetical use cases.
- **timeToRead:** Estimate roughly 200–250 words per minute. A 1,200-word post = ~5–6 min read.

---

## Adding a New Blog

1. Add the title to `BLOG_TITLES.md` (one title per line, no numbering format required but currently uses `N→Title`).
2. Create `blogs/<slug>.md` with correct frontmatter.
3. Write the post following the structure and tone guidelines above.
4. Ensure the slug is consistent: filename, cover image path, and any internal links should all use the same slug.

---

## Common Pitfalls to Avoid

- Starting with "In this post, we will..." — just start with the argument.
- Over-explaining what the reader already knows — assume developer competence.
- Ending with "Let us know your thoughts!" — this blog doesn't use that style.
- Using passive voice where active voice is clearer.
- Writing section headers as questions — use declarative headers instead.