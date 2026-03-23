# Classplay Design System Page — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a single self-contained HTML page that documents the complete Classplay Design System with live component previews, dark/light toggle, and markdown download.

**Architecture:** One HTML file (`index.html`) containing all CSS (inline `<style>`), component previews, and JS for theme toggle + markdown generation. The page uses a fixed sidebar for navigation with anchor links to each section. All design tokens from the spec are embedded as CSS custom properties. The only external dependency is Google Fonts (Nunito + JetBrains Mono).

**Tech Stack:** HTML5, CSS3 (custom properties), Vanilla JS, Google Fonts

**Spec:** `docs/superpowers/specs/2026-03-23-classplay-design-system.md`

---

## File Structure

- **Create:** `index.html` — the complete design system documentation page (single file, self-contained)

That's it. One file. All CSS is inline via `<style>`, all JS is inline via `<script>`.

---

## Task 1: HTML Shell + CSS Tokens + Theme Toggle

**Files:**
- Create: `index.html`

The foundation: HTML document structure, all CSS custom property declarations from spec sections 1-5, dark/light theme surfaces, Google Fonts import, page layout (sidebar + main content area), and the JS theme toggle.

- [ ] **Step 1: Create `index.html` with the document shell**

```html
<!DOCTYPE html>
<html lang="pt-BR" data-theme="dark">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Classplay Design System</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Nunito:wght@400;600;700;800;900&display=swap" rel="stylesheet">
  <style>
    /* === RESET === */
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

    /* === COLOR TOKENS === */
    /* Copy ALL :root tokens from spec section 1.4 exactly */
    :root {
      --cp-primary-50: #FAF5FF;
      --cp-primary-100: #F3E8FF;
      --cp-primary-200: #E9D5FF;
      --cp-primary-300: #D8B4FE;
      --cp-primary-400: #C084FC;
      --cp-primary-500: #A855F7;
      --cp-primary-600: #7C3AED;
      --cp-primary-700: #6D28D9;
      --cp-primary-800: #5B21B6;
      --cp-primary-900: #4C1D95;

      --cp-xp: #F59E0B;
      --cp-xp-50: #FFFBEB; --cp-xp-100: #FEF3C7; --cp-xp-200: #FDE68A;
      --cp-xp-300: #FCD34D; --cp-xp-400: #FBBF24; --cp-xp-500: #F59E0B;
      --cp-xp-600: #D97706; --cp-xp-700: #B45309; --cp-xp-800: #92400E;
      --cp-xp-900: #78350F;

      --cp-streak: #F97316;
      --cp-streak-50: #FFF7ED; --cp-streak-100: #FFEDD5; --cp-streak-200: #FED7AA;
      --cp-streak-300: #FDBA74; --cp-streak-400: #FB923C; --cp-streak-500: #F97316;
      --cp-streak-600: #EA580C; --cp-streak-700: #C2410C; --cp-streak-800: #9A3412;
      --cp-streak-900: #7C2D12;

      --cp-success: #10B981;
      --cp-success-50: #ECFDF5; --cp-success-100: #D1FAE5; --cp-success-200: #A7F3D0;
      --cp-success-300: #6EE7B7; --cp-success-400: #34D399; --cp-success-500: #10B981;
      --cp-success-600: #059669; --cp-success-700: #047857; --cp-success-800: #065F46;
      --cp-success-900: #064E3B;

      --cp-info: #3B82F6;
      --cp-info-50: #EFF6FF; --cp-info-100: #DBEAFE; --cp-info-200: #BFDBFE;
      --cp-info-300: #93C5FD; --cp-info-400: #60A5FA; --cp-info-500: #3B82F6;
      --cp-info-600: #2563EB; --cp-info-700: #1D4ED8; --cp-info-800: #1E40AF;
      --cp-info-900: #1E3A8A;

      --cp-danger: #EF4444;
      --cp-danger-50: #FEF2F2; --cp-danger-100: #FEE2E2; --cp-danger-200: #FECACA;
      --cp-danger-300: #FCA5A5; --cp-danger-400: #F87171; --cp-danger-500: #EF4444;
      --cp-danger-600: #DC2626; --cp-danger-700: #B91C1C; --cp-danger-800: #991B1B;
      --cp-danger-900: #7F1D1D;

      --cp-bonus: #EC4899;
      --cp-bonus-50: #FDF2F8; --cp-bonus-100: #FCE7F3; --cp-bonus-200: #FBCFE8;
      --cp-bonus-300: #F9A8D4; --cp-bonus-400: #F472B6; --cp-bonus-500: #EC4899;
      --cp-bonus-600: #DB2777; --cp-bonus-700: #BE185D; --cp-bonus-800: #9D174D;
      --cp-bonus-900: #831843;

      --cp-level: #06B6D4;
      --cp-level-50: #ECFEFF; --cp-level-100: #CFFAFE; --cp-level-200: #A5F3FC;
      --cp-level-300: #67E8F9; --cp-level-400: #22D3EE; --cp-level-500: #06B6D4;
      --cp-level-600: #0891B2; --cp-level-700: #0E7490; --cp-level-800: #155E75;
      --cp-level-900: #164E63;

      /* TYPOGRAPHY TOKENS */
      --cp-font-family: 'Nunito', sans-serif;
      --cp-font-mono: 'JetBrains Mono', 'Fira Code', monospace;
      --cp-text-xs: 0.75rem; --cp-text-sm: 0.875rem; --cp-text-base: 1rem;
      --cp-text-lg: 1.125rem; --cp-text-xl: 1.25rem; --cp-text-2xl: 1.5rem;
      --cp-text-3xl: 1.875rem; --cp-text-4xl: 2.25rem; --cp-text-display: 3rem;
      --cp-font-regular: 400; --cp-font-semibold: 600; --cp-font-bold: 700;
      --cp-font-extra: 800; --cp-font-black: 900;

      /* SPACING TOKENS */
      --cp-space-1: 4px; --cp-space-2: 8px; --cp-space-3: 12px;
      --cp-space-4: 16px; --cp-space-5: 20px; --cp-space-6: 24px;
      --cp-space-8: 32px; --cp-space-10: 40px; --cp-space-12: 48px;
      --cp-space-16: 64px; --cp-space-20: 80px;

      /* BORDER RADIUS TOKENS */
      --cp-radius-sm: 6px; --cp-radius-md: 8px; --cp-radius-lg: 12px;
      --cp-radius-xl: 16px; --cp-radius-pill: 9999px; --cp-radius-circle: 50%;

      /* SHADOW TOKENS (uses --cp-shadow-color from theme) */
      --cp-shadow-sm: 0 1px 2px var(--cp-shadow-color);
      --cp-shadow-md: 0 4px 6px var(--cp-shadow-color);
      --cp-shadow-lg: 0 10px 25px var(--cp-shadow-color);
      --cp-shadow-xl: 0 20px 40px var(--cp-shadow-color);
      --cp-shadow-3d: 0 4px 0px;
      --cp-shadow-glow: 0 0 20px;

      /* TRANSITION TOKENS */
      --cp-transition-fast: 0.1s ease;
      --cp-transition-base: 0.2s ease;
      --cp-transition-slow: 0.3s ease;
      --cp-transition-bounce: 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
      --cp-transition-spring: 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);

      /* Z-INDEX TOKENS */
      --cp-z-base: 0; --cp-z-dropdown: 100; --cp-z-sticky: 200;
      --cp-z-overlay: 300; --cp-z-modal: 400; --cp-z-toast: 500; --cp-z-confetti: 600;
    }

    /* THEME: DARK */
    [data-theme="dark"] {
      --cp-bg-primary: #0F0A1A;
      --cp-bg-secondary: #1A1128;
      --cp-bg-tertiary: #2D1F42;
      --cp-bg-elevated: #251A38;
      --cp-text-primary: #F5F0FF;
      --cp-text-secondary: #B8A0D4;
      --cp-text-muted: #7A6895;
      --cp-border: #2D1F42;
      --cp-border-subtle: #1F1630;
      --cp-shadow-color: rgba(0, 0, 0, 0.4);
      --cp-overlay: rgba(15, 10, 26, 0.8);
    }
    /* THEME: LIGHT */
    [data-theme="light"] {
      --cp-bg-primary: #FFFFFF;
      --cp-bg-secondary: #FAF5FF;
      --cp-bg-tertiary: #F3E8FF;
      --cp-bg-elevated: #FFFFFF;
      --cp-text-primary: #1A1128;
      --cp-text-secondary: #6B5A82;
      --cp-text-muted: #9B8AB3;
      --cp-border: #E9D5FF;
      --cp-border-subtle: #F3E8FF;
      --cp-shadow-color: rgba(124, 58, 237, 0.08);
      --cp-overlay: rgba(255, 255, 255, 0.8);
    }

    /* === PAGE LAYOUT === */
    body {
      font-family: var(--cp-font-family);
      background: var(--cp-bg-primary);
      color: var(--cp-text-primary);
      line-height: 1.6;
    }
    /* Fixed sidebar nav */
    .ds-sidebar { /* prefix ds- for doc-site layout, not cp- design system components */
      width: 260px;
      height: 100vh;
      position: fixed;
      top: 0; left: 0;
      background: var(--cp-bg-secondary);
      border-right: 1px solid var(--cp-border-subtle);
      padding: var(--cp-space-6) 0;
      overflow-y: auto;
      z-index: var(--cp-z-sticky);
    }
    .ds-sidebar__logo {
      padding: 0 var(--cp-space-5);
      margin-bottom: var(--cp-space-6);
      font-size: var(--cp-text-2xl);
      font-weight: var(--cp-font-black);
      color: var(--cp-primary-600);
    }
    .ds-sidebar a {
      display: block;
      padding: var(--cp-space-2) var(--cp-space-5);
      color: var(--cp-text-secondary);
      text-decoration: none;
      font-size: var(--cp-text-sm);
      font-weight: var(--cp-font-semibold);
      transition: background var(--cp-transition-base), color var(--cp-transition-base);
      border-left: 3px solid transparent;
    }
    .ds-sidebar a:hover, .ds-sidebar a.active {
      background: var(--cp-bg-tertiary);
      color: var(--cp-text-primary);
    }
    .ds-sidebar a.active {
      border-left-color: var(--cp-primary-600);
      color: var(--cp-primary-600);
    }
    /* Main content area */
    .ds-main {
      margin-left: 260px;
      padding: var(--cp-space-8) var(--cp-space-10);
      max-width: 1060px;
    }
    /* Header bar with theme toggle + download */
    .ds-header {
      position: fixed;
      top: 0; left: 260px; right: 0;
      height: 60px;
      background: var(--cp-bg-elevated);
      border-bottom: 1px solid var(--cp-border-subtle);
      display: flex;
      align-items: center;
      justify-content: flex-end;
      padding: 0 var(--cp-space-6);
      gap: var(--cp-space-3);
      z-index: var(--cp-z-sticky);
      box-shadow: var(--cp-shadow-sm);
    }
    .ds-main { padding-top: calc(60px + var(--cp-space-8)); }

    /* === SECTION STYLING === */
    .ds-section {
      margin-bottom: var(--cp-space-16);
      scroll-margin-top: 80px;
    }
    .ds-section h2 {
      font-size: var(--cp-text-3xl);
      font-weight: var(--cp-font-black);
      color: var(--cp-text-primary);
      margin-bottom: var(--cp-space-2);
    }
    .ds-section h3 {
      font-size: var(--cp-text-xl);
      font-weight: var(--cp-font-bold);
      color: var(--cp-text-primary);
      margin-top: var(--cp-space-8);
      margin-bottom: var(--cp-space-4);
    }
    .ds-section p.desc {
      color: var(--cp-text-secondary);
      font-size: var(--cp-text-base);
      margin-bottom: var(--cp-space-6);
    }
    /* Preview container for component demos */
    .ds-preview {
      background: var(--cp-bg-secondary);
      border: 1px solid var(--cp-border-subtle);
      border-radius: var(--cp-radius-lg);
      padding: var(--cp-space-6);
      margin-bottom: var(--cp-space-4);
    }
    /* Code block showing CSS */
    .ds-code {
      background: var(--cp-bg-tertiary);
      border: 1px solid var(--cp-border-subtle);
      border-radius: var(--cp-radius-md);
      padding: var(--cp-space-4);
      font-family: var(--cp-font-mono);
      font-size: var(--cp-text-sm);
      color: var(--cp-text-secondary);
      overflow-x: auto;
      margin-bottom: var(--cp-space-6);
      white-space: pre;
      line-height: 1.6;
    }
    /* Swatch grid for colors */
    .ds-swatches {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
      gap: var(--cp-space-3);
    }
    .ds-swatch {
      border-radius: var(--cp-radius-md);
      overflow: hidden;
      cursor: pointer;
      transition: transform var(--cp-transition-fast);
      border: 1px solid var(--cp-border-subtle);
    }
    .ds-swatch:hover { transform: scale(1.05); }
    .ds-swatch__color {
      height: 60px;
      display: flex; align-items: flex-end; justify-content: flex-start;
      padding: var(--cp-space-1);
    }
    .ds-swatch__label {
      padding: var(--cp-space-2);
      font-size: var(--cp-text-xs);
      font-weight: var(--cp-font-bold);
      background: var(--cp-bg-secondary);
    }
    .ds-swatch__hex {
      font-family: var(--cp-font-mono);
      font-size: 10px;
      color: var(--cp-text-muted);
      display: block;
    }
    /* Flex row helper for previews */
    .ds-flex { display: flex; flex-wrap: wrap; gap: var(--cp-space-3); align-items: center; }
    .ds-grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: var(--cp-space-4); }

    /* FOCUS GLOBAL (from spec 6.0) */
    :focus-visible { outline: 2px solid var(--cp-primary-600); outline-offset: 2px; }
    [data-theme="dark"] :focus-visible { outline-color: var(--cp-primary-400); }
    :focus:not(:focus-visible) { outline: none; }

    /* REDUCED MOTION (from spec 8.6) */
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
      }
    }
  </style>
</head>
<body>
  <!-- Sidebar navigation -->
  <nav class="ds-sidebar">
    <div class="ds-sidebar__logo">Classplay DS</div>
    <a href="#colors">Cores</a>
    <a href="#typography">Tipografia</a>
    <a href="#spacing">Espaçamento</a>
    <a href="#radius">Border Radius</a>
    <a href="#shadows">Sombras</a>
    <a href="#buttons">Botões</a>
    <a href="#forms">Formulários</a>
    <a href="#cards">Cards</a>
    <a href="#badges">Badges & Tags</a>
    <a href="#progress">Progresso</a>
    <a href="#gamification">Gamificação</a>
    <a href="#animations">Animações</a>
    <a href="#loading">Loading States</a>
    <a href="#toasts">Toasts</a>
    <a href="#layout">Layout</a>
    <a href="#gradients">Gradientes</a>
  </nav>

  <!-- Top header bar -->
  <header class="ds-header">
    <button id="theme-toggle" onclick="toggleTheme()" style="/* styled in Task 2 */">
      Toggle Theme
    </button>
    <button id="download-md" onclick="downloadMarkdown()" style="/* styled in Task 2 */">
      Download Markdown
    </button>
  </header>

  <!-- Main content -->
  <main class="ds-main">
    <!-- Sections will be added in subsequent tasks -->
  </main>

  <script>
    // Theme toggle
    function toggleTheme() {
      const html = document.documentElement;
      const current = html.getAttribute('data-theme');
      const next = current === 'dark' ? 'light' : 'dark';
      html.setAttribute('data-theme', next);
      localStorage.setItem('cp-theme', next);
      updateThemeIcon();
    }
    function updateThemeIcon() {
      const btn = document.getElementById('theme-toggle');
      const isDark = document.documentElement.getAttribute('data-theme') === 'dark';
      btn.textContent = isDark ? '☀️ Light' : '🌙 Dark';
    }
    // Load saved theme
    const saved = localStorage.getItem('cp-theme');
    if (saved) document.documentElement.setAttribute('data-theme', saved);
    updateThemeIcon();

    // Sidebar active state on scroll
    const sections = () => document.querySelectorAll('.ds-section');
    const navLinks = () => document.querySelectorAll('.ds-sidebar a');
    window.addEventListener('scroll', () => {
      let current = '';
      sections().forEach(s => {
        if (window.scrollY >= s.offsetTop - 100) current = s.id;
      });
      navLinks().forEach(a => {
        a.classList.toggle('active', a.getAttribute('href') === '#' + current);
      });
    });

    // Copy to clipboard on swatch click
    function copySwatch(hex) {
      navigator.clipboard.writeText(hex);
      // Brief visual feedback handled by caller
    }

    // Markdown download — placeholder, full implementation in Task 8
    function downloadMarkdown() {
      alert('Markdown download will be implemented in Task 8');
    }
  </script>
</body>
</html>
```

