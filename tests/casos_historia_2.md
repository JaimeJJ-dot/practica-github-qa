# Casos de Prueba – Historia 2: Inicio de Sesión con Roles

---

## TC-003 | Caso Positivo – Inicio de sesión exitoso como Administrador

| Campo | Detalle |
|-------|---------|
| **ID** | TC-003 |
| **Historia relacionada** | HU-02 – Inicio de Sesión con Roles |
| **Título** | Inicio de sesión exitoso con credenciales de Administrador |
| **Tipo** | Positivo (flujo normal) |

### Objetivo
Validar que un usuario con rol Admin puede iniciar sesión correctamente con credenciales válidas, que la sesión se crea con el rol correspondiente y que el sistema redirige al Dashboard con las opciones de administración visibles.

### Precondiciones
- El sistema está en funcionamiento y accesible.
- Existe una cuenta con rol **Admin** registrada en la base de datos.
- El usuario se encuentra en la pantalla de inicio de sesión.
- No hay sesión activa en el navegador.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Correo electrónico | `admin@huerto.com` |
| Contraseña | `Admin2026#` |
| Rol esperado en sesión | `Admin` |

### Pasos
1. Abrir el sistema web en el navegador.
2. En la pantalla de **"Iniciar Sesión"**, ingresar el correo: `admin@huerto.com`.
3. Ingresar la contraseña: `Admin2026#`.
4. Presionar el botón **"Ingresar"**.
5. Observar la redirección y el contenido del Dashboard.
6. Verificar que en la barra de navegación aparece el menú **"Gestión Usuarios"** (exclusivo de Admin).

### Resultado Esperado
- El sistema valida las credenciales correctamente contra la tabla `Usuarios`.
- Se crea la sesión con `Session['UsuarioID']` y `Session['Rol'] = "Admin"`.
- El usuario es redirigido al **Dashboard del Huerto**.
- La barra de navegación muestra las opciones: Dashboard, Plantas, Gestión Usuarios y Ejecutar Tests.
- El nombre del usuario y su rol aparecen en la esquina superior derecha (ej: *"Admin (Admin)"*).

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla o logs tras la ejecución._

---

## TC-004 | Caso Negativo – Inicio de sesión con contraseña incorrecta

| Campo | Detalle |
|-------|---------|
| **ID** | TC-004 |
| **Historia relacionada** | HU-02 – Inicio de Sesión con Roles |
| **Título** | Inicio de sesión rechazado por contraseña inválida |
| **Tipo** | Negativo (flujo alterno) |

### Objetivo
Validar que el sistema rechaza el intento de inicio de sesión cuando la contraseña es incorrecta, no crea ninguna sesión activa y muestra un mensaje de error genérico sin revelar cuál campo específico falló.

### Precondiciones
- El sistema está en funcionamiento y accesible.
- Existe la cuenta `admin@huerto.com` registrada en la base de datos.
- El usuario se encuentra en la pantalla de inicio de sesión.
- No hay sesión activa en el navegador.

### Datos de Prueba
| Campo | Valor |
|-------|-------|
| Correo electrónico | `admin@huerto.com` ← _correo válido_ |
| Contraseña | `ClaveIncorrecta123` ← _contraseña incorrecta_ |

### Pasos
1. Abrir el sistema web en el navegador.
2. En la pantalla de **"Iniciar Sesión"**, ingresar el correo: `admin@huerto.com`.
3. Ingresar la contraseña incorrecta: `ClaveIncorrecta123`.
4. Presionar el botón **"Ingresar"**.
5. Observar el comportamiento del sistema.
6. Intentar acceder directamente a `/Dashboard` mediante la barra de direcciones.

### Resultado Esperado
- El sistema detecta que la contraseña no coincide con el hash almacenado.
- No se crea ninguna sesión (`Session['UsuarioID']` permanece vacío).
- Se muestra un mensaje de error genérico (ej: *"Correo o contraseña incorrectos"*) sin indicar cuál campo específicamente falló.
- El usuario permanece en la pantalla de login.
- Al intentar acceder a `/Dashboard` directamente, el sistema redirige nuevamente al login.

### Resultado Obtenido
> _Pendiente de ejecución_

### Estado
> ⬜ **Pendiente** (Pass / Fail)

### Notas / Evidencias
> _Completar con capturas de pantalla o logs tras la ejecución._
