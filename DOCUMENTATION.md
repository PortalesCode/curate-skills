# 📦 Curate Skills — Documentación

Sistema de curación bilingüe de skills para OpenCode/OpenChamber.
Organizado por **idioma primero**, para evitar duplicados al escanear con OpenChamber.

## Estructura

```
curate_skills/
├── english/                        ← Catálogo completo en inglés
│   ├── frontend/                   ← Categorías
│   │   └── <skill-name>/           ← Skill individual
│   │       ├── description.md      ← Ficha rápida
│   │       ├── source.md           ← Trazabilidad (origen, versión, licencia)
│   │       ├── SKILL.md            ← Skill completa con frontmatter + body
│   │       └── references/         ← Documentación de referencia
│   ├── backend/
│   ├── datos/
│   ├── infra-devops/
│   ├── seguridad/
│   ├── testing/
│   ├── arquitectura/
│   ├── ml-ai/
│   └── herramientas/
└── spanish/                        ← Catálogo completo en español (misma estructura)
    └── ...
```

## Uso en OpenChamber

Cada carpeta de idioma es un **catálogo independiente**.
No hay duplicados porque cada skill aparece una sola vez por idioma.

| Catálogo | Ruta en OpenChamber |
|----------|-------------------|
| Skills en inglés | `curate_skills/english/` |
| Skills en español | `curate_skills/spanish/` |
| Frontend (inglés) | `curate_skills/english/frontend/` |
| Frontend (español) | `curate_skills/spanish/frontend/` |
| Y así con cada categoría... | |

## Reglas de curación

### SKILL.md
- Debe tener **frontmatter YAML** válido con `name` y `description`
- `name` debe ser único en kebab-case, 1-64 caracteres
- `description` debe ser específica (1-1024 caracteres)
- El body debe mantener el **mismo contenido** en ambas versiones, solo cambia el idioma

### Frontmatter template

```yaml
---
name: <skill-name>
description: <descripción clara en el idioma correspondiente>
license: MIT
compatibility: opencode
metadata:
  author: <fuente original>
  version: "1.0.0"
  domain: <categoría>
  triggers: <palabras clave separadas por coma>
  role: specialist
  scope: implementation
  related-skills: <skills relacionadas>
---
```

### description.md
- Ficha rápida de la skill: categoría, origen, qué cubre y skills relacionadas
- Sirve para identificar la skill de un vistazo sin abrir el SKILL.md

### source.md
- Trazabilidad completa: repositorio de origen, URL, licencia, proceso de adaptación
- Versión actual y versión original
- Notas sobre modificaciones realizadas respecto al original

### references/
- Archivos `.md` de referencia que se cargan bajo demanda
- Deben traducirse al mismo idioma que la skill
- Organizados por tema (ej: `authentication.md`, `testing.md`)

## Categorías disponibles

| Carpeta | Descripción |
|---------|-------------|
| `frontend/` | React, Vue, Next.js, Angular, diseño UI |
| `backend/` | FastAPI, NestJS, Django, Go, Rust, etc. |
| `datos/` | SQL, Postgres, Pandas, Spark, optimización |
| `infra-devops/` | Docker, K8s, Terraform, SRE, monitoreo |
| `seguridad/` | Code review de seguridad, guardian |
| `testing/` | Playwright, test-master, E2E |
| `arquitectura/` | Microservicios, GraphQL, API design |
| `ml-ai/` | ML pipelines, RAG, fine-tuning |
| `herramientas/` | CLI, MCP, debugging, legacy modernizer |

## Origen de skills

Las skills vienen de:
- **Repos externos** clonados en `repos_extern/`
- **Creación propia** desde cero
- **Adaptaciones** de skills existentes con mejoras propias

Siempre documentar el origen en `source.md` y en el metadata del `SKILL.md`.