- [ ] **Step 2: Open in browser and verify**

Run: open `index.html` in browser (or use `npx serve .`)
Expected:
- Dark theme by default
- Sidebar visible on left with navigation links
- Header bar at top with theme toggle and download button
- Toggle switches between dark and light themes
- Sidebar highlights active section on scroll

- [ ] **Step 3: Commit**

```bash
git add index.html
git commit -m "feat: HTML shell with CSS tokens, theme toggle, and page layout"
```

---

## Task 2: Colors Section

**Files:**
- Modify: `index.html` — add colors section inside `<main>`

Add the color documentation section with interactive swatches for primary scale and all 7 functional color scales. Clicking a swatch copies the hex value.

- [ ] **Step 1: Add colors section HTML**

Inside `<main>`, add:

```html
<section id="colors" class="ds-section">
  <h2>1. Cores</h2>
  <p class="desc">Prefixo <code>--cp-</code>. Clique em qualquer swatch para copiar o valor hex.</p>

  <h3>Primária — Roxo</h3>
  <div class="ds-swatches" id="primary-swatches"></div>

  <h3>XP (Âmbar)</h3>
  <div class="ds-swatches" id="xp-swatches"></div>

  <h3>Streak (Laranja)</h3>
  <div class="ds-swatches" id="streak-swatches"></div>

  <h3>Success (Esmeralda)</h3>
  <div class="ds-swatches" id="success-swatches"></div>

  <h3>Info (Azul)</h3>
  <div class="ds-swatches" id="info-swatches"></div>

  <h3>Danger (Vermelho)</h3>
  <div class="ds-swatches" id="danger-swatches"></div>

  <h3>Bonus (Rosa)</h3>
  <div class="ds-swatches" id="bonus-swatches"></div>

  <h3>Level (Cyan)</h3>
  <div class="ds-swatches" id="level-swatches"></div>

  <h3>Superfícies</h3>
  <div class="ds-grid-2">
    <div>
      <h4 style="margin-bottom:var(--cp-space-3);color:var(--cp-text-secondary);">Dark Mode</h4>
      <div class="ds-swatches" id="surface-dark-swatches"></div>
    </div>
    <div>
      <h4 style="margin-bottom:var(--cp-space-3);color:var(--cp-text-secondary);">Light Mode</h4>
      <div class="ds-swatches" id="surface-light-swatches"></div>
    </div>
  </div>
</section>
```

