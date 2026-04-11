---
layout: post
title: "Getting Started with Jekyll and GitHub Pages"
date: 2026-04-11 10:00:00
categories: [jekyll, github-pages, tutorial]
excerpt: "Learn how to set up a Jekyll-based portfolio site on GitHub Pages with multiple pages and a blog."
---

## Introduction

Welcome to my first blog post! This post demonstrates how the blog system works and gives you a template for creating your own posts.

## Why Jekyll?

Jekyll is a static site generator that integrates seamlessly with GitHub Pages. Here are the key benefits:

- **No server required** — Everything is static HTML, CSS, and JavaScript
- **Version controlled** — Your entire site lives in Git
- **Markdown support** — Write posts in Markdown for simplicity
- **Automatic builds** — GitHub Pages automatically builds Jekyll on every push
- **Free hosting** — GitHub Pages is free for public repositories

## Writing Blog Posts

To create a new blog post:

1. Create a new file in `_posts/` with the format `YYYY-MM-DD-title.md`
2. Add front matter at the top (the metadata between `---` markers)
3. Write your content in Markdown
4. Push to GitHub — it builds automatically!

### Front Matter Example

```yaml
---
layout: post
title: "Your Post Title"
date: 2026-04-11 10:00:00
categories: [category1, category2]
excerpt: "Optional brief excerpt for the post archive"
---
```

## Markdown Formatting

### Lists

**Unordered list:**
- Item 1
- Item 2
- Item 3

**Ordered list:**
1. First
2. Second
3. Third

### Code Blocks

Here's a Python example:

```python
def hello_world():
    print("Hello, GitHub Pages!")

hello_world()
```

### Blockquotes

> This is a blockquote. Use it for highlighting important quotes or ideas.
>
> — Someone Important

## Tips for Blogging

1. **Be consistent** — Regular posts help build an audience
2. **Share knowledge** — Tutorials and lessons learned are valuable
3. **Include links** — Link to relevant resources, your projects, and other posts
4. **Use formatting** — Headers, lists, and code blocks make posts readable
5. **Proofread** — Take time to review before publishing

## Next Steps

- Customize the site colors and fonts by editing `assets/css/style.css`
- Add your own projects to `_data/projects.yml`
- Write your first post and push it live!
- Share your portfolio on social media

---

**Thanks for reading!** If you found this helpful, feel free to check out my other posts and projects on the [Projects](/projects/) page.
