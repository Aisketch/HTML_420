# MAIN INSTRUCTION v1.0: Development Protocols & Frameworks
## Detailed Guidelines for Mobile First HTML Single Page Development

**Version:** 1.0  
**Type:** Detailed Protocols + Frameworks  
**Load:** For MEDIUM/HIGH complexity requests  
**Last Updated:** November 2025

---

## 📋 WHEN THIS LOADS

**MEDIUM Requests (Score 4-6):**
- Load relevant sections based on request type
- Apply specific protocols
- Use decision frameworks

**HIGH Requests (Score 7-10):**
- Load FULL instruction
- Apply all frameworks
- Comprehensive analysis
- Multi-phase quality checks

---

# SECTION 1: CODE PATTERNS LIBRARY

## 1.1 HTML5 SEMANTIC PATTERNS

### Pattern A: Landing Page Structure
**When:** New landing page project  
**Pareto Score:** ⭐⭐⭐⭐⭐ (used in 70% of projects)

```html
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Your SEO-optimized description (150-160 chars)">
    
    <!-- Open Graph / Social -->
    <meta property="og:title" content="Your Page Title">
    <meta property="og:description" content="Social share description">
    <meta property="og:image" content="https://yourdomain.com/og-image.jpg">
    
    <!-- Performance -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="dns-prefetch" href="https://analytics.google.com">
    
    <title>Your Page Title | Brand</title>
    
    <!-- Critical CSS inline -->
    <style>
        /* Critical above-fold styles here */
        /* Keep under 14KB */
    </style>
</head>
<body>
    <!-- Header -->
    <header role="banner">
        <nav role="navigation" aria-label="Main navigation">
            <!-- Navigation -->
        </nav>
    </header>

    <!-- Main Content -->
    <main role="main">
        <!-- Hero Section -->
        <section class="hero" aria-labelledby="hero-title">
            <h1 id="hero-title">Your Main Headline</h1>
            <!-- Hero content -->
        </section>

        <!-- Features/Benefits -->
        <section class="features" aria-labelledby="features-title">
            <h2 id="features-title">Key Features</h2>
            <!-- Features content -->
        </section>

        <!-- CTA Section -->
        <section class="cta" aria-labelledby="cta-title">
            <h2 id="cta-title">Ready to Start?</h2>
            <!-- CTA content -->
        </section>
    </main>

    <!-- Footer -->
    <footer role="contentinfo">
        <!-- Footer content -->
    </footer>

    <!-- Deferred JavaScript -->
    <script defer src="main.js"></script>
</body>
</html>
```

**Key Principles:**
- Semantic HTML5 tags (`<header>`, `<main>`, `<section>`, `<footer>`)
- ARIA labels for accessibility
- Meta tags for SEO and social
- Critical CSS inline, defer JavaScript
- Mobile viewport configured

---

### Pattern B: Form Structure (High-Converting)
**When:** Contact forms, lead generation  
**Pareto Score:** ⭐⭐⭐⭐ (used in 50% of projects)

```html
<form class="contact-form" method="post" action="/submit" novalidate>
    <!-- Hidden honeypot for spam prevention -->
    <input type="text" name="website" style="display:none" tabindex="-1" autocomplete="off">
    
    <div class="form-group">
        <label for="name">
            Ваше ім'я <span class="required" aria-label="required">*</span>
        </label>
        <input 
            type="text" 
            id="name" 
            name="name" 
            required 
            aria-required="true"
            autocomplete="name"
            placeholder="Іван Петренко"
        >
        <span class="error" role="alert" aria-live="polite"></span>
    </div>

    <div class="form-group">
        <label for="email">
            Email <span class="required" aria-label="required">*</span>
        </label>
        <input 
            type="email" 
            id="email" 
            name="email" 
            required 
            aria-required="true"
            autocomplete="email"
            placeholder="ivan@example.com"
        >
        <span class="error" role="alert" aria-live="polite"></span>
    </div>

    <div class="form-group">
        <label for="message">Ваше повідомлення</label>
        <textarea 
            id="message" 
            name="message" 
            rows="5"
            placeholder="Розкажіть детальніше..."
        ></textarea>
    </div>

    <button type="submit" class="btn-primary">
        <span class="btn-text">Відправити</span>
        <span class="btn-loader" hidden aria-hidden="true">Відправка...</span>
    </button>
</form>
```

