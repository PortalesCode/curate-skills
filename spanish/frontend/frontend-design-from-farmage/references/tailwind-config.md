# Guía de Configuración Tailwind CSS v4

## Extensión del tema

```css
@import "tailwindcss";

@theme {
  /* Colores de marca */
  --color-brand-50: #eff6ff;
  --color-brand-100: #dbeafe;
  --color-brand-500: #3b82f6;
  --color-brand-900: #1e3a5f;

  /* Colores de superficie */
  --color-surface: #ffffff;
  --color-surface-muted: #f8fafc;

  /* Tipografía */
  --font-sans: "Inter", system-ui, sans-serif;
  --font-mono: "JetBrains Mono", monospace;

  /* Espaciado */
  --spacing-page: 2rem;

  /* Radio de borde */
  --radius-sm: 0.375rem;
  --radius-md: 0.5rem;
  --radius-lg: 0.75rem;

  /* Breakpoints (container queries) */
  --breakpoint-sm: 640px;
  --breakpoint-md: 768px;
  --breakpoint-lg: 1024px;
}
```

## Utilidades clave

- `@container` — container queries para componentes responsivos
- `@starting-style` — animaciones de entrada
- `@media (prefers-reduced-motion: no-preference)` — animaciones respetuosas
