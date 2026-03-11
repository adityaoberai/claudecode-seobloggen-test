---
name: writing-blogs
description: Writes, structures, and formats SEO-optimized blog posts for the Appwrite blog following established conventions for voice, tone, frontmatter, and post structure. Use when the user asks to write, draft, create, or outline a blog post, or when working with files in the blogs/ directory.
---

# Blog Writing

## Blog structure

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

The filename (slug) must match the `cover` image path: e.g. `avoid-backend-overengineering.md` maps to `/images/blog/avoid-backend-overengineering/cover/cover.png`.

## Voice and tone

- **Direct and opinionated.** State positions clearly. Avoid hedging language like "it depends" without then explaining what it depends on.
- **Developer-first.** Write for engineers making real decisions. No fluff, no marketing speak.
- **Practical over theoretical.** Lead with the concrete problem, then the reasoning, then the solution.
- **No unnecessary superlatives.** Don't call things "amazing" or "powerful" — show why they matter.

## Post structure pattern

1. **Hook** — Open with the real problem or a common misconception. No preamble.
2. **Establish the cost** — Why this problem matters in practice.
3. **Break it down** — Use H1/H2 sections to cover each dimension clearly.
4. **Concrete guidance** — What to actually do. Be specific.
5. **Close with a combined CTA and resources section** — Merge "Moving forward" and "Resources" into one section. The heading must be specific to the post's topic (e.g. "Getting started with Appwrite Auth", not "Moving forward"). End with 2-4 relevant doc links fetched from `https://appwrite.io/llms.txt`. Only link to pages directly relevant to the post. Do not include generic links to the homepage, Discord, or GitHub unless nothing more specific exists.

## Formatting conventions

- Use `**bold**` for key terms and important callouts within paragraphs.
- Use bullet lists for enumerating capabilities, trade-offs, or steps — not for general prose.
- Avoid nested lists unless strictly necessary.
- Use H1 (`#`) for major sections, H2 (`##`) for subsections.
- Link to official docs for referenced features: e.g. `[Appwrite Sites](https://appwrite.io/docs/products/sites)`.
- Keep paragraphs short: 2-4 sentences as a rule.
- **No em dashes.** Do not use `—` anywhere. Rewrite the sentence to avoid it using a period, comma, or restructured clause.
- **Section headings must be specific and declarative.** Avoid vague closers like "Moving forward", "What this means", or "Where to go from here". Bad: "Moving forward". Good: "Getting started with Appwrite Storage".

## SEO guidelines

- **Title:** Include the primary keyword naturally. Keep it under 60 characters. Front-load the keyword when possible (e.g. "JWT Authentication with Appwrite" not "Using Appwrite to Do JWT Authentication").
- **Description frontmatter:** Write 1 sentence, 140-160 characters, that includes the primary keyword and clearly states what the reader will learn or get.
- **Slug:** Short, keyword-rich, hyphen-separated. Match the exact topic (e.g. `appwrite-jwt-auth`, not `how-to-do-authentication-in-your-app-using-appwrite`).
- **Headings:** Use the primary keyword in at least one H1 or H2. Headings should reflect real search queries developers type, not internal jargon.
- **Search intent:** Match the post type to intent. A "how to" post should answer a specific task. A comparison post should help the reader make a decision. Do not write a conceptual post when developers are searching for a tutorial.
- **Internal links:** Link to at least one other relevant Appwrite blog post or doc page from within the body, not just the closing section.

## What is Appwrite