- [ ] **Step 2: Add JS to generate swatches**

In the `<script>` section, add a function that generates swatch HTML from data arrays and populates each container:

```javascript
function renderSwatches(containerId, swatches) {
  const container = document.getElementById(containerId);
  container.innerHTML = swatches.map(([name, hex]) => `
    <div class="ds-swatch" onclick="copySwatch('${hex}')" title="Click to copy ${hex}">
      <div class="ds-swatch__color" style="background:${hex};"></div>
      <div class="ds-swatch__label">
        ${name}<span class="ds-swatch__hex">${hex}</span>
      </div>
    </div>
  `).join('');
}

// Call for each color scale with all values from spec section 1.4
renderSwatches('primary-swatches', [
  ['50', '#FAF5FF'], ['100', '#F3E8FF'], ['200', '#E9D5FF'],
  ['300', '#D8B4FE'], ['400', '#C084FC'], ['500', '#A855F7'],
  ['600', '#7C3AED'], ['700', '#6D28D9'], ['800', '#5B21B6'], ['900', '#4C1D95']
]);
renderSwatches('xp-swatches', [
  ['50','#FFFBEB'],['100','#FEF3C7'],['200','#FDE68A'],['300','#FCD34D'],
  ['400','#FBBF24'],['500','#F59E0B'],['600','#D97706'],['700','#B45309'],
  ['800','#92400E'],['900','#78350F']
]);
renderSwatches('streak-swatches', [
  ['50','#FFF7ED'],['100','#FFEDD5'],['200','#FED7AA'],['300','#FDBA74'],
  ['400','#FB923C'],['500','#F97316'],['600','#EA580C'],['700','#C2410C'],
  ['800','#9A3412'],['900','#7C2D12']
]);
renderSwatches('success-swatches', [
  ['50','#ECFDF5'],['100','#D1FAE5'],['200','#A7F3D0'],['300','#6EE7B7'],
  ['400','#34D399'],['500','#10B981'],['600','#059669'],['700','#047857'],
  ['800','#065F46'],['900','#064E3B']
]);
renderSwatches('info-swatches', [
  ['50','#EFF6FF'],['100','#DBEAFE'],['200','#BFDBFE'],['300','#93C5FD'],
  ['400','#60A5FA'],['500','#3B82F6'],['600','#2563EB'],['700','#1D4ED8'],
  ['800','#1E40AF'],['900','#1E3A8A']
]);
renderSwatches('danger-swatches', [
  ['50','#FEF2F2'],['100','#FEE2E2'],['200','#FECACA'],['300','#FCA5A5'],
  ['400','#F87171'],['500','#EF4444'],['600','#DC2626'],['700','#B91C1C'],
  ['800','#991B1B'],['900','#7F1D1D']
]);
renderSwatches('bonus-swatches', [
  ['50','#FDF2F8'],['100','#FCE7F3'],['200','#FBCFE8'],['300','#F9A8D4'],
  ['400','#F472B6'],['500','#EC4899'],['600','#DB2777'],['700','#BE185D'],
  ['800','#9D174D'],['900','#831843']
]);
renderSwatches('level-swatches', [
  ['50','#ECFEFF'],['100','#CFFAFE'],['200','#A5F3FC'],['300','#67E8F9'],
  ['400','#22D3EE'],['500','#06B6D4'],['600','#0891B2'],['700','#0E7490'],
  ['800','#155E75'],['900','#164E63']
]);

// Surface swatches
renderSwatches('surface-dark-swatches', [
  ['bg-primary','#0F0A1A'],['bg-secondary','#1A1128'],
  ['bg-tertiary','#2D1F42'],['bg-elevated','#251A38'],
  ['text-primary','#F5F0FF'],['text-secondary','#B8A0D4'],
  ['text-muted','#7A6895'],['border','#2D1F42']
]);
renderSwatches('surface-light-swatches', [
  ['bg-primary','#FFFFFF'],['bg-secondary','#FAF5FF'],
  ['bg-tertiary','#F3E8FF'],['bg-elevated','#FFFFFF'],
  ['text-primary','#1A1128'],['text-secondary','#6B5A82'],
  ['text-muted','#9B8AB3'],['border','#E9D5FF']
]);
```

- [ ] **Step 3: Verify in browser**

