# Section Library

Complete HTML/CSS/JS patterns for every landing page section. Read this file during Phase 3 (generation).

Each section includes: structure, responsive considerations, and animation hooks.

---

## Table of Contents

1. [Navigation Bar](#navigation-bar)
2. [Hero Section](#hero-section)
3. [Features Grid](#features-grid)
4. [How It Works](#how-it-works)
5. [Stats & Metrics](#stats--metrics)
6. [Testimonials](#testimonials)
7. [Pricing](#pricing)
8. [FAQ Accordion](#faq-accordion)
9. [CTA Final](#cta-final)
10. [Footer](#footer)
11. [Shared JavaScript Patterns](#shared-javascript-patterns)
12. [Background Effects Library](#background-effects-library)

---

## Navigation Bar

Sticky top navigation. Becomes opaque on scroll.

```html
<nav class="nav" id="nav">
  <div class="nav-inner">
    <a href="#" class="nav-brand">{ProductName}</a>
    <div class="nav-links">
      <a href="#features">Features</a>
      <a href="#pricing">Pricing</a>
      <a href="#faq">FAQ</a>
    </div>
    <a href="#cta" class="nav-cta">{CTA Text}</a>
  </div>
</nav>
```

```css
.nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 100;
  padding: clamp(0.75rem, 2vw, 1.25rem) 0;
  transition: background var(--transition-fast), box-shadow var(--transition-fast);
}
.nav.scrolled {
  background: var(--bg-primary);
  box-shadow: 0 1px 0 var(--border-color);
  backdrop-filter: blur(12px);
}
.nav-inner {
  max-width: var(--content-width);
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 clamp(1rem, 4vw, 2rem);
}
.nav-brand {
  font-family: var(--font-display);
  font-weight: 700;
  font-size: clamp(1.1rem, 2vw, 1.4rem);
  color: var(--text-primary);
  text-decoration: none;
}
.nav-links {
  display: flex;
  gap: clamp(1.5rem, 3vw, 2.5rem);
}
.nav-links a {
  color: var(--text-secondary);
  text-decoration: none;
  font-size: var(--body-size);
  transition: color var(--transition-fast);
}
.nav-links a:hover { color: var(--text-primary); }
.nav-cta {
  background: var(--accent);
  color: var(--bg-primary);
  padding: 0.5rem 1.25rem;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  font-size: clamp(0.8rem, 1.2vw, 0.95rem);
  transition: all var(--transition-fast);
}
.nav-cta:hover { opacity: 0.9; transform: translateY(-1px); }

/* Mobile: hide links, show hamburger if needed */
@media (max-width: 768px) {
  .nav-links { display: none; }
}
```

```javascript
// Nav scroll effect
window.addEventListener('scroll', () => {
  document.getElementById('nav').classList.toggle('scrolled', window.scrollY > 50);
});
```

---

## Hero Section

Above the fold. One clear message, one clear CTA.

**Density limit**: 1 headline (max 8 words), 1 subheadline (max 20 words), 1-2 buttons, optional badge/tag above headline.

```html
<section class="hero" id="hero">
  <div class="hero-bg"><!-- Background effects go here --></div>
  <div class="hero-content">
    <div class="hero-badge reveal">{Badge text, e.g. "Now in Beta" or "Open Source"}</div>
    <h1 class="hero-title reveal">{Headline}</h1>
    <p class="hero-subtitle reveal">{Subheadline}</p>
    <div class="hero-actions reveal">
      <a href="#" class="btn btn-primary">{Primary CTA}</a>
      <a href="#" class="btn btn-secondary">{Secondary CTA}</a>
    </div>
  </div>
</section>
```

```css
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  position: relative;
  overflow: hidden;
  padding: clamp(6rem, 12vw, 10rem) clamp(1rem, 4vw, 2rem);
}
.hero-bg {
  position: absolute;
  inset: 0;
  pointer-events: none;
  z-index: 0;
}
.hero-content {
  position: relative;
  z-index: 1;
  max-width: 800px;
}
.hero-badge {
  display: inline-block;
  padding: 0.35rem 1rem;
  border: 1px solid var(--border-color);
  border-radius: 999px;
  font-size: clamp(0.75rem, 1.2vw, 0.875rem);
  color: var(--text-secondary);
  margin-bottom: 1.5rem;
}
.hero-title {
  font-family: var(--font-display);
  font-size: var(--heading-size);
  font-weight: 700;
  color: var(--text-primary);
  line-height: 1.1;
  margin-bottom: clamp(1rem, 2vw, 1.5rem);
}
.hero-subtitle {
  font-size: clamp(1rem, 2vw, 1.35rem);
  color: var(--text-secondary);
  line-height: 1.6;
  margin-bottom: clamp(1.5rem, 3vw, 2.5rem);
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}
.hero-actions {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}
.btn {
  padding: clamp(0.7rem, 1.5vw, 0.9rem) clamp(1.5rem, 3vw, 2rem);
  border-radius: 10px;
  font-weight: 600;
  font-size: clamp(0.85rem, 1.3vw, 1.05rem);
  text-decoration: none;
  transition: all var(--transition-fast);
  cursor: pointer;
  border: none;
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
}
.btn-primary {
  background: var(--cta-gradient);
  color: var(--bg-primary);
}
.btn-primary:hover { transform: translateY(-2px); box-shadow: var(--shadow-glow, 0 4px 15px rgba(0,0,0,0.2)); }
.btn-secondary {
  background: transparent;
  color: var(--text-primary);
  border: 1px solid var(--border-color);
}
.btn-secondary:hover { border-color: var(--text-secondary); }
```

---

## Features Grid

3-6 feature cards in a responsive grid.

**Density limit**: Max 6 cards. Each: icon + title (3-4 words) + description (max 15 words).

```html
<section class="features" id="features">
  <div class="section-inner">
    <h2 class="section-title reveal">{Section Title}</h2>
    <p class="section-subtitle reveal">{Brief description}</p>
    <div class="features-grid">
      <!-- Repeat for each feature -->
      <div class="feature-card reveal">
        <div class="feature-icon">{Icon: emoji, Font Awesome, or CSS shape}</div>
        <h3 class="feature-title">{Title}</h3>
        <p class="feature-desc">{Description}</p>
      </div>
    </div>
  </div>
</section>
```

```css
.section-inner {
  max-width: var(--content-width);
  margin: 0 auto;
  padding: var(--section-padding) clamp(1rem, 4vw, 2rem);
  text-align: center;
}
.section-title {
  font-family: var(--font-display);
  font-size: clamp(1.75rem, 4vw, 3rem);
  color: var(--text-primary);
  margin-bottom: 1rem;
}
.section-subtitle {
  font-size: clamp(0.95rem, 1.5vw, 1.15rem);
  color: var(--text-secondary);
  max-width: 600px;
  margin: 0 auto 3rem;
}
.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 280px), 1fr));
  gap: clamp(1rem, 2vw, 1.5rem);
  text-align: left;
}
.feature-card {
  background: var(--bg-card);
  border: 1px solid var(--border-color);
  border-radius: 12px;
  padding: clamp(1.5rem, 3vw, 2rem);
  transition: all var(--transition-fast);
}
.feature-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-hover, 0 8px 25px rgba(0,0,0,0.1));
}
.feature-icon {
  font-size: 1.75rem;
  margin-bottom: 1rem;
}
.feature-card h3 {
  font-family: var(--font-display);
  font-size: clamp(1rem, 1.5vw, 1.2rem);
  margin-bottom: 0.5rem;
  color: var(--text-primary);
}
.feature-desc {
  color: var(--text-secondary);
  font-size: clamp(0.8rem, 1.2vw, 0.95rem);
  line-height: 1.6;
}
```

---

## How It Works

Numbered steps (3-4 steps max).

```html
<section class="steps" id="how-it-works">
  <div class="section-inner">
    <h2 class="section-title reveal">How It Works</h2>
    <div class="steps-container">
      <div class="step reveal">
        <div class="step-number">1</div>
        <div class="step-content">
          <h3>{Step Title}</h3>
          <p>{Step Description}</p>
        </div>
      </div>
      <!-- Repeat for each step -->
    </div>
  </div>
</section>
```

---

## Stats & Metrics

Animated number counters. Max 4 items.

```html
<section class="stats" id="stats">
  <div class="section-inner">
    <div class="stats-grid">
      <div class="stat-item reveal">
        <span class="stat-number" data-target="10000">0</span>
        <span class="stat-suffix">+</span>
        <span class="stat-label">{Label}</span>
      </div>
    </div>
  </div>
</section>
```

```javascript
// Counter animation — trigger on scroll
function animateCounters() {
  document.querySelectorAll('.stat-number').forEach(counter => {
    const target = parseInt(counter.dataset.target);
    const duration = 2000;
    const start = performance.now();
    
    function update(now) {
      const elapsed = now - start;
      const progress = Math.min(elapsed / duration, 1);
      const eased = 1 - Math.pow(1 - progress, 3); // ease-out cubic
      counter.textContent = Math.floor(eased * target).toLocaleString();
      if (progress < 1) requestAnimationFrame(update);
    }
    requestAnimationFrame(update);
  });
}

// Trigger counters when stats section enters viewport
const statsObserver = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      animateCounters();
      statsObserver.disconnect();
    }
  });
}, { threshold: 0.3 });
const statsEl = document.querySelector('.stats');
if (statsEl) statsObserver.observe(statsEl);
```

---

## Testimonials

Max 3 testimonial cards.

```html
<section class="testimonials" id="testimonials">
  <div class="section-inner">
    <h2 class="section-title reveal">What People Say</h2>
    <div class="testimonial-grid">
      <div class="testimonial-card reveal">
        <p class="testimonial-text">"{Quote}"</p>
        <div class="testimonial-author">
          <div class="testimonial-avatar">{Initials or emoji}</div>
          <div>
            <div class="testimonial-name">{Name}</div>
            <div class="testimonial-role">{Role, Company}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
```

---

## Pricing

Max 3 tiers. One should be "highlighted" / recommended.

```html
<section class="pricing" id="pricing">
  <div class="section-inner">
    <h2 class="section-title reveal">Pricing</h2>
    <div class="pricing-grid">
      <div class="pricing-card reveal">
        <div class="pricing-name">{Tier Name}</div>
        <div class="pricing-price"><span class="pricing-currency">$</span>{Price}<span class="pricing-period">/mo</span></div>
        <ul class="pricing-features">
          <li>{Feature 1}</li>
        </ul>
        <a href="#" class="btn btn-secondary">{CTA}</a>
      </div>
      <div class="pricing-card pricing-featured reveal">
        <div class="pricing-badge">Most Popular</div>
        <!-- same structure, with btn-primary -->
      </div>
    </div>
  </div>
</section>
```

---

## FAQ Accordion

Max 6 items. Click to expand/collapse.

```html
<section class="faq" id="faq">
  <div class="section-inner">
    <h2 class="section-title reveal">FAQ</h2>
    <div class="faq-list">
      <div class="faq-item reveal">
        <button class="faq-question" onclick="this.parentElement.classList.toggle('open')">
          <span>{Question}</span>
          <span class="faq-icon">+</span>
        </button>
        <div class="faq-answer"><p>{Answer}</p></div>
      </div>
    </div>
  </div>
</section>
```

```css
.faq-list { max-width: 700px; margin: 0 auto; text-align: left; }
.faq-item { border-bottom: 1px solid var(--border-color); }
.faq-question {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.25rem 0;
  background: none;
  border: none;
  color: var(--text-primary);
  font-size: clamp(0.95rem, 1.3vw, 1.1rem);
  font-family: var(--font-display);
  cursor: pointer;
  text-align: left;
}
.faq-icon { transition: transform 0.3s ease; font-size: 1.3rem; }
.faq-item.open .faq-icon { transform: rotate(45deg); }
.faq-answer {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.4s ease, padding 0.4s ease;
}
.faq-item.open .faq-answer {
  max-height: 300px;
  padding-bottom: 1.25rem;
}
.faq-answer p { color: var(--text-secondary); line-height: 1.7; }
```

---

## CTA Final

Last push. Simple and direct.

```html
<section class="cta-final" id="cta">
  <div class="section-inner">
    <h2 class="cta-title reveal">{Strong closing statement}</h2>
    <p class="cta-subtitle reveal">{One line of supporting text}</p>
    <div class="hero-actions reveal">
      <a href="#" class="btn btn-primary">{CTA}</a>
    </div>
  </div>
</section>
```

---

## Footer

Minimal footer.

```html
<footer class="footer">
  <div class="section-inner footer-inner">
    <span class="footer-brand">{ProductName}</span>
    <div class="footer-links">
      <a href="#">GitHub</a>
      <a href="#">Twitter</a>
      <a href="#">Docs</a>
    </div>
    <span class="footer-copy">© {Year} {ProductName}</span>
  </div>
</footer>
```

---

## Shared JavaScript Patterns

Always include these at the bottom of every landing page:

```javascript
// 1. Scroll Reveal (IntersectionObserver)
const revealObserver = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
    }
  });
}, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });

document.querySelectorAll('.reveal').forEach(el => revealObserver.observe(el));

// 2. Stagger children (add data-stagger to parent)
document.querySelectorAll('[data-stagger]').forEach(parent => {
  [...parent.children].forEach((child, i) => {
    child.style.transitionDelay = `${i * 0.1}s`;
  });
});

// 3. Smooth scroll for anchor links
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
  anchor.addEventListener('click', function(e) {
    e.preventDefault();
    const target = document.querySelector(this.getAttribute('href'));
    if (target) target.scrollIntoView({ behavior: 'smooth', block: 'start' });
  });
});

// 4. Nav scroll effect
window.addEventListener('scroll', () => {
  document.getElementById('nav')?.classList.toggle('scrolled', window.scrollY > 50);
});
```

---

## Background Effects Library

Reusable background effects. Add to `.hero-bg` or any section's background layer.

### Particle Field (for Mission Control / Neon presets)
```javascript
function createParticles(container, count = 30) {
  for (let i = 0; i < count; i++) {
    const p = document.createElement('div');
    const size = Math.random() * 4 + 1;
    Object.assign(p.style, {
      position: 'absolute',
      width: size + 'px',
      height: size + 'px',
      background: 'var(--accent)',
      borderRadius: '50%',
      top: Math.random() * 100 + '%',
      left: Math.random() * 100 + '%',
      opacity: Math.random() * 0.3 + 0.1,
      animation: `float ${Math.random() * 8 + 6}s ease-in-out infinite alternate`,
      animationDelay: `${Math.random() * 4}s`,
      pointerEvents: 'none'
    });
    container.appendChild(p);
  }
}
// CSS keyframes needed:
// @keyframes float { 0% { transform: translateY(0) translateX(0); } 100% { transform: translateY(-20px) translateX(10px); } }
```

### Grid Overlay (for Mission Control preset)
```css
.bg-grid::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(var(--border-color) 1px, transparent 1px),
    linear-gradient(90deg, var(--border-color) 1px, transparent 1px);
  background-size: 50px 50px;
  opacity: 0.3;
}
```

### Gradient Mesh (for Neon Playground preset)
```css
.bg-mesh {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(ellipse at 20% 50%, rgba(0, 255, 136, 0.08) 0%, transparent 50%),
    radial-gradient(ellipse at 80% 20%, rgba(255, 0, 170, 0.06) 0%, transparent 50%),
    radial-gradient(ellipse at 50% 80%, rgba(59, 130, 246, 0.05) 0%, transparent 50%);
}
```

### Noise Texture (for Warm Craft / Neon presets)
```css
.bg-noise::after {
  content: '';
  position: absolute;
  inset: 0;
  opacity: 0.03;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
  pointer-events: none;
}
```

### Spotlight (for Glass Tower preset)
```css
.bg-spotlight {
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse at 50% 30%, rgba(255,255,255,0.03) 0%, transparent 70%);
}
```
