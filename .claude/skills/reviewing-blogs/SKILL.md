---
name: reviewing-blogs
description: Reviews and critiques blog posts in the blogs/ directory against Appwrite's established standards for voice, tone, structure, SEO, formatting, and accuracy. Use when the user asks to review, audit, critique, or improve an existing blog post.
---

# Blog Review

## How to run a review

When asked to review a blog post, read the file at `blogs/<slug>/+page.markdoc`, then evaluate it against every section below. Produce a structured report using the format at the end of this document.

**Before starting:** Identify which sections of `src/routes/docs/` are relevant to the post's topic, then read those `+page.markdoc` files directly to use as the ground truth for the accuracy review. The docs map to public URLs as `src/routes/docs/{section}/{subsection}/+page.markdoc` → `https://appwrite.io/docs/{section}/{subsection}`. Key sections: `products/{auth,databases,storage,functions,messaging,sites,ai}/`, `quick-starts/`, `tutorials/`, `advanced/{platform,security,self-hosting}/`, `apis/`, `tooling/`.

## Review checklist

### Frontmatter

- [ ] `layout: post` is present
- [ ] `title` is a quoted string, under 60 characters, front-loads the primary keyword
- [ ] `description` is 140-160 characters, includes the primary keyword, states what the reader will learn
- [ ] `date` is in `YYYY-MM-DD` format
- [ ] `cover` path matches the slug: `/images/blog/<slug>/cover.png`
- [ ] `timeToRead` is plausible given word count (roughly 200-250 wpm)
- [ ] `author` is set
- [ ] `category` is set
- [ ] `featured` and `unlisted` are present

### Slug consistency

- [ ] Filename slug matches `cover` image path slug
- [ ] Any internal links use the same slug

### Voice and tone

- [ ] Direct and opinionated — no hedging without follow-through
- [ ] Developer-first — no marketing speak or fluff
- [ ] Practical over theoretical — concrete problems before reasoning
- [ ] No unnecessary superlatives ("amazing", "powerful") without substance

### Post structure

- [ ] Opens with the real problem or a misconception — no preamble like "In this post, we will..."
- [ ] Establishes the cost or stakes early
- [ ] Uses H1/H2 sections to cover each dimension clearly
- [ ] Includes concrete, specific guidance (not just "consider X")
- [ ] Closes with a single combined CTA and resources section
- [ ] Closing section heading is specific to the post topic (not "Moving forward", "Conclusion", "Next steps", "Where to go from here")
- [ ] Closing paragraph reflects the post's specific argument, not boilerplate Appwrite pitch

### Formatting

- [ ] `**bold**` used for key terms and callouts within paragraphs
- [ ] Bullet lists used for enumerating items, not for general prose
- [ ] No nested lists unless strictly necessary
- [ ] H1 (`#`) for major sections, H2 (`##`) for subsections
- [ ] Paragraphs are 2-4 sentences
- [ ] No em dashes (`—`) anywhere — sentence must be rewritten if one exists
- [ ] Section headings are specific and declarative, not questions or vague phrases

### SEO

- [ ] Primary keyword appears naturally in the title
- [ ] Primary keyword appears in the `description` frontmatter
- [ ] Slug is short, keyword-rich, and hyphen-separated
- [ ] Primary keyword appears in at least one H1 or H2
- [ ] Headings reflect real developer search queries, not internal jargon
- [ ] Post type matches search intent (tutorial for "how to", comparison for decision-making, etc.)
- [ ] At least one internal link to a relevant Appwrite blog post or doc within the body (not just the closing section)

### Appwrite accuracy

**Read the relevant local doc files before evaluating this section.** Use the directory structure in `src/routes/docs/` to identify which files apply, then read each one. Do not rely on training data — verify every Appwrite-specific claim against the local docs.

- [ ] All Appwrite feature names match the live docs exactly (e.g. "Appwrite Auth" not "Appwrite Authentication")
- [ ] All API method names, parameters, and signatures match the live docs
- [ ] Configuration options and their valid values match the live docs
- [ ] Behavioral descriptions (e.g. "Appwrite automatically does X") are confirmed by the docs
- [ ] No outdated or deprecated references (check if the feature still exists and works as described)
- [ ] Comparisons to alternatives (Firebase, Vercel, Netlify, etc.) are fair and factual
- [ ] Trade-offs are acknowledged rather than dismissed

For each inaccuracy found, note: the claim in the post, what the docs actually say, and the doc URL.

### Links and resources

- [ ] All doc links in the closing section are directly relevant to the post's topic
- [ ] No filler links to Discord, GitHub, or the Appwrite homepage unless nothing more specific exists
- [ ] Closing section includes a link to [Appwrite Cloud](https://cloud.appwrite.io) unless the post is specifically about self-hosting
- [ ] All linked URLs resolve (cross-check against the local doc files in `src/routes/docs/`)

### Common pitfalls

Check whether the post commits any of these:

- Starts with "In this post, we will..." or similar throat-clearing
- Over-explains basics the target developer already knows
- Ends with "Let us know your thoughts!" or similar engagement bait
- Uses passive voice where active is clearer
- Uses em dashes
- Uses question-format section headings
- Uses generic closing headers
- Repeats boilerplate CTA phrasing
- Links to Discord/GitHub/homepage as filler

---

## Review report format

Output the review as a structured Markdown report with these sections:

```
## Blog Review: <title>

### Summary
<2-3 sentence overall assessment: what works, what needs the most attention>

### Frontmatter
<Pass / Issues found — list each issue>

### Voice and tone
<Pass / Issues found>

### Structure
<Pass / Issues found>

### Formatting
<Pass / Issues found>

### SEO
<Pass / Issues found>

### Appwrite accuracy
<Pass / Issues found — note any claims that could not be verified>

### Links and resources
<Pass / Issues found>

### Specific rewrites
<For each issue that has a clear fix, show the before and after>

### Priority fixes
1. <Most important fix>
2. <Second most important>
3. <Third most important>
```

Be specific. Quote the problematic text directly. Suggest the exact rewrite where possible. Do not pad the report with praise for things that merely meet the baseline standard.