Appwrite is an open-source developer infrastructure platform for building web, mobile, and AI apps. It includes both a backend server, providing authentication, databases, file storage, serverless functions, real-time subscriptions, and messaging, and a fully integrated hosting solution for deploying static and server-side rendered frontends. Appwrite can be fully self-hosted on any Docker-compatible infrastructure or used as a managed service through [Appwrite Cloud](https://cloud.appwrite.io).

## Content guidelines

- **Appwrite context:** Posts often compare Appwrite to alternatives (Firebase, Vercel, Netlify, etc.) or explain how Appwrite solves a specific developer problem. Keep comparisons fair and factual.
- **Avoid lock-in anxiety:** When recommending Appwrite, acknowledge trade-offs rather than dismissing alternatives.
- **Use real examples:** Reference actual developer workflows (Git-based deployments, serverless functions, auth flows) rather than hypothetical use cases.
- **timeToRead:** Estimate roughly 200-250 words per minute. A 1,200-word post = ~5-6 min read.

## Appwrite documentation reference

**Always fetch `https://appwrite.io/llms.txt` before writing a new post.** Use it to find the specific doc pages relevant to that post's topic, then link only to those. Every resource link in a post must be directly relevant to what the post covers. A post about authentication should link to auth docs; a post about storage should link to storage docs. Do not add links to Discord, GitHub, or the homepage unless nothing more specific exists.

**Prioritize Appwrite Cloud over self-hosting.** When linking to Appwrite, prefer `https://cloud.appwrite.io` over self-hosting documentation. Include a Cloud signup link in the resources section of every post unless the post is specifically about self-hosting or a compliance use case where self-hosting is the core recommendation (e.g. HIPAA, data residency). In CTAs and inline mentions, refer to Appwrite Cloud first and self-hosting as a secondary option.

## Adding a new blog

Copy this checklist and check off items as you complete them:

```
Blog Creation Progress:
- [ ] Step 1: Fetch https://appwrite.io/llms.txt to find relevant doc links
- [ ] Step 2: Add the title to BLOG_TITLES.md
- [ ] Step 3: Create blogs/<slug>.md with correct frontmatter
- [ ] Step 4: Write the post following the structure and tone guidelines
- [ ] Step 5: Verify accuracy of all Appwrite-specific claims against the fetched docs
- [ ] Step 6: Verify slug consistency across filename, cover image path, and internal links
```

**Step 1: Fetch the docs index**

Fetch `https://appwrite.io/llms.txt` to identify the specific doc pages for this post's topic.

**Step 2: Add to BLOG_TITLES.md**

Add the title (one title per line; currently uses `N->Title` format).

**Step 3: Create the file**

Create `blogs/<slug>.md` with the frontmatter template from "Blog structure" above.

**Step 4: Write the post**

Follow the post structure pattern and voice/tone guidelines. Refer to the style reference posts below to calibrate tone and section depth.

**Step 5: Verify accuracy against Appwrite docs**

Fetch each doc page linked in the post and cross-check every Appwrite-specific claim: feature names, API method names, configuration options, and behavioral descriptions. Correct any discrepancies before finalizing. Do not rely on training data for product details — always verify against the live docs.

**Step 6: Verify slug consistency**

Confirm the filename, cover image path, and any internal links all use the same slug.

## Style references

These posts represent the target style:

- [Password Protection](https://appwrite.io/blog/post/password-protection.md) — Security-focused with practical developer guidance, clear section structure, and no marketing fluff.
- [Push Notifications Best Practices](https://appwrite.io/blog/post/push-notifications-best-practices.md) — Feature-focused, explaining Appwrite capabilities in context with concrete implementation details.

## Common pitfalls

- Starting with "In this post, we will..." — just start with the argument.
- Over-explaining what the reader already knows — assume developer competence.
- Ending with "Let us know your thoughts!" — this blog doesn't use that style.
- Using passive voice where active voice is clearer.
- Writing section headers as questions — use declarative headers instead.
- Using em dashes (`—`) anywhere in the post. Use commas, parentheses, periods, colons, or semicolons instead as appropriate.
- Generic closing headers like "Moving forward", "Conclusion", or "Next steps". The final section heading must be specific to the post's topic.
- Repeating the same CTA phrasing across posts. The closing paragraph should reflect the post's specific argument, not a boilerplate Appwrite pitch.
- Linking to Discord, GitHub, or the Appwrite homepage as filler resources. Only include links the reader would actually click given the post's topic.
