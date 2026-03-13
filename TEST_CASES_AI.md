# Matriz de Casos de Prueba — Sistema de Turnos EPS

## Casos de Prueba HU-02: Inicio de sesión seguro para empleados y administradores

### TC-1: Inicio de sesión exitoso con credenciales correctas
```
Dado que soy un empleado o administrador autorizado
Y tengo una cuenta registrada en el sistema
Cuando ingreso mi correo electrónico y contraseña correctos en el formulario de inicio de sesión
Entonces el sistema me redirige al panel principal (dashboard)
Y puedo ver el historial de turnos asignados
```

### TC-2: Inicio de sesión fallido con contraseña incorrecta
```
Dado que soy un empleado o administrador autorizado
Y tengo una cuenta registrada en el sistema
Cuando ingreso mi correo electrónico correcto pero una contraseña incorrecta en el formulario de inicio de sesión
Entonces el sistema muestra un mensaje de error indicando que las credenciales son incorrectas
Y no me permite acceder al panel principal (dashboard)
```

### TC-3: Inicio de sesión fallido con correo electrónico no registrado
```
Dado que no tengo una cuenta registrada en el sistema
Cuando ingreso un correo electrónico no registrado y una contraseña en el formulario de inicio de sesión
Entonces el sistema muestra un mensaje de error indicando que el correo electrónico no está registrado
Y no me permite acceder al panel principal (dashboard)
```

### TC-4: Validación de campos vacíos en el formulario de inicio de sesión
```
Dado que estoy en la pantalla de inicio de sesión
Cuando intento iniciar sesión sin ingresar el correo electrónico ni la contraseña
Entonces el sistema muestra un mensaje de error indicando que los campos son obligatorios
Y no me permite acceder al panel principal (dashboard)
```

### TC-5: Validación de longitud máxima permitida para el correo electrónico
```
Dado que estoy en la pantalla de inicio de sesión
Cuando ingreso un correo electrónico que excede la longitud máxima permitida en el formulario
Entonces el sistema muestra un mensaje de error indicando que el correo electrónico es demasiado largo
Y no me permite acceder al panel principal (dashboard)
```

### TC-6: Validación de longitud máxima permitida para la contraseña
```
Dado que estoy en la pantalla de inicio de sesión
Cuando ingreso una contraseña que excede la longitud máxima permitida en el formulario
Entonces el sistema muestra un mensaje de error indicando que la contraseña es demasiado larga
Y no me permite acceder al panel principal (dashboard)
```

### TC-7: Redirección automática al inicio de sesión desde una sección protegida sin sesión activa
```
Dado que no he iniciado sesión en el sistema
Cuando intento acceder directamente al panel principal (dashboard) escribiendo la URL en el navegador
Entonces el sistema me redirige automáticamente a la pantalla de inicio de sesión
Y muestra un mensaje indicando que debo iniciar sesión para continuar
```

### TC-8: Manejo de sesión vencida
```
Dado que mi sesión ha expirado
Cuando intento acceder al panel principal (dashboard)
Entonces el sistema detecta que mi sesión no es válida
Y me redirige automáticamente a la pantalla de inicio de sesión
Y muestra un mensaje indicando que debo iniciar sesión nuevamente
```

### TC-9: Indicador de carga al verificar sesión activa
```
Dado que estoy en la pantalla de inicio de sesión
Y el sistema está verificando si tengo una sesión activa
Cuando accedo al sistema
Entonces el sistema muestra un indicador de carga mientras realiza la verificación
Y no muestra contenido restringido hasta que la verificación se complete
```

### TC-10: Mensaje de error controlado si el servicio de autenticación no responde
```
Dado que estoy en la pantalla de inicio de sesión
Y el servicio de autenticación no está disponible
Cuando intento iniciar sesión con mi correo electrónico y contraseña
Entonces el sistema muestra un mensaje de error indicando que el servicio no está disponible
Y me permite reintentar el inicio de sesión más tarde
```

### TC-11: Inicio de sesión con datos maliciosos
```
Dado que estoy en la pantalla de inicio de sesión
Cuando ingreso datos maliciosos en los campos de correo electrónico o contraseña
Entonces el sistema limpia y valida los datos ingresados
Y muestra un mensaje de error indicando que las credenciales son inválidas
Y no me permite acceder al panel principal (dashboard)
```

