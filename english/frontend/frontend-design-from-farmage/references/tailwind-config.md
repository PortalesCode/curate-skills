# Tailwind CSS v4 Configuration Guide

## Theme Extension

```css
@import "tailwindcss";

@theme {
  /* Brand colors */
  --color-brand-50: #eff6ff;
  --color-brand-100: #dbeafe;
  --color-brand-500: #3b82f6;
  --color-brand-900: #1e3a5f;

  /* Surface colors */
  --color-surface: #ffffff;
  --color-surface-muted: #f8fafc;

  /* Typography */
  --font-sans: "Inter", system-ui, sans-serif;
  --font-mono: "JetBrains Mono", monospace;

  /* Spacing */
  --spacing-page: 2rem;

  /* Border radius */
  --radius-sm: 0.375rem;
  --radius-md: 0.5rem;
  --radius-lg: 0.75rem;

  /* Breakpoints (container queries) */
  --breakpoint-sm: 640px;
  --breakpoint-md: 768px;
  --breakpoint-lg: 1024px;
}
```

## Key Utilities

- `@container` — container queries for responsive components
- `@starting-style` — entry animations
- `@media (prefers-reduced-motion: no-preference)` — respectful animations