**Key Features:**
- Honeypot spam prevention
- Proper `<label>` association
- Required field indicators
- Autocomplete attributes
- ARIA live regions for errors
- Loading state UI

---

## 1.2 CSS MOBILE-FIRST PATTERNS

### Pattern C: Responsive Container System
**When:** Every project  
**Pareto Score:** ⭐⭐⭐⭐⭐ (100% of projects)

```css
/* Mobile First Container */
.container {
    width: 100%;
    padding-left: 1rem;   /* 16px */
    padding-right: 1rem;
    margin-left: auto;
    margin-right: auto;
}

/* Tablet (641px+) */
@media (min-width: 40.0625em) {
    .container {
        padding-left: 2rem;   /* 32px */
        padding-right: 2rem;
        max-width: 48rem;     /* 768px */
    }
}

/* Desktop (1025px+) */
@media (min-width: 64.0625em) {
    .container {
        max-width: 75rem;     /* 1200px */
    }
}

/* Wide (1441px+) */
@media (min-width: 90.0625em) {
    .container {
        max-width: 87.5rem;   /* 1400px */
    }
}
```

**Breakpoint Strategy:**
- Mobile: `< 640px` (default, no media query)
- Tablet: `641px - 1024px`
- Desktop: `1025px - 1440px`
- Wide: `1441px+`

**Total: 4 breakpoints (Pareto optimal)**

---

### Pattern D: Fluid Typography
**When:** All text content  
**Pareto Score:** ⭐⭐⭐⭐⭐ (100% of projects)

```css
/* Modern fluid typography using clamp() */

body {
    /* 16px mobile → 18px desktop */
    font-size: clamp(1rem, 0.9rem + 0.5vw, 1.125rem);
    line-height: 1.6;
}

h1 {
    /* 32px mobile → 56px desktop */
    font-size: clamp(2rem, 1.5rem + 2.5vw, 3.5rem);
    line-height: 1.2;
    margin-bottom: 1rem;
}

h2 {
    /* 24px mobile → 40px desktop */
    font-size: clamp(1.5rem, 1.2rem + 1.5vw, 2.5rem);
    line-height: 1.3;
    margin-bottom: 0.75rem;
}

h3 {
    /* 20px mobile → 28px desktop */
    font-size: clamp(1.25rem, 1.1rem + 0.8vw, 1.75rem);
    line-height: 1.4;
}

/* Utility: Responsive spacing */
.spacing-y {
    /* 48px mobile → 96px desktop */
    padding-top: clamp(3rem, 2rem + 5vw, 6rem);
    padding-bottom: clamp(3rem, 2rem + 5vw, 6rem);
}
```

**Why `clamp()`:**
- No media queries needed
- Smooth scaling between breakpoints
- Accessible (respects user font preferences)
- Modern browser support (95%+)

---

### Pattern E: Mobile-First Grid Layout
**When:** Multi-column content  
**Pareto Score:** ⭐⭐⭐⭐ (60% of projects)

```css
/* Cards/Features Grid */
.grid {
    display: grid;
    gap: 1.5rem;
    /* Mobile: 1 column (default) */
    grid-template-columns: 1fr;
}

/* Tablet: 2 columns */
@media (min-width: 40.0625em) {
    .grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

/* Desktop: 3 columns */
@media (min-width: 64.0625em) {
    .grid {
        grid-template-columns: repeat(3, 1fr);
        gap: 2rem;
    }
}

/* Alternative: Auto-fit (no media queries) */
.grid-auto {
    display: grid;
    gap: 1.5rem;
    /* Minimum 280px, maximum 1fr */
    grid-template-columns: repeat(auto-fit, minmax(min(280px, 100%), 1fr));
}
```

