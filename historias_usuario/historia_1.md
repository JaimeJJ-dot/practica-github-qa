# Historia de Usuario #1 – Registro de Usuario

## Información General

| Campo | Detalle |
|-------|---------|
| **ID** | HU-01 |
| **Módulo** | Autenticación |
| **Prioridad** | Alta |
| **Estimación** | 3 puntos de historia |

---

## Historia de Usuario

**Como** visitante del sistema,  
**quiero** poder crear una cuenta con mi nombre, correo electrónico y contraseña,  
**para** acceder al sistema de gestión de huertos comunitarios y registrar mi información como miembro activo.

---

## Flujo Guiado

1. El usuario ingresa a la página principal del sistema.
2. Hace clic en el enlace **"¿No tienes cuenta? Regístrate aquí"**.
3. Se muestra el formulario de registro con los campos: nombre completo, correo electrónico y contraseña.
4. El usuario completa el formulario y presiona **"Registrarse"**.
5. El sistema valida los datos (formato de email, longitud mínima de contraseña, campos no vacíos).
6. Si los datos son válidos, el sistema almacena la cuenta con la contraseña hasheada y redirige al login.
7. Si hay errores, se muestran mensajes de validación junto a cada campo.

---

## Criterios de Aceptación

### 01: Formulario de registro visible
- **Dado que** el visitante está en la página de login,
- **cuando** hace clic en el enlace de registro,
- **entonces** se muestra un formulario con los campos: nombre, correo electrónico y contraseña.

### 02: Validación de campos obligatorios
- **Dado que** el usuario deja campos en blanco,
- **cuando** intenta enviar el formulario,
- **entonces** el sistema muestra mensajes de error indicando qué campos son requeridos y no procede con el registro.

### 03: Validación de formato de correo
- **Dado que** el usuario escribe un correo con formato inválido (sin @, sin dominio),
- **cuando** envía el formulario,
- **entonces** el sistema muestra un mensaje de error de formato en el campo de correo.

### 04: Contraseña almacenada de forma segura
- **Dado que** el usuario completa el formulario correctamente,
- **cuando** el sistema registra la cuenta,
- **entonces** la contraseña se almacena con hashing (no en texto plano) en la tabla `Usuarios`.

### 05: Redirección tras registro exitoso
- **Dado que** el registro fue completado sin errores,
- **cuando** el sistema guarda la cuenta,
- **entonces** el usuario es redirigido a la pantalla de inicio de sesión con un mensaje de confirmación.

### 06: Correo duplicado rechazado
- **Dado que** el correo ingresado ya existe en la base de datos,
- **cuando** el usuario intenta registrarse,
- **entonces** el sistema muestra un error indicando que el correo ya está registrado.


