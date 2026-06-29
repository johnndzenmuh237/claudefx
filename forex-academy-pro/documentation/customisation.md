# Forex Academy Pro — Extended Customisation Guide

## CSS Variable Reference

All design tokens are in `assets/css/style.css` under `:root`. Change any value to instantly update the whole site.

### Colour System
```css
:root {
  /* ── BRAND COLOURS — change these to rebrand ── */
  --color-gold:        #C9A84C;   /* Primary accent */
  --color-gold-light:  #E8C96B;   /* Hover states */
  --color-gold-dark:   #9E7A2E;   /* Active states */

  /* ── BACKGROUNDS ── */
  --color-black:       #0A0B0D;   /* Page background */
  --color-dark:        #111318;   /* Footer, sidebar */
  --color-dark-2:      #181C23;   /* Cards */
  --color-dark-3:      #1F242E;   /* Form inputs */
  --color-dark-4:      #252B37;   /* Hover surfaces */
  --color-surface:     #2C3345;   /* Selected items */

  /* ── TEXT ── */
  --color-text-primary:   #F0EDE6;
  --color-text-secondary: #9CA3B0;
  --color-text-muted:     #5A6070;

  /* ── SEMANTIC ── */
  --color-success:     #22C55E;   /* Green — wins, completed */
  --color-danger:      #EF4444;   /* Red — losses, errors */
  --color-warning:     #F59E0B;   /* Amber — warnings */
  --color-info:        #3B82F6;   /* Blue — info */
}
```

### Spacing
```css
:root {
  --space-1:  0.25rem;  /*  4px */
  --space-2:  0.5rem;   /*  8px */
  --space-3:  0.75rem;  /* 12px */
  --space-4:  1rem;     /* 16px */
  --space-5:  1.25rem;  /* 20px */
  --space-6:  1.5rem;   /* 24px */
  --space-8:  2rem;     /* 32px */
  --space-10: 2.5rem;   /* 40px */
  --space-12: 3rem;     /* 48px */
  --space-16: 4rem;     /* 64px */
  --space-20: 5rem;     /* 80px */
  --space-24: 6rem;     /* 96px */
  --space-32: 8rem;     /* 128px */
}
```

### Border Radius
```css
:root {
  --radius-sm:   4px;
  --radius-md:   8px;
  --radius-lg:   12px;
  --radius-xl:   20px;
  --radius-2xl:  32px;
  --radius-full: 9999px;  /* Pills and circles */
}
```

---

## Adding a New Page

1. Copy any existing page as a starting point
2. Update `<title>` and `<meta name="description">`
3. Change the active nav link class:
```html
<a href="your-page.html" class="nav-link active">Your Page</a>
```
4. Add your content between the navbar and footer
5. Link the page from the navbar dropdown or footer

---

## Component Reference

### Buttons
```html
<!-- Primary (gold fill) -->
<a href="#" class="btn btn-primary">Button</a>

<!-- Outline white -->
<a href="#" class="btn btn-outline">Button</a>

<!-- Outline gold -->
<a href="#" class="btn btn-outline-gold">Button</a>

<!-- Ghost (subtle) -->
<a href="#" class="btn btn-ghost">Button</a>

<!-- Danger -->
<a href="#" class="btn btn-danger">Button</a>

<!-- Sizes -->
<a href="#" class="btn btn-primary btn-sm">Small</a>
<a href="#" class="btn btn-primary btn-lg">Large</a>
<a href="#" class="btn btn-primary btn-xl">Extra Large</a>

<!-- Icon button -->
<button class="btn btn-ghost btn-icon"><i class="fas fa-search"></i></button>
```

### Cards
```html
<!-- Standard card -->
<div class="card">Content</div>

<!-- Gold-tinted card -->
<div class="card-gold">Content</div>

<!-- Glass effect -->
<div class="card-glass">Content</div>
```

### Badges
```html
<span class="badge badge-gold">Gold</span>
<span class="badge badge-success">Success</span>
<span class="badge badge-danger">Danger</span>
<span class="badge badge-info">Info</span>
<span class="badge badge-warning">Warning</span>
<span class="badge badge-surface">Default</span>
```

### Progress Bar
```html
<div class="progress">
  <div class="progress-bar" style="width: 75%"></div>
</div>
```