**When to use:**
- `.grid` - Fixed column counts at breakpoints
- `.grid-auto` - Automatic responsive (simpler!)

---

## 1.3 JAVASCRIPT INTERACTION PATTERNS

### Pattern F: Smooth Scroll Navigation
**When:** Single-page sites with anchor navigation  
**Pareto Score:** ⭐⭐⭐⭐ (50% of projects)

```javascript
// Vanilla JS - No library needed
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        
        if (target) {
            // Smooth scroll with offset for fixed header
            const headerOffset = 80;
            const elementPosition = target.getBoundingClientRect().top;
            const offsetPosition = elementPosition + window.pageYOffset - headerOffset;

            window.scrollTo({
                top: offsetPosition,
                behavior: 'smooth'
            });
            
            // Update URL without jump
            history.pushState(null, null, this.getAttribute('href'));
        }
    });
});
```

**Features:**
- Header offset support
- URL update without reload
- Fallback for no `target`

---

### Pattern G: Form Validation
**When:** Contact forms, lead gen  
**Pareto Score:** ⭐⭐⭐⭐⭐ (70% of projects)

```javascript
// Simple, effective form validation
const form = document.querySelector('.contact-form');

form.addEventListener('submit', async (e) => {
    e.preventDefault();
    
    // Reset errors
    form.querySelectorAll('.error').forEach(el => el.textContent = '');
    
    // Validate
    const formData = new FormData(form);
    const errors = validateForm(formData);
    
    if (errors.length > 0) {
        // Show errors
        errors.forEach(error => {
            const errorEl = form.querySelector(`[name="${error.field}"]`)
                .closest('.form-group')
                .querySelector('.error');
            errorEl.textContent = error.message;
        });
        return;
    }
    
    // Submit
    const submitBtn = form.querySelector('button[type="submit"]');
    submitBtn.disabled = true;
    submitBtn.querySelector('.btn-text').hidden = true;
    submitBtn.querySelector('.btn-loader').hidden = false;
    
    try {
        const response = await fetch(form.action, {
            method: 'POST',
            body: formData
        });
        
        if (response.ok) {
            // Success
            form.reset();
            showSuccessMessage();
        } else {
            throw new Error('Submission failed');
        }
    } catch (error) {
        showErrorMessage('Помилка відправки. Спробуйте пізніше.');
    } finally {
        submitBtn.disabled = false;
        submitBtn.querySelector('.btn-text').hidden = false;
        submitBtn.querySelector('.btn-loader').hidden = true;
    }
});

function validateForm(formData) {
    const errors = [];
    
    // Name validation
    const name = formData.get('name')?.trim();
    if (!name) {
        errors.push({ field: 'name', message: "Ім'я обов'язкове" });
    }
    
    // Email validation
    const email = formData.get('email')?.trim();
    if (!email) {
        errors.push({ field: 'email', message: 'Email обов\'язковий' });
    } else if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {
        errors.push({ field: 'email', message: 'Некоректний email' });
    }
    
    return errors;
}
```

**Features:**
- Client-side validation
- Clear error messages
- Loading state
- Async submission
- Accessible error announcements

---

### Pattern H: Mobile Menu Toggle
**When:** Hamburger menu  
**Pareto Score:** ⭐⭐⭐⭐ (60% of projects)

```javascript
// Simple mobile menu with Alpine.js (simpler than vanilla)
<div x-data="{ open: false }">
    <button 
        @click="open = !open"
        :aria-expanded="open"
        aria-label="Toggle menu"
        class="menu-toggle"
    >
        <span x-show="!open">☰</span>
        <span x-show="open">✕</span>
    </button>
    
    <nav 
        x-show="open"
        x-transition
        @click.away="open = false"
        class="mobile-menu"
    >
        <!-- Menu items -->
    </nav>
</div>

<!-- Include Alpine.js -->
<script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
```

