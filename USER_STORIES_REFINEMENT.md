# Refinamiento de Historias de Usuario — Sistema de Turnos EPS

## HU-02: Inicio de sesión seguro para empleados y administradores

**Descripción:**  
Como **empleado o administrador autorizado**, quiero iniciar sesión en la plataforma utilizando mi correo electrónico y contraseña, para acceder al panel principal (dashboard) y a las secciones internas que me permitan gestionar y consultar turnos de atención en la EPS.

**Criterios de aceptación:**

1. El usuario debe ingresar un correo electrónico válido y una contraseña en el formulario de inicio de sesión.
2. Si las credenciales son correctas, el sistema debe redirigir al usuario al panel principal (dashboard) donde podrá visualizar el historial de turnos asignados y acceder a las secciones internas permitidas.
3. Si las credenciales son incorrectas, se debe mostrar un mensaje de error claro ("Correo o contraseña incorrectos").
4. Si el sistema de autenticación no está disponible, se debe mostrar un mensaje de error controlado ("No es posible iniciar sesión en este momento. Por favor, intente más tarde").
5. Las credenciales deben procesarse y almacenarse de manera segura, siguiendo las buenas prácticas de cifrado y protección de datos personales.
6. El acceso al panel principal y a las secciones internas está restringido únicamente a empleados y administradores con sesión activa; cualquier intento de acceso sin sesión válida debe redirigir automáticamente a la pantalla de inicio de sesión.
7. Los datos ingresados en el formulario deben ser validados y limpiados antes de ser procesados por el sistema para prevenir intentos maliciosos.
8. El menú de navegación superior solo debe aparecer cuando el usuario tenga una sesión activa.
9. La sesión del usuario debe ser gestionada de forma segura, y el sistema debe detectar automáticamente si la sesión expira o es inválida, solicitando al usuario que inicie sesión nuevamente.

---

## HU-04: Restauración Automática de Sesión

**Descripción:**  
Como usuario autenticado, quiero que al recargar la página, cerrar y volver a abrir el navegador, o reiniciar el dispositivo, mi sesión se restaure automáticamente dentro de las 24 horas desde la última actividad, para no tener que iniciar sesión cada vez que regreso al sistema y mejorar mi experiencia de uso.

**Criterios de Aceptación:**

1. **Recarga de la Página**
   - Dado que soy un usuario autenticado,
   - cuando recargo la página,
   - mi sesión debe restaurarse automáticamente si no ha expirado (dentro de las 24 horas desde la última actividad).

2. **Cierre y Reapertura del Navegador**
   - Dado que soy un usuario autenticado,
   - cuando cierro y vuelvo a abrir el navegador dentro de las 24 horas desde la última actividad,
   - mi sesión debe restaurarse automáticamente.

3. **Reinicio del Dispositivo**
   - Dado que soy un usuario autenticado,
   - cuando reinicio el dispositivo y vuelvo a abrir el navegador dentro de las 24 horas desde la última actividad,
   - mi sesión debe restaurarse automáticamente.

4. **Expiración de Sesión**
   - Dado que mi sesión ha expirado (más de 24 horas desde la última actividad),
   - cuando intento acceder al sistema,
   - debo ser redirigido a la pantalla de inicio de sesión.

5. **Mecanismos de Restauración**
   - Dado que la sesión se restaura automáticamente,
   - el sistema debe utilizar cookies o tokens de sesión para mantener la autenticación,
   - y debe mostrar un mensaje al usuario indicando que la sesión ha sido restaurada.

6. **Medidas de Seguridad**
   - Dado que la sesión se restaura automáticamente,
   - el sistema debe implementar medidas de seguridad para evitar el acceso no autorizado,
   - como la validación de la identidad del usuario y la protección de los datos sensibles.

---

## HU-05: Cierre de sesión seguro desde el menú de navegación

**Descripción:**
Como **usuario autenticado**, quiero poder cerrar mi sesión desde el menú de navegación, para asegurar que mi acceso al sistema quede completamente desactivado al finalizar mi uso de la aplicación, garantizando la protección de mi información y evitando accesos no autorizados.

**Criterios de Aceptación:**

1. Al seleccionar la opción “Cerrar sesión” en el menú de navegación, el sistema debe invalidar la sesión activa del usuario en el servidor.
2. El usuario debe ser redirigido automáticamente a la pantalla de inicio de sesión después de cerrar la sesión.
3. El menú de navegación debe actualizarse y dejar de mostrar opciones exclusivas para usuarios autenticados, reflejando el estado de visitante/no autenticado.
4. Si ocurre un error en el proceso de cierre de sesión, se debe mostrar un mensaje de error controlado y ofrecer al usuario la opción de reintentar.
5. El sistema no debe permitir el acceso a secciones internas o restringidas después del cierre de sesión; cualquier intento de acceso debe redirigir al usuario a la pantalla de inicio de sesión.
6. Toda la información de la sesión debe eliminarse de la interfaz y del almacenamiento local del navegador al cerrar sesión.
7. El evento de cierre de sesión debe ser registrado para fines de auditoría y trazabilidad.
8. El cierre de sesión debe cumplir con los mecanismos de seguridad establecidos en el proyecto, asegurando la transmisión cifrada y la correcta invalidación de tokens.

---

## Tabla de Comparación entre Historias de Usuario Originales y Refinadas

| HU original | HU refinada por la instrucción | Diferencias detectadas |
| :--- | :--- | :--- |
| "Como **usuario registrado**, quiero iniciar sesión con mi correo electrónico y contraseña, para acceder al panel principal y a las demás secciones internas de la plataforma." | "Como empleado o administrador autorizado, quiero iniciar sesión en la plataforma utilizando mi correo electrónico y contraseña, para acceder al panel principal (dashboard) y a las secciones internas que me permitan gestionar y consultar turnos de atención en la EPS." | La instrucción ajustó quién puede iniciar sesión (solo Administrador o Empleado), aclaró las áreas a las que se accede y añadió qué pasa si alguien intenta entrar sin haber iniciado sesión. |
| "Como **usuario autenticado**, quiero que al recargar o volver a abrir la aplicación mi sesión se restaure automáticamente, para no tener que iniciar sesión cada vez que regreso al sistema." | "Como usuario autenticado, quiero que al recargar la página, cerrar y volver a abrir el navegador, o reiniciar el dispositivo, mi sesión se restaure automáticamente dentro de las 24 horas desde la última actividad, para no tener que iniciar sesión cada vez que regreso al sistema y mejorar mi experiencia de uso." | La instrucción especificó el tiempo de validez de la sesión y los escenarios en los que se restaura automáticamente. |
| "Como **usuario autenticado**, quiero poder cerrar mi sesión desde el menú de navegación, para garantizar que mi acceso quede desactivado cuando ya no estoy usando la aplicación." | "Como usuario autenticado, quiero poder cerrar mi sesión desde el menú de navegación, para asegurar que mi acceso al sistema quede completamente desactivado al finalizar mi uso de la aplicación, garantizando la protección de mi información y evitando accesos no autorizados." | La instrucción aclaró que el cierre de sesión es inmediato, especificó que el sistema elimina el acceso del usuario al hacerlo. |