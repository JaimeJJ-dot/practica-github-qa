# Historia de Usuario #4 – Búsqueda Inteligente de Cuidados (API REST)

## Información General

| Campo | Detalle |
|-------|---------|
| **ID** | HU-04 |
| **Módulo** | Búsqueda / API REST |
| **Prioridad** | Media |
| **Estimación** | 4 puntos de historia |

---

## Historia de Usuario

**Como** voluntario o agricultor del huerto,  
**quiero** buscar una planta por su nombre y obtener los cuidados recomendados para cada etapa de su ciclo de vida,  
**para** saber exactamente qué acciones tomar (riego, fertilización, control de plagas) en el momento adecuado sin depender de conocimiento oral.

---

## Flujo Guiado

1. El usuario accede al módulo **"Buscar cuidados por planta"**.
2. Escribe el nombre de la planta en el campo de búsqueda (ej: "Sandía", "Tomate Cherry").
3. Presiona el botón **"Consultar"**.
4. El sistema realiza una consulta a la API REST interna con filtros por especie.
5. Se muestra una tabla con las etapas del ciclo de vida: Siembra, Germinación, Crecimiento, Floración, Fructificación/Producción, con la semana de inicio y los cuidados recomendados para cada una.
6. El usuario puede presionar **"Buscar otra planta"** para iniciar una nueva consulta o **"Volver al inicio"** para regresar al dashboard.

---

## Criterios de Aceptación

### 01: Campo de búsqueda disponible
- **Dado que** el usuario accede al módulo de búsqueda,
- **cuando** carga la vista,
- **entonces** se muestra un campo de texto con el placeholder de ejemplo (ej. "Sandía") y el botón "Consultar".

### 02: Resultados de cuidados por etapa
- **Dado que** el usuario escribe el nombre de una planta registrada en el sistema,
- **cuando** presiona "Consultar",
- **entonces** la API devuelve y la vista muestra una tabla con columnas: Etapa, Semana de Inicio y Cuidados Recomendados, con una fila por cada etapa del ciclo.

### 03: Filtros dinámicos por especie, etapa y ubicación
- **Dado que** la API soporta parámetros de consulta,
- **cuando** se realiza una petición con filtros específicos (especie, etapa, ubicación),
- **entonces** el endpoint retorna únicamente los registros que coinciden con los filtros aplicados.

### 04: Planta no encontrada
- **Dado que** el usuario busca un nombre de planta que no existe en el sistema,
- **cuando** la API no encuentra registros,
- **entonces** la vista muestra un mensaje informativo indicando que no se encontraron resultados para esa especie.

### 05: Respuesta en formato JSON desde el endpoint
- **Dado que** una aplicación externa realiza una petición GET al endpoint de la API,
- **cuando** incluye el nombre de la planta como parámetro,
- **entonces** el sistema responde con un JSON que contiene los campos: `planta`, `etapa` y `cuidados`.

### 06: Prevención de inyección SQL
- **Dado que** un usuario malicioso intenta inyectar SQL en el campo de búsqueda,
- **cuando** el sistema procesa la consulta,
- **entonces** la entrada es sanitizada mediante consultas parametrizadas y no se ejecuta código SQL arbitrario.

### 07: Opción de nueva búsqueda
- **Dado que** se muestran los resultados de una consulta,
- **cuando** el usuario presiona "Buscar otra planta",
- **entonces** el formulario se limpia y queda listo para una nueva búsqueda.


