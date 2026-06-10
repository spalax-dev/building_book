---
id: BKB-P001
title: Plan de Proyecto - Building Book
version: 0.4.0
status: pending
author: building-book-team
created: 2026-06-09
updated: 2026-06-09
tags:
  - plan
  - sdd
---

# Plan del Proyecto: Building Book

## Visión general

Building Book es un **Framework AI Harness SDD** (Specification-Driven Development) que proporciona trazabilidad completa entre especificaciones, diagramas y código. Opera como CLI standalone y servidor web local con live reload.

## Estructura del proyecto

!["Project Structure"](../diagrams/filetree.svg)

## Arquitectura

Arquitectura por capas:

```
Infraestructura → Negocio ← Presentación
```

### Presentación

Capa de comunicación: CLI, Web, API.

### Dominio

Lógica de negocio: interfaces y abstracciones, solo Java.

### Infraestructura

Comunicación con librerías y datos.

La inyección de dependencias conecta infraestructura con negocio.

## Procesos

### BKB-001: CLI

Comandos `bbook build`, `bbook open`, `bbook plan`. Punto de entrada con Picoli/GraalVM.

**Actividades:**
- BKB-002: Comando build
- BKB-003: Comando open
- BKB-004: Comando plan

### BKB-005: Web Server

HTTP server embebido con live reload, file watcher y WebSocket.

**Actividades:**
- BKB-006: HTTP Server
- BKB-007: File Watcher
- BKB-008: WebSocket Handler

### BKB-009: Core

Lógica de negocio: estados, rendering, tracking. Java 25 + PlantUML.

**Actividades:**
- BKB-010: Config Loader
- BKB-011: State Manager
- BKB-012: PlantUML Renderer

## Tracking

El archivo [status.yml](../status.yml) contiene el detalle de procesos, actividades y tareas con su estado actual.

## Decisiones clave (ADRs)

- [ADR-001](adrs/ADR-001.md): CLI con Picoli + GraalVM
- [ADR-002](adrs/ADR-002.md): Diagramas en formato .puml embebidos
- [ADR-003](adrs/ADR-003.md): Integración con opencode
- [ADR-004](adrs/ADR-004.md): Rendering markdown con commonmark-java
- [ADR-005](adrs/ADR-005.md): Templates HTML con Pebble
- [ADR-006](adrs/ADR-006.md): Arquitectura por capas (Presentación → Dominio ← Infraestructura)
- [ADR-007](adrs/ADR-007.md): AI Harness SDD (StageEnforcer, TestFirstEnforcer)

## Integración con opencode

El proyecto incluye configuración en `.opencode/` para activar el workflow SDD en agentes.

### agents.md

Define el comportamiento del agente SDD.

### rules.md

Define reglas de documentación específicas del framework.

## Changelog

Ver [CHANGELOG.log](../CHANGELOG.log)