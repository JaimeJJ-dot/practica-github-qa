# Historia de Usuario #7 – Exportación de Reportes PDF

## Información General

| Campo | Detalle |
|-------|---------|
| **ID** | HU-07 |
| **Módulo** | Reportes / Exportación |
| **Prioridad** | Media |
| **Estimación** | 3 puntos de historia |

---

## Historia de Usuario

**Como** administrador del huerto comunitario,  
**quiero** poder generar y descargar reportes en formato PDF desde el listado de plantas y desde el dashboard,  
**para** compartir información oficial con autoridades, coordinadores o miembros de la comunidad que no tienen acceso al sistema.

---

## Flujo Guiado

1. El administrador accede al **listado de plantas** o al **Dashboard**.
2. Presiona el botón **"Exportar a PDF"** (rojo) visible en la vista.
3. El sistema genera el reporte en el servidor de forma inmediata ("on-the-fly").
4. El archivo PDF se descarga automáticamente en el dispositivo del usuario.
5. El reporte incluye:
   - **Desde el listado:** encabezado institucional, tabla con todas las plantas (Especie, Etapa, Responsable, Ubicación, Humedad, Fecha de Riego) y fecha de generación.
   - **Desde el dashboard:** KPIs (total de plantas, humedad promedio), plantas por etapa con cantidades y plantas por ubicación/parroquia con cantidades.

---

## Criterios de Aceptación

### 01: Botón de exportar visible en el listado de plantas
- **Dado que** el administrador está en el módulo de plantas,
- **cuando** la vista carga,
- **entonces** se muestra el botón "Exportar a PDF" claramente visible en la interfaz.

### 02: Generación inmediata del PDF
- **Dado que** el administrador presiona el botón "Exportar a PDF",
- **cuando** el servidor procesa la solicitud,
- **entonces** el archivo PDF se genera en el servidor de forma inmediata y comienza la descarga sin recargar la página.

### 03: Contenido correcto en el reporte del listado
- **Dado que** se generó el PDF desde el módulo de plantas,
- **cuando** el usuario abre el archivo,
- **entonces** el reporte contiene: encabezado institucional ("Huerto Comunitario"), tabla estructurada con todos los registros visibles y la fecha de generación al pie.

### 04: Contenido correcto en el reporte del dashboard
- **Dado que** se generó el PDF desde el dashboard,
- **cuando** el usuario abre el archivo,
- **entonces** el reporte contiene: total de plantas, humedad promedio, tabla de plantas por etapa con cantidades y tabla de plantas por parroquia/ubicación con cantidades.

### 05: Formato oficial con encabezado institucional
- **Dado que** el PDF es descargado,
- **cuando** el usuario lo revisa,
- **entonces** el documento incluye encabezados institucionales estructurados y tablas formateadas, aptas para presentación oficial.

### 06: Portabilidad del archivo generado
- **Dado que** el PDF fue descargado,
- **cuando** el usuario lo comparte con una autoridad o coordinador externo,
- **entonces** el archivo puede abrirse en cualquier visor de PDF estándar sin requerir acceso al sistema.

### 07: Fecha de generación incluida en el reporte
- **Dado que** el PDF es generado,
- **cuando** se incluye el pie de página,
- **entonces** el reporte muestra la fecha y hora exacta de su generación (ej: "Generado el 28/1/2026 – Huerto Comunitario").

