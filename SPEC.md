# Jekyll Blog Specification

## Project Overview
A simple personal blog built with Jekyll and hosted on GitHub Pages. Features a minimal splash page landing and separate blog post listing.

## File Structure

```
username.github.io/
├── _config.yml
├── _layouts/
│   ├── default.html
│   ├── post.html
│   └── page.html
├── _includes/
│   ├── header.html
│   ├── footer.html
│   └── navigation.html
├── _posts/
│   └── (markdown files named YYYY-MM-DD-title.md)
├── assets/
│   ├── css/
│   │   └── style.css
│   └── images/
│       └── logo.png
├── index.html
├── blog.html
├── about.md
└── README.md
```

## Technical Decisions

### CSS Approach
- **Use plain CSS** in `assets/css/style.css`
- No Tailwind or CSS frameworks
- Keep styles simple and maintainable
- Jekyll supports SCSS if needed later

### Static Site Generator
- **Jekyll** (GitHub Pages native)
- No custom build process required
- Automatic markdown-to-HTML conversion
- Built-in templating with Liquid

### Blog Posts
- Location: `_posts/` directory
- Naming convention: `YYYY-MM-DD-post-title.md`
- Format: Markdown with YAML front matter
- Layout: Uses `post.html` layout

## File Specifications

### _config.yml
```yaml
title: Your Site Title
description: Your site description
baseurl: ""
url: "https://username.github.io"

markdown: kramdown
highlighter: rouge

permalink: /blog/:title

collections:
  posts:
    output: true
    permalink: /blog/:title
```

### _layouts/default.html
Base layout with:
- HTML5 doctype
- Head section with title, meta tags, CSS link
- Navigation include
- Content block: `{{ content }}`
- Footer include

### _layouts/post.html
Extends default layout with:
- Front matter: `layout: default`
- Article header with title and date
- Post content: `{{ content }}`
- Optional: previous/next post navigation

### _layouts/page.html
Extends default layout with:
- Front matter: `layout: default`
- Page title
- Page content: `{{ content }}`

### _includes/navigation.html
- Simple nav element
- Links to: Home (`/`), Blog (`/blog.html`), About (`/about.html`)
- Clean, semantic HTML

### _includes/header.html
- Site title or logo (if on non-splash pages)
- Navigation include

### _includes/footer.html
- Copyright notice
- Optional social links
- Minimal design

### index.html (Splash Page)
- Front matter: `layout: default` (or no layout for full control)
- Large centered logo image
- Navigation bar
- Minimal styling - centered vertical/horizontal
- Clean, spacious design

### blog.html (Blog Listing)
- Front matter: `layout: default`, `title: Blog`
- Loop through posts using Liquid:
  ```liquid
  {% for post in site.posts %}
    <article>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <time>{{ post.date | date: "%B %d, %Y" }}</time>
      <p>{{ post.excerpt }}</p>
    </article>
  {% endfor %}
  ```

### about.md
- Front matter with `layout: page` and `title: About`
- Markdown content about the site/author

### Blog Post Template (_posts/)
```markdown
---
title: Post Title
date: YYYY-MM-DD
tags: [tag1, tag2]
excerpt: Brief description for listing page
---

Post content in markdown format...
```

## CSS Guidelines (assets/css/style.css)

### General Principles
- Mobile-first responsive design
- Simple, readable typography
- Minimal color palette
- Generous whitespace

### Key Selectors Needed
```css
/* Reset and base styles */
* { box-sizing: border-box; }
body { font-family, line-height, color, margin }

/* Navigation */
nav { layout, spacing }
nav a { styling, hover states }

/* Splash page */
.splash { centering, layout }
.logo { sizing, spacing }

/* Blog listing */
.post-list { layout, spacing }
.post-list article { styling, margins }

/* Blog posts */
.post-header { styling }
.post-content { typography, spacing }
.post-content h1, h2, h3 { styles }
.post-content p, ul, ol { spacing }
.post-content code { inline code styling }
.post-content pre { code block styling }

/* Responsive */
@media (max-width: 768px) { mobile adjustments }
```

## Content Guidelines

### README.md
- Brief description of the site
- Local development instructions
- Deployment notes

## Jekyll-Specific Notes

### Liquid Template Syntax
- `{{ variable }}` - Output variable
- `{% logic %}` - Logic/loops
- `{{ content }}` - Page content placeholder
- `{% include file.html %}` - Include partial

### Front Matter Requirements
- Must be at top of file
- Enclosed in triple dashes `---`
- YAML format
- Required for Jekyll processing

### Local Development
```bash
bundle exec jekyll serve
# Site available at http://localhost:4000
```

### GitHub Pages Deployment
- Push to `main` branch
- GitHub automatically builds and deploys
- Enable GitHub Pages in repo settings

## Design Philosophy
- **Simplicity first**: Clean, minimal design
- **Content focus**: Let writing be the star
- **Performance**: Fast loading, minimal assets
- **Accessibility**: Semantic HTML, good contrast
- **Maintainability**: Easy to update and extend

## Future Enhancements (Optional)
- Tags/categories for posts
- Search functionality
- RSS feed (Jekyll generates this easily)
- Comments system (Disqus, utterances)
- Analytics (Google Analytics, Plausible)
- Dark mode toggle