### TC-12: Acceso al menú de navegación condicional
```
Dado que soy un empleado o administrador autorizado
Y he iniciado sesión correctamente
Cuando accedo al sistema
Entonces el menú de navegación aparece en la parte superior de la pantalla
Y puedo utilizar las opciones disponibles
```

### TC-13: Menú de navegación no visible sin sesión activa
```
Dado que no he iniciado sesión en el sistema
Cuando accedo a la pantalla pública de turnos
Entonces el menú de navegación no aparece en la parte superior de la pantalla
Y solo puedo ver las opciones públicas disponibles
```

### TC-14: Inicio de sesión exitoso con credenciales cifradas
```
Dado que soy un empleado o administrador autorizado
Y tengo una cuenta registrada en el sistema
Cuando ingreso mi correo electrónico y contraseña correctos en el formulario de inicio de sesión
Entonces el sistema transmite mis credenciales de forma cifrada
Y me redirige al panel principal (dashboard) sin exponer información sensible
```

### TC-15: Protección de contraseñas en el navegador
```
Dado que estoy en la pantalla de inicio de sesión
Cuando ingreso mi contraseña en el formulario
Entonces el sistema no almacena mi contraseña en el navegador
Y protege la información sensible durante el proceso de autenticación
```

| ID      | HU | Caso de Prueba generado por la instrucción | Ajuste del realizado por el probador | ¿Por qué se ajustó? |
| :--- | :--- | :--- | :--- | :--- |
| TC-1    | HU-02  | Dado que soy un empleado o administrador autorizado Y tengo una cuenta registrada en el sistema Cuando ingreso mi correo electrónico y contraseña correctos en el formulario de inicio de sesión Entonces el sistema me redirige al panel principal (dashboard) Y puedo ver el historial de turnos asignados |
| TC-2    | HU-02  | Dado que soy un empleado o administrador autorizado Y tengo una cuenta registrada en el sistema Cuando ingreso mi correo electrónico correcto pero una contraseña incorrecta en el formulario de inicio de sesión Entonces el sistema muestra un mensaje de error indicando que las credenciales son incorrectas Y no me permite acceder al panel principal (dashboard) |
| TC-3    | HU-02  | Dado que no tengo una cuenta registrada en el sistema Cuando ingreso un correo electrónico no registrado y una contraseña en el formulario de inicio de sesión Entonces el sistema muestra un mensaje de error indicando que el correo electrónico no está registrado Y no me permite acceder al panel principal (dashboard) |
| TC-4    | HU-02  | Dado que estoy en la pantalla de inicio de sesión Cuando intento iniciar sesión sin ingresar el correo electrónico ni la contraseña Entonces el sistema muestra un mensaje de error indicando que los campos son obligatorios Y no me permite acceder al panel principal (dashboard) |
| TC-5    | HU-02  | Dado que estoy en la pantalla de inicio de sesión Cuando ingreso un correo electrónico que excede la longitud máxima permitida en el formulario Entonces el sistema muestra un mensaje de error indicando que el correo electrónico es demasiado largo Y no me permite acceder al panel principal (dashboard) |
| TC-6    | HU-02  | Dado que estoy en la pantalla de inicio de sesión Cuando ingreso una contraseña que excede la longitud máxima permitida en el formulario Entonces el sistema muestra un mensaje de error indicando que la contraseña es demasiado larga Y no me permite acceder al panel principal (dashboard) |
| TC-7    | HU-02  | Dado que no he iniciado sesión en el sistema Cuando intento acceder directamente al panel principal (dashboard) escribiendo la URL en el navegador Entonces el sistema me redirige automáticamente a la pantalla de inicio de sesión Y muestra un mensaje indicando que debo iniciar sesión para continuar |
| TC-8    | HU-02  | Dado que mi sesión ha expirado Cuando intento acceder al panel principal (dashboard) Entonces el sistema detecta que mi sesión no es válida Y me redirige automáticamente a la pantalla de inicio de sesión Y muestra un mensaje indicando que debo iniciar sesión nuevamente |
| TC-9    | HU-02  | Dado que estoy en la pantalla de inicio de sesión Y el sistema está verificando si tengo una sesión activa Cuando accedo al sistema Entonces el sistema muestra un indicador de carga mientras realiza la verificación Y no muestra contenido restringido hasta que la verificación se complete |
| TC-10   | HU-02  | Dado que estoy en la pantalla de inicio de sesión Y el servicio de autenticación no está disponible Cuando intento iniciar sesión con mi correo electrónico y contraseña Entonces el sistema muestra un mensaje de error indicando que el servicio no está disponible Y me permite reintentar el inicio de sesión más tarde |
| TC-11   | HU-02  | Dado que estoy en la pantalla de inicio de sesión Cuando ingreso datos maliciosos en los campos de correo electrónico o contraseña Entonces el sistema limpia y valida los datos ingresados Y muestra un mensaje de error indicando que las credenciales son inválidas Y no me permite acceder al panel principal (dashboard) |
| TC-12   | HU-02  | Dado que soy un empleado o administrador autorizado Y he iniciado sesión correctamente Cuando accedo al sistema Entonces el menú de navegación aparece en la parte superior de la pantalla Y puedo utilizar las opciones disponibles |
| TC-13   | HU-02  | Dado que no he iniciado sesión en el sistema Cuando accedo a la pantalla pública de turnos Entonces el menú de navegación no aparece en la parte superior de la pantalla Y solo puedo ver las opciones públicas disponibles |
| TC-14   | HU-02  | Dado que soy un empleado o administrador autorizado Y tengo una cuenta registrada en el sistema Cuando ingreso mi correo electrónico y contraseña correctos en el formulario de inicio de sesión Entonces el sistema transmite mis credenciales de forma cifrada Y me redirige al panel principal (dashboard) sin exponer información sensible |
| TC-15   | HU-02  | Dado que estoy en la pantalla de inicio de sesión Cuando ingreso mi contraseña en el formulario Entonces el sistema no almacena mi contraseña en el navegador Y protege la información sensible durante el proceso de autenticación |


