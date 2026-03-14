# Refinamiento de Historias de Usuario — Sistema de Turnos EPS

## Tabla de Comparación

| HU original | HU refinada por la instrucción | Diferencias detectadas |
| :--- | :--- | :--- |
| [HU-02 Original](#hu-02-inicio-de-sesión-original) | [HU-02 Refinada](#hu-02-inicio-de-sesión-seguro-para-empleados-y-administradores-refinada) | La instrucción ajustó quién puede iniciar sesión (solo Administrador o Empleado), aclaró las áreas a las que se accede y añadió qué pasa si alguien intenta entrar sin haber iniciado sesión y añadió mejores prácticas de seguridad y criterios de aceptación. |
| [HU-04 Original](#hu-04-restauración-de-sesión-original) | [HU-04 Refinada](#hu-04-restauración-automática-de-sesión-refinada) | La instrucción especificó el tiempo de validez de la sesión, los escenarios en los que se restaura automáticamente y añadió mejores criterios de aceptación. |
| [HU-05 Original](#hu-05-cierre-de-sesión-original) | [HU-05 Refinada](#hu-05-cierre-de-sesión-seguro-desde-el-menú-de-navegación-refinada) | La instrucción aclaró que el cierre de sesión es inmediato, especificó que el sistema elimina el acceso del usuario al hacerlo y añadió criterios de aceptación mejorados. |

---

### HU-02: Inicio de sesión (Original)

**ID:** HU-02  
**Módulo:** Autenticación  
**Prioridad:** Alta  
**Versión:** 1.0

**Descripción**

Como **usuario registrado**, quiero iniciar sesión con mi correo electrónico y contraseña, para acceder al panel principal y a las demás secciones internas de la plataforma.

**Criterios de aceptación**

- El formulario de inicio de sesión solicita correo electrónico y contraseña.
- El sistema no permite continuar si alguno de los dos campos está vacío.
- Al ingresar credenciales correctas, el usuario accede al panel principal y su sesión queda activa.
- Si las credenciales son incorrectas, el sistema informa el error sin redirigir al usuario a otra pantalla.
- Si el usuario llega a esta pantalla inmediatamente después de haber creado su cuenta, ve un mensaje de bienvenida confirmando la creación exitosa de su cuenta.
- El mensaje de bienvenida desaparece automáticamente transcurridos 4 segundos y no vuelve a aparecer si el usuario recarga la página.
- La pantalla de inicio de sesión es pública y accesible sin necesidad de haber ingresado previamente.

**Escenarios de validación**

| ID            | Escenario                             | Resultado esperado                    |
| :------------ | :------------------------------------ | :------------------------------------ |
| CA-AUTH-02-01 | Credenciales correctas                | El usuario accede al panel principal  |
| CA-AUTH-02-02 | Credenciales incorrectas              | Se muestra mensaje de error           |
| CA-AUTH-02-03 | Campos vacíos al enviar               | El sistema no procesa el ingreso      |
| CA-AUTH-02-04 | Usuario viene de registro exitoso     | Se muestra mensaje de bienvenida      |
| CA-AUTH-02-05 | Mensaje de bienvenida tras 4 segundos | El mensaje desaparece automáticamente |

---

### HU-02: Inicio de sesión seguro para empleados y administradores (Refinada)

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

### HU-04: Restauración de sesión (Original)

**ID:** HU-04  
**Módulo:** Autenticación  
**Prioridad:** Media  
**Versión:** 1.0

**Descripción:**

Como **usuario autenticado**, quiero que al recargar o volver a abrir la aplicación mi sesión se restaure automáticamente, para no tener que iniciar sesión cada vez que regreso al sistema.

**Criterios de aceptación:**

- Al recargar la página o volver a la aplicación, el sistema verifica automáticamente si existe una sesión activa sin que el usuario tenga que hacer nada.
- Si la sesión sigue siendo válida, el usuario permanece autenticado y puede continuar usando la aplicación sin interrupciones.
- Si la sesión expiró o no existe, el sistema trata al usuario como no autenticado y le solicita que inicie sesión nuevamente.
- Durante la verificación inicial de la sesión, el sistema no muestra ni oculta contenido de forma abrupta; mantiene una transición visible y controlada.

**Escenarios de validación**

| ID | Escenario | Resultado esperado |
| :--- | :--- | :--- |
| CA-AUTH-04-01 | Recarga con sesión válida | El usuario permanece autenticado |
| CA-AUTH-04-02 | Recarga sin sesión o con sesión expirada | El usuario debe iniciar sesión nuevamente |
| CA-AUTH-04-03 | Verificación inicial de sesión | No se muestra contenido restringido durante la verificación |

---

### HU-04: Restauración Automática de Sesión (Refinada)

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

### HU-05: Cierre de sesión (Original)

**ID:** HU-05  
**Módulo:** Autenticación  
**Prioridad:** Media  
**Versión:** 1.0

**Descripción**

Como **usuario autenticado**, quiero poder cerrar mi sesión desde el menú de navegación, para garantizar que mi acceso quede desactivado cuando ya no estoy usando la aplicación.

**Criterios de aceptación**

- El menú de navegación superior muestra una opción visible para cerrar sesión cuando el usuario está autenticado.
- Al presionar la opción de cierre de sesión, el sistema desactiva la sesión activa del usuario de forma inmediata.
- Tras cerrar la sesión, el usuario es llevado automáticamente a la pantalla de inicio de sesión.
- Una vez cerrada la sesión, el usuario no puede regresar a secciones protegidas usando el botón "atrás" del navegador; el sistema lo redirige nuevamente al inicio de sesión.
- El menú de navegación desaparece después del cierre de sesión.

**Escenarios de validación**

| ID | Escenario | Resultado esperado |
| :--- | :--- | :--- |
| CA-AUTH-05-01 | Cierre de sesión exitoso | Sesión desactivada y redirección a inicio de sesión |
| CA-AUTH-05-02 | Intento de acceso tras cerrar sesión | El sistema redirige a la pantalla de inicio de sesión |
| CA-AUTH-05-03 | Menú de navegación tras cierre de sesión | El menú no aparece |

---

### HU-05: Cierre de sesión seguro desde el menú de navegación (Refinada)

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
