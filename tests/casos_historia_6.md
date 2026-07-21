# Casos de Prueba – Historia 6: Geolocalización y Mapas

---

## TC-011 | Caso Positivo – Visualización correcta del mapa con marcadores activos

| Campo | Detalle |
|-------|---------|
| **ID** | TC-011 |
| **Historia relacionada** | HU-06 – Geolocalización y Mapas |
| **Título** | Mapa interactivo carga con marcadores dinámicos de los huertos |
| **Tipo** | Positivo (flujo normal) |

### Objetivo
Validar que el mapa interactivo de Quito carga correctamente con Leaflet/OpenStreetMap, que los marcadores dinámicos se generan desde la base de datos para cada parroquia con huertos registrados, y que al hacer clic en un marcador se muestra información del huerto.

### Precondiciones
- El usuario ha iniciado sesión en el sistema.
- Existen plantas registradas en la base de datos con ubicaciones asignadas a diferentes parroquias de Quito.
- El dispositivo tiene conexión a internet (para cargar los tiles de OpenStreetMap).
- La sección de **"Ubicación de los Huertos"** está accesible.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Parroquias con plantas | Parque La Carolina, El Inca, Miraflores, La Floresta, Cotocollao |
| Número mínimo de marcadores esperados | `5` |
| Nivel de zoom inicial | Centrado en Quito |

### Pasos
1. Iniciar sesión en el sistema.
2. Navegar a la sección **"Ubicación de los Huertos"** desde el menú o vista general.
3. Observar que el mapa de Quito carga correctamente con los controles de zoom (+/-).
4. Verificar que aparecen marcadores azules en las parroquias con huertos registrados.
5. Hacer clic en uno de los marcadores.
6. Usar los controles de zoom para acercar y alejar el mapa.
7. Arrastrar el mapa para explorar diferentes zonas.

### Resultado Esperado
- El mapa de Quito se renderiza correctamente centrado en la ciudad.
- Los controles de zoom (+/-) son funcionales.
- Los marcadores dinámicos (puntos azules) aparecen en cada parroquia con huertos activos.
- Al hacer clic en un marcador, se muestra un popup con información del huerto (nombre de la parroquia/ubicación).
- El mapa responde fluidamente al arrastre y al zoom.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla del mapa tras la ejecución._

---

## TC-012 | Caso Negativo – Mapa sin conexión a internet (tiles no disponibles)

| Campo | Detalle |
|-------|---------|
| **ID** | TC-012 |
| **Historia relacionada** | HU-06 – Geolocalización y Mapas |
| **Título** | Comportamiento del mapa sin conexión a internet |
| **Tipo** | Negativo (flujo alterno) |

### Objetivo
Validar el comportamiento del sistema cuando no hay conexión a internet y los tiles del mapa de OpenStreetMap no pueden cargarse, verificando que el sistema no genere un error crítico y que los marcadores de datos propios sigan siendo accesibles o se muestre un mensaje adecuado.

### Precondiciones
- El usuario ha iniciado sesión en el sistema.
- El dispositivo **no tiene conexión a internet** o la conexión a OpenStreetMap está bloqueada.
- Existen plantas registradas en la base de datos con ubicaciones asignadas.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Estado de red | Sin conexión a internet o red bloqueada |
| URL de tiles | `https://tile.openstreetmap.org/{z}/{x}/{y}.png` ← _inaccesible_ |

### Pasos
1. Iniciar sesión en el sistema con conexión a internet activa.
2. Desactivar la conexión a internet en el dispositivo (modo avión o desconectar red).
3. Navegar a la sección **"Ubicación de los Huertos"**.
4. Observar el comportamiento del mapa sin tiles disponibles.
5. Verificar si los marcadores de datos propios siguen apareciendo.
6. Observar si el sistema muestra algún mensaje de error al usuario.

### Resultado Esperado
- El mapa no puede cargar los tiles de OpenStreetMap (fondo gris o cuadrícula vacía).
- El sistema **no genera un error crítico** ni una pantalla de error 500.
- Los marcadores dinámicos generados desde la base de datos propia siguen siendo visibles (o al menos no causan un crash).
- Se muestra un mensaje o indicador que comunica al usuario que el mapa de fondo no está disponible.
- El resto del sistema (menú, navegación) sigue funcionando con normalidad.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla del comportamiento sin conexión tras la ejecución._
