# Blended Website Design - Blue Theme + Steve Dylan Minimalism

## Overview
Blend the current blue-themed design with Steve Dylan's clean, minimalist, mobile-responsive approach.

## 1. Color Scheme & Typography

### Colors (Keeping Blue Theme)
```css
:root {
  --bg-primary: #0000fe;
  --text-primary: #ffffff;
  --text-secondary: rgba(255, 255, 255, 0.9);
  --border: rgba(255, 255, 255, 0.2);
  --link: #ffffff;
  --link-hover: rgba(255, 255, 255, 0.7);
  --box-bg: #ffffff;
  --box-text: #0000fe;
}
```

### Typography
```css
body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
               'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  line-height: 1.6;
  color: var(--text-primary);
  background: var(--bg-primary);
}

h1 { font-size: 2rem; font-weight: 700; }
h2 { font-size: 1.5rem; font-weight: 600; }
h3 { font-size: 1.25rem; font-weight: 600; }

/* Mobile Typography */
@media (max-width: 768px) {
  body { font-size: 14px; }
  h1 { font-size: 1.75rem; }
  h2 { font-size: 1.25rem; }
}
```

## 2. HTML Structure

### Complete Page Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Smilodon Software</title>
  <style>
    /* CSS goes here */
  </style>
</head>
<body>
  <!-- Skip to content for accessibility -->
  <a href="#main" class="sr-only">Skip to content</a>

  <!-- Header with Navigation -->
  <header>
    <div class="container">
      <nav class="nav-wrapper">
        <a href="/" class="logo">
          <img src="assets/saberteeth.png" alt="Smilodon" class="logo-icon">
          <span>Smilodon Software</span>
        </a>

        <!-- Desktop Navigation -->
        <div class="nav-links desktop-only">
          <a href="/">Home</a>
          <a href="#about">About</a>
          <a href="#blog">Blog</a>
          <a href="#connect">Connect</a>
        </div>

        <!-- Mobile Menu Button -->
        <button class="mobile-menu-btn mobile-only" aria-label="Menu">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor">
            <path d="M3 12h18M3 6h18M3 18h18" stroke-width="2" stroke-linecap="round"/>
          </svg>
        </button>
      </nav>

      <!-- Mobile Navigation Drawer -->
      <div class="mobile-nav" id="mobile-nav">
        <a href="/">Home</a>
        <a href="#about">About</a>
        <a href="#blog">Blog</a>
        <a href="#connect">Connect</a>
      </div>
    </div>
  </header>

  <!-- Main Content -->
  <main id="main" class="container">
    <!-- Hero Section -->
    <section class="hero">
      <h1 class="hero-title">Smilodon Software</h1>
      <p class="subtitle">Software & AI Engineering</p>

      <!-- Logo Image -->
      <div class="hero-logo">
        <img src="assets/saberteeth.png" alt="Smilodon Logo" class="logo-main">
      </div>
    </section>

    <!-- Connect Section (moved up like you requested) -->
    <section id="connect" class="section">
      <h2 class="section-title">Connect</h2>
      <div class="contact-info">
        <a href="mailto:admin@smilodonsoftware.co">admin@smilodonsoftware.co</a>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section">
      <h2 class="section-title">About</h2>
      <div class="content">
        <p>Building AI orchestration tools for small companies.
           Helping clients get the most out of their tokens.
           Writing some thoughts on technology and AI.</p>
        <p>Preference for open-source and in-house tooling.</p>
        <p>Writing code in the following languages:</p>
        <ul class="tech-list">
          <li>Rust</li>
          <li>Go</li>
          <li>Python</li>
          <li>TypeScript</li>
        </ul>
        <p>Everyone needs inference - let us show you how to do it.</p>
      </div>
    </section>

    <!-- Blog Section -->
    <section id="blog" class="section">
      <h2 class="section-title">Blog</h2>
      <ul class="post-list">
        <li class="post-item">
          <time datetime="2025-01-22">22 Jan 2025</time>
          <a href="#" class="post-link">Blog posts coming soon...</a>
        </li>
      </ul>
    </section>
  </main>

  <!-- Footer -->
  <footer>
    <div class="container">
      <div class="footer-content">
        <div class="copyright">© 2025 Smilodon Software</div>
        <nav class="footer-nav">
          <a href="/">Home</a>
          <a href="#blog">Blog</a>
          <a href="#about">About</a>
        </nav>
      </div>
    </div>
  </footer>

  <script>
    // Mobile menu toggle
    document.addEventListener('DOMContentLoaded', function() {
      const menuBtn = document.querySelector('.mobile-menu-btn');
      const mobileNav = document.querySelector('.mobile-nav');

      if (menuBtn) {
        menuBtn.addEventListener('click', function() {
          mobileNav.classList.toggle('active');
        });
      }
    });
  </script>