**Why Alpine.js:**
- Simpler than vanilla for state management
- Lightweight (15KB min+gzip)
- Declarative syntax
- Good for simple interactions

**When NOT to use Alpine:**
- Static page with no interactions
- Need SEO for menu content
- Want zero dependencies

---

## 1.4 PERFORMANCE OPTIMIZATION PATTERNS

### Pattern I: Lazy Loading Images
**When:** Multiple images below fold  
**Pareto Score:** ⭐⭐⭐⭐ (50% of projects)

```html
<!-- Modern browsers (native lazy load) -->
<img 
    src="image.jpg" 
    alt="Descriptive alt text"
    loading="lazy"
    width="800"
    height="600"
>

<!-- Responsive with lazy load -->
<img 
    srcset="image-400.jpg 400w,
            image-800.jpg 800w,
            image-1200.jpg 1200w"
    sizes="(max-width: 640px) 100vw,
           (max-width: 1024px) 50vw,
           800px"
    src="image-800.jpg"
    alt="Descriptive alt text"
    loading="lazy"
    width="800"
    height="600"
>

<!-- WebP with fallback -->
<picture>
    <source 
        srcset="image.webp" 
        type="image/webp"
    >
    <source 
        srcset="image.jpg" 
        type="image/jpeg"
    >
    <img 
        src="image.jpg" 
        alt="Descriptive alt text"
        loading="lazy"
        width="800"
        height="600"
    >
</picture>
```

**Key Points:**
- Always include `width` and `height` (prevents CLS)
- Use `loading="lazy"` for below-fold images
- Don't lazy-load LCP image (above fold)
- Provide WebP for modern browsers

---

### Pattern J: Critical CSS Inline
**When:** Every project  
**Pareto Score:** ⭐⭐⭐⭐⭐ (100% of projects)

```html
<head>
    <!-- Inline critical CSS (above-fold styles) -->
    <style>
        /* Reset + Mobile styles for above-fold content */
        /* Keep under 14KB for performance */
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            font-size: 16px;
            line-height: 1.6;
            color: #333;
        }
        
        /* Hero section (above fold) */
        .hero {
            min-height: 100vh;
            padding: 2rem 1rem;
            /* Critical styles only */
        }
        
        /* CTA button (above fold) */
        .btn-primary {
            display: inline-block;
            padding: 1rem 2rem;
            background: #007bff;
            color: white;
            /* Critical styles only */
        }
    </style>
    
    <!-- Load non-critical CSS asynchronously -->
    <link rel="preload" href="styles.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <noscript><link rel="stylesheet" href="styles.css"></noscript>
</head>
```

**Strategy:**
1. Inline critical above-fold CSS (<14KB)
2. Async load full stylesheet
3. Noscript fallback for no-JS users

---

# SECTION 2: OPERATIONAL MODES

## 2.1 QUICK MODE (for SIMPLE requests)

**When:** Score 1-3, quick questions

**Protocol:**
1. Understand question (10 seconds)
2. Check if answer in Core 5 knowledge (direct access)
3. Provide direct answer with code example
4. Keep explanation brief (2-3 sentences)

**Example Input:** "How to center a div?"
**Example Output:**
```css
/* Modern CSS centering */
.container {
    display: grid;
    place-items: center;
    min-height: 100vh;
}

/* Or with Flexbox */
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}
```
Both methods work on all modern browsers. Grid is simpler (1 line vs 2).

---

## 2.2 DEVELOPMENT MODE (for MEDIUM requests)

**When:** Score 4-6, component creation, sections

**Protocol:**

### Phase 1: UNDERSTAND (2 min)
- Clarify requirements
- Identify project type (landing/proposal/form)
- Determine complexity drivers

### Phase 2: SEARCH & PLAN (3 min)
- Load Core 5 files
- Search 2-4 additional relevant files
- Select appropriate patterns
- Check Connection Map for dependencies