Expected: All color swatches render in grids. Clicking copies hex to clipboard. Dark/light surfaces show side by side.

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: add colors section with interactive swatches"
```

---

## Task 3: Typography + Spacing + Radius + Shadows Sections

**Files:**
- Modify: `index.html` — add sections for spec sections 2-5

- [ ] **Step 1: Add typography section**

After the colors section in `<main>`, add:

```html
<section id="typography" class="ds-section">
  <h2>2. Tipografia</h2>
  <p class="desc">Nunito para interface, JetBrains Mono para código.</p>

  <h3>Escala</h3>
  <div class="ds-preview">
    <div style="margin-bottom:var(--cp-space-4);">
      <span style="font-size:var(--cp-text-xs);color:var(--cp-text-muted);">--cp-text-xs (12px)</span>
      <div style="font-size:var(--cp-text-xs);">Classplay Design System</div>
    </div>
    <!-- Repeat for each size: sm, base, lg, xl, 2xl, 3xl, 4xl, display -->
    <div style="margin-bottom:var(--cp-space-4);">
      <span style="font-size:var(--cp-text-xs);color:var(--cp-text-muted);">--cp-text-sm (14px)</span>
      <div style="font-size:var(--cp-text-sm);">Classplay Design System</div>
    </div>
    <div style="margin-bottom:var(--cp-space-4);">
      <span style="font-size:var(--cp-text-xs);color:var(--cp-text-muted);">--cp-text-base (16px)</span>
      <div style="font-size:var(--cp-text-base);">Classplay Design System</div>
    </div>
    <div style="margin-bottom:var(--cp-space-4);">
      <span style="font-size:var(--cp-text-xs);color:var(--cp-text-muted);">--cp-text-lg (18px)</span>
      <div style="font-size:var(--cp-text-lg);font-weight:var(--cp-font-semibold);">Classplay Design System</div>
    </div>
    <div style="margin-bottom:var(--cp-space-4);">
      <span style="font-size:var(--cp-text-xs);color:var(--cp-text-muted);">--cp-text-xl (20px)</span>
      <div style="font-size:var(--cp-text-xl);font-weight:var(--cp-font-bold);">Classplay Design System</div>
    </div>
    <div style="margin-bottom:var(--cp-space-4);">
      <span style="font-size:var(--cp-text-xs);color:var(--cp-text-muted);">--cp-text-2xl (24px)</span>
      <div style="font-size:var(--cp-text-2xl);font-weight:var(--cp-font-bold);">Classplay Design System</div>
    </div>
    <div style="margin-bottom:var(--cp-space-4);">
      <span style="font-size:var(--cp-text-xs);color:var(--cp-text-muted);">--cp-text-3xl (30px)</span>
      <div style="font-size:var(--cp-text-3xl);font-weight:var(--cp-font-extra);">Classplay Design System</div>
    </div>
    <div style="margin-bottom:var(--cp-space-4);">
      <span style="font-size:var(--cp-text-xs);color:var(--cp-text-muted);">--cp-text-4xl (36px)</span>
      <div style="font-size:var(--cp-text-4xl);font-weight:var(--cp-font-extra);">1,250 XP</div>
    </div>
    <div>
      <span style="font-size:var(--cp-text-xs);color:var(--cp-text-muted);">--cp-text-display (48px)</span>
      <div style="font-size:var(--cp-text-display);font-weight:var(--cp-font-black);">Level Up!</div>
    </div>
  </div>

  <h3>Pesos</h3>
  <div class="ds-preview">
    <div style="font-size:var(--cp-text-xl);margin-bottom:var(--cp-space-2);font-weight:400;">Regular (400) — Corpo de texto</div>
    <div style="font-size:var(--cp-text-xl);margin-bottom:var(--cp-space-2);font-weight:600;">SemiBold (600) — Labels, ênfase</div>
    <div style="font-size:var(--cp-text-xl);margin-bottom:var(--cp-space-2);font-weight:700;">Bold (700) — Títulos, botões</div>
    <div style="font-size:var(--cp-text-xl);margin-bottom:var(--cp-space-2);font-weight:800;">ExtraBold (800) — XP, displays</div>
    <div style="font-size:var(--cp-text-xl);font-weight:900;">Black (900) — Conquistas, hero</div>
  </div>

  <h3>Monospace</h3>
  <div class="ds-preview">
    <code style="font-family:var(--cp-font-mono);font-size:var(--cp-text-base);color:var(--cp-primary-400);">
      const xp = user.getXP(); // JetBrains Mono
    </code>
  </div>
</section>
```

- [ ] **Step 2: Add spacing section**

```html
<section id="spacing" class="ds-section">
  <h2>3. Espaçamento</h2>
  <p class="desc">Escala baseada em múltiplos de 4px.</p>
  <div class="ds-preview" id="spacing-preview"></div>
</section>
```

Generate spacing bars via JS:

```javascript
const spacingPreview = document.getElementById('spacing-preview');
const spaces = [
  ['1', '4px'], ['2', '8px'], ['3', '12px'], ['4', '16px'],
  ['5', '20px'], ['6', '24px'], ['8', '32px'], ['10', '40px'],
  ['12', '48px'], ['16', '64px'], ['20', '80px']
];
spacingPreview.innerHTML = spaces.map(([n, px]) => `
  <div style="display:flex;align-items:center;gap:var(--cp-space-3);margin-bottom:var(--cp-space-2);">
    <code style="font-family:var(--cp-font-mono);font-size:var(--cp-text-xs);width:120px;color:var(--cp-text-muted);">--cp-space-${n} (${px})</code>
    <div style="height:12px;width:var(--cp-space-${n});background:var(--cp-primary-600);border-radius:var(--cp-radius-sm);min-width:4px;"></div>
  </div>
`).join('');
```

- [ ] **Step 3: Add border radius section**

```html
<section id="radius" class="ds-section">
  <h2>4. Border Radius</h2>
  <p class="desc">Moderado como padrão, pill para badges.</p>
  <div class="ds-preview ds-flex">
    <div style="width:80px;height:80px;background:var(--cp-primary-600);border-radius:var(--cp-radius-sm);display:flex;align-items:center;justify-content:center;color:white;font-size:var(--cp-text-xs);font-weight:var(--cp-font-bold);">sm 6px</div>
    <div style="width:80px;height:80px;background:var(--cp-primary-600);border-radius:var(--cp-radius-md);display:flex;align-items:center;justify-content:center;color:white;font-size:var(--cp-text-xs);font-weight:var(--cp-font-bold);">md 8px</div>
    <div style="width:80px;height:80px;background:var(--cp-primary-600);border-radius:var(--cp-radius-lg);display:flex;align-items:center;justify-content:center;color:white;font-size:var(--cp-text-xs);font-weight:var(--cp-font-bold);">lg 12px</div>
    <div style="width:80px;height:80px;background:var(--cp-primary-600);border-radius:var(--cp-radius-xl);display:flex;align-items:center;justify-content:center;color:white;font-size:var(--cp-text-xs);font-weight:var(--cp-font-bold);">xl 16px</div>
    <div style="padding:var(--cp-space-2) var(--cp-space-4);background:var(--cp-primary-600);border-radius:var(--cp-radius-pill);color:white;font-size:var(--cp-text-xs);font-weight:var(--cp-font-bold);">pill</div>
    <div style="width:80px;height:80px;background:var(--cp-primary-600);border-radius:var(--cp-radius-circle);display:flex;align-items:center;justify-content:center;color:white;font-size:var(--cp-text-xs);font-weight:var(--cp-font-bold);">circle</div>
  </div>
</section>
```

- [ ] **Step 4: Add shadows section**

```html
<section id="shadows" class="ds-section">
  <h2>5. Sombras</h2>
  <div class="ds-preview ds-flex">
    <div style="width:120px;height:80px;background:var(--cp-bg-elevated);border-radius:var(--cp-radius-md);box-shadow:var(--cp-shadow-sm);display:flex;align-items:center;justify-content:center;font-size:var(--cp-text-sm);font-weight:var(--cp-font-bold);">sm</div>
    <div style="width:120px;height:80px;background:var(--cp-bg-elevated);border-radius:var(--cp-radius-md);box-shadow:var(--cp-shadow-md);display:flex;align-items:center;justify-content:center;font-size:var(--cp-text-sm);font-weight:var(--cp-font-bold);">md</div>
    <div style="width:120px;height:80px;background:var(--cp-bg-elevated);border-radius:var(--cp-radius-md);box-shadow:var(--cp-shadow-lg);display:flex;align-items:center;justify-content:center;font-size:var(--cp-text-sm);font-weight:var(--cp-font-bold);">lg</div>
    <div style="width:120px;height:80px;background:var(--cp-bg-elevated);border-radius:var(--cp-radius-md);box-shadow:var(--cp-shadow-xl);display:flex;align-items:center;justify-content:center;font-size:var(--cp-text-sm);font-weight:var(--cp-font-bold);">xl</div>
  </div>
