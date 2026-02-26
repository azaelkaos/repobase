# Contributing Guidelines (Enterprise Mode)

Este proyecto utiliza una arquitectura Blueprint-Driven estricta.

El incumplimiento de estas reglas resultará en el rechazo automático del Pull Request.

---

# 1. Principio Arquitectónico Fundamental

La arquitectura está protegida por Blueprint.

Si un cambio afecta:

- Modelos
- Migraciones
- Relaciones
- Filament Resources
- Formularios
- Tablas
- Policies

ENTONCES requiere actualización de Blueprint.

No hay excepciones.

---

# 2. Clasificación Oficial de Cambios

Todos los cambios deben pertenecer a una de estas categorías:

## A) Arquitectura (Requiere Blueprint)

Incluye:

- Nuevos módulos
- Nuevas tablas
- Nuevas columnas
- Nuevas relaciones
- Modificaciones estructurales
- Nuevos Resources de Filament
- Cambios en Forms o Tables

Proceso obligatorio:

1. Crear o actualizar:
   docs/blueprints/{Module}.md

2. Validar Blueprint (logan-guardian)

3. Implementar código (logan-builder)

4. Crear tests (logan-tester)

Pull Request será rechazado si:
- Se detectan cambios en app/Models sin Blueprint actualizado
- Se detectan nuevas migraciones sin Blueprint
- Se detectan cambios en Resources sin Blueprint

---

## B) Configuración (No requiere Blueprint)

Incluye:

- config/*
- routes/*
- bootstrap/*
- .env.example
- composer.json
- Service Providers
- Cambios de infraestructura

Requiere:

- Commit claro
- Justificación en Pull Request

---

## C) Fixes

Correcciones de bugs sin alterar estructura.

Formato:

fix(scope): description

Ejemplo:

fix(product): correct price casting

---

## D) Refactor

Mejoras internas sin cambiar comportamiento externo.

Formato:

refactor(scope): description

---

# 3. Protección Automática (Recomendado en CI)

El pipeline debe bloquear PR si:

- Se modifica:
  app/Models/*
  database/migrations/*
  app/Filament/Resources/*

Y NO existe cambio en:

  docs/blueprints/*

Esta validación puede implementarse en GitHub Actions.

---

# 4. Convención Obligatoria de Commits

Formato:

type(scope): description

Tipos permitidos:

- blueprint
- migration
- model
- resource
- policy
- test
- config
- fix
- refactor
- docs

Ejemplos válidos:

blueprint(product): define product module
migration(product): create products table
model(product): add casts
resource(product): implement form schema
config(app): change timezone to UTC
fix(order): correct total calculation
refactor(user): simplify relationship loading

Commits inválidos:

- "update stuff"
- "changes"
- "fix"
- "wip"

Serán rechazados en revisión.

---

# 5. Reglas de Pull Request

Todo cambio debe hacerse vía Pull Request.

Nunca hacer push directo a main.

El Pull Request debe:

- Explicar el propósito
- Especificar tipo de cambio
- Confirmar si requiere Blueprint
- Confirmar que tests pasan
- Confirmar revisión manual

Template obligatorio en:
.github/pull_request_template.md

---

# 6. Prohibiciones Absolutas

Nunca:

- Modificar vendor
- Alterar migraciones ya ejecutadas en producción
- Crear columnas no documentadas
- Crear relaciones no planificadas
- Introducir lógica de negocio en Resource
- Mezclar múltiples módulos en un mismo PR

---

# 7. Separación de Pull Requests

Un PR debe contener solo:

- Un módulo
- O una mejora
- O un fix

Nunca mezclar:

- Nueva feature + refactor
- Migración + config unrelated
- Dos módulos distintos

---

# 8. Flujo Oficial del Proyecto

Para arquitectura:

planner → guardian → builder → tester → PR → review → merge

Para config/fix:

branch → commit → PR → review → merge

---

# 9. Estructura Oficial del Proyecto

docs/
  blueprints/

app/
  Models/
  Filament/
  Policies/

database/
  migrations/

Cualquier cambio estructural fuera de este patrón será revisado.

---

# 10. Objetivo

Estas reglas existen para garantizar:

- Consistencia arquitectónica
- Escalabilidad
- Seguridad
- Mantenibilidad a largo plazo
- Trazabilidad total

Si tienes dudas sobre si un cambio requiere Blueprint:

Asume que SÍ lo requiere.