### Phase 3: DEVELOP (10-15 min)
- Write HTML structure (semantic)
- Add CSS (mobile-first, clamp())
- Add JS if needed (vanilla or Alpine)
- Include comments for key decisions

### Phase 4: EXPLAIN (3 min)
- Key design decisions
- Usage instructions
- Customization options
- Performance notes

### Phase 5: VERIFY (2 min)
- Simplicity check
- Mobile-first verified
- Pareto alignment
- Developer Test criteria

**Total Time:** 20-25 minutes

---

## 2.3 OPTIMIZATION MODE (for performance issues)

**When:** Performance problems, Lighthouse score improvement

**Protocol:**

### Phase 1: AUDIT (5 min)
- Review current Lighthouse score
- Identify bottlenecks:
  * LCP (Largest Contentful Paint)
  * CLS (Cumulative Layout Shift)
  * INP (Interaction to Next Paint)
  * FCP (First Contentful Paint)

### Phase 2: PRIORITIZE (Pareto 80/20)
**High-Impact Fixes (do first):**
1. LCP optimization (images, fonts, critical CSS)
2. CLS prevention (image dimensions, font loading)
3. Minimize render-blocking resources

**Medium-Impact Fixes (do if time):**
4. JavaScript optimization (defer, async)
5. Asset compression
6. CDN setup

**Low-Impact Fixes (skip unless easy):**
7. Minor code cleanup
8. Microoptimizations

### Phase 3: IMPLEMENT
- Apply fixes from high to medium
- Re-test after each major change
- Stop when 90+ Lighthouse achieved

### Phase 4: VERIFY
- Final Lighthouse test
- Real device test (mobile)
- Core Web Vitals check

---

## 2.4 ANALYSIS MODE (code review, audit)

**When:** Review existing code, provide recommendations

**Protocol:**

### Phase 1: SCAN (5 min)
```
CHECKLIST:
- [ ] HTML semantic and valid?
- [ ] CSS mobile-first?
- [ ] JavaScript necessary?
- [ ] Performance optimized?
- [ ] Accessibility OK?
- [ ] Simple and maintainable?
```

### Phase 2: ISSUES (prioritized)
**🔴 CRITICAL (fix immediately):**
- Accessibility violations
- Performance blockers (LCP >4s, CLS >0.25)
- Invalid HTML
- Security issues

**🟡 IMPORTANT (fix soon):**
- Non-mobile-first CSS
- Unoptimized images
- Render-blocking resources
- Complexity without justification

**🟢 NICE-TO-HAVE (consider):**
- Code cleanup
- Better comments
- Modern CSS features

### Phase 3: RECOMMENDATIONS
- Prioritized list (Pareto 80/20)
- Code examples for fixes
- Expected impact of each fix

### Phase 4: REFACTOR (if requested)
- Provide improved code
- Explain changes
- Show before/after metrics

---

# SECTION 3: DECISION FRAMEWORKS

## 3.1 CSS Strategy Decision Tree

```
QUESTION: Should I use Tailwind CSS or custom CSS?

├─ Project Size < 5 components?
│  └─ YES → Custom CSS (simpler, less setup)
│
├─ Team familiar with Tailwind?
│  └─ NO → Custom CSS (learning curve not worth it)
│
├─ Need rapid prototyping?
│  └─ YES → Tailwind (faster initial development)
│
├─ Design system needed?
│  └─ YES → Tailwind (built-in consistency)
│
└─ DEFAULT → Custom CSS (Pareto: works for 70% of projects)

PARETO INSIGHT:
Custom CSS is simpler for most single-page projects.
Use Tailwind only when benefits clearly outweigh complexity.
```

---

## 3.2 JavaScript Library Decision Tree

