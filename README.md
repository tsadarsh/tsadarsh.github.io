# Portfolio Website - Built with Jekyll

This is a Jekyll-based portfolio website hosted on GitHub Pages.

## Project Structure

```
├── _config.yml                # Jekyll configuration
├── _layouts/                  # HTML templates
│   ├── default.html          # Base layout with nav/footer
│   ├── home.html             # Home page layout
│   ├── page.html             # Static page layout
│   └── post.html             # Blog post layout
├── _includes/                # Reusable HTML components
│   ├── nav.html              # Navigation menu
│   └── footer.html           # Footer with social links
├── _posts/                   # Blog posts (Markdown)
│   └── YYYY-MM-DD-title.md
├── _data/                    # Data files (YAML)
│   └── projects.yml          # Projects list
├── pages/                    # Static pages (Markdown)
│   ├── about.md              # Home page (permalink: /)
│   ├── projects.md           # Projects showcase
│   └── blog.md               # Blog archive
├── assets/
│   ├── css/
│   │   └── style.css         # Main stylesheet
│   └── images/
│       └── profile.png       # Profile image
├── Gemfile                   # Ruby dependencies
└── README.md                 # This file
```

## Getting Started

### Local Development

1. **Install Ruby** (if not already installed)
   - Windows: Use [RubyInstaller](https://rubyinstaller.org/)

2. **Install dependencies**
   ```bash
   bundle install
   ```

3. **Run Jekyll locally**
   ```bash
   bundle exec jekyll serve
   ```
   
   Then visit `http://localhost:4000` in your browser

4. **Make changes** and see them live-reload

### Adding Content

#### New Blog Post
1. Create file: `_posts/YYYY-MM-DD-title.md`
2. Add front matter:
   ```yaml
   ---
   layout: post
   title: "Your Title"
   date: YYYY-MM-DD HH:MM:SS
   categories: [category1, category2]
   ---
   ```
3. Write content in Markdown

#### Adding Projects
1. Edit `_data/projects.yml`
2. Add new project entry with title, description, tags, and links
3. The projects page auto-generates from this data

#### Customizing Pages
- Edit `/pages/blog.md` — Blog index page
- Edit `/pages/projects.md` — Projects showcase page
- Edit `/pages/about.md` — Home/about page

## Customization

### Styling
- Edit `assets/css/style.css` to customize colors, fonts, and layout
- The design is responsive and mobile-friendly

### Site Metadata
- Edit `_config.yml` to update:
  - Site title and description
  - Your GitHub, LinkedIn, Instagram usernames
  - Base URL

### Navigation
- Edit `_includes/nav.html` to add/remove menu items
- Edit `_includes/footer.html` to update social links

## Deployment

GitHub Pages automatically builds and deploys when you push to the repository.

1. **First time setup**
   ```bash
   git add .
   git commit -m "Initial portfolio setup"
   git push origin main
   ```

2. **Check deployment status**
   - Go to GitHub repo → Settings → Pages
   - Your site will be live at `https://tsadarsh.github.io/`

3. **Make updates**
   ```bash
   git add .
   git commit -m "Add blog post about X"
   git push origin main
   ```

## Important Notes

### Images
- **Profile picture**: Needs to be placed at `assets/images/profile.png`
- If you have an image called "Adarsh ts.png" in the root, copy it to `assets/images/` and rename to `profile.png`
- External images can be linked directly (no need to add them to the repo)

### Old Files
- The old `index.html` and `index.css` have been replaced by Jekyll's system
- You can delete them, or keep them for reference

### Blog Post URLs
- Posts are automatically available at `/blog/YYYY/MM/DD/post-title/`
- Or use the cleaner permalink in front matter: `/blog/:title/`

## Tips

1. **Use Markdown** — It's simpler than HTML and auto-converts to pages
2. **Test locally** — Always run `bundle exec jekyll serve` before pushing
3. **Meaningful commits** — Use descriptive commit messages for future reference
4. **Check homepage** — After first setup, verify GitHub Pages builds successfully (repo → Actions)

## Resources

- [Jekyll Documentation](https://jekyllrb.com/)
- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
- [Liquid Template Documentation](https://shopify.github.io/liquid/)

---

Built with [Jekyll](https://jekyllrb.com/) and hosted on [GitHub Pages](https://pages.github.com/)