</section>
```

- [ ] **Step 5: Verify in browser**

Expected: All four sections render correctly with live previews. Typography shows all sizes/weights. Spacing shows proportional bars. Radius shows shape previews. Shadows visible on both themes.

- [ ] **Step 6: Commit**

```bash
git add index.html
git commit -m "feat: add typography, spacing, radius, and shadows sections"
```

---

## Task 4: Buttons Section

**Files:**
- Modify: `index.html` — add component CSS for all buttons from spec 6.1, plus the buttons section HTML

- [ ] **Step 1: Add button component CSS**

In the `<style>` block, add ALL button CSS from spec section 6.1 (`.cp-btn`, `.cp-btn-primary`, `.cp-btn-secondary`, `.cp-btn-ghost`, `.cp-btn-success`, `.cp-btn-danger`, size modifiers, disabled state). Copy CSS blocks exactly from the spec.

- [ ] **Step 2: Style the header buttons**

Replace the placeholder `style=""` on the theme toggle and download buttons in the header with proper classes:

```html
<button id="theme-toggle" class="cp-btn cp-btn-ghost" onclick="toggleTheme()"></button>
<button id="download-md" class="cp-btn cp-btn-primary cp-btn--sm" onclick="downloadMarkdown()">Download .md</button>
```

- [ ] **Step 3: Add buttons section HTML**

```html
<section id="buttons" class="ds-section">
  <h2>6. Botões</h2>
  <p class="desc">3D para CTAs, flat para secundários. Todos compartilham a base <code>.cp-btn</code>.</p>

  <h3>Primário (3D)</h3>
  <div class="ds-preview ds-flex">
    <button class="cp-btn cp-btn-primary cp-btn--sm">Small</button>
    <button class="cp-btn cp-btn-primary">Default</button>
    <button class="cp-btn cp-btn-primary cp-btn--lg">Large</button>
    <button class="cp-btn cp-btn-primary" disabled>Disabled</button>
  </div>

  <h3>Secundário (Flat)</h3>
  <div class="ds-preview ds-flex">
    <button class="cp-btn cp-btn-secondary cp-btn--sm">Small</button>
    <button class="cp-btn cp-btn-secondary">Default</button>
    <button class="cp-btn cp-btn-secondary cp-btn--lg">Large</button>
    <button class="cp-btn cp-btn-secondary" disabled>Disabled</button>
  </div>

  <h3>Ghost</h3>
  <div class="ds-preview ds-flex">
    <button class="cp-btn cp-btn-ghost">Ghost Button</button>
    <button class="cp-btn cp-btn-ghost" disabled>Disabled</button>
  </div>

  <h3>Sucesso & Perigo (3D)</h3>
  <div class="ds-preview ds-flex">
    <button class="cp-btn cp-btn-success">Completar</button>
    <button class="cp-btn cp-btn-danger">Excluir</button>
    <button class="cp-btn cp-btn-success" disabled>Disabled</button>
    <button class="cp-btn cp-btn-danger" disabled>Disabled</button>
  </div>
</section>
```

- [ ] **Step 4: Verify in browser**

Expected: All button variants render with correct 3D shadows, hover lifts up, active presses down. Disabled buttons are dimmed. Theme toggle button now styled. Works in both themes.

- [ ] **Step 5: Commit**

```bash
git add index.html
git commit -m "feat: add buttons section with all variants and states"
```

---

## Task 5: Forms Section

**Files:**
- Modify: `index.html` — add form component CSS from spec 6.2, plus section HTML

- [ ] **Step 1: Add form component CSS**

In `<style>`, add all CSS from spec section 6.2: `.cp-input`, `.cp-input:focus`, `.cp-input--error`, `.cp-label`, `.cp-select` (with SVG arrow), `.cp-textarea`, `.cp-toggle` (with accessible checkbox pattern). Copy exactly from spec.

- [ ] **Step 2: Add forms section HTML**

```html
<section id="forms" class="ds-section">
  <h2>7. Formulários</h2>

  <h3>Input</h3>
  <div class="ds-preview" style="max-width:400px;">
    <label class="cp-label">Nome do curso</label>
    <input class="cp-input" type="text" placeholder="Ex: Introdução ao Vibe Coding">
    <div style="margin-top:var(--cp-space-4);">
      <label class="cp-label">Email (com erro)</label>
      <input class="cp-input cp-input--error" type="email" value="email-invalido">
    </div>
  </div>

  <h3>Select</h3>
  <div class="ds-preview" style="max-width:400px;">
    <label class="cp-label">Categoria</label>
    <select class="cp-select" style="width:100%;">
      <option>IA Generativa</option>
      <option>Vibe Coding</option>
      <option>Automação</option>
    </select>
  </div>

  <h3>Textarea</h3>
  <div class="ds-preview" style="max-width:400px;">
    <label class="cp-label">Descrição</label>
    <textarea class="cp-input cp-textarea" placeholder="Descreva o módulo..."></textarea>
  </div>

  <h3>Toggle</h3>
  <div class="ds-preview ds-flex">
    <label class="cp-toggle">
      <input type="checkbox" role="switch">
      <span class="cp-toggle__track"></span>
    </label>
    <span style="color:var(--cp-text-secondary);font-size:var(--cp-text-sm);">Notificações</span>

    <label class="cp-toggle" style="margin-left:var(--cp-space-6);">
      <input type="checkbox" role="switch" checked>
      <span class="cp-toggle__track"></span>
    </label>
    <span style="color:var(--cp-text-secondary);font-size:var(--cp-text-sm);">Dark Mode (ativo)</span>
  </div>
</section>
```

- [ ] **Step 3: Verify in browser**

Expected: Inputs show focus ring on click. Error input has red border. Select has custom chevron arrow. Toggle switches animate smoothly. All elements work in both themes.

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: add forms section with inputs, select, textarea, toggle"
```

---

## Task 6: Cards + Badges + Progress + Avatar + Modal + Tooltip Sections

**Files:**
- Modify: `index.html` — add CSS from spec 6.3-6.9, plus section HTML

- [ ] **Step 1: Add card, badge, tag, progress, avatar, modal, and tooltip CSS**

In `<style>`, add all CSS from spec sections:
- 6.3: `.cp-card`, `.cp-card-course`, `.cp-card-lesson`, `.cp-card-elevated`
- 6.4: `.cp-badge-xp`, `.cp-badge-streak`, `.cp-badge-level`, `.cp-tag`
- 6.5: `.cp-progress`, `.cp-progress__fill`, variants
- 6.6: `.cp-avatar` (all sizes + bordered variant)
- 6.7: `.cp-sidebar`, `.cp-sidebar__item` (all states + dark override) — note: these are the design system sidebar component styles, separate from the doc-site `.ds-sidebar`
- 6.8: `.cp-modal-overlay`, `.cp-modal`, `@keyframes cp-modal-in`
- 6.9: `.cp-tooltip`, `.cp-tooltip__content`

Copy exactly from spec.

- [ ] **Step 2: Add cards section HTML**

```html
<section id="cards" class="ds-section">
  <h2>8. Cards</h2>

  <h3>Card Padrão</h3>
  <div class="ds-preview" style="max-width:350px;">
    <div class="cp-card">
      <h4 style="font-weight:var(--cp-font-bold);margin-bottom:var(--cp-space-2);">Card simples</h4>
      <p style="color:var(--cp-text-secondary);font-size:var(--cp-text-sm);">Hover para ver a elevação.</p>
    </div>
  </div>

  <h3>Card de Curso</h3>
  <div class="ds-preview" style="max-width:350px;">
    <div class="cp-card-course">
      <div class="cp-card-course__image" style="background:linear-gradient(135deg,var(--cp-primary-600),var(--cp-level));display:flex;align-items:center;justify-content:center;color:white;font-size:var(--cp-text-3xl);">⚡</div>
      <div class="cp-card-course__body">
        <div class="cp-card-course__title">IA Generativa na Prática</div>
        <div class="cp-card-course__meta">12 aulas · 4h 30min</div>
        <div class="cp-card-course__progress" style="margin-top:var(--cp-space-3);">
          <div class="cp-progress"><div class="cp-progress__fill" style="width:65%;"></div></div>
        </div>
      </div>
    </div>
  </div>

  <h3>Card de Aula</h3>
  <div class="ds-preview" style="max-width:500px;">
    <div class="cp-card-lesson cp-card-lesson--completed" style="margin-bottom:var(--cp-space-2);">
      <span style="font-size:20px;">✅</span>
      <div><strong>Aula 1:</strong> O que é IA Generativa</div>
    </div>
    <div class="cp-card-lesson" style="margin-bottom:var(--cp-space-2);">
      <span style="font-size:20px;">▶️</span>
      <div><strong>Aula 2:</strong> Prompts avançados</div>
    </div>
    <div class="cp-card-lesson cp-card-lesson--locked">
      <span style="font-size:20px;">🔒</span>
      <div><strong>Aula 3:</strong> Agents e automação</div>
    </div>
  </div>

  <h3>Card Elevado</h3>
  <div class="ds-preview">
    <div class="cp-card-elevated" style="max-width:400px;">
      <h4 style="font-weight:var(--cp-font-extra);font-size:var(--cp-text-xl);margin-bottom:var(--cp-space-2);">Destaque especial</h4>
      <p style="color:var(--cp-text-secondary);">Usado para conteúdo premium ou em destaque.</p>
    </div>
  </div>
</section>
```

