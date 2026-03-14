# Matriz de Casos de Prueba — Sistema de Turnos EPS

## Casos de Prueba HU-02: Inicio de sesión seguro para empleados y administradores

| ID | Caso de Prueba generado por la instrucción | Ajuste del realizado por el probador | ¿Por qué se ajustó? |
| :--- | :--- | :--- | :--- |
| TC-01-HU-02 | [Inicio de sesión exitoso con credenciales correctas](#tc-01-hu-02) | | |
| TC-02-HU-02 | [Inicio de sesión fallido con contraseña incorrecta](#tc-02-hu-02) | | |
| TC-03-HU-02 | [Inicio de sesión fallido con correo electrónico no registrado](#tc-03-hu-02) | | |
| TC-04-HU-02 | [Validación de campos vacíos en el formulario de inicio de sesión](#tc-04-hu-02) | | |
| TC-05-HU-02 | [Validación de longitud máxima permitida para el correo electrónico](#tc-05-hu-02) | | |
| TC-06-HU-02 | [Validación de longitud máxima permitida para la contraseña](#tc-06-hu-02) | | |
| TC-07-HU-02 | [Redirección automática al inicio de sesión desde una sección protegida sin sesión activa](#tc-07-hu-02) | | |
| TC-08-HU-02 | [Manejo de sesión vencida](#tc-08-hu-02) | | |
| TC-09-HU-02 | [Indicador de carga al verificar sesión activa](#tc-09-hu-02) | | |
| TC-10-HU-02 | [Mensaje de error controlado si el servicio de autenticación no responde](#tc-10-hu-02) | | |
| TC-11-HU-02 | [Inicio de sesión con datos maliciosos](#tc-11-hu-02) | | |
| TC-12-HU-02 | [Acceso al menú de navegación condicional](#tc-12-hu-02) | | |
| TC-13-HU-02 | [Menú de navegación no visible sin sesión activa](#tc-13-hu-02) | | |
| TC-14-HU-02 | [Inicio de sesión exitoso con credenciales cifradas](#tc-14-hu-02) | | |
| TC-15-HU-02 | [Protección de contraseñas en el navegador](#tc-15-hu-02) | | |

### TC-01-HU-02: 
Inicio de sesión exitoso con credenciales correctas (Generado por la instrucción)

```
Dado que soy un empleado o administrador autorizado
Y tengo una cuenta registrada en el sistema
Cuando ingreso mi correo electrónico y contraseña correctos en el formulario de inicio de sesión
Entonces el sistema me redirige al panel principal (dashboard)
Y puedo ver el historial de turnos asignados
```

### TC-02-HU-02: 
Inicio de sesión fallido con contraseña incorrecta (Generado por la instrucción)
```
Dado que soy un empleado o administrador autorizado
Y tengo una cuenta registrada en el sistema
Cuando ingreso mi correo electrónico correcto pero una contraseña incorrecta en el formulario de inicio de sesión
Entonces el sistema muestra un mensaje de error indicando que las credenciales son incorrectas
Y no me permite acceder al panel principal (dashboard)
```

### TC-03-HU-02: 
Inicio de sesión fallido con correo electrónico no registrado (Generado por la instrucción)
```
Dado que no tengo una cuenta registrada en el sistema
Cuando ingreso un correo electrónico no registrado y una contraseña en el formulario de inicio de sesión
Entonces el sistema muestra un mensaje de error indicando que el correo electrónico no está registrado
Y no me permite acceder al panel principal (dashboard)
```

### TC-04-HU-02: 
Validación de campos vacíos en el formulario de inicio de sesión (Generado por la instrucción)
```
Dado que estoy en la pantalla de inicio de sesión
Cuando intento iniciar sesión sin ingresar el correo electrónico ni la contraseña
Entonces el sistema muestra un mensaje de error indicando que los campos son obligatorios
Y no me permite acceder al panel principal (dashboard)
```

### TC-05-HU-02: 
Validación de longitud máxima permitida para el correo electrónico (Generado por la instrucción)
```
Dado que estoy en la pantalla de inicio de sesión
Cuando ingreso un correo electrónico que excede la longitud máxima permitida en el formulario
Entonces el sistema muestra un mensaje de error indicando que el correo electrónico es demasiado largo
Y no me permite acceder al panel principal (dashboard)
```

### TC-06-HU-02: 
Validación de longitud máxima permitida para la contraseña (Generado por la instrucción)
```
Dado que estoy en la pantalla de inicio de sesión
Cuando ingreso una contraseña que excede la longitud máxima permitida en el formulario
Entonces el sistema muestra un mensaje de error indicando que la contraseña es demasiado larga
Y no me permite acceder al panel principal (dashboard)
```

### TC-07-HU-02: 
Redirección automática al inicio de sesión desde una sección protegida sin sesión activa (Generado por la instrucción)
```
Dado que no he iniciado sesión en el sistema
Cuando intento acceder directamente al panel principal (dashboard) escribiendo la URL en el navegador
Entonces el sistema me redirige automáticamente a la pantalla de inicio de sesión
Y muestra un mensaje indicando que debo iniciar sesión para continuar
```

### TC-08-HU-02: 
Manejo de sesión vencida (Generado por la instrucción)
```
Dado que mi sesión ha expirado
Cuando intento acceder al panel principal (dashboard)
Entonces el sistema detecta que mi sesión no es válida
Y me redirige automáticamente a la pantalla de inicio de sesión
Y muestra un mensaje indicando que debo iniciar sesión nuevamente
```

### TC-09-HU-02: 
Indicador de carga al verificar sesión activa (Generado por la instrucción)
```
Dado que estoy en la pantalla de inicio de sesión
Y el sistema está verificando si tengo una sesión activa
Cuando accedo al sistema
Entonces el sistema muestra un indicador de carga mientras realiza la verificación
Y no muestra contenido restringido hasta que la verificación se complete
```

### TC-10-HU-02: 
Mensaje de error controlado si el servicio de autenticación no responde (Generado por la instrucción)
```
Dado que estoy en la pantalla de inicio de sesión
Y el servicio de autenticación no está disponible
Cuando intento iniciar sesión con mi correo electrónico y contraseña
Entonces el sistema muestra un mensaje de error indicando que el servicio no está disponible
Y me permite reintentar el inicio de sesión más tarde
```

### TC-11-HU-02: 
Inicio de sesión con datos maliciosos (Generado por la instrucción)
```
Dado que estoy en la pantalla de inicio de sesión
Cuando ingreso datos maliciosos en los campos de correo electrónico o contraseña
Entonces el sistema limpia y valida los datos ingresados
Y muestra un mensaje de error indicando que las credenciales son inválidas
Y no me permite acceder al panel principal (dashboard)
```

### TC-12-HU-02: 
Acceso al menú de navegación condicional (Generado por la instrucción)
```
Dado que soy un empleado o administrador autorizado
Y he iniciado sesión correctamente
Cuando accedo al sistema
Entonces el menú de navegación aparece en la parte superior de la pantalla
Y puedo utilizar las opciones disponibles
```

### TC-13-HU-02: 
Menú de navegación no visible sin sesión activa (Generado por la instrucción)
```
Dado que no he iniciado sesión en el sistema
Cuando accedo a la pantalla pública de turnos
Entonces el menú de navegación no aparece en la parte superior de la pantalla
Y solo puedo ver las opciones públicas disponibles
```

### TC-14-HU-02: 
Inicio de sesión exitoso con credenciales cifradas (Generado por la instrucción)
```
Dado que soy un empleado o administrador autorizado
Y tengo una cuenta registrada en el sistema
Cuando ingreso mi correo electrónico y contraseña correctos en el formulario de inicio de sesión
Entonces el sistema transmite mis credenciales de forma cifrada
Y me redirige al panel principal (dashboard) sin exponer información sensible
```

### TC-15-HU-02: 
Protección de contraseñas en el navegador (Generado por la instrucción)
```
Dado que estoy en la pantalla de inicio de sesión
Cuando ingreso mi contraseña en el formulario
Entonces el sistema no almacena mi contraseña en el navegador
Y protege la información sensible durante el proceso de autenticación
```

---

## Casos de Prueba HU-04: Restauración Automática de Sesión

| ID | Caso de Prueba generado por la instrucción | Ajuste del realizado por el probador | ¿Por qué se ajustó? |
| :--- | :--- | :--- | :--- |
| TC-01-HU-04 | [Restauración de sesión al recargar la página](#tc-01-hu-04) | | |
| TC-02-HU-04 | [Restauración de sesión al cerrar y reabrir el navegador](#tc-02-hu-04) | | |
| TC-03-HU-04 | [Restauración de sesión al reiniciar el dispositivo](#tc-03-hu-04) | | |
| TC-04-HU-04 | [Redirección al inicio de sesión cuando la sesión ha expirado](#tc-04-hu-04) | | |
| TC-05-HU-04 | [Uso de cookies o tokens para restaurar la sesión](#tc-05-hu-04) | | |
| TC-06-HU-04 | [Mensaje de confirmación al restaurar la sesión](#tc-06-hu-04) | | |
| TC-07-HU-04 | [Validación de identidad del usuario al restaurar la sesión](#tc-07-hu-04) | | |
| TC-08-HU-04 | [Protección de datos sensibles durante la restauración de sesión](#tc-08-hu-04) | | |
| TC-09-HU-04 | [Sesión no restaurada si los tokens son inválidos](#tc-09-hu-04) | | |
| TC-10-HU-04 | [Sesión no restaurada si el navegador bloquea cookies](#tc-10-hu-04) | | |

### TC-01-HU-04: 
Restauración de sesión al recargar la página (Generado por la instrucción)
```
Dado que soy un usuario autenticado
Y mi sesión no ha expirado (dentro de las 24 horas desde la última actividad)
Cuando recargo la página
Entonces mi sesión debe restaurarse automáticamente
Y debo permanecer en la misma sección en la que estaba antes de recargar
Y no debo ser redirigido a la pantalla de inicio de sesión
```

### TC-02-HU-04: 
Restauración de sesión al cerrar y reabrir el navegador (Generado por la instrucción)
```
Dado que soy un usuario autenticado
Y mi sesión no ha expirado (dentro de las 24 horas desde la última actividad)
Cuando cierro y vuelvo a abrir el navegador
Entonces mi sesión debe restaurarse automáticamente
Y debo ser redirigido a la última sección visitada
Y no debo ser solicitado a iniciar sesión nuevamente
```

### TC-03-HU-04: 
Restauración de sesión al reiniciar el dispositivo (Generado por la instrucción)
```
Dado que soy un usuario autenticado
Y mi sesión no ha expirado (dentro de las 24 horas desde la última actividad)
Cuando reinicio el dispositivo y vuelvo a abrir el navegador
Entonces mi sesión debe restaurarse automáticamente
Y debo ser redirigido a la última sección visitada
Y no debo ser solicitado a iniciar sesión nuevamente
```

### TC-04-HU-04: 
Redirección al inicio de sesión cuando la sesión ha expirado (Generado por la instrucción)
```
Dado que mi sesión ha expirado (más de 24 horas desde la última actividad)
Cuando intento acceder al sistema
Entonces debo ser redirigido a la pantalla de inicio de sesión
Y no debo poder acceder a ninguna sección protegida
```

### TC-05-HU-04: 
Uso de cookies o tokens para restaurar la sesión (Generado por la instrucción)
```
Dado que la sesión se restaura automáticamente
Cuando el sistema valida mi autenticación
Entonces debe utilizar cookies o tokens de sesión para mantener la autenticación
Y no debe almacenar información sensible en el navegador
```

### TC-06-HU-04: 
Mensaje de confirmación al restaurar la sesión (Generado por la instrucción)
```
Dado que la sesión se restaura automáticamente
Cuando accedo al sistema después de recargar la página, cerrar y reabrir el navegador, o reiniciar el dispositivo
Entonces el sistema debe mostrar un mensaje indicando que la sesión ha sido restaurada
Y debo poder continuar utilizando el sistema sin interrupciones
```

### TC-07-HU-04: 
Validación de identidad del usuario al restaurar la sesión (Generado por la instrucción)
```
Dado que la sesión se restaura automáticamente
Cuando el sistema intenta restaurar mi sesión
Entonces debe validar la identidad del usuario mediante los tokens de sesión
Y debe garantizar que no haya acceso no autorizado
```

### TC-08-HU-04: 
Protección de datos sensibles durante la restauración de sesión (Generado por la instrucción)
```
Dado que la sesión se restaura automáticamente
Cuando el sistema procesa las cookies o tokens de sesión
Entonces debe proteger los datos sensibles mediante cifrado
Y no debe exponer información sensible en las solicitudes o respuestas del servidor
```

### TC-09-HU-04: 
Sesión no restaurada si los tokens son inválidos (Generado por la instrucción)
```
Dado que la sesión se restaura automáticamente
Cuando los tokens de sesión son inválidos o han sido manipulados
Entonces el sistema no debe restaurar la sesión
Y debo ser redirigido a la pantalla de inicio de sesión
```

### TC-10-HU-04: 
Sesión no restaurada si el navegador bloquea cookies (Generado por la instrucción)
```
Dado que la sesión se restaura automáticamente
Cuando el navegador bloquea las cookies necesarias para la autenticación
Entonces el sistema no debe restaurar la sesión
Y debo ser redirigido a la pantalla de inicio de sesión
Y el sistema debe mostrar un mensaje indicando que las cookies están bloqueadas
```

---

## Casos de Prueba HU-05: Cierre de sesión seguro desde el menú de navegación

| ID | Caso de Prueba generado por la instrucción | Ajuste del realizado por el probador | ¿Por qué se ajustó? |
| :--- | :--- | :--- | :--- |
| TC-01-HU-05 | [Cerrar sesión correctamente desde el menú de navegación](#tc-01-hu-05) | | |
| TC-02-HU-05 | [Intento de acceso a secciones internas después de cerrar sesión](#tc-02-hu-05) | | |
| TC-03-HU-05 | [Mensaje de error controlado al fallar el cierre de sesión](#tc-03-hu-05) | | |
| TC-04-HU-05 | [Eliminación de datos de sesión en el navegador al cerrar sesión](#tc-04-hu-05) | | |
| TC-05-HU-05 | [Redirección al inicio de sesión tras cerrar sesión](#tc-05-hu-05) | | |
| TC-06-HU-05 | [Actualización del menú de navegación tras cerrar sesión](#tc-06-hu-05) | | |
| TC-07-HU-05 | [Transmisión cifrada al cerrar sesión](#tc-07-hu-05) | | |
| TC-08-HU-05 | [Registro del evento de cierre de sesión para auditoría](#tc-08-hu-05) | | |
| TC-09-HU-05 | [Comportamiento en alta concurrencia al cerrar sesión](#tc-09-hu-05) | | |
| TC-10-HU-05 | [Indicador de carga al procesar el cierre de sesión](#tc-10-hu-05) | | |

### TC-01-HU-05: 
Cerrar sesión correctamente desde el menú de navegación (Generado por la instrucción)
```
Dado que el usuario tiene una sesión activa en el sistema
Y el usuario está en una sección interna del sistema
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el sistema invalida la sesión activa en el servidor
Y el usuario es redirigido automáticamente a la pantalla de inicio de sesión
Y el menú de navegación deja de mostrar opciones exclusivas para usuarios autenticados
Y toda la información de la sesión se elimina del almacenamiento local del navegador
Y el evento de cierre de sesión queda registrado para auditoría
```

### TC-02-HU-05: 
Intento de acceso a secciones internas después de cerrar sesión (Generado por la instrucción)
```
Dado que el usuario ha cerrado sesión correctamente
Cuando intenta acceder a una sección interna escribiendo la URL directamente en el navegador
Entonces el sistema redirige al usuario automáticamente a la pantalla de inicio de sesión
Y no se muestra contenido de la sección interna
```

### TC-03-HU-05: 
Mensaje de error controlado al fallar el cierre de sesión (Generado por la instrucción)
```
Dado que el usuario tiene una sesión activa en el sistema
Y el sistema presenta un fallo al procesar el cierre de sesión
Cuando el usuario selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces se muestra un mensaje de error controlado indicando que no se pudo cerrar la sesión
Y se ofrece al usuario la opción de reintentar el cierre de sesión
```

### TC-04-HU-05: 
Eliminación de datos de sesión en el navegador al cerrar sesión (Generado por la instrucción)
```
Dado que el usuario tiene una sesión activa en el sistema
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces toda la información de la sesión se elimina del almacenamiento local del navegador
Y no queda información sensible visible en el navegador tras el cierre de sesión
```

### TC-05-HU-05: 
Redirección al inicio de sesión tras cerrar sesión (Generado por la instrucción)
```
Dado que el usuario tiene una sesión activa en el sistema
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el usuario es redirigido automáticamente a la pantalla de inicio de sesión
Y el sistema no permite acceder a secciones internas sin iniciar sesión nuevamente
```

### TC-06-HU-05: 
Actualización del menú de navegación tras cerrar sesión (Generado por la instrucción)
```
Dado que el usuario tiene una sesión activa en el sistema
Y el menú de navegación muestra opciones exclusivas para usuarios autenticados
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el menú de navegación deja de mostrar opciones exclusivas para usuarios autenticados
Y refleja el estado de visitante/no autenticado
```

### TC-07-HU-05: 
Transmisión cifrada al cerrar sesión (Generado por la instrucción)
```
Dado que el usuario tiene una sesión activa en el sistema
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el sistema asegura que la transmisión de datos para invalidar la sesión es cifrada
Y no se expone información sensible durante el proceso
```

### TC-08-HU-05: 
Registro del evento de cierre de sesión para auditoría (Generado por la instrucción)
```
Dado que el usuario tiene una sesión activa en el sistema
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el evento de cierre de sesión queda registrado en el sistema
Y el registro incluye la fecha, hora y usuario que realizó el cierre de sesión
```

### TC-09-HU-05: 
Comportamiento en alta concurrencia al cerrar sesión (Generado por la instrucción)
```
Dado que múltiples usuarios tienen sesiones activas en el sistema
Y el sistema está procesando múltiples solicitudes simultáneamente
Cuando el usuario selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el sistema procesa la solicitud de cierre de sesión sin errores
Y el usuario es redirigido a la pantalla de inicio de sesión
```

### TC-10-HU-05: 
Indicador de carga al procesar el cierre de sesión (Generado por la instrucción)
```
Dado que el usuario tiene una sesión activa en el sistema
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el sistema muestra un indicador de carga mientras se procesa el cierre de sesión
Y el indicador desaparece una vez que el usuario es redirigido a la pantalla de inicio de sesión
```
