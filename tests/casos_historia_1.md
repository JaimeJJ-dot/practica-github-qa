# Casos de Prueba – Historia 1: Registro de Usuario

---

## TC-001 | Caso Positivo – Registro exitoso de usuario

| Campo | Detalle |
|-------|---------|
| **ID** | TC-001 |
| **Historia relacionada** | HU-01 – Registro de Usuario |
| **Título** | Registro exitoso con datos válidos |
| **Tipo** | Positivo (flujo normal) |

### Objetivo
Validar que un visitante puede crear una cuenta correctamente ingresando nombre, correo electrónico y contraseña válidos, y que el sistema almacena la cuenta con la contraseña hasheada y redirige al login.

### Precondiciones
- El sistema está en funcionamiento y accesible.
- El correo `voluntario01@gmail.com` no está registrado previamente en la base de datos.
- El usuario se encuentra en la pantalla de inicio de sesión.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Nombre completo | `Carlos Pérez` |
| Correo electrónico | `voluntario01@gmail.com` |
| Contraseña | `Huerto2026#` |

### Pasos
1. Abrir el sistema web en el navegador.
2. En la pantalla de login, hacer clic en el enlace **"¿No tienes cuenta? Regístrate aquí"**.
3. Ingresar el nombre completo: `Carlos Pérez`.
4. Ingresar el correo electrónico: `voluntario01@gmail.com`.
5. Ingresar la contraseña: `Huerto2026#`.
6. Presionar el botón **"Registrarse"**.
7. Observar el comportamiento del sistema.

### Resultado Esperado
- El sistema valida los datos correctamente.
- La cuenta queda registrada en la tabla `Usuarios` con la contraseña almacenada en formato hash (no texto plano).
- El rol asignado es **"User"** por defecto.
- El sistema redirige a la pantalla de inicio de sesión con un mensaje de confirmación de registro exitoso.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla o logs tras la ejecución._

---

## TC-002 | Caso Negativo – Registro con correo ya existente

| Campo | Detalle |
|-------|---------|
| **ID** | TC-002 |
| **Historia relacionada** | HU-01 – Registro de Usuario |
| **Título** | Registro rechazado por correo duplicado |
| **Tipo** | Negativo (flujo alterno) |

### Objetivo
Validar que el sistema impide el registro de una cuenta cuando el correo electrónico ingresado ya está registrado en la base de datos, mostrando un mensaje de error claro al usuario.

### Precondiciones
- El sistema está en funcionamiento y accesible.
- El correo `voluntario01@gmail.com` **ya existe** en la base de datos (cuenta creada previamente).
- El usuario se encuentra en el formulario de registro.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Nombre completo | `Laura Mendoza` |
| Correo electrónico | `voluntario01@gmail.com` ← _ya registrado_ |
| Contraseña | `OtroPass2026!` |

### Pasos
1. Abrir el sistema web en el navegador.
2. En la pantalla de login, hacer clic en **"¿No tienes cuenta? Regístrate aquí"**.
3. Ingresar el nombre completo: `Laura Mendoza`.
4. Ingresar el correo duplicado: `voluntario01@gmail.com`.
5. Ingresar la contraseña: `OtroPass2026!`.
6. Presionar el botón **"Registrarse"**.
7. Observar el comportamiento del sistema.

### Resultado Esperado
- El sistema detecta que el correo ya está registrado.
- No se crea ningún registro nuevo en la tabla `Usuarios`.
- Se muestra un mensaje de error indicando que el correo ya está en uso (ej: *"El correo electrónico ya está registrado"*).
- El usuario permanece en el formulario de registro con los datos ingresados.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla o logs tras la ejecución._