- [ ] **Step 3: Add avatar, modal, and tooltip preview sections**

```html
<h3>Avatar</h3>
<div class="ds-preview ds-flex">
  <div class="cp-avatar cp-avatar--sm" style="background:var(--cp-primary-300);"></div>
  <div class="cp-avatar" style="background:var(--cp-info-300);"></div>
  <div class="cp-avatar cp-avatar--lg" style="background:var(--cp-success-300);"></div>
  <div class="cp-avatar cp-avatar--xl cp-avatar--bordered" style="background:var(--cp-xp-300);"></div>
</div>

<h3>Modal</h3>
<div class="ds-preview">
  <button class="cp-btn cp-btn-primary cp-btn--sm" onclick="document.getElementById('demo-modal').style.display='flex'">Abrir Modal</button>
</div>
<div class="cp-modal-overlay" id="demo-modal" style="display:none;" onclick="if(event.target===this)this.style.display='none'">
  <div class="cp-modal">
    <h3 style="margin-bottom:var(--cp-space-4);font-weight:var(--cp-font-extra);">Level Up!</h3>
    <p style="color:var(--cp-text-secondary);margin-bottom:var(--cp-space-6);">Você alcançou o nível 5!</p>
    <button class="cp-btn cp-btn-primary" onclick="this.closest('.cp-modal-overlay').style.display='none'">Continuar</button>
  </div>
</div>

<h3>Tooltip</h3>
<div class="ds-preview ds-flex">
  <div class="cp-tooltip">
    <button class="cp-btn cp-btn-secondary cp-btn--sm">Hover me</button>
    <div class="cp-tooltip__content">Dica de ferramenta</div>
  </div>
</div>
```

- [ ] **Step 4: Add badges + tags section**

```html
<section id="badges" class="ds-section">
  <h2>9. Badges & Tags</h2>
  <div class="ds-preview ds-flex">
    <span class="cp-badge-xp">+120 XP</span>
    <span class="cp-badge-streak">🔥 14 dias</span>
    <span class="cp-badge-level">Nível 5</span>
    <span class="cp-tag">IA</span>
    <span class="cp-tag">Vibe Coding</span>
  </div>
</section>
```

- [ ] **Step 4: Add progress section**

```html
<section id="progress" class="ds-section">
  <h2>10. Barras de Progresso</h2>

  <h3>Padrão (roxo → laranja)</h3>
  <div class="ds-preview">
    <div class="cp-progress" style="margin-bottom:var(--cp-space-4);"><div class="cp-progress__fill" style="width:35%;"></div></div>
    <div class="cp-progress" style="margin-bottom:var(--cp-space-4);"><div class="cp-progress__fill" style="width:65%;"></div></div>
    <div class="cp-progress"><div class="cp-progress__fill" style="width:100%;"></div></div>
  </div>

  <h3>Variantes</h3>
  <div class="ds-preview">
    <p style="font-size:var(--cp-text-sm);color:var(--cp-text-muted);margin-bottom:var(--cp-space-2);">Success</p>
    <div class="cp-progress cp-progress--success" style="margin-bottom:var(--cp-space-4);"><div class="cp-progress__fill" style="width:80%;"></div></div>
    <p style="font-size:var(--cp-text-sm);color:var(--cp-text-muted);margin-bottom:var(--cp-space-2);">XP</p>
    <div class="cp-progress cp-progress--xp" style="margin-bottom:var(--cp-space-4);"><div class="cp-progress__fill" style="width:45%;"></div></div>
    <p style="font-size:var(--cp-text-sm);color:var(--cp-text-muted);margin-bottom:var(--cp-space-2);">Large</p>
    <div class="cp-progress cp-progress--lg"><div class="cp-progress__fill" style="width:60%;"></div></div>
  </div>
</section>
```

- [ ] **Step 5: Verify in browser**

Expected: Cards show hover effects. Course card has gradient image area, progress bar. Lesson cards show completed/locked states. Badges are colorful pills. Progress bars show gradients.

- [ ] **Step 6: Commit**

```bash
git add index.html
git commit -m "feat: add cards, badges, and progress sections"
```

---

## Task 7: Gamification + Animations + Loading + Toasts + Gradients Sections

**Files:**
- Modify: `index.html` — add remaining component CSS from spec 7.1-7.6, 8.1-8.5, 6.10-6.11, 11.1-11.2 and section HTML

This is the largest task. It covers all remaining visual sections.

- [ ] **Step 1: Add gamification component CSS**

In `<style>`, add all CSS from spec sections 7.1-7.6: `.cp-xp-panel`, `.cp-streak-counter`, `.cp-achievement` (all tiers), `.cp-leaderboard`, `.cp-mission`, `.cp-level-indicator`. Copy exactly from spec.

- [ ] **Step 2: Add animation keyframes + utility classes + confetti CSS**

In `<style>`, add all keyframes from spec 8.2, utility classes from 8.3, and confetti CSS from 8.5 (`.cp-confetti-container`, `.cp-confetti-particle`). All 12 `@keyframes` and 9 `.cp-animate-*` classes.

- [ ] **Step 3: Add loading component CSS**

In `<style>`, add spinner (`.cp-spinner`, sizes) and skeleton (`.cp-skeleton`, variants, `@keyframes cp-skeleton-pulse`) from spec 6.11.

- [ ] **Step 4: Add toast component CSS**

In `<style>`, add toast CSS from spec 6.10 (`.cp-toast-container`, `.cp-toast`, variants, `.cp-toast__message`, `.cp-toast__close`).

- [ ] **Step 5: Add gradient CSS + layout/responsive CSS**

In `<style>`, add:
- All gradient classes from spec 11.1 (`.cp-gradient-hero-dark`, `.cp-gradient-hero-light`, `.cp-gradient-premium`, `.cp-gradient-streak`, `.cp-gradient-xp`, `.cp-gradient-levelup`) and pattern classes from 11.2.
- Layout CSS from spec 9.1-9.2 (`.cp-container` variants, `.cp-layout`, `.cp-layout__main`, `.cp-layout__content`, `.cp-layout__aside`, `.cp-layout--with-aside`)
- Responsive CSS from spec 9.4 (sidebar drawer `@media (max-width: 1023px)`, mobile adjustments `@media (max-width: 767px)`, `.cp-sidebar-toggle`, `.cp-sidebar--open`)

- [ ] **Step 6: Add gamification section HTML**

