# Historia de Usuario #2 – Inicio de Sesión con Roles

## Información General

| Campo | Detalle |
|-------|---------|
| **ID** | HU-02 |
| **Módulo** | Autenticación y Seguridad |
| **Prioridad** | Alta |
| **Estimación** | 3 puntos de historia |

---

## Historia de Usuario

**Como** usuario registrado en el sistema,  
**quiero** poder iniciar sesión con mi correo electrónico y contraseña,  
**para** acceder de forma segura a las funcionalidades del sistema según mi rol (Administrador o Usuario).

---

## Flujo Guiado

1. El usuario ingresa a la URL principal del sistema.
2. Se muestra la pantalla de **"Iniciar Sesión"** con los campos: correo electrónico y contraseña.
3. Opcionalmente, activa la casilla **"Recuérdame en este dispositivo"**.
4. Presiona el botón **"Ingresar"**.
5. El sistema valida las credenciales contra la tabla `Usuarios` de la base de datos.
6. Si son correctas, se crea la sesión con `Session['UsuarioID']` y `Session['Rol']`.
7. El usuario es redirigido al Dashboard o al módulo correspondiente según su rol.
8. Si las credenciales son incorrectas, se muestra un mensaje de error sin revelar cuál campo falló.

---

## Criterios de Aceptación

### 01: Pantalla de login visible al ingresar al sistema
- **Dado que** un usuario no autenticado accede al sistema,
- **cuando** navega a cualquier ruta protegida,
- **entonces** es redirigido automáticamente a la pantalla de inicio de sesión.

### 02: Autenticación exitosa con credenciales válidas
- **Dado que** el usuario ingresa un correo y contraseña correctos,
- **cuando** presiona "Ingresar",
- **entonces** el sistema crea la sesión, asigna el rol correspondiente y redirige al dashboard.

### 03: Rechazo de credenciales incorrectas
- **Dado que** el usuario ingresa una contraseña o correo incorrecto,
- **cuando** intenta iniciar sesión,
- **entonces** el sistema muestra un mensaje de error genérico sin indicar cuál campo es incorrecto.

### 04: Gestión de sesión por roles
- **Dado que** el usuario inicia sesión correctamente,
- **cuando** accede al sistema,
- **entonces** `Session['Rol']` contiene el valor correcto ("Admin" o "User"), y las opciones del menú se ajustan según ese rol.

### 05: Protección de rutas sin sesión activa
- **Dado que** un usuario intenta acceder directamente a una URL protegida sin haber iniciado sesión,
- **cuando** el sistema detecta que no hay sesión activa,
- **entonces** redirige automáticamente al login sin mostrar el contenido protegido.

### 06: Cierre de sesión seguro
- **Dado que** el usuario hace clic en "Cerrar Sesión",
- **cuando** el sistema procesa la solicitud,
- **entonces** elimina la sesión activa y redirige al login, impidiendo el acceso con el botón "Atrás" del navegador.

### 07: Token Anti-CSRF en formulario
- **Dado que** el formulario de login está activo,
- **cuando** se renderiza la vista,
- **entonces** el sistema incluye un token Anti-CSRF que debe coincidir al enviar el formulario.


