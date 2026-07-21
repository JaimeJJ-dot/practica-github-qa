# Casos de Prueba – Historia 5: Dashboard Analítico

---

## TC-009 | Caso Positivo – Visualización correcta del Dashboard con datos reales

| Campo | Detalle |
|-------|---------|
| **ID** | TC-009 |
| **Historia relacionada** | HU-05 – Dashboard Analítico |
| **Título** | Dashboard carga correctamente con KPIs y gráficos actualizados |
| **Tipo** | Positivo (flujo normal) |

### Objetivo
Validar que el Dashboard muestra correctamente los KPIs de total de plantas y humedad promedio, el gráfico de barras por etapa y el gráfico de torta por distribución geográfica, con datos calculados en tiempo real desde la base de datos.

### Precondiciones
- El usuario ha iniciado sesión con rol **Admin**.
- Existen al menos **10 plantas registradas** en la base de datos con etapas y ubicaciones distintas.
- El módulo de Dashboard está accesible desde la barra de navegación.

### Datos de Prueba
| Campo | Valor de referencia esperado |
|-------|------------------------------|
| Total de plantas en BD | `65` (según datos del sistema) |
| Humedad promedio esperada | `58.65 %` |
| Etapas con datos | Crecimiento, Floración, Germinación, Madurez, Producción |
| Parroquias con datos | Parque La Carolina, El Inca, Miraflores, La Floresta, entre otras |

### Pasos
1. Iniciar sesión con cuenta de administrador.
2. Ser redirigido automáticamente al **Dashboard del Huerto** o hacer clic en "Dashboard" en el menú.
3. Observar el panel superior con los KPIs.
4. Verificar el valor de **"Total Plantas"**.
5. Verificar el valor de **"Humedad Promedio"**.
6. Verificar que el **gráfico de barras** muestra datos agrupados por etapa.
7. Verificar que el **gráfico de torta** muestra la distribución por parroquia.

### Resultado Esperado
- El KPI **"Total Plantas"** muestra el número exacto de registros en la base de datos.
- El KPI **"Humedad Promedio"** muestra el porcentaje calculado correctamente.
- El **gráfico de barras** muestra una barra por cada etapa activa con su conteo correcto.
- El **gráfico de torta** muestra segmentos para cada parroquia con plantas registradas.
- El botón **"Exportar Dashboard a PDF"** es visible en la parte superior del dashboard.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla del dashboard tras la ejecución._

---

## TC-010 | Caso Negativo – Acceso al Dashboard sin sesión activa

| Campo | Detalle |
|-------|---------|
| **ID** | TC-010 |
| **Historia relacionada** | HU-05 – Dashboard Analítico |
| **Título** | Acceso denegado al Dashboard sin autenticación |
| **Tipo** | Negativo (flujo alterno) |

### Objetivo
Validar que el sistema impide el acceso directo al Dashboard a usuarios no autenticados, redirigiendo automáticamente a la pantalla de inicio de sesión sin mostrar ningún dato del huerto.

### Precondiciones
- No existe ninguna sesión activa en el navegador.
- El sistema está en funcionamiento y accesible.
- El usuario conoce la URL directa del Dashboard.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| URL de acceso directo | `/Dashboard` o `/Dashboard/Index` |
| Estado de sesión | Sin sesión activa |
| Cookies | Sin cookie de sesión válida |

### Pasos
1. Abrir el navegador en modo normal (sin sesión iniciada) o cerrar sesión si hubiera una activa.
2. Escribir directamente en la barra de direcciones la URL: `[dominio]/Dashboard`.
3. Presionar Enter para navegar a esa URL.
4. Observar el comportamiento del sistema.

### Resultado Esperado
- El sistema detecta que no hay sesión activa (`Session['UsuarioID']` está vacío).
- El sistema **no muestra** el contenido del Dashboard.
- El usuario es redirigido automáticamente a la pantalla de **inicio de sesión**.
- En la pantalla de login puede aparecer un mensaje informativo (ej: *"Debe iniciar sesión para acceder"*).
- Al presionar el botón "Atrás" del navegador, el sistema no permite el acceso al Dashboard.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla o logs de redirección tras la ejecución._
