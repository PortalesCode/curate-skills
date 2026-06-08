---
name: frontend-design-from-farmage
description: Use when designing and implementing UI components, layouts, design systems, or responsive interfaces. Covers accessibility, CSS/Tailwind patterns, component architecture, and design-to-code workflows. Trigger terms: UI design, component design, design system, accessibility, Tailwind CSS, responsive layout, CSS architecture, animations.
license: MIT
compatibility: opencode
metadata:
  author: farmage/opencode-skills (adapted)
  version: "1.0.0"
  domain: frontend
  triggers: UI design, design system, Tailwind, CSS, accessibility, responsive, layout, animations, styling
  role: specialist
  scope: implementation
  output-format: code
  related-skills: react-expert, vue-expert, design-system, accessibility-reviewer
---

# Frontend Design

Expert in UI/UX implementation, design systems, and production-grade CSS architecture.

## When to Use This Skill

- Building or extending a design system
- Implementing responsive layouts and components
- Setting up Tailwind CSS configuration
- Ensuring WCAG accessibility compliance
- Creating animations and transitions
- Converting Figma/mockup designs to code

## Core Workflow

1. **Analyze requirements** — Identify layout structure, component hierarchy, design tokens
2. **Design system** — Define colors, typography, spacing, breakpoints
3. **Implement components** — Build with semantic HTML + CSS/Tailwind
4. **Validate accessibility** — Check contrast, keyboard navigation, ARIA attributes
5. **Test responsive** — Verify all breakpoints, touch targets, and interactions
6. **Optimize** — Purge unused CSS, lazy load, reduce CLS

> **Checkpoint:** validate accessibility (axe/Lighthouse) before considering done.

## Key Patterns

### Design Tokens (Tailwind)

```css
@theme {
  --color-brand: #2563eb;
  --color-surface: #f8fafc;
  --radius-sm: 0.375rem;
  --radius-lg: 0.75rem;
  --font-display: "Inter", system-ui, sans-serif;
}
```

### Responsive Component Pattern

```tsx
function Card({ title, children }: CardProps) {
  return (
    <article className="grid gap-4 p-6 @md:flex @md:p-8 @lg:p-12 rounded-xl shadow-sm">
      <h2 className="text-lg @md:text-xl font-semibold">{title}</h2>
      <div className="prose max-w-none">{children}</div>
    </article>
  );
}
```

### Accessible Button with States

```tsx
function Button({ variant = "primary", disabled, children }: ButtonProps) {
  return (
    <button
      className={clsx(
        "inline-flex items-center justify-center rounded-md px-4 py-2 text-sm font-medium transition-colors",
        "focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-600",
        "disabled:pointer-events-none disabled:opacity-50",
        variant === "primary" && "bg-blue-600 text-white hover:bg-blue-700 active:bg-blue-800",
        variant === "ghost" && "bg-transparent hover:bg-gray-100 active:bg-gray-200"
      )}
      disabled={disabled}
      aria-disabled={disabled}
    >
      {children}
    </button>
  );
}
```

## Constraints

### MUST DO
- Use semantic HTML elements (`<nav>`, `<main>`, `<aside>`, etc.)
- Ensure minimum contrast ratio (4.5:1 normal text, 3:1 large)
- Support keyboard navigation (Tab, Enter, Escape)
- Use `prefers-reduced-motion` for animations
- Add `alt` text to all images

### MUST NOT DO
- Use divs for everything (no semantic structure)
- Hardcode colors or spacing (use design tokens)
- Skip focus indicators
- Use px for responsive layouts (use rem/em)
- Ignore touch target sizes (minimum 44×44px)

## Reference Guide

| Topic | Reference | Load When |
|-------|-----------|-----------|
| Tailwind Config | `references/tailwind-config.md` | Setting up or extending theme |
| Accessibility | `references/accessibility.md` | WCAG compliance, ARIA patterns |
| Animations | `references/animations.md` | CSS animations, transitions, keyframes |
| Responsive | `references/responsive.md` | Breakpoints, container queries, layout |
| Design Tokens | `references/design-tokens.md` | Color, typography, spacing systems |

## Knowledge Reference

Tailwind CSS v4, CSS container queries, WCAG 2.2, design tokens, responsive design, CSS Grid, Flexbox, accessibility (ARIA), animations, design systems
