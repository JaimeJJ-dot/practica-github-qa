# Historia de Usuario #3 – Gestión CRUD de Plantas

## Información General

| Campo | Detalle |
|-------|---------|
| **ID** | HU-03 |
| **Módulo** | Gestión de Datos (CRUD) |
| **Prioridad** | Alta |
| **Estimación** | 5 puntos de historia |

---

## Historia de Usuario

**Como** administrador del sistema,  
**quiero** poder registrar, consultar, editar y eliminar plantas del huerto comunitario,  
**para** mantener un inventario digital actualizado con información de especie, etapa de crecimiento, responsable, ubicación, humedad y fecha de riego.

---

## Flujo Guiado

1. El administrador inicia sesión y accede al módulo **"Plantas"** desde el menú de navegación.
2. Se muestra el **listado de plantas** con columnas: Especie, Etapa, Responsable, Ubicación, Humedad y Fecha de Riego.
3. El administrador puede:
   - **Crear:** Presionar "Nueva Planta", completar el formulario y guardar.
   - **Leer:** Ver el listado completo; usar el buscador por especie o responsable; filtrar por etapa.
   - **Editar:** Presionar el botón de edición (amarillo) en cualquier registro y modificar sus datos.
   - **Eliminar:** Presionar el botón de eliminación (rojo) y confirmar la acción.
4. Los cambios se reflejan inmediatamente en el listado y en el dashboard.

---

## Criterios de Aceptación

### 01: Registrar una nueva planta (Create)
- **Dado que** el administrador accede al formulario de nueva planta,
- **cuando** completa todos los campos obligatorios y presiona "Guardar",
- **entonces** el sistema persiste el registro en la base de datos y lo muestra en el listado.

### 02: Consultar y paginar listado de plantas (Read)
- **Dado que** el administrador accede al módulo de plantas,
- **cuando** la lista carga,
- **entonces** se muestran todas las plantas registradas en un listado paginado con columnas: Especie, Etapa, Responsable, Ubicación, Humedad y Fecha de Riego.

### 03: Buscar por especie o responsable
- **Dado que** el administrador escribe texto en el campo de búsqueda,
- **cuando** presiona "Buscar",
- **entonces** el listado se filtra mostrando solo registros que coincidan con la especie o el nombre del responsable.

### 04: Filtrar por etapa de crecimiento
- **Dado que** el administrador selecciona una etapa en el selector desplegable,
- **cuando** aplica el filtro,
- **entonces** el listado muestra únicamente las plantas en la etapa seleccionada (Germinación, Crecimiento, Floración, Madurez o Producción).

### 05: Editar un registro existente (Update)
- **Dado que** el administrador presiona el botón de edición de una planta,
- **cuando** modifica los datos y guarda los cambios,
- **entonces** el sistema actualiza el registro en la base de datos y refleja los cambios en el listado.

### 06: Eliminar un registro (Delete)
- **Dado que** el administrador presiona el botón de eliminación,
- **cuando** confirma la acción en el diálogo de confirmación,
- **entonces** el sistema elimina el registro (lógica o físicamente) y lo retira del listado.

### 07: Validación de datos al crear o editar
- **Dado que** el administrador intenta guardar un formulario con campos obligatorios vacíos o datos inválidos,
- **cuando** presiona "Guardar",
- **entonces** el sistema muestra mensajes de error de validación junto a cada campo sin guardar el registro.