```html
<section id="gamification" class="ds-section">
  <h2>11. Gamificação</h2>

  <h3>Painel de XP</h3>
  <div class="ds-preview" style="max-width:300px;">
    <div class="cp-xp-panel">
      <div>
        <div class="cp-xp-panel__number">1,250</div>
        <div class="cp-xp-panel__label">XP Total</div>
      </div>
    </div>
  </div>

  <h3>Streak Counter</h3>
  <div class="ds-preview" style="max-width:250px;">
    <div class="cp-streak-counter">
      <span style="font-size:28px;">🔥</span>
      <div>
        <div class="cp-streak-counter__number">14</div>
        <div class="cp-streak-counter__label">dias seguidos</div>
      </div>
    </div>
  </div>

  <h3>Conquistas</h3>
  <div class="ds-preview ds-flex" style="gap:var(--cp-space-6);">
    <div class="cp-achievement">
      <div class="cp-achievement__icon cp-achievement__icon--bronze">🎯</div>
      <div class="cp-achievement__title">Primeira Aula</div>
      <div class="cp-achievement__description">Complete sua primeira aula</div>
    </div>
    <div class="cp-achievement">
      <div class="cp-achievement__icon cp-achievement__icon--silver">📚</div>
      <div class="cp-achievement__title">Dedicado</div>
      <div class="cp-achievement__description">Complete 10 aulas</div>
    </div>
    <div class="cp-achievement">
      <div class="cp-achievement__icon cp-achievement__icon--gold">⭐</div>
      <div class="cp-achievement__title">Mestre</div>
      <div class="cp-achievement__description">Complete um curso inteiro</div>
    </div>
    <div class="cp-achievement">
      <div class="cp-achievement__icon cp-achievement__icon--diamond">💎</div>
      <div class="cp-achievement__title">Lenda</div>
      <div class="cp-achievement__description">Complete todos os cursos</div>
    </div>
    <div class="cp-achievement">
      <div class="cp-achievement__icon cp-achievement__icon--locked">🔒</div>
      <div class="cp-achievement__title">???</div>
      <div class="cp-achievement__description">Conquista secreta</div>
    </div>
  </div>

  <h3>Leaderboard</h3>
  <div class="ds-preview" style="max-width:500px;">
    <div class="cp-leaderboard">
      <div class="cp-leaderboard__item">
        <div class="cp-leaderboard__rank cp-leaderboard__rank--1">1</div>
        <span>Ana Silva</span>
        <span class="cp-leaderboard__xp">2,450 XP</span>
      </div>
      <div class="cp-leaderboard__item">
        <div class="cp-leaderboard__rank cp-leaderboard__rank--2">2</div>
        <span>Carlos Lima</span>
        <span class="cp-leaderboard__xp">2,180 XP</span>
      </div>
      <div class="cp-leaderboard__item">
        <div class="cp-leaderboard__rank cp-leaderboard__rank--3">3</div>
        <span>Marina Costa</span>
        <span class="cp-leaderboard__xp">1,920 XP</span>
      </div>
      <div class="cp-leaderboard__item cp-leaderboard__item--me">
        <div class="cp-leaderboard__rank">4</div>
        <span><strong>Você</strong></span>
        <span class="cp-leaderboard__xp">1,250 XP</span>
      </div>
    </div>
  </div>

  <h3>Missões Diárias</h3>
  <div class="ds-preview" style="max-width:500px;display:flex;flex-direction:column;gap:var(--cp-space-3);">
    <div class="cp-mission">
      <div class="cp-mission__icon cp-mission__icon--xp">⚡</div>
      <div class="cp-mission__info">
        <div class="cp-mission__title">Ganhe 50 XP</div>
        <div class="cp-mission__progress-bar"><div class="cp-mission__progress-fill" style="width:60%;"></div></div>
      </div>
      <div class="cp-mission__reward">+10 XP</div>
    </div>
    <div class="cp-mission">
      <div class="cp-mission__icon cp-mission__icon--time">⏱️</div>
      <div class="cp-mission__info">
        <div class="cp-mission__title">Estude por 15 minutos</div>
        <div class="cp-mission__progress-bar"><div class="cp-mission__progress-fill" style="width:30%;"></div></div>
      </div>
      <div class="cp-mission__reward">+15 XP</div>
    </div>
    <div class="cp-mission cp-mission--completed">
      <div class="cp-mission__icon cp-mission__icon--lesson">✅</div>
      <div class="cp-mission__info">
        <div class="cp-mission__title">Complete 1 aula</div>
        <div class="cp-mission__progress-bar"><div class="cp-mission__progress-fill"></div></div>
      </div>
      <div class="cp-mission__reward">+20 XP</div>
    </div>
  </div>

  <h3>Indicador de Nível</h3>
  <div class="ds-preview ds-flex">
    <div class="cp-level-indicator">
      <div class="cp-level-indicator__badge">5</div>
      <div>
        <div style="font-weight:var(--cp-font-bold);">Nível 5</div>
        <div class="cp-level-indicator__xp-to-next">750 XP para o próximo nível</div>
      </div>
    </div>
  </div>
</section>
```

- [ ] **Step 7: Add animations section HTML**

```html
<section id="animations" class="ds-section">
  <h2>12. Animações</h2>
  <p class="desc">Clique nos botões para ver as animações ao vivo.</p>

  <div class="ds-preview ds-flex" style="gap:var(--cp-space-4);flex-wrap:wrap;">
    <button class="cp-btn cp-btn-primary cp-btn--sm" onclick="demoAnimation(this,'cp-animate-bounce-in')">Bounce In</button>
    <button class="cp-btn cp-btn-primary cp-btn--sm" onclick="demoAnimation(this,'cp-animate-pulse')">Pulse</button>
    <button class="cp-btn cp-btn-primary cp-btn--sm" onclick="demoAnimation(this,'cp-animate-shake')">Shake</button>
    <button class="cp-btn cp-btn-primary cp-btn--sm" onclick="demoAnimation(this,'cp-animate-glow')">Glow</button>
    <button class="cp-btn cp-btn-primary cp-btn--sm" onclick="demoAnimation(this,'cp-animate-float')">Float</button>
    <button class="cp-btn cp-btn-primary cp-btn--sm" onclick="demoAnimation(this,'cp-animate-spin')">Spin</button>
    <button class="cp-btn cp-btn-primary cp-btn--sm" onclick="demoAnimation(this,'cp-animate-star-burst')">Star Burst</button>
  </div>

  <div style="margin-top:var(--cp-space-6);">
    <h3>XP Fly-Up Demo</h3>
    <div class="ds-preview" style="position:relative;min-height:100px;">
      <button class="cp-btn cp-btn-success" onclick="demoXPFlyup(this)">Ganhar +50 XP</button>
    </div>
  </div>
</section>
```

Add JS for animation demos:

```javascript
function demoAnimation(btn, cls) {
  btn.classList.remove(cls);
  void btn.offsetWidth; // force reflow
  btn.classList.add(cls);
  btn.addEventListener('animationend', () => btn.classList.remove(cls), { once: true });
}

function demoXPFlyup(btn) {
  const flyup = document.createElement('div');
  flyup.textContent = '+50 XP';
  flyup.style.cssText = 'position:absolute;color:var(--cp-xp);font-weight:900;font-size:1.5rem;pointer-events:none;';
  flyup.classList.add('cp-animate-xp-flyup');
  btn.parentElement.appendChild(flyup);
  const rect = btn.getBoundingClientRect();
  const parentRect = btn.parentElement.getBoundingClientRect();
  flyup.style.left = (rect.left - parentRect.left + rect.width/2 - 30) + 'px';
  flyup.style.top = (rect.top - parentRect.top) + 'px';
  flyup.addEventListener('animationend', () => flyup.remove());
}
```

- [ ] **Step 8: Add loading states section**

```html
<section id="loading" class="ds-section">
  <h2>13. Loading States</h2>

  <h3>Spinner</h3>
  <div class="ds-preview ds-flex">
    <div class="cp-spinner cp-spinner--sm"></div>
    <div class="cp-spinner"></div>
    <div class="cp-spinner cp-spinner--lg"></div>
  </div>

  <h3>Skeleton</h3>
  <div class="ds-preview" style="max-width:400px;">
    <div style="display:flex;gap:var(--cp-space-3);margin-bottom:var(--cp-space-4);">
      <div class="cp-skeleton cp-skeleton--avatar"></div>
      <div style="flex:1;">
        <div class="cp-skeleton cp-skeleton--title"></div>
        <div class="cp-skeleton cp-skeleton--text"></div>
      </div>
    </div>
    <div class="cp-skeleton cp-skeleton--card"></div>
  </div>
</section>
```

- [ ] **Step 9: Add toasts section**

