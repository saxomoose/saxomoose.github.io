# Legal Tinkerer Blog - Maintenance Guide

This is the Jekyll-based blog for [legal tinkerer](https://saxomoose.github.io), powered by GitHub Pages.

## Project Structure

```
.
├── _config.yml          # Site configuration
├── Gemfile              # Ruby dependencies
├── index.md             # Homepage
├── about.md             # About page
├── _posts/              # Published blog posts (YYYY-MM-DD-title.md)
├── wip/                 # Work-in-progress posts and drafts
├── _sass/               # Custom CSS/Sass
└── _site/               # Built site (generated, not committed)
```

---

## 1. Technical Workflow (Site Building & Deployment)

### Prerequisites
- Ruby 3.3+
- Bundler: `gem install bundler`
- Jekyll: `bundle install`

### Local Development
```bash
# Install dependencies (first time or after Gemfile changes)
bundle install

# Build the site
bundle exec jekyll build

# Serve locally with live reload
bundle exec jekyll serve
# Site available at: http://localhost:4000
```

### Deployment Workflow
```bash
# 1. Make your changes (posts, config, etc.)
# 2. Test locally with `bundle exec jekyll serve`

# 3. Commit changes to dev branch
git add -A
git commit -m "Your commit message"
git push origin dev

# 4. Create Pull Request (via GitHub UI or CLI)
#    - Base: master
#    - Compare: dev
#    - Title: Descriptive title
#    - Description: What changed

# 5. Review and merge PR to master
#    - GitHub Pages auto-deploys from master branch
#    - Live site updates within ~1 minute
```

### Common Commands
```bash
# Update all dependencies
bundle update --all

# Check for outdated gems
bundle outdated

# Clean build (remove _site and rebuild)
bundle exec jekyll clean && bundle exec jekyll build
```

---

## 2. Post Writing & Editing

### Creating a New Post
```bash
# Create file in _posts with format: YYYY-MM-DD-title.md
# Example:
touch _posts/$(date +%Y-%m-%d)-my-new-post.md
```

### Post Template
```markdown
---
layout: post
title: "Your Post Title"
date: YYYY-MM-DD HH:MM:SS +0200
categories: [category1, category2]
---

Your content here.

<!--end-excerpt-->

More content after excerpt break.
```

### Proofreading Checklist
- [ ] Title is clear and compelling
- [ ] Date is correct
- [ ] Categories/tags are appropriate
- [ ] Spelling and grammar
- [ ] Code blocks are properly formatted
- [ ] Links work
- [ ] Images have alt text
- [ ] Excerpt break (`<!--end-excerpt-->`) is present if needed

### Formal Modifications
- Ensure consistent markdown style
- Use ATX-style headings: `# H1`, `## H2`, `### H3`
- Wrap code in triple backticks with language: ```` ```ruby ````
- Use `**bold**` and `_italic_` sparingly

---

## 3. Content Assistance

### Research Support
- Web search for technical references
- Fact-checking claims and statistics
- Finding relevant links and resources
- Suggesting related topics or follow-up ideas

### Content Organization
- Suggesting post structure and flow
- Identifying gaps or unclear sections
- Recommending visual aids (diagrams, screenshots)
- Helping create series or multi-part posts

### Style Guidelines
- Technical accuracy is paramount
- Explain concepts clearly for varied audiences
- Use examples liberally
- Prefer practical, actionable content
- Keep politics out (as per site promise)

---

## Troubleshooting

### Build Errors
```bash
# Remove vendor/bundle and reinstall
rm -rf vendor/bundle Gemfile.lock
bundle install

# Or try with clean slate
rm -rf vendor/bundle Gemfile.lock _site
bundle install
bundle exec jekyll build
```

### Common Issues
- **Sass deprecation warnings**: From minima theme, safe to ignore for now
- **Liquid errors**: Usually syntax issues in markdown front matter
- **Missing gems**: Run `bundle install`

---

## Resources
- [Jekyll Docs](https://jekyllrb.com/docs/)
- [GitHub Pages Docs](https://pages.github.com/)
- [Minima Theme](https://github.com/jekyll/minima)
- [Markdown Guide](https://www.markdownguide.org/)

---

## Contact
For questions about this setup, ask me (the assistant) or check the [GitHub repository](https://github.com/saxomoose/saxomoose.github.io).