## Casos de Prueba HU-04: Restauración Automática de Sesión

### TC-01: Restauración de sesión al recargar la página
```
Dado que soy un usuario autenticado
Y mi sesión no ha expirado (dentro de las 24 horas desde la última actividad)
Cuando recargo la página
Entonces mi sesión debe restaurarse automáticamente
Y debo permanecer en la misma sección en la que estaba antes de recargar
Y no debo ser redirigido a la pantalla de inicio de sesión
```

### TC-02: Restauración de sesión al cerrar y reabrir el navegador
```
Dado que soy un usuario autenticado
Y mi sesión no ha expirado (dentro de las 24 horas desde la última actividad)
Cuando cierro y vuelvo a abrir el navegador
Entonces mi sesión debe restaurarse automáticamente
Y debo ser redirigido a la última sección visitada
Y no debo ser solicitado a iniciar sesión nuevamente
```

### TC-03: Restauración de sesión al reiniciar el dispositivo
```
Dado que soy un usuario autenticado
Y mi sesión no ha expirado (dentro de las 24 horas desde la última actividad)
Cuando reinicio el dispositivo y vuelvo a abrir el navegador
Entonces mi sesión debe restaurarse automáticamente
Y debo ser redirigido a la última sección visitada
Y no debo ser solicitado a iniciar sesión nuevamente
```

### TC-04: Redirección al inicio de sesión cuando la sesión ha expirado
```
Dado que mi sesión ha expirado (más de 24 horas desde la última actividad)
Cuando intento acceder al sistema
Entonces debo ser redirigido a la pantalla de inicio de sesión
Y no debo poder acceder a ninguna sección protegida
```

### TC-05: Uso de cookies o tokens para restaurar la sesión
```
Dado que la sesión se restaura automáticamente
Cuando el sistema valida mi autenticación
Entonces debe utilizar cookies o tokens de sesión para mantener la autenticación
Y no debe almacenar información sensible en el navegador
```

### TC-06: Mensaje de confirmación al restaurar la sesión
```
Dado que la sesión se restaura automáticamente
Cuando accedo al sistema después de recargar la página, cerrar y reabrir el navegador, o reiniciar el dispositivo
Entonces el sistema debe mostrar un mensaje indicando que la sesión ha sido restaurada
Y debo poder continuar utilizando el sistema sin interrupciones
```

### TC-07: Validación de identidad del usuario al restaurar la sesión
```
Dado que la sesión se restaura automáticamente
Cuando el sistema intenta restaurar mi sesión
Entonces debe validar la identidad del usuario mediante los tokens de sesión
Y debe garantizar que no haya acceso no autorizado
```

### TC-08: Protección de datos sensibles durante la restauración de sesión
```
Dado que la sesión se restaura automáticamente
Cuando el sistema procesa las cookies o tokens de sesión
Entonces debe proteger los datos sensibles mediante cifrado
Y no debe exponer información sensible en las solicitudes o respuestas del servidor
```