```html
<section id="toasts" class="ds-section">
  <h2>14. Toasts</h2>
  <p class="desc">Clique para ver exemplos de toast.</p>
  <div class="ds-preview ds-flex">
    <button class="cp-btn cp-btn-primary cp-btn--sm" onclick="showToast('info')">Info Toast</button>
    <button class="cp-btn cp-btn-success cp-btn--sm" onclick="showToast('success')">Success Toast</button>
    <button class="cp-btn cp-btn-danger cp-btn--sm" onclick="showToast('danger')">Danger Toast</button>
    <button class="cp-btn cp-btn--sm" style="background:var(--cp-xp);color:white;font-weight:700;box-shadow:0 4px 0 var(--cp-xp-700);" onclick="showToast('xp')">XP Toast</button>
  </div>
</section>

<!-- Toast container (fixed, always present) -->
<div class="cp-toast-container" id="toast-container"></div>
```

Add JS for toast demos:

```javascript
function showToast(type) {
  const messages = {
    info: 'Nova aula disponível no módulo de IA.',
    success: 'Aula concluída com sucesso!',
    danger: 'Erro ao salvar progresso.',
    xp: '+50 XP ganhos!'
  };
  const container = document.getElementById('toast-container');
  const toast = document.createElement('div');
  toast.className = 'cp-toast cp-toast--' + type;
  toast.innerHTML = `<span class="cp-toast__message">${messages[type]}</span><button class="cp-toast__close" onclick="this.parentElement.remove()">✕</button>`;
  container.appendChild(toast);
  setTimeout(() => { if (toast.parentElement) toast.remove(); }, 4000);
}
```

- [ ] **Step 10: Add gradients + layout section**

```html
<section id="gradients" class="ds-section">
  <h2>15. Gradientes & Fundos</h2>
  <div class="ds-preview" style="display:grid;grid-template-columns:1fr 1fr 1fr;gap:var(--cp-space-3);">
    <div class="cp-gradient-premium" style="height:100px;border-radius:var(--cp-radius-lg);display:flex;align-items:center;justify-content:center;color:white;font-weight:var(--cp-font-bold);font-size:var(--cp-text-sm);">Premium</div>
    <div class="cp-gradient-streak" style="height:100px;border-radius:var(--cp-radius-lg);display:flex;align-items:center;justify-content:center;color:white;font-weight:var(--cp-font-bold);font-size:var(--cp-text-sm);">Streak</div>
    <div class="cp-gradient-xp" style="height:100px;border-radius:var(--cp-radius-lg);display:flex;align-items:center;justify-content:center;color:white;font-weight:var(--cp-font-bold);font-size:var(--cp-text-sm);">XP</div>
    <div class="cp-gradient-levelup" style="height:100px;border-radius:var(--cp-radius-lg);display:flex;align-items:center;justify-content:center;color:white;font-weight:var(--cp-font-bold);font-size:var(--cp-text-sm);">Level Up</div>
    <div class="cp-pattern-dots" style="height:100px;border-radius:var(--cp-radius-lg);display:flex;align-items:center;justify-content:center;font-size:var(--cp-text-sm);color:var(--cp-text-muted);border:1px solid var(--cp-border-subtle);">Dots</div>
    <div class="cp-pattern-grid" style="height:100px;border-radius:var(--cp-radius-lg);display:flex;align-items:center;justify-content:center;font-size:var(--cp-text-sm);color:var(--cp-text-muted);border:1px solid var(--cp-border-subtle);">Grid</div>
  </div>
</section>

<section id="layout" class="ds-section">
  <h2>16. Layout</h2>
  <p class="desc">Layout principal: sidebar fixa (240px) + conteúdo com margin-left. Responsivo: sidebar vira drawer abaixo de 1024px.</p>
  <div class="ds-preview">
    <div style="border:1px solid var(--cp-border);border-radius:var(--cp-radius-md);overflow:hidden;height:200px;display:flex;">
      <div style="width:60px;background:var(--cp-bg-secondary);border-right:1px solid var(--cp-border-subtle);padding:var(--cp-space-2);font-size:10px;color:var(--cp-text-muted);">Sidebar</div>
      <div style="flex:1;padding:var(--cp-space-3);font-size:var(--cp-text-sm);color:var(--cp-text-secondary);">Main Content Area</div>
      <div style="width:80px;background:var(--cp-bg-secondary);border-left:1px solid var(--cp-border-subtle);padding:var(--cp-space-2);font-size:10px;color:var(--cp-text-muted);">Aside</div>
    </div>
  </div>
</section>
```

- [ ] **Step 11: Verify in browser**

Expected: All gamification components render. Animation demos work on click. Spinners animate. Skeletons pulse. Toasts appear and auto-dismiss. Gradients show vibrant colors. Everything works in both themes.

- [ ] **Step 12: Commit**

```bash
git add index.html
git commit -m "feat: add gamification, animations, loading, toasts, and gradients sections"
```

---

## Task 8: Markdown Download Feature

**Files:**
- Modify: `index.html` — implement the `downloadMarkdown()` function

The markdown file should contain the full design system spec — all tokens, all CSS, all component definitions — so another agent can read it and reproduce the design system. We generate this from the existing spec document content, embedded as a JS string.

- [ ] **Step 1: Implement `downloadMarkdown()` function**

Replace the placeholder `downloadMarkdown` function in the `<script>` section. The spec content must be embedded safely — it contains backticks and `${` sequences that would break template literals. Use a hidden `<script type="text/plain">` block to hold the markdown:

**In the HTML body (before closing `</body>`):**
```html
<script type="text/plain" id="markdown-content">
[PASTE FULL SPEC CONTENT HERE — raw text, no escaping needed]
</script>
```

Read the full content of `docs/superpowers/specs/2026-03-23-classplay-design-system.md` and paste it verbatim inside this `<script type="text/plain">` tag. No escaping is needed because `type="text/plain"` prevents the browser from parsing it as JS.

**The only character that needs escaping is `</script>` if it appears in the content** (unlikely in a markdown spec). If found, replace with `<\/script>`.

**In the JS:**
```javascript
function downloadMarkdown() {
  const md = document.getElementById('markdown-content').textContent;
  const blob = new Blob([md], { type: 'text/markdown' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = 'classplay-design-system.md';
  a.click();
  URL.revokeObjectURL(url);
}
```

- [ ] **Step 2: Verify in browser**

Click "Download .md" button. Expected: Browser downloads `classplay-design-system.md`. Open the file — it should contain the complete design system spec, identical to the source.

- [ ] **Step 3: Commit**

```bash
git add index.html
git commit -m "feat: add markdown download with full spec content"
```

---

## Task 9: Final Polish + Browser Test

**Files:**
- Modify: `index.html` — final visual tweaks

- [ ] **Step 1: Visual review in browser**

Open `index.html` in browser. Check each section visually in BOTH themes (dark and light):
- All swatches render and copy works
- Typography renders at all sizes
- Spacing bars are proportional
- All button states work (hover, active, disabled)
- Forms focus/error states work
- Cards hover effects work
- Badges are colorful
- Progress bars show gradients
- All gamification components render
- Animation demos work
- Spinners spin, skeletons pulse
- Toasts appear and dismiss
- Gradients are vibrant
- Sidebar navigation scrollspy works
- Theme toggle persists on reload
- Markdown download works

- [ ] **Step 2: Fix any visual issues found**

Address any misalignments, missing styles, or broken interactions found during review.

- [ ] **Step 3: Add .gitignore for .superpowers**

```
# .gitignore
.superpowers/
```

- [ ] **Step 4: Final commit**

```bash
git add index.html .gitignore
git commit -m "feat: final polish and visual review pass"
```

---

## Summary

| Task | What it builds | Sections covered |
|---|---|---|
| 1 | HTML shell, CSS tokens, theme toggle, page layout | Spec 1-5 (tokens), 12 (z-index), 13 (page structure) |
| 2 | Color swatches with copy-to-clipboard | Spec 1.1-1.4 |
| 3 | Typography, spacing, radius, shadows previews | Spec 2-5 |
| 4 | All button variants + header styling | Spec 6.0-6.1 |
| 5 | Form components | Spec 6.2 |
| 6 | Cards, badges, progress, avatar, modal, tooltip | Spec 6.3-6.9 |
| 7 | Gamification, animations, confetti, loading, toasts, gradients, layout/responsive | Spec 7, 8 (incl. 8.5), 6.10-6.11, 9, 11 |
| 8 | Markdown download feature | Spec 13 (deliverable) |
| 9 | Final visual polish + browser test | All |