</body>
</html>
```

## 3. Responsive CSS Styles

### Base Styles
```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
               'Helvetica Neue', Arial, sans-serif;
  background: #0000fe;
  color: #ffffff;
  line-height: 1.6;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.container {
  max-width: 960px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Accessibility */
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0,0,0,0);
  white-space: nowrap;
  border-width: 0;
}
```

### Navigation Styles
```css
header {
  background: #0000fe;
  border-bottom: 1px solid rgba(255, 255, 255, 0.2);
  position: sticky;
  top: 0;
  z-index: 100;
  padding: 1rem 0;
}

.nav-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  text-decoration: none;
  color: #ffffff;
  font-weight: 600;
  font-size: 1.25rem;
}

.logo-icon {
  width: 30px;
  height: 30px;
}

/* Desktop Navigation */
.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-links a {
  color: #ffffff;
  text-decoration: none;
  padding: 0.5rem 0;
  border-bottom: 2px solid transparent;
  transition: all 0.2s;
}

.nav-links a:hover {
  opacity: 0.7;
  border-bottom-color: #ffffff;
}

/* Mobile Navigation */
.mobile-menu-btn {
  display: none;
  background: none;
  border: 1px solid rgba(255, 255, 255, 0.3);
  border-radius: 4px;
  padding: 0.5rem;
  cursor: pointer;
  color: #ffffff;
  transition: all 0.2s;
}

.mobile-menu-btn:hover {
  background: rgba(255, 255, 255, 0.1);
}

.mobile-nav {
  display: none;
  position: absolute;
  top: 100%;
  left: 0;
  right: 0;
  background: #0000fe;
  border-bottom: 1px solid rgba(255, 255, 255, 0.2);
  padding: 1rem 0;
}

.mobile-nav.active {
  display: block;
}

