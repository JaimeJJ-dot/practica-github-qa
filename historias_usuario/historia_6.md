# Historia de Usuario #6 – Geolocalización y Mapas

## Información General

| Campo | Detalle |
|-------|---------|
| **ID** | HU-06 |
| **Módulo** | Geolocalización / Mapas |
| **Prioridad** | Media |
| **Estimación** | 3 puntos de historia |

---

## Historia de Usuario

**Como** miembro de la comunidad o administrador del sistema,  
**quiero** visualizar en un mapa interactivo la ubicación de todos los huertos comunitarios activos en Quito,  
**para** conocer la red de huertos existentes, identificar zonas de cobertura y facilitar la coordinación territorial entre voluntarios y responsables.

---

## Flujo Guiado

1. El usuario accede a la sección de **"Ubicación de los Huertos"** desde el menú o desde la vista general del sistema.
2. Se carga un mapa interactivo de Quito (integrado con Leaflet.js y OpenStreetMap).
3. El mapa muestra **marcadores dinámicos** (puntos azules) en cada parroquia donde existe al menos un huerto registrado.
4. El usuario puede hacer zoom, desplazarse y explorar el mapa libremente.
5. Al hacer clic en un marcador, se muestra información básica del huerto: nombre de la parroquia o ubicación.
6. El usuario puede identificar visualmente qué sectores de Quito tienen mayor concentración de huertos.

---

## Criterios de Aceptación

### 01: Mapa interactivo carga correctamente
- **Dado que** el usuario accede a la sección de mapas,
- **cuando** la vista se renderiza,
- **entonces** se muestra un mapa de Quito centrado en la ciudad, con controles de zoom (+/-) funcionales.

### 02: Marcadores dinámicos desde base de datos
- **Dado que** existen plantas y huertos registrados con ubicación (parroquia),
- **cuando** el mapa carga,
- **entonces** se colocan marcadores dinámicos en las coordenadas correspondientes a cada parroquia con huertos activos.

### 03: Información al hacer clic en marcador
- **Dado que** el usuario hace clic en un marcador del mapa,
- **cuando** se dispara el evento de clic,
- **entonces** aparece un popup o tooltip con información del huerto (nombre de ubicación o parroquia).

### 04: Navegación libre por el mapa
- **Dado que** el mapa está cargado,
- **cuando** el usuario arrastra el mapa o usa los controles de zoom,
- **entonces** el mapa responde fluidamente permitiendo explorar diferentes zonas de Quito.

### 05: Marcadores actualizados al agregar nuevos huertos
- **Dado que** el administrador registra una nueva planta con una ubicación nueva,
- **cuando** accede nuevamente al mapa,
- **entonces** el marcador correspondiente a esa nueva parroquia aparece en el mapa sin necesidad de intervención manual.

### 06: Vista responsiva del mapa
- **Dado que** el usuario accede desde un dispositivo móvil (teléfono o tablet),
- **cuando** carga el mapa,
- **entonces** el mapa se adapta al tamaño de pantalla y sigue siendo funcional e interactivo.

### 07: Transparencia comunitaria
- **Dado que** cualquier miembro de la comunidad accede al sistema,
- **cuando** consulta el mapa,
- **entonces** puede identificar visualmente toda la red de huertos comunitarios de Quito sin necesidad de tener rol de administrador.