### TC-09: Sesión no restaurada si los tokens son inválidos
```
Dado que la sesión se restaura automáticamente
Cuando los tokens de sesión son inválidos o han sido manipulados
Entonces el sistema no debe restaurar la sesión
Y debo ser redirigido a la pantalla de inicio de sesión
```

### TC-10: Sesión no restaurada si el navegador bloquea cookies
```
Dado que la sesión se restaura automáticamente
Cuando el navegador bloquea las cookies necesarias para la autenticación
Entonces el sistema no debe restaurar la sesión
Y debo ser redirigido a la pantalla de inicio de sesión
Y el sistema debe mostrar un mensaje indicando que las cookies están bloqueadas
```

| ID      | HU | Caso de Prueba generado por la instrucción | Ajuste del realizado por el probador | ¿Por qué se ajustó? |
| :--- | :--- | :--- | :--- | :--- |
| TC-01   | HU-04  | Dado que soy un usuario autenticado Y mi sesión no ha expirado (dentro de las 24 horas desde la última actividad) Cuando recargo la página Entonces mi sesión debe restaurarse automáticamente Y debo permanecer en la misma sección en la que estaba antes de recargar Y no debo ser redirigido a la pantalla de inicio de sesión | Dado que soy un usuario autenticado Y han transcurrido menos de 24 horas desde la última actividad Cuando recargo la página Entonces mi sesión debe restaurarse automáticamente Y debo permanecer en la misma sección Y el sistema muestra un mensaje confirmando que la sesión fue restaurada Y no soy redirigido a la pantalla de inicio de sesión | Se precisó la precondición temporal ("menos de 24 horas") para hacerla medible y reproducible según ISTQB. Se añadió la verificación del mensaje de confirmación que exige el CA-5, el cual no estaba contemplado en el resultado esperado original. |
| TC-02   | HU-04  | Dado que soy un usuario autenticado Y mi sesión no ha expirado (dentro de las 24 horas desde la última actividad) Cuando cierro y vuelvo a abrir el navegador Entonces mi sesión debe restaurarse automáticamente Y debo ser redirigido a la última sección visitada Y no debo ser solicitado a iniciar sesión nuevamente | Dado que soy un usuario autenticado Y han transcurrido menos de 24 horas desde la última actividad Cuando cierro y vuelvo a abrir el navegador Entonces mi sesión debe restaurarse automáticamente Y el sistema muestra un mensaje confirmando que la sesión fue restaurada Y no se me solicita iniciar sesión nuevamente | Se reemplazó "redirigido a la última sección visitada" por la carga de la pantalla principal (dashboard), ya que el sistema no exige memorizar la última URL. Se añadió la verificación del mensaje de confirmación (CA-5). "No debo ser solicitado" se corrigió a "no se me solicita" para mantener la voz activa del sistema. |
| TC-03   | HU-04  | Dado que soy un usuario autenticado Y mi sesión no ha expirado (dentro de las 24 horas desde la última actividad) Cuando reinicio el dispositivo y vuelvo a abrir el navegador Entonces mi sesión debe restaurarse automáticamente Y debo ser redirigido a la última sección visitada Y no debo ser solicitado a iniciar sesión nuevamente | Dado que soy un usuario autenticado Y han transcurrido menos de 24 horas desde la última actividad Cuando reinicio el dispositivo y vuelvo a abrir el navegador Entonces mi sesión debe restaurarse automáticamente Y el sistema muestra un mensaje confirmando que la sesión fue restaurada Y no se me solicita iniciar sesión nuevamente | Mismos ajustes aplicados que en TC-02: se eliminó la mención de redirigir a la última sección (no declarada en la HU), se añadió la confirmación del CA-5 y se corrigió la redacción del resultado esperado. |
| TC-04   | HU-04  | Dado que mi sesión ha expirado (más de 24 horas desde la última actividad) Cuando intento acceder al sistema Entonces debo ser redirigido a la pantalla de inicio de sesión Y no debo poder acceder a ninguna sección protegida | Dado que han transcurrido más de 24 horas desde la última actividad del usuario Cuando intento acceder al sistema (ya sea recargando la página, reabriendo el navegador o reiniciando el dispositivo) Entonces el sistema redirige automáticamente a la pantalla de inicio de sesión Y no se muestra ningún fragmento de contenido restringido antes de la redirección Y no es posible acceder a ninguna sección protegida | Se explicitó el criterio temporal en la precondición para que sea inequívoca. Se enumeraron los escenarios de acceso cubiertos por el CA-4 (recarga, reapertura, reinicio). Se añadió la condición de que no se exponga contenido restringido antes de la redirección, alineándose con el comportamiento de seguridad documentado en el contexto de negocio. |
| TC-05   | HU-04  | Dado que la sesión se restaura automáticamente Cuando el sistema valida mi autenticación Entonces debe utilizar cookies o tokens de sesión para mantener la autenticación Y no debe almacenar información sensible en el navegador | Dado que la sesión se restaura automáticamente Cuando el sistema procesa el token o cookie de sesión Entonces utiliza el mecanismo de sesión seguro generado por el servidor para validar la autenticación Y no almacena contraseñas ni información sensible en el almacenamiento local del navegador Y el token o cookie de sesión se transmite de forma cifrada | Se amplió el resultado esperado para especificar que la validación la realiza el servidor (no el cliente), conforme al CA-6. Se separó explícitamente la prohibición de almacenar contraseñas del cifrado en tránsito, ya que son dos controles de seguridad distintos (OWASP A02:2021 — Cryptographic Failures). |
| TC-06   | HU-04  | Dado que la sesión se restaura automáticamente Cuando accedo al sistema después de recargar la página, cerrar y reabrir el navegador, o reiniciar el dispositivo Entonces el sistema debe mostrar un mensaje indicando que la sesión ha sido restaurada Y debo poder continuar utilizando el sistema sin interrupciones | Dado que la sesión se restaura automáticamente Cuando accedo al sistema tras recargar la página, cerrar y reabrir el navegador, o reiniciar el dispositivo Entonces el sistema muestra un mensaje visible al usuario indicando que la sesión ha sido restaurada Y el usuario puede continuar usando el sistema sin necesidad de re-autenticarse Y el mensaje desaparece o puede ser descartado sin bloquear la navegación | Se añadió que el mensaje no debe bloquear la navegación, requisito de usabilidad implícito. Se precisó que el usuario no debe re-autenticarse al restaurar la sesión para distinguir este flujo del inicio de sesión manual. La redacción se ajustó para describir el comportamiento observable del sistema en vez del comportamiento esperado del usuario. |
| TC-07   | HU-04  | Dado que la sesión se restaura automáticamente Cuando el sistema intenta restaurar mi sesión Entonces debe validar la identidad del usuario mediante los tokens de sesión Y debe garantizar que no haya acceso no autorizado | Dado que la sesión se restaura automáticamente Cuando el sistema procesa el token de sesión almacenado Entonces valida que el token corresponde al usuario original y no ha sido alterado Y si la validación es exitosa, restaura la sesión sin solicitar credenciales Y si la validación falla (token inválido o manipulado), redirige al usuario a la pantalla de inicio de sesión | El resultado esperado original era demasiado abstracto ("garantizar que no haya acceso no autorizado"). Se especificaron los dos flujos posibles del mecanismo de validación (éxito y falla), haciendo el caso ejecutable y verificable, conforme al CA-6. Esto también cubre el escenario de TC-09 desde la perspectiva del servidor. |
| TC-08   | HU-04  | Dado que la sesión se restaura automáticamente Cuando el sistema procesa las cookies o tokens de sesión Entonces debe proteger los datos sensibles mediante cifrado Y no debe exponer información sensible en las solicitudes o respuestas del servidor | Dado que la sesión se restaura automáticamente Cuando el sistema envía o recibe el token de sesión entre el navegador y el servidor Entonces la transmisión ocurre bajo protocolo seguro (HTTPS) Y el token no aparece expuesto en la URL ni en logs accesibles al usuario Y no se incluyen datos personales (nombre, correo, contraseña) en el payload de la respuesta | Se reemplazó la afirmación genérica "cifrado" por los controles técnicos observables: uso de HTTPS, ausencia del token en la URL y ausencia de datos personales en la respuesta. Esto permite verificar el caso mediante herramientas de red (DevTools), haciéndolo ejecutable según los principios ISTQB de resultados esperados concretos y alineado con OWASP A02:2021. |
| TC-09   | HU-04  | Dado que la sesión se restaura automáticamente Cuando los tokens de sesión son inválidos o han sido manipulados Entonces el sistema no debe restaurar la sesión Y debo ser redirigido a la pantalla de inicio de sesión | Dado que el token de sesión almacenado en el navegador ha sido manipulado o es inválido Cuando el sistema intenta restaurar la sesión al acceder a la aplicación Entonces el sistema detecta que el token no es válido Y invalida cualquier sesión asociada a ese token en el servidor Y redirige al usuario a la pantalla de inicio de sesión Y no muestra ningún contenido restringido durante el proceso | Se añadió la invalidación del token en el servidor como paso explícito, ya que detener la restauración solo en el cliente no es suficiente contra ataques de manipulación de tokens (OWASP A07:2021). Se añadió la condición de que no se muestre contenido protegido, consistente con el comportamiento de seguridad definido en el contexto de negocio. |
| TC-10   | HU-04  | Dado que la sesión se restaura automáticamente Cuando el navegador bloquea las cookies necesarias para la autenticación Entonces el sistema no debe restaurar la sesión Y debo ser redirigido a la pantalla de inicio de sesión Y el sistema debe mostrar un mensaje indicando que las cookies están bloqueadas | Dado que el navegador tiene bloqueadas las cookies de terceros o de sesión Cuando el sistema intenta restaurar la sesión al cargar la aplicación Entonces no puede recuperar el token de sesión Y redirige al usuario a la pantalla de inicio de sesión Y muestra un mensaje de error controlado (sin exponer detalles técnicos internos) indicando que no fue posible restaurar la sesión | Se corrigió la redacción del mensaje: en lugar de indicar que "las cookies están bloqueadas" (lo cual expone detalles técnicos internos), el sistema debe mostrar un mensaje genérico controlado, conforme al principio de gestión segura de errores (OWASP A05:2021). Se ajustó la precondición para distinguir entre cookies de sesión y cookies de terceros, mejorando la precisión del escenario de prueba. |


