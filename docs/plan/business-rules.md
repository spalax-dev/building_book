---
id: BKB-BR001
title: Reglas de Negocio - Building Book
version: 0.1.0
status: pending
---

# Reglas de Negocio - Building Book

- BR-001: Las reglas de negocio deben ser atómicas.
- BR-002: Todo proyecto debe tener `building-book.yml` en la raíz.
- BR-003: Los documentos tienen estado `pending`, `accepted` o `needs-work`.
- BR-004: `pending` transiciona a `accepted` o `needs-work`.
- BR-005: `accepted` solo transiciona a `needs-work`.
- BR-006: `needs-work` transiciona a `pending` o `accepted`.
- BR-007: Para avanzar de fase, todos los artefactos deben estar `accepted`.
- BR-008: `status.yml` es manipulado por el sistema, no por el usuario.
- BR-009: El usuario marca tareas completadas en frontmatter y el sistema actualiza `status.yml`.
- BR-010: Los IDs tienen formato `<CODE>-<NUM>` con NUM secuencial desde `001`.
- BR-011: `CODE` se define en `building-book.yml` bajo `project.idPrefix`.
- BR-012: Los IDs no se reutilizan aunque el elemento sea eliminado.
- BR-013: El framework es reconocido por opencode cuando existe `.opencode/agents.md`.
- BR-014: Los diagramas se crean en formato `.puml` y renderizan a SVG en `diagrams/`.
- BR-015: Los diagramas se incrustan con `![alt](ruta.svg)`.
- BR-016: Todo `.md` en `docs/` debe tener frontmatter con `id`, `title`, `version`, `status`, `author`, `created`, `updated`.
- BR-017: `bbook build` inicializa la estructura de documentación.
- BR-018: `bbook open` inicia el servidor web.
- BR-019: `bbook plan` muestra el estado de procesos y actividades.
- BR-020: El servidor detecta cambios en `.md` y `.puml` y actualiza el navegador automáticamente.
- BR-021: Si el JAR de PlantUML no existe, se descarga automáticamente.