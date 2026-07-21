# Casos de Prueba – Historia 8: Accesibilidad e Inclusión Digital (WCAG)

---

## TC-015 | Caso Positivo – Activación exitosa de Text-to-Speech en la vista de cuidados

| Campo | Detalle |
|-------|---------|
| **ID** | TC-015 |
| **Historia relacionada** | HU-08 – Accesibilidad e Inclusión Digital (WCAG) |
| **Título** | Lectura automática Text-to-Speech funciona correctamente en pantalla de cuidados |
| **Tipo** | Positivo (flujo normal) |

### Objetivo
Validar que la función Text-to-Speech lee en voz alta el contenido visible en la pantalla de cuidados de plantas cuando el usuario presiona el botón "🔊 Leer", y que se detiene correctamente al presionar "⏹ Detener", permitiendo a adultos mayores o personas con dificultades visuales usar el sistema de forma autónoma.

### Precondiciones
- El usuario ha iniciado sesión en el sistema.
- El navegador utilizado soporta la **Web Speech API** (Chrome, Edge o Firefox actualizados).
- El dispositivo tiene altavoces o auriculares conectados con volumen activado.
- La barra de accesibilidad está visible en la interfaz.
- Se ha realizado una búsqueda previa y se muestra la tabla de cuidados de la planta **"Sandía"**.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Navegador | Google Chrome (versión actual) |
| Volumen del dispositivo | Activado al 70% |
| Pantalla activa | Vista de cuidados de "Sandía" |
| Idioma del sistema | Español |

### Pasos
1. Iniciar sesión en el sistema.
2. Navegar al módulo **"Buscar cuidados por planta"** y buscar la planta **"Sandía"**.
3. Verificar que la tabla de cuidados por etapa está visible en pantalla.
4. Localizar la barra de accesibilidad en la interfaz.
5. Presionar el botón **"🔊 Leer"**.
6. Escuchar que el sistema inicia la lectura en voz alta del contenido visible.
7. Presionar el botón **"⏹ Detener"** mientras la lectura está activa.
8. Verificar que la lectura se detiene de inmediato.

### Resultado Esperado
- Al presionar **"🔊 Leer"**, el sistema inicia inmediatamente la lectura en voz alta del contenido de la tabla de cuidados visible en pantalla.
- La voz es comprensible y en idioma español.
- Al presionar **"⏹ Detener"**, la lectura se interrumpe de forma inmediata.
- No se producen errores en la consola del navegador relacionados con la Web Speech API.
- La funcionalidad es usable de forma autónoma sin asistencia externa.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla y/o grabación de audio/video de la funcionalidad tras la ejecución._

---

## TC-016 | Caso Negativo – Text-to-Speech en navegador sin soporte para Web Speech API

| Campo | Detalle |
|-------|---------|
| **ID** | TC-016 |
| **Historia relacionada** | HU-08 – Accesibilidad e Inclusión Digital (WCAG) |
| **Título** | Comportamiento del sistema cuando el navegador no soporta Text-to-Speech |
| **Tipo** | Negativo (flujo alterno) |

### Objetivo
Validar que el sistema maneja correctamente el caso en que el navegador del usuario no soporta la Web Speech API, evitando que se muestre un error técnico y comunicando al usuario de forma clara que la función de lectura no está disponible en su entorno.

### Precondiciones
- El usuario ha iniciado sesión en el sistema.
- El navegador utilizado **no soporta** la Web Speech API (ej: Internet Explorer 11, versiones antiguas de navegadores).
- La barra de accesibilidad está visible en la interfaz.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Navegador | Internet Explorer 11 o navegador sin soporte de Web Speech API |
| `window.speechSynthesis` | `undefined` ← _no disponible_ |
| Pantalla activa | Cualquier vista del sistema |

### Pasos
1. Abrir el sistema en un navegador que **no soporte** la Web Speech API (ej: IE11 o simular con DevTools deshabilitando `speechSynthesis`).
2. Iniciar sesión en el sistema.
3. Localizar la barra de accesibilidad con el botón **"🔊 Leer"**.
4. Presionar el botón **"🔊 Leer"**.
5. Observar el comportamiento del sistema y revisar la consola del navegador.

### Resultado Esperado
- El sistema detecta que `window.speechSynthesis` no está disponible en el navegador.
- **No se produce un error crítico** ni se rompe la interfaz del usuario.
- Se muestra un mensaje informativo al usuario indicando que la función de lectura no está disponible en su navegador (ej: *"La función de lectura no está disponible en este navegador. Por favor use Chrome o Edge"*).
- El resto de controles de accesibilidad (A+, A-, Contraste, modo oscuro) **siguen funcionando** correctamente.
- No se expone ningún error técnico en la interfaz visible al usuario.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla del mensaje de error y logs de consola tras la ejecución._
