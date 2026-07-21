# Casos de Prueba – Historia 4: Búsqueda Inteligente de Cuidados (API REST)

---

## TC-007 | Caso Positivo – Búsqueda exitosa de cuidados por especie

| Campo | Detalle |
|-------|---------|
| **ID** | TC-007 |
| **Historia relacionada** | HU-04 – Búsqueda Inteligente de Cuidados (API REST) |
| **Título** | Consulta exitosa de cuidados para una planta registrada |
| **Tipo** | Positivo (flujo normal) |

### Objetivo
Validar que el sistema devuelve correctamente la guía de cuidados por etapa de crecimiento cuando el usuario busca una planta que existe en la base de datos, mostrando la tabla con todas sus etapas, semana de inicio y cuidados recomendados.

### Precondiciones
- El usuario ha iniciado sesión en el sistema.
- La planta **"Sandía"** está registrada en la base de datos con datos de cuidados por etapa.
- El módulo de **"Buscar cuidados por planta"** está accesible.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Nombre de la planta | `Sandía` |
| Endpoint consultado | `GET /api/plantas/cuidados?especie=Sandia` |

### Pasos
1. Iniciar sesión en el sistema.
2. Acceder al módulo **"Buscar cuidados por planta"**.
3. En el campo de búsqueda, ingresar el nombre: `Sandía`.
4. Presionar el botón **"Consultar"**.
5. Observar los resultados devueltos por la API.
6. Verificar que la tabla muestra las etapas completas del ciclo de vida.

### Resultado Esperado
- La API responde con los datos de cuidados de la planta **Sandía**.
- Se muestra una tabla con las siguientes columnas: **Etapa**, **Semana Inicio**, **Cuidados Recomendados**.
- Las etapas incluidas son: Siembra, Germinación, Crecimiento, Floración, Fructificación.
- Los datos de la tabla coinciden con los registrados en la base de datos.
- Se muestran los botones **"Volver al inicio"** y **"Buscar otra planta"**.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla o logs de respuesta JSON tras la ejecución._

---

## TC-008 | Caso Negativo – Búsqueda de planta inexistente en el sistema

| Campo | Detalle |
|-------|---------|
| **ID** | TC-008 |
| **Historia relacionada** | HU-04 – Búsqueda Inteligente de Cuidados (API REST) |
| **Título** | Búsqueda sin resultados para planta no registrada |
| **Tipo** | Negativo (flujo alterno) |

### Objetivo
Validar que el sistema responde de forma adecuada cuando el usuario busca una planta que no existe en la base de datos, mostrando un mensaje informativo claro en lugar de un error técnico o pantalla en blanco.

### Precondiciones
- El usuario ha iniciado sesión en el sistema.
- La planta **"Durian"** no existe en la base de datos del sistema.
- El módulo de **"Buscar cuidados por planta"** está accesible.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Nombre de la planta | `Durian` ← _no registrada_ |
| Endpoint consultado | `GET /api/plantas/cuidados?especie=Durian` |

### Pasos
1. Iniciar sesión en el sistema.
2. Acceder al módulo **"Buscar cuidados por planta"**.
3. En el campo de búsqueda, ingresar el nombre: `Durian`.
4. Presionar el botón **"Consultar"**.
5. Observar el comportamiento del sistema y la respuesta de la API.

### Resultado Esperado
- La API no encuentra registros para la especie **"Durian"**.
- El sistema **no muestra** un error 500 ni una pantalla en blanco.
- Se despliega un mensaje informativo al usuario (ej: *"No se encontraron resultados para la planta 'Durian'"*).
- La interfaz mantiene el botón **"Buscar otra planta"** disponible para intentar una nueva consulta.
- No se expone ningún mensaje técnico interno ni stack trace al usuario.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla o logs de respuesta JSON tras la ejecución._
