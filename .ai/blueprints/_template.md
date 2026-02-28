# Blueprint: {{ModuleName}}

Version: 1.0
Estado: DRAFT | APPROVED | IMPLEMENTED
Planner: logan-planner
Fecha: {{YYYY-MM-DD}}

---

# 0. Objetivo del módulo

Descripción clara y concisa del propósito del módulo.

Debe responder:

* Qué resuelve
* Para quién es
* Qué permite hacer
* Qué NO hace

Ejemplo:

Este módulo permite gestionar productos dentro del sistema administrativo usando Filament v5.
Permite crear, editar, listar y eliminar productos.

No gestiona inventario ni órdenes.

---

# 1. Modelo

Archivo:
app/Models/{{Model}}.php

Tabla:
{{table}}

Responsabilidades:

* Representa {{concepto}}
* Define estructura de datos
* Define relaciones
* Define casts()

---

## 1.1 Campos

| Campo | Tipo | Nullable | Default | Descripción | Ejemplo |
| ----- | ---- | -------- | ------- | ----------- | ------- |

---

## 1.2 Relaciones

belongsTo:

| Relación | Modelo | FK | Descripción |

hasMany:

| Relación | Modelo | FK | Descripción |

belongsToMany:

| Relación | Modelo | Tabla pivote | Descripción |

---

## 1.3 Casts

| Campo | Tipo | Motivo |

---

# 2. Migración

Archivo:
database/migrations/{{timestamp}}*create*{{table}}_table.php

---

## 2.1 Columnas

| Columna | Tipo | Nullable | Default | Index | Unique | Notes |

---

## 2.2 Índices

| Nombre | Columnas | Tipo |

---

## 2.3 Constraints

| Tipo | Tabla relacionada | Columna |

---

# 3. Enum (si aplica)

Archivo:
app/Enums/{{Enum}}.php

Valores:

| Valor | Descripción |

Uso:

| Campo | Motivo |

---

# 4. Policy

Archivo:
app/Policies/{{Model}}Policy.php

Métodos:

| Método  | Descripción |
| ------- | ----------- |
| viewAny |             |
| view    |             |
| create  |             |
| update  |             |
| delete  |             |

---

# 5. Filament Resource

Archivo:
app/Filament/Resources/{{Model}}Resource.php

Panel:
app/Providers/Filament/AdminPanelProvider.php

Registrado:
Sí / No

Navigation:

| Propiedad | Valor |
| --------- | ----- |
| Icon      |       |
| Group     |       |
| Sort      |       |

---

# 6. Form Schema

Archivo:
app/Filament/Resources/{{Model}}Resource.php

---

## 6.1 Layout

Section: Información general

| Campo | Componente | Required | Validation | Reactive | Disabled |

---

# 7. Table Schema

Archivo:
app/Filament/Resources/{{Model}}Resource.php

---

## 7.1 Columnas

| Campo | Columna | Sortable | Searchable | Toggleable |

---

## 7.2 Filtros

| Nombre | Tipo | Campo |

---

## 7.3 Acciones

Fila:

| Acción | Clase |

Tabla:

| Acción | Clase |

---

# 8. Pages

Archivos:

app/Filament/Resources/{{Model}}Resource/Pages/List{{Model}}.php
app/Filament/Resources/{{Model}}Resource/Pages/Create{{Model}}.php
app/Filament/Resources/{{Model}}Resource/Pages/Edit{{Model}}.php

---

# 9. Relation Managers (si aplica)

Archivo:
app/Filament/Resources/{{Model}}Resource/RelationManagers/{{Relation}}RelationManager.php

Relación:
{{relation}}

Columnas:

| Campo | Columna |

Form:

| Campo | Componente |

---

# 10. Factory

Archivo:
database/factories/{{Model}}Factory.php

Campos:

| Campo | Tipo |

---

# 11. Seeder (si aplica)

Archivo:
database/seeders/{{Model}}Seeder.php

---

# 12. Testing requerido

Archivo:
tests/Feature/Filament/{{Model}}ResourceTest.php

Casos:

| Caso     | Descripción |
| -------- | ----------- |
| listar   |             |
| crear    |             |
| editar   |             |
| eliminar |             |

Validaciones:

| Campo | Regla |

---

# 13. Dependencias

Modelos:

| Modelo | Motivo |

Resources:

| Resource | Motivo |

Enums:

| Enum | Motivo |

---

# 14. Seguridad

Policy aplicada:
Sí / No

Campos protegidos:

| Campo | Motivo |

---

# 15. Diagrama

Entidad principal:

{{Model}}

Relaciones:

{{Model}}
├── belongsTo {{Related}}
└── hasMany {{Related}}

---

# 16. Checklist de integridad

| Regla              | Estado |
| ------------------ | ------ |
| Modelo definido    | ✔      |
| Migración definida | ✔      |
| Resource definido  | ✔      |
| Forms definidos    | ✔      |
| Table definida     | ✔      |
| Policy definida    | ✔      |
| Tests definidos    | ✔      |

---

# 17. Información faltante

Lista de preguntas pendientes.

Si esta sección no está vacía → Estado = DRAFT

---

# 18. Estado final

DRAFT
APPROVED
IMPLEMENTED

---

# 19. Historial de cambios

| Versión | Fecha | Cambio |
| ------- | ----- | ------ |

---

# FIN DEL BLUEPRINT