### Alert
```html
<div class="alert alert-success">
  <i class="fas fa-check-circle"></i>
  <span>Your message here.</span>
</div>

<!-- Types: alert-success | alert-danger | alert-warning | alert-info -->
```

### Form Controls
```html
<div class="form-group">
  <label class="form-label">Field Label</label>
  <input type="text" class="form-control" placeholder="Placeholder">
</div>

<!-- Select -->
<select class="form-control">
  <option>Option 1</option>
</select>

<!-- Textarea -->
<textarea class="form-control" rows="4"></textarea>
```

### Section Structure
```html
<section class="section">
  <div class="container">
    <div class="section-head center">
      <span class="section-label">Label Text</span>
      <h2 class="section-title">Your <span class="gradient-text">Heading</span></h2>
      <p class="section-subtitle">Optional subtitle text below the heading.</p>
    </div>
    <!-- Content here -->
  </div>
</section>
```

### Grid Layouts
```html
<!-- 2 columns -->
<div class="grid-2">...</div>

<!-- 3 columns -->
<div class="grid-3">...</div>

<!-- 4 columns -->
<div class="grid-4">...</div>

<!-- Auto-fit (min 280px each) -->
<div class="grid-auto">...</div>
```

---

## Counter Animation

Add `data-count` to any element to animate numbers when scrolled into view:

```html
<!-- Basic number -->
<div data-count="14000">0</div>

<!-- With prefix and suffix -->
<div data-count="4.2" data-prefix="$" data-suffix="M" data-decimals="1">$0M</div>

<!-- Custom duration (ms) -->
<div data-count="79" data-suffix="%" data-duration="3000">0%</div>
```

---

## Toast Notifications

Show a toast from any JavaScript:

```javascript
// From main.js, available globally after page load
Toast.show('Payment received successfully!', 'success');
Toast.show('Connection error. Please try again.', 'danger');
Toast.show('Your session expires in 5 minutes.', 'warning');
Toast.show('New signal just posted.', 'info');

// Custom duration (ms, default 4000)
Toast.show('Logged in!', 'success', 2000);
```

---

## Scroll Animation (AOS)

Add `data-aos` attributes to any element:

```html
<div data-aos="fade-up">Fades up on scroll</div>
<div data-aos="fade-left" data-aos-delay="200">Delayed left fade</div>
<div data-aos="zoom-in" data-aos-duration="800">Zoom in</div>
```

Available effects: `fade`, `fade-up`, `fade-down`, `fade-left`, `fade-right`, `zoom-in`, `zoom-out`, `flip-left`, `flip-right`, `slide-up`.

AOS is configured in `main.js`:
```javascript
AOS.init({ duration: 600, easing: 'ease-out-quart', once: true, offset: 60 });
```

---

## Tab Switching

```html
<!-- Tabs nav -->
<div class="tabs" data-tabs>
  <button class="tab-btn active" data-tab="tab-one">Tab One</button>
  <button class="tab-btn" data-tab="tab-two">Tab Two</button>
</div>

<!-- Tab panes — IDs match data-tab values -->
<div id="tab-one" class="tab-pane active">Content A</div>
<div id="tab-two" class="tab-pane">Content B</div>
```

---

## Connecting Real Data

### Signal Feed
Replace the `sampleData` array in `signals.js` with API calls:

```javascript
async init() {
  // Replace static data with your API
  const response = await fetch('https://your-api.com/signals');
  this.sampleData = await response.json();
  this.render();
}
```

### Contact Form (Formspree)
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
  <!-- your form fields -->
  <button type="submit" class="btn btn-primary">Send</button>
</form>
```

### Newsletter (Mailchimp)
Replace the `.newsletter-form` action with your Mailchimp embed code action URL.

---

## Performance Tips

1. **Compress images** — Use Squoosh or TinyPNG before uploading
2. **Use WebP format** — ~30% smaller than JPG
3. **Lazy load images** — All `<img>` tags already have `loading="lazy"`
4. **Minify CSS/JS** — Use a minifier before production
5. **Enable Gzip** — Configure on your server/hosting
6. **Use CDN** — Serve static assets from a CDN for global speed

---

*Forex Academy Pro Template — documentation v1.0.0*
