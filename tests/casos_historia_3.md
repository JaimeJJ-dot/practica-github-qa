# Casos de Prueba – Historia 3: Gestión CRUD de Plantas

---

## TC-005 | Caso Positivo – Registro exitoso de una nueva planta

| Campo | Detalle |
|-------|---------|
| **ID** | TC-005 |
| **Historia relacionada** | HU-03 – Gestión CRUD de Plantas |
| **Título** | Registro exitoso de una nueva planta con datos válidos |
| **Tipo** | Positivo (flujo normal) |

### Objetivo
Validar que un administrador puede registrar correctamente una nueva planta con todos sus datos obligatorios (especie, etapa, responsable, ubicación, humedad y fecha de riego) y que el registro aparece en el listado inmediatamente después de guardarse.

### Precondiciones
- El usuario ha iniciado sesión con rol **Admin**.
- El sistema está en funcionamiento y accesible.
- El módulo de **"Plantas"** está disponible en el menú de navegación.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Especie | `Tomate Cherry` |
| Etapa | `Germinación` |
| Responsable | `Ana Villalba` |
| Ubicación | `Guamaní` |
| Humedad | `52.00` |
| Fecha de Riego | `07/01/2025` |

### Pasos
1. Iniciar sesión con cuenta de administrador.
2. En el menú de navegación, hacer clic en **"Plantas"**.
3. Presionar el botón **"Nueva Planta"**.
4. Completar el formulario con los datos de prueba indicados.
5. Presionar el botón **"Guardar"**.
6. Observar el comportamiento del sistema y revisar el listado de plantas.

### Resultado Esperado
- El sistema valida todos los campos correctamente.
- El registro de `Tomate Cherry` se persiste en la base de datos.
- El listado de plantas se actualiza mostrando el nuevo registro con todos sus datos.
- El Dashboard refleja el incremento en el total de plantas.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla o logs tras la ejecución._

---

## TC-006 | Caso Negativo – Intento de registro con campos obligatorios vacíos

| Campo | Detalle |
|-------|---------|
| **ID** | TC-006 |
| **Historia relacionada** | HU-03 – Gestión CRUD de Plantas |
| **Título** | Registro rechazado por campos obligatorios vacíos |
| **Tipo** | Negativo (flujo alterno) |

### Objetivo
Validar que el sistema impide guardar una nueva planta cuando los campos obligatorios están vacíos, mostrando mensajes de error de validación junto a cada campo sin persistir ningún dato en la base de datos.

### Precondiciones
- El usuario ha iniciado sesión con rol **Admin**.
- El sistema está en funcionamiento y accesible.
- El administrador se encuentra en el formulario de **"Nueva Planta"**.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Especie | _(vacío)_ |
| Etapa | _(sin seleccionar)_ |
| Responsable | _(vacío)_ |
| Ubicación | _(vacío)_ |
| Humedad | _(vacío)_ |
| Fecha de Riego | _(vacío)_ |

### Pasos
1. Iniciar sesión con cuenta de administrador.
2. En el menú de navegación, hacer clic en **"Plantas"**.
3. Presionar el botón **"Nueva Planta"**.
4. Dejar todos los campos del formulario **en blanco**.
5. Presionar el botón **"Guardar"**.
6. Observar el comportamiento del sistema.

### Resultado Esperado
- El sistema detecta los campos obligatorios vacíos mediante validaciones de Data Annotations.
- No se guarda ningún registro en la base de datos.
- Se muestran mensajes de error de validación junto a cada campo obligatorio vacío.
- El usuario permanece en el formulario con los campos resaltados.
- El listado de plantas no muestra ningún registro nuevo.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla o logs tras la ejecución._