```
QUESTION: Vanilla JS, Alpine.js, or something else?

├─ No interactivity needed?
│  └─ Vanilla JS or none (simplest)
│
├─ Simple state (show/hide, toggle)?
│  ├─ 1-2 components → Vanilla JS (20-30 lines)
│  └─ 3+ components → Alpine.js (cleaner)
│
├─ Forms with validation?
│  └─ Vanilla JS (good enough, no dependency)
│
├─ Complex SPA needed?
│  └─ STOP: Wrong project type (use React/Vue, but not single-page HTML)
│
└─ DEFAULT → Vanilla JS (Pareto: handles 80% of cases)

NEVER USE:
- jQuery (outdated, bloated)
- React/Vue for simple pages (overkill)
- Heavy libraries for simple tasks
```

---

## 3.3 Image Format Decision Tree

```
QUESTION: What image format should I use?

├─ Photo / Gradient?
│  ├─ Modern browsers (95%)? → WebP (smaller, good quality)
│  └─ Need IE11 support? → JPEG with WebP fallback
│
├─ Logo / Icon / Illustration?
│  ├─ Simple shapes? → SVG (vector, perfect scaling)
│  └─ Complex illustration? → WebP or AVIF
│
├─ Animation needed?
│  ├─ Simple? → CSS animation on SVG
│  ├─ Complex? → WebM video (better than GIF)
│  └─ Fallback? → GIF
│
└─ DEFAULT:
    - Photos → WebP with JPEG fallback
    - Icons → SVG
    - Complex → AVIF with WebP/JPEG fallback

OPTIMIZATION:
Always provide multiple resolutions (srcset)
Always include width/height attributes (CLS prevention)
```

---

## 3.4 Responsive Breakpoint Strategy

```
QUESTION: How many breakpoints do I need?

PARETO ANSWER: 2-4 breakpoints cover 90% of devices

RECOMMENDED (Pareto Optimal):
1. Mobile: < 640px (default, no media query)
2. Tablet: 641px - 1024px
3. Desktop: 1025px+

OPTIONAL 4th:
4. Wide: 1441px+ (if design needs it)

WHEN TO ADD MORE:
- Specific device targeting
- Complex multi-column layouts
- Client requirement

WHEN NOT TO:
- Most projects (2-3 is enough)
- Simple layouts (might need only mobile + desktop)

MODERN ALTERNATIVE:
Use clamp() and container queries (no breakpoints!)
```

---

# SECTION 4: SPECIALIZED PROTOCOLS

## 4.1 New Landing Page Protocol (HIGH Complexity)

**Full process for creating landing page from scratch**

### Phase 1: REQUIREMENTS (5 min)
```
GATHER:
- [ ] Goal (lead gen, sales, info)
- [ ] Target audience
- [ ] Key message
- [ ] CTA (primary action)
- [ ] Content (headlines, copy, images)
- [ ] Constraints (timeline, complexity)
```

### Phase 2: ARCHITECTURE (10 min)
```
DECIDE:
- [ ] Preset to use (Express? Full-Feature?)
- [ ] Sections needed (hero, features, testimonials, CTA)
- [ ] Form required?
- [ ] Media (images, video)?
- [ ] Integrations (analytics, chat)?

LOAD FILES:
- Core 5 (always)
- Additional from Preset
```

### Phase 3: STRUCTURE (15 min)
```
HTML:
1. Semantic structure (Pattern A)
2. Hero section (above fold)
3. Features/benefits sections
4. Social proof (if applicable)
5. CTA section(s)
6. Footer

CHECKLIST:
- [ ] Semantic tags
- [ ] ARIA labels
- [ ] Meta tags (SEO, social)
- [ ] Proper heading hierarchy (h1 → h2 → h3)
```

### Phase 4: STYLING (20 min)
```
CSS (Mobile First):
1. Critical CSS inline (hero + CTA)
2. Typography (clamp() for fluid sizing)
3. Layout (Grid/Flexbox)
4. Responsive (2-4 breakpoints)
5. Components (buttons, cards, forms)

CHECKLIST:
- [ ] Mobile-first (375px default)
- [ ] Touch targets 44x44px+
- [ ] Fluid typography (clamp)
- [ ] Performance-optimized
```

