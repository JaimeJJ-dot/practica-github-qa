# 🌱 Sistema Web para Gestión de Huertos Comunitarios

## Descripción del Proyecto

**Huertos Urbanos Digitales** es un sistema web desarrollado en arquitectura MVC que digitaliza y centraliza la gestión agrícola urbana de huertos comunitarios en Quito. Permite registrar plantas, hacer seguimiento de etapas de cultivo, visualizar datos en un dashboard analítico, ubicar huertos en un mapa interactivo y consultar guías de cuidados por especie, todo desde una plataforma accesible, responsiva y segura.

---

## Funcionalidades Principales

Cada funcionalidad sigue un flujo guiado orientado al usuario:

1. **Registro de usuario:** Crear cuenta con nombre, correo electrónico y contraseña para acceder al sistema de gestión.
2. **Inicio de sesión:** Acceso seguro con validación de credenciales contra base de datos, hashing de contraseñas y gestión de sesión con roles (Admin / User).
3. **Gestión CRUD de plantas:** Registrar, consultar, editar y eliminar especies con sus datos de etapa, responsable, ubicación, humedad y fecha de riego.
4. **Búsqueda inteligente de cuidados:** Buscar una planta por nombre y obtener la guía de cuidados recomendados por etapa de crecimiento a través de la API REST.
5. **Dashboard analítico:** Visualizar KPIs del huerto (total de plantas, humedad promedio), gráficos de barras por etapa y distribución geográfica por parroquia.
6. **Geolocalización y mapas:** Ver la ubicación de todos los huertos comunitarios de Quito en un mapa interactivo con marcadores dinámicos (Leaflet / OpenStreetMap).
7. **Exportación de reportes PDF:** Generar y descargar reportes en formato PDF con datos del listado de plantas y el resumen del dashboard.
8. **Accesibilidad e inclusión digital (WCAG):** Ajuste de tamaño de fuente, alto contraste, modo oscuro/claro y lectura automática Text-to-Speech para adultos mayores.

---

## Estructura del Repositorio

```
historias_usuario/
│
├── historia_1.md       → Registro de usuario
├── historia_2.md       → Inicio de sesión con roles
├── historia_3.md       → Gestión CRUD de plantas
├── historia_4.md       → Búsqueda inteligente de cuidados (API REST)
├── historia_5.md       → Dashboard analítico
├── historia_6.md       → Geolocalización y mapas
├── historia_7.md       → Exportación de reportes PDF
├── historia_8.md       → Accesibilidad e inclusión digital (WCAG)
└── README.md           → Este archivo
```

