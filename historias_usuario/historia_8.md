# Historia de Usuario #8 – Accesibilidad e Inclusión Digital (WCAG)

## Información General

| Campo | Detalle |
|-------|---------|
| **ID** | HU-08 |
| **Módulo** | Experiencia de Usuario / Accesibilidad |
| **Prioridad** | Media |
| **Estimación** | 3 puntos de historia |

---

## Historia de Usuario

**Como** adulto mayor o voluntario con dificultades visuales o de lectura,  
**quiero** poder ajustar el tamaño de texto, activar alto contraste, cambiar entre modo oscuro y claro, y escuchar la lectura automática de los cuidados de las plantas,  
**para** gestionar el huerto de forma independiente sin depender de ayuda externa y sin barreras digitales.

---

## Flujo Guiado

1. El usuario accede al sistema desde cualquier dispositivo.
2. En la barra de accesibilidad visible en todas las vistas, encuentra los controles:
   - **A+** y **A-**: aumentar o reducir el tamaño de la fuente.
   - **Contraste**: activar modo de alto contraste (texto negro sobre fondo amarillo o blanco sobre negro).
   - **Leer**: iniciar la lectura Text-to-Speech del contenido visible en pantalla.
   - **Detener**: detener la lectura de voz en curso.
3. El usuario activa el **modo oscuro/claro** desde el ícono de palanca en la barra de navegación.
4. La preferencia de tema (oscuro/claro) queda guardada en **LocalStorage** y persiste entre sesiones.
5. En dispositivos móviles o tablets, la interfaz se adapta automáticamente con diseño responsivo (Bootstrap 5).

---

## Criterios de Aceptación

### 01: Barra de accesibilidad visible en todas las vistas
- **Dado que** el usuario accede a cualquier pantalla del sistema,
- **cuando** la vista carga,
- **entonces** la barra de accesibilidad con los controles A+, A-, Contraste, Leer y Detener es visible y funcional.

### 02: Ajuste de tamaño de fuente
- **Dado que** el usuario tiene dificultad para leer texto pequeño,
- **cuando** presiona el botón "A+" repetidamente,
- **entonces** el tamaño de fuente de toda la interfaz aumenta de forma progresiva; con "A-" disminuye.

### 03: Modo de alto contraste
- **Dado que** el usuario activa el botón "Contraste",
- **cuando** se aplica el modo,
- **entonces** la interfaz cambia a una paleta de alto contraste que mejora la legibilidad para personas con baja visión.

### 04: Lectura Text-to-Speech del contenido
- **Dado que** el usuario no puede leer el contenido en pantalla,
- **cuando** presiona el botón "🔊 Leer",
- **entonces** el sistema inicia la lectura en voz alta del texto visible en la vista actual (cuidados de plantas u otro contenido relevante).

### 05: Detener lectura en cualquier momento
- **Dado que** la lectura de voz está activa,
- **cuando** el usuario presiona el botón "⏹ Detener",
- **entonces** la reproducción de voz se detiene inmediatamente.

### 06: Modo oscuro/claro con persistencia
- **Dado que** el usuario activa el modo oscuro desde la barra de navegación,
- **cuando** cierra el navegador y regresa al sistema,
- **entonces** el sistema recuerda la preferencia guardada en LocalStorage y aplica el mismo tema automáticamente.

### 07: Diseño responsivo en dispositivos móviles
- **Dado que** el voluntario accede al sistema desde su teléfono en el campo,
- **cuando** la interfaz carga en pantalla pequeña,
- **entonces** el diseño se adapta correctamente con Bootstrap 5 sin perder funcionalidad ni legibilidad.

### 08: Autonomía para adultos mayores
- **Dado que** un adulto mayor con movilidad reducida o baja visión utiliza el sistema,
- **cuando** combina los controles de accesibilidad disponibles (fuente grande + alto contraste + Text-to-Speech),
- **entonces** puede gestionar sus plantas del huerto de forma completamente independiente.