### Phase 5: INTERACTIONS (10 min)
```
JAVASCRIPT (if needed):
- Smooth scroll (if multi-section)
- Form validation (if form present)
- Mobile menu (if nav complex)
- Analytics events

DEFAULT: Vanilla JS
CONSIDER: Alpine.js if 3+ interactive components
```

### Phase 6: OPTIMIZATION (15 min)
```
PERFORMANCE:
- [ ] Images optimized (WebP, lazy load)
- [ ] Fonts optimized (preload, swap)
- [ ] CSS/JS minified
- [ ] Critical CSS inline
- [ ] Scripts deferred

TARGET:
- Lighthouse 90+
- LCP < 2.5s
- CLS < 0.1
```

### Phase 7: QUALITY CHECK (10 min)
```
VERIFY:
- [ ] Mobile-first design works
- [ ] All links functional
- [ ] Forms validated
- [ ] Images load
- [ ] Performance target met
- [ ] Accessibility OK (ARIA, keyboard nav)
- [ ] Cross-browser tested (Chrome, Firefox, Safari)

DEVELOPER TEST:
- [ ] Simple & readable
- [ ] Mobile first
- [ ] Performance optimized
- [ ] Knowledge base used
- [ ] Immediately usable
```

### Phase 8: DELIVERY (5 min)
```
PROVIDE:
1. Complete HTML file
2. CSS (inline + external)
3. JavaScript (if needed)
4. Usage instructions
5. Customization notes
6. Performance report (expected Lighthouse score)

TOTAL TIME: 90 minutes
```

---

## 4.2 Component Creation Protocol (MEDIUM Complexity)

**For creating reusable components (hero, form, CTA, etc.)**

### Phase 1: IDENTIFY (2 min)
```
WHAT: What component? (hero, form, card, etc.)
WHERE: Which section of page?
WHEN: When does it appear? (above/below fold)
WHY: What job does it solve?
```

### Phase 2: SEARCH (3 min)
```
LOAD:
- Relevant pattern from Code Library (Section 1)
- Related file from knowledge base
- Connection Map for dependencies

EXAMPLE:
Hero section → Load 3.1_Landing_Page_Structures.md
Form → Load 3.3_Form_Design_Conversions.md
```

### Phase 3: BUILD (15 min)
```
STRUCTURE:
1. HTML (semantic, accessible)
2. CSS (mobile-first, scoped)
3. JS (if needed, simple)

KEEP:
- Self-contained (minimal dependencies)
- Reusable (easy to adapt)
- Simple (easy to understand)
```

### Phase 4: VARIANTS (5 min)
```
PROVIDE:
- Option A (primary design)
- Option B (alternative style/layout)
- Optional: Option C (if significantly different approach)

WHY: A/B testing, flexibility
```

### Phase 5: DOCUMENT (5 min)
```
INCLUDE:
- Usage example
- Customization options (colors, sizing, etc.)
- Dependencies (if any)
- Performance notes

TOTAL TIME: 30 minutes
```

---

## 4.3 Performance Audit Protocol (MEDIUM Complexity)

**For reviewing and optimizing existing pages**

### Phase 1: BENCHMARK (5 min)
```
RUN:
- Lighthouse (mobile + desktop)
- Core Web Vitals check
- PageSpeed Insights

RECORD:
- LCP (goal: < 2.5s)
- CLS (goal: < 0.1)
- INP (goal: < 200ms)
- Overall score (goal: 90+)
```

### Phase 2: DIAGNOSE (10 min)
```
IDENTIFY ISSUES (Pareto Priority):

🔴 HIGH IMPACT:
- [ ] LCP slow (> 2.5s)
- [ ] CLS high (> 0.1)
- [ ] Render-blocking resources
- [ ] Unoptimized images

🟡 MEDIUM IMPACT:
- [ ] JavaScript not deferred
- [ ] No lazy loading
- [ ] Uncompressed assets
- [ ] No caching headers

🟢 LOW IMPACT:
- [ ] Minor code cleanup
- [ ] Unused CSS
- [ ] Small optimizations
```

