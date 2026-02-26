# Pull Request: Implementación de módulo

---

# 📋 Información general

## Tipo de cambio

Marca una opción:

* [ ] blueprint
* [ ] migration
* [ ] model
* [ ] filament resource
* [ ] policy
* [ ] test
* [ ] refactor
* [ ] fix
* [ ] documentation

---

## Nombre del módulo

<!-- Ejemplo: Product -->

```
{MODULE_NAME}
```

---

# 📐 Blueprint

## Archivo Blueprint

<!-- Ruta obligatoria -->

```
docs/blueprints/{MODULE_NAME}.md
```

---

## Estado del Blueprint

* [ ] Existe
* [ ] Aprobado por logan-guardian
* [ ] No fue modificado fuera del flujo planner

---

# 🧱 Cambios implementados

Marca lo que aplique:

## Base de datos

* [ ] Migration creada
* [ ] Migration sigue Blueprint exactamente

Ruta:

```
database/migrations/
```

---

## Modelo

* [ ] Modelo creado o actualizado
* [ ] casts() implementado correctamente
* [ ] Relaciones correctas
* [ ] Sin lógica no definida en Blueprint

Ruta:

```
app/Models/
```

---

## Filament Resource

* [ ] Resource creado
* [ ] Form schema sigue Blueprint
* [ ] Table schema sigue Blueprint
* [ ] Namespaces correctos (Filament v5)
* [ ] Sin lógica inventada

Ruta:

```
app/Filament/Resources/
```

---

## Policy

* [ ] Policy creada o actualizada
* [ ] Permisos siguen Blueprint

Ruta:

```
app/Policies/
```

---

## Tests

* [ ] Tests creados
* [ ] Tests pasan correctamente
* [ ] Tests siguen Blueprint
* [ ] No testean lógica inexistente

Ruta:

```
tests/Feature/
```

---

# 🔍 Validación arquitectónica

Validado con:

* [ ] logan-planner
* [ ] logan-builder
* [ ] logan-guardian
* [ ] logan-tester

---

# 🛡️ Verificación de integridad

Confirmo que:

* [ ] No se modificó `/vendor`
* [ ] No se cambió arquitectura fuera del Blueprint
* [ ] No se agregaron campos no definidos
* [ ] No se agregaron relaciones no definidas
* [ ] Compatible con Laravel 12
* [ ] Compatible con Filament v5

---

# 📂 Archivos afectados

Lista principal:

```
app/Models/
app/Filament/Resources/
database/migrations/
tests/Feature/
docs/blueprints/
```

---

# 🧪 Cómo probar manualmente

Pasos:

1. Ejecutar migraciones

```
php artisan migrate
```

2. Acceder a Filament

```
/admin
```

3. Verificar:

* crear registro
* editar registro
* eliminar registro
* listar registros

---

# 📸 Evidencia visual (opcional)

Agregar screenshots si aplica.

---

# ⚠️ Riesgo de cambio

Seleccionar uno:

* [ ] Bajo
* [ ] Medio
* [ ] Alto

Justificación:

```
{DESCRIBE}
```

---

# 🧹 Refactor

* [ ] No aplica
* [ ] Incluido
* [ ] Validado con logan-refactor

---

# ✅ Checklist final obligatorio

Confirmo que:

* [ ] El Blueprint existe
* [ ] El Blueprint fue aprobado
* [ ] El código sigue el Blueprint
* [ ] El código fue auditado
* [ ] Los tests pasan
* [ ] El PR está listo para merge

---

# 🧠 Notas adicionales

Agregar contexto adicional si es necesario.

---

# 🚀 Aprobación

Reviewer debe validar:

* [ ] Blueprint correcto
* [ ] Implementación correcta
* [ ] Tests correctos
* [ ] Arquitectura intacta

---

# Resultado esperado

Este PR implementa el módulo siguiendo estrictamente el Blueprint aprobado y las reglas de arquitectura establecidas.