.mobile-nav a {
  display: block;
  padding: 0.75rem 1rem;
  color: #ffffff;
  text-decoration: none;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.mobile-nav a:hover {
  background: rgba(255, 255, 255, 0.1);
}

/* Responsive Utilities */
@media (max-width: 768px) {
  .desktop-only { display: none !important; }
  .mobile-menu-btn { display: block !important; }
}

@media (min-width: 769px) {
  .mobile-only { display: none !important; }
  .mobile-nav { display: none !important; }
}
```

### Hero Section
```css
.hero {
  padding: 4rem 0;
  text-align: left;
}

.hero-title {
  font-size: 2rem;
  font-weight: bold;
  text-transform: uppercase;
  letter-spacing: 4px;
  background: white;
  color: #0000fe;
  padding: 15px 30px;
  display: inline-block;
  border: 2px solid white;
  margin-bottom: 2rem;
}

.subtitle {
  font-size: 1.25rem;
  opacity: 0.9;
  margin-bottom: 2rem;
}

.hero-logo {
  margin: 3rem 0;
}

.logo-main {
  width: 300px;
  height: 300px;
  max-width: 100%;
  height: auto;
}

@media (min-width: 768px) {
  .hero {
    text-align: center;
  }

  .logo-main {
    width: 400px;
    height: 400px;
  }
}
```

### Content Sections
```css
.section {
  margin: 2rem 0;
  padding: 2rem 0;
  border-top: 1px solid rgba(255, 255, 255, 0.2);
}

.section-title {
  font-size: 1.5rem;
  text-transform: uppercase;
  letter-spacing: 2px;
  margin-bottom: 1.5rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid rgba(255, 255, 255, 0.3);
  display: inline-block;
}

.content {
  opacity: 0.9;
}

.content p {
  margin-bottom: 1rem;
  line-height: 1.8;
}

/* Tech List */
.tech-list {
  list-style: none;
  padding: 0;
  margin: 1rem 0;
}

.tech-list li {
  padding: 0.25rem 0;
  padding-left: 1.5rem;
  position: relative;
}

.tech-list li::before {
  content: "¸";
  position: absolute;
  left: 0;
}

/* Contact Info */
.contact-info a {
  color: #ffffff;
  text-decoration: underline;
  font-size: 1.1rem;
}

.contact-info a:hover {
  opacity: 0.7;
}

/* Blog Posts */
.post-list {
  list-style: none;
  padding: 0;
}

.post-item {
  display: flex;
  gap: 2rem;
  margin-bottom: 1rem;
  padding: 0.5rem 0;
  flex-direction: column;
}

.post-item time {
  opacity: 0.7;
  min-width: 120px;
  font-size: 0.9rem;
}

.post-link {
  color: #ffffff;
  text-decoration: underline;
}

.post-link:hover {
  opacity: 0.7;
}

@media (min-width: 640px) {
  .post-item {
    flex-direction: row;
    align-items: baseline;
  }
}
```

### Footer
```css
footer {
  margin-top: auto;
  padding: 3rem 0 2rem;
  border-top: 1px solid rgba(255, 255, 255, 0.2);
}

.footer-content {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  align-items: center;
  text-align: center;
  opacity: 0.8;
}

.footer-nav {
  display: flex;
  gap: 2rem;
}

.footer-nav a {
  color: #ffffff;
  text-decoration: none;
  padding: 0.25rem;
}

.footer-nav a:hover {
  text-decoration: underline;
}

@media (min-width: 640px) {
  .footer-content {
    flex-direction: row;
    justify-content: space-between;
    text-align: left;
  }
}
```

## 4. Mobile-Specific Optimizations

### Touch Targets & Responsive Images
```css
/* Minimum touch target size */
a, button {
  min-height: 44px;
  display: inline-flex;
  align-items: center;
}

/* Responsive Images */
img {
  max-width: 100%;
  height: auto;
}

/* Mobile-specific adjustments */
@media (max-width: 768px) {
  .section {
    margin: 1.5rem 0;
    padding: 1.5rem 0;
  }

  .hero {
    padding: 2rem 0;
  }

  .hero-title {
    font-size: 1.5rem;
    letter-spacing: 2px;
    padding: 10px 20px;
  }

  .logo-main {
    width: 200px;
    height: 200px;
  }
}
```

## 5. Key Design Decisions

### What We Keep from Current Design:
- Blue background (#0000fe)
- White text throughout
- White boxed title style
- Your existing logo/branding

### What We Adopt from Steve Dylan:
- Clean, semantic HTML structure
- Mobile-responsive navigation
- Left-aligned content (center on desktop for hero)
- Minimalist approach (no animations)
- Date/time stamps for blog posts
- Simple underlined links
- Responsive breakpoints

## 6. Implementation Checklist

- [ ] Replace current HTML with semantic structure
- [ ] Add viewport meta tag
- [ ] Implement responsive navigation
- [ ] Update CSS to mobile-first approach
- [ ] Test on multiple screen sizes
- [ ] Ensure touch targets are 44px minimum
- [ ] Add mobile menu JavaScript
- [ ] Test with real devices
- [ ] Optimize images for different sizes
- [ ] Verify accessibility features

## 7. JavaScript for Mobile Menu

```javascript
document.addEventListener('DOMContentLoaded', function() {
  const menuBtn = document.querySelector('.mobile-menu-btn');
  const mobileNav = document.querySelector('.mobile-nav');

  if (menuBtn) {
    menuBtn.addEventListener('click', function() {
      mobileNav.classList.toggle('active');
      menuBtn.setAttribute('aria-expanded',
        mobileNav.classList.contains('active'));
    });
  }

  // Close menu when clicking links
  const mobileLinks = document.querySelectorAll('.mobile-nav a');
  mobileLinks.forEach(link => {
    link.addEventListener('click', () => {
      mobileNav.classList.remove('active');
    });
  });

  // Close menu when clicking outside
  document.addEventListener('click', (e) => {
    if (!menuBtn.contains(e.target) && !mobileNav.contains(e.target)) {
      mobileNav.classList.remove('active');
    }
  });
});
```

## 8. Comparison Table

| Feature | Current Design | New Blended Design |
|---------|---------------|-------------------|
| Background | Blue (#0000fe) | Blue (#0000fe)  |
| Text Color | White | White  |
| Layout | Center-aligned | Left-aligned (mobile), Mixed (desktop) |
| Navigation | None | Clean header with mobile menu |
| Logo Size | 600px fixed | 200-400px responsive |
| Animations | Yes | None (minimal transitions only) |
| Mobile Support | Limited | Full responsive design |
| Typography | Courier | Modern sans-serif |
| Sections | Center blocks | Left-aligned with borders |

This design maintains your distinctive blue aesthetic while implementing modern, mobile-responsive best practices inspired by Steve Dylan's minimalist approach.