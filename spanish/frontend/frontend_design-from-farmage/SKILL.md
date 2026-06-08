---
name: frontend-design
description: Usar para diseñar e implementar componentes de UI, layouts, sistemas de diseño o interfaces responsivas. Cubre accesibilidad, patrones CSS/Tailwind, arquitectura de componentes y flujos de diseño a código. Términos de activación: diseño UI, diseño de componentes, sistema de diseño, accesibilidad, Tailwind CSS, layout responsive, arquitectura CSS, animaciones.
license: MIT
compatibility: opencode
metadata:
  author: farmage/opencode-skills (adaptada)
  version: "1.0.0"
  domain: frontend
  triggers: diseño UI, sistema de diseño, Tailwind, CSS, accesibilidad, responsive, layout, animaciones, estilos
  role: specialist
  scope: implementation
  output-format: code
  related-skills: react-expert, vue-expert, design-system, accessibility-reviewer
---

# Frontend Design

Experto en implementación de UI/UX, sistemas de diseño y arquitectura CSS de nivel producción.

## Cuándo usar esta skill

- Crear o extender un sistema de diseño
- Implementar layouts y componentes responsivos
- Configurar Tailwind CSS
- Asegurar cumplimiento de accesibilidad WCAG
- Crear animaciones y transiciones
- Convertir diseños de Figma/mockups a código

## Flujo de trabajo

1. **Analizar requisitos** — Identificar estructura del layout, jerarquía de componentes, tokens de diseño
2. **Sistema de diseño** — Definir colores, tipografía, espaciado, breakpoints
3. **Implementar componentes** — Construir con HTML semántico + CSS/Tailwind
4. **Validar accesibilidad** — Verificar contraste, navegación por teclado, atributos ARIA
5. **Probar responsive** — Verificar todos los breakpoints, objetivos táctiles e interacciones
6. **Optimizar** — Purgar CSS no usado, lazy load, reducir CLS

> **Checkpoint:** validar accesibilidad (axe/Lighthouse) antes de dar por terminado.

## Patrones clave

### Tokens de diseño (Tailwind)

```css
@theme {
  --color-brand: #2563eb;
  --color-surface: #f8fafc;
  --radius-sm: 0.375rem;
  --radius-lg: 0.75rem;
  --font-display: "Inter", system-ui, sans-serif;
}
```

### Patrón de componente responsive

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

### Botón accesible con estados

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

## Restricciones

### OBLIGATORIO
- Usar elementos HTML semánticos (`<nav>`, `<main>`, `<aside>`, etc.)
- Asegurar relación de contraste mínima (4.5:1 texto normal, 3:1 grande)
- Soportar navegación por teclado (Tab, Enter, Escape)
- Usar `prefers-reduced-motion` para animaciones
- Agregar texto `alt` a todas las imágenes

### PROHIBIDO
- Usar divs para todo (sin estructura semántica)
- Hardcodear colores o espaciado (usar tokens de diseño)
- Omitir indicadores de foco
- Usar px para layouts responsivos (usar rem/em)
- Ignorar tamaños de objetivo táctil (mínimo 44×44px)

## Guía de referencia

| Tema | Referencia | Cargar cuando |
|------|-----------|---------------|
| Config Tailwind | `references/tailwind-config.md` | Configurando o extendiendo el tema |
| Accesibilidad | `references/accessibility.md` | Cumplimiento WCAG, patrones ARIA |
| Animaciones | `references/animations.md` | Animaciones CSS, transiciones, keyframes |
| Responsive | `references/responsive.md` | Breakpoints, container queries, layout |
| Tokens de diseño | `references/design-tokens.md` | Sistemas de color, tipografía, espaciado |

## Referencia de conocimiento

Tailwind CSS v4, CSS container queries, WCAG 2.2, design tokens, diseño responsive, CSS Grid, Flexbox, accesibilidad (ARIA), animaciones, sistemas de diseño