### Phase 3: FIX (Pareto 80/20)
```
FOCUS ON HIGH IMPACT (20% effort, 80% result):

1. LCP OPTIMIZATION:
   - Optimize largest image (WebP, srcset, preload)
   - Inline critical CSS
   - Reduce server response time

2. CLS PREVENTION:
   - Add width/height to images
   - Reserve space for dynamic content
   - Avoid layout shifts

3. RESOURCE OPTIMIZATION:
   - Defer JavaScript
   - Async non-critical CSS
   - Compress images

SKIP LOW IMPACT unless trivial to fix
```

### Phase 4: RE-TEST (5 min)
```
VERIFY:
- Run Lighthouse again
- Check improvement
- If < 90, identify next bottleneck
- Repeat Phase 3 for next issue

STOP when 90+ achieved
```

### Phase 5: REPORT (5 min)
```
PROVIDE:
- Before/After scores
- Changes made
- Expected impact
- Additional recommendations (if < 90)

TOTAL TIME: 30 minutes
```

---

# SECTION 5: QUALITY GATES

## 5.1 Simplicity Gate (MANDATORY)

**Before delivering code, answer:**

```
QUESTION 1: Can I simplify this?
├─ Vanilla JS instead of library?
├─ Custom CSS instead of framework?
├─ 2 breakpoints instead of 4?
├─ Inline instead of external?
└─ Remove unnecessary code?

QUESTION 2: Is every line justified?
├─ Why this dependency?
├─ Why this complexity?
├─ Why this abstraction?
└─ Can I explain this to junior dev in 2 min?

QUESTION 3: What's the Pareto score?
├─ Does this solve 80% of problem with 20% effort?
├─ Or am I over-engineering the 20%?

PASS: All questions answered satisfactorily
FAIL: Simplify before delivering
```

---

## 5.2 Mobile First Gate (MANDATORY)

**Verification checklist:**

```
MOBILE DESIGN (375px):
- [ ] Content readable without zoom
- [ ] Touch targets 44x44px minimum
- [ ] Navigation accessible
- [ ] Forms usable
- [ ] No horizontal scroll

PERFORMANCE (Mobile Network):
- [ ] LCP < 2.5s on 3G
- [ ] Page usable within 3s
- [ ] Images optimized
- [ ] Scripts deferred

PROGRESSIVE ENHANCEMENT:
- [ ] Works without JavaScript
- [ ] Enhanced with JavaScript
- [ ] Tablet layout improves mobile
- [ ] Desktop layout improves tablet

PASS: All verified
FAIL: Fix mobile experience first
```

---

## 5.3 Pareto Alignment Gate (RECOMMENDED)

**Verify 80/20 principle applied:**

```
FRAMEWORK CHOICE:
- [ ] Vanilla/Alpine (not React/Vue)
- [ ] Custom CSS or Tailwind (not Bootstrap)
- [ ] 2-4 breakpoints (not 6-8)

FILE USAGE:
- [ ] Core 5 consulted
- [ ] Only relevant files loaded
- [ ] Not overloaded with info

CODE COMPLEXITY:
- [ ] Simple solutions prioritized
- [ ] Complexity justified
- [ ] Junior-developer friendly

OPTIMIZATION:
- [ ] High-impact fixes applied
- [ ] Low-impact skipped
- [ ] 90+ Lighthouse achievable

PASS: Pareto principle consistently applied
WARN: Review if over-engineered
```

---

# CLOSING

**Main Instruction loaded.**

This instruction provides detailed protocols and frameworks for MEDIUM and HIGH complexity development tasks. Use in combination with Upper-Level Instruction for complete system.

**Remember:**
- Simplicity First (Pareto 80/20)
- Mobile First Always (375px → desktop)
- Knowledge Base Powered (Core 5 + relevant files)
- Performance Optimized (90+ Lighthouse)
- Developer-Friendly Quality (readable, maintainable)

**STATUS:** ✅ Ready for complex development tasks
