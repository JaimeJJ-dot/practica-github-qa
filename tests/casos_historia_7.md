# Casos de Prueba – Historia 7: Exportación de Reportes PDF

---

## TC-013 | Caso Positivo – Generación y descarga exitosa del reporte PDF del Dashboard

| Campo | Detalle |
|-------|---------|
| **ID** | TC-013 |
| **Historia relacionada** | HU-07 – Exportación de Reportes PDF |
| **Título** | Exportación exitosa del reporte PDF desde el Dashboard |
| **Tipo** | Positivo (flujo normal) |

### Objetivo
Validar que el administrador puede generar y descargar correctamente un reporte PDF desde el Dashboard, que el archivo contiene los KPIs, la tabla de plantas por etapa, la tabla de plantas por parroquia, el encabezado institucional y la fecha de generación.

### Precondiciones
- El usuario ha iniciado sesión con rol **Admin**.
- Existen plantas registradas en la base de datos con distintas etapas y ubicaciones.
- El Dashboard está cargado y visible con datos actualizados.
- El navegador permite descargas de archivos.

### Datos de Prueba
| Campo | Valor esperado en el PDF |
|-------|--------------------------|
| Total plantas en reporte | `65` |
| Humedad promedio en reporte | `58.65%` |
| Encabezado institucional | `"Dashboard Resumido - Huerto Comunitario"` |
| Fecha de generación | `28/1/2026 – Huerto Comunitario` |
| Formato del archivo | `.pdf` |

### Pasos
1. Iniciar sesión con cuenta de administrador.
2. Acceder al **Dashboard del Huerto**.
3. Verificar que los datos del dashboard están cargados correctamente.
4. Presionar el botón **"Exportar Dashboard a PDF"** (botón rojo en la parte superior).
5. Esperar a que el servidor genere el archivo.
6. Verificar que el archivo PDF se descarga automáticamente.
7. Abrir el archivo PDF descargado y revisar su contenido.

### Resultado Esperado
- El servidor genera el PDF de forma inmediata ("on-the-fly") sin recargar la página.
- El archivo PDF se descarga automáticamente en el dispositivo con nombre descriptivo.
- El documento contiene:
  - Encabezado institucional: *"Dashboard Resumido - Huerto Comunitario"*
  - KPI: Total de plantas con su valor numérico.
  - KPI: Humedad promedio en porcentaje.
  - Tabla **"Plantas por etapa"** con columnas: Etapa | Cantidad.
  - Tabla **"Plantas por ubicación"** con columnas: Ubicación | Cantidad.
  - Pie de página con la fecha exacta de generación.
- El archivo se abre correctamente en cualquier visor de PDF estándar.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas del PDF generado y logs del servidor tras la ejecución._

---

## TC-014 | Caso Negativo – Exportación PDF sin datos registrados en el sistema

| Campo | Detalle |
|-------|---------|
| **ID** | TC-014 |
| **Historia relacionada** | HU-07 – Exportación de Reportes PDF |
| **Título** | Exportación PDF cuando no hay plantas registradas en el sistema |
| **Tipo** | Negativo (flujo alterno) |

### Objetivo
Validar el comportamiento del sistema cuando el administrador intenta exportar el reporte PDF del Dashboard en un estado donde no existen plantas registradas, verificando que el sistema no genere un error crítico y que el PDF resultante comunique correctamente el estado vacío.

### Precondiciones
- El usuario ha iniciado sesión con rol **Admin**.
- La base de datos de plantas está **vacía** (0 registros).
- El Dashboard muestra **Total Plantas: 0** y **Humedad Promedio: 0%**.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Total plantas en BD | `0` ← _sin registros_ |
| Humedad promedio | `0.00 %` |
| Estado de tablas | Vacías |

### Pasos
1. Iniciar sesión con cuenta de administrador en un entorno con la base de datos vacía.
2. Acceder al **Dashboard del Huerto**.
3. Verificar que el Dashboard muestra **"Total Plantas: 0"** y **"Humedad Promedio: 0%"**.
4. Presionar el botón **"Exportar Dashboard a PDF"**.
5. Esperar la respuesta del servidor.
6. Si se descarga un archivo, abrirlo y revisar su contenido.

### Resultado Esperado
- El sistema **no genera un error 500** ni una excepción no controlada.
- El servidor responde de una de estas dos formas aceptables:
  - **Opción A:** Genera y descarga un PDF con los valores en cero y tablas vacías, indicando que no hay datos disponibles.
  - **Opción B:** Muestra un mensaje informativo en el Dashboard indicando que no hay datos suficientes para generar el reporte.
- En ningún caso se expone al usuario un error técnico interno o stack trace.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas del comportamiento y/o del PDF generado tras la ejecución._
