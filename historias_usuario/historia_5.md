# Historia de Usuario #5 – Dashboard Analítico

## Información General

| Campo | Detalle |
|-------|---------|
| **ID** | HU-05 |
| **Módulo** | Dashboard / Reportes |
| **Prioridad** | Alta |
| **Estimación** | 4 puntos de historia |

---

## Historia de Usuario

**Como** administrador del huerto comunitario,  
**quiero** ver un dashboard con indicadores clave, gráficos de plantas por etapa y distribución geográfica por parroquia,  
**para** tomar decisiones informadas sobre el estado general del huerto, identificar alertas (como falta de riego) y detectar tendencias de cultivo rápidamente.

---

## Flujo Guiado

1. El administrador inicia sesión y es redirigido automáticamente al **Dashboard del Huerto**.
2. La página muestra en la parte superior dos KPIs inmediatos:
   - **Total de Plantas** registradas en el sistema.
   - **Humedad Promedio** (en %) calculada de todos los registros.
3. Debajo se presentan dos gráficos en tiempo real:
   - **Gráfico de barras:** cantidad de plantas agrupadas por etapa (Crecimiento, Floración, Germinación, Madurez, Producción).
   - **Gráfico de torta:** distribución de plantas por parroquia/ubicación geográfica.
4. El administrador puede identificar visualmente qué etapas concentran más plantas y qué parroquias tienen mayor actividad.
5. Desde el dashboard puede presionar **"Exportar Dashboard a PDF"** para generar un reporte descargable.

---

## Criterios de Aceptación

### 01: KPI de total de plantas actualizado
- **Dado que** el administrador accede al dashboard,
- **cuando** la página carga,
- **entonces** se muestra el número total de plantas registradas en la base de datos, calculado en tiempo real.

### 02: KPI de humedad promedio
- **Dado que** existen registros de plantas con datos de humedad,
- **cuando** el dashboard carga,
- **entonces** se muestra el porcentaje promedio de humedad calculado del total de plantas registradas.

### 03: Gráfico de barras por etapa
- **Dado que** el sistema tiene plantas en distintas etapas de crecimiento,
- **cuando** el dashboard renderiza los gráficos,
- **entonces** se muestra un gráfico de barras con el conteo de plantas para cada etapa: Germinación, Crecimiento, Floración, Madurez y Producción.

### 04: Gráfico de torta por distribución geográfica
- **Dado que** las plantas tienen asignada una parroquia/ubicación,
- **cuando** el dashboard carga,
- **entonces** se muestra un gráfico de torta que representa el porcentaje de plantas por cada parroquia de Quito.

### 05: Identificación rápida de alertas
- **Dado que** el administrador revisa el dashboard,
- **cuando** detecta una etapa con muy pocas plantas o una parroquia sin actividad,
- **entonces** los gráficos permiten identificar visualmente esa anomalía (ej. alerta de falta de riego).

### 06: Acceso restringido por rol
- **Dado que** un usuario con rol "User" inicia sesión,
- **cuando** intenta acceder al dashboard,
- **entonces** el sistema muestra solo la información permitida para su rol, ocultando controles administrativos.

### 07: Botón de exportar a PDF disponible
- **Dado que** el administrador visualiza el dashboard,
- **cuando** presiona el botón "Exportar Dashboard a PDF",
- **entonces** el sistema genera y descarga un archivo PDF con el resumen del dashboard (KPIs, plantas por etapa y distribución geográfica).