## Casos de Prueba HU-05: Cierre de sesión seguro desde el menú de navegación

### TC-01: Cerrar sesión correctamente desde el menú de navegación
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

### TC-02: Intento de acceso a secciones internas después de cerrar sesión
```
Dado que el usuario ha cerrado sesión correctamente
Cuando intenta acceder a una sección interna escribiendo la URL directamente en el navegador
Entonces el sistema redirige al usuario automáticamente a la pantalla de inicio de sesión
Y no se muestra contenido de la sección interna
```

### TC-03: Mensaje de error controlado al fallar el cierre de sesión
```
Dado que el usuario tiene una sesión activa en el sistema
Y el sistema presenta un fallo al procesar el cierre de sesión
Cuando el usuario selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces se muestra un mensaje de error controlado indicando que no se pudo cerrar la sesión
Y se ofrece al usuario la opción de reintentar el cierre de sesión
```

### TC-04: Eliminación de datos de sesión en el navegador al cerrar sesión
```
Dado que el usuario tiene una sesión activa en el sistema
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces toda la información de la sesión se elimina del almacenamiento local del navegador
Y no queda información sensible visible en el navegador tras el cierre de sesión
```

### TC-05: Redirección al inicio de sesión tras cerrar sesión
```
Dado que el usuario tiene una sesión activa en el sistema
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el usuario es redirigido automáticamente a la pantalla de inicio de sesión
Y el sistema no permite acceder a secciones internas sin iniciar sesión nuevamente
```

### TC-06: Actualización del menú de navegación tras cerrar sesión
```
Dado que el usuario tiene una sesión activa en el sistema
Y el menú de navegación muestra opciones exclusivas para usuarios autenticados
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el menú de navegación deja de mostrar opciones exclusivas para usuarios autenticados
Y refleja el estado de visitante/no autenticado
```

### TC-07: Transmisión cifrada al cerrar sesión
```
Dado que el usuario tiene una sesión activa en el sistema
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el sistema asegura que la transmisión de datos para invalidar la sesión es cifrada
Y no se expone información sensible durante el proceso
```

### TC-08: Registro del evento de cierre de sesión para auditoría
```
Dado que el usuario tiene una sesión activa en el sistema
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el evento de cierre de sesión queda registrado en el sistema
Y el registro incluye la fecha, hora y usuario que realizó el cierre de sesión
```

### TC-09: Comportamiento en alta concurrencia al cerrar sesión
```
Dado que múltiples usuarios tienen sesiones activas en el sistema
Y el sistema está procesando múltiples solicitudes simultáneamente
Cuando el usuario selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el sistema procesa la solicitud de cierre de sesión sin errores
Y el usuario es redirigido a la pantalla de inicio de sesión
```

### TC-10: Indicador de carga al procesar el cierre de sesión
```
Dado que el usuario tiene una sesión activa en el sistema
Cuando selecciona la opción "Cerrar sesión" en el menú de navegación
Entonces el sistema muestra un indicador de carga mientras se procesa el cierre de sesión
Y el indicador desaparece una vez que el usuario es redirigido a la pantalla de inicio de sesión
```

| ID      | HU | Caso de Prueba generado por la instrucción | Ajuste del realizado por el probador | ¿Por qué se ajustó? |
| :--- | :--- | :--- | :--- | :--- |
| TC-01   | HU-05  | Dado que el usuario tiene una sesión activa en el sistema Y el usuario está en una sección interna del sistema Cuando selecciona la opción "Cerrar sesión" en el menú de navegación Entonces el sistema invalida la sesión activa en el servidor Y el usuario es redirigido automáticamente a la pantalla de inicio de sesión Y el menú de navegación deja de mostrar opciones exclusivas para usuarios autenticados Y toda la información de la sesión se elimina del almacenamiento local del navegador Y el evento de cierre de sesión queda registrado para auditoría | | |
| TC-02   | HU-05  | Dado que el usuario ha cerrado sesión correctamente Cuando intenta acceder a una sección interna escribiendo la URL directamente en el navegador Entonces el sistema redirige al usuario automáticamente a la pantalla de inicio de sesión Y no se muestra contenido de la sección interna | | |
| TC-03   | HU-05  | Dado que el usuario tiene una sesión activa en el sistema Y el sistema presenta un fallo al procesar el cierre de sesión Cuando el usuario selecciona la opción "Cerrar sesión" en el menú de navegación Entonces se muestra un mensaje de error controlado indicando que no se pudo cerrar la sesión Y se ofrece al usuario la opción de reintentar el cierre de sesión | | |
| TC-04   | HU-05  | Dado que el usuario tiene una sesión activa en el sistema Cuando selecciona la opción "Cerrar sesión" en el menú de navegación Entonces toda la información de la sesión se elimina del almacenamiento local del navegador Y no queda información sensible visible en el navegador tras el cierre de sesión | | |
| TC-05   | HU-05  | Dado que el usuario tiene una sesión activa en el sistema Cuando selecciona la opción "Cerrar sesión" en el menú de navegación Entonces el usuario es redirigido automáticamente a la pantalla de inicio de sesión Y el sistema no permite acceder a secciones internas sin iniciar sesión nuevamente | | |
| TC-06   | HU-05  | Dado que el usuario tiene una sesión activa en el sistema Y el menú de navegación muestra opciones exclusivas para usuarios autenticados Cuando selecciona la opción "Cerrar sesión" en el menú de navegación Entonces el menú de navegación deja de mostrar opciones exclusivas para usuarios autenticados Y refleja el estado de visitante/no autenticado | | |
| TC-07   | HU-05  | Dado que el usuario tiene una sesión activa en el sistema Cuando selecciona la opción "Cerrar sesión" en el menú de navegación Entonces el sistema asegura que la transmisión de datos para invalidar la sesión es cifrada Y no se expone información sensible durante el proceso | | |
| TC-08   | HU-05  | Dado que el usuario tiene una sesión activa en el sistema Cuando selecciona la opción "Cerrar sesión" en el menú de navegación Entonces el evento de cierre de sesión queda registrado en el sistema Y el registro incluye la fecha, hora y usuario que realizó el cierre de sesión | | |
| TC-09   | HU-05  | Dado que múltiples usuarios tienen sesiones activas en el sistema Y el sistema está procesando múltiples solicitudes simultáneamente Cuando el usuario selecciona la opción "Cerrar sesión" en el menú de navegación Entonces el sistema procesa la solicitud de cierre de sesión sin errores Y el usuario es redirigido a la pantalla de inicio de sesión | | |
| TC-10   | HU-05  | Dado que el usuario tiene una sesión activa en el sistema Cuando selecciona la opción "Cerrar sesión" en el menú de navegación Entonces el sistema muestra un indicador de carga mientras se procesa el cierre de sesión Y el indicador desaparece una vez que el usuario es redirigido a la pantalla de inicio de sesión | | |