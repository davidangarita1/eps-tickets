# Contexto de Negocio — Sistema de Turnos EPS

## 1. Descripción del Proyecto

- **Nombre del Proyecto:** Sistema de Turnos EPS
- **Objetivo del Proyecto:** Facilitar la gestión de turnos de atención en una EPS a través de una plataforma en línea. El sistema permite que cualquier persona pueda consultar los turnos disponibles o crear su cuenta de forma libre, mientras que las funciones de administración y registro de turnos están reservadas para el personal autorizado que haya ingresado al sistema.

---

## 2. Flujos Críticos del Negocio

- **Principales Flujos de Trabajo:**
  - **Crear cuenta:** El formulario de registro es públicamente visible, pero internamente exclusivo para empleados. Un empleado completa un formulario con nombre, correo y contraseña del nuevo empleado; el sistema valida que el registrador sea un empleado autorizado. El perfil se asigna automáticamente. Al finalizar, si la validación es exitosa, el sistema confirma que la cuenta fue creada.
  - **Ingresar al sistema:** Un usuario registrado escribe su correo y contraseña. Si los datos son correctos, el sistema lo lleva al panel principal.
  - **Salir del sistema:** Desde el menú superior, el usuario puede cerrar su sesión en cualquier momento. El sistema lo regresa a la pantalla de ingreso.
  - **Restricción de acceso:** Si alguien intenta ingresar directamente al panel principal o al módulo de turnos sin haber iniciado sesión, el sistema lo redirige automáticamente a la pantalla de ingreso.
  - **Solicitud de turnos:** Los usuarios con sesión activa pueden registrar nuevas solicitudes de turno, las cuales el sistema recibe y procesa de forma ordenada.

- **Módulos o Funcionalidades Críticas:**
  - Gestión de acceso: creación de cuentas de empleados, inicio de sesión, cierre de sesión y recuperación de sesión activa.
  - Control de áreas restringidas: protección automática de las secciones internas para que solo el personal autorizado pueda acceder.
  - Menú de navegación condicional: el menú principal solo aparece cuando el usuario ha iniciado sesión.
  - Gestión de turnos: solicitud y visualización de turnos con actualización inmediata en pantalla.

---

## 3. Reglas de Negocio y Restricciones

- **Reglas de Negocio Relevantes:**
  - El panel principal y el módulo de registro de turnos son exclusivos para personal autorizado (administradores y empleados) que hayan iniciado sesión. Cualquier intento de acceso sin sesión redirige a la pantalla de ingreso.
  - El formulario de creación de cuentas de empleados es públicamente visible pero internamente exclusivo para empleados autenticados. El sistema valida que el registrador sea un empleado mediante el dominio del correo o lista de autorizados; intentos de no-empleados son rechazados.
  - El menú de navegación superior solo aparece para usuarios con sesión activa; en las pantallas públicas no se muestra.
  - Las credenciales de acceso se protegen mediante mecanismos seguros de almacenamiento; las contraseñas nunca quedan visibles ni almacenadas más allá del momento del ingreso.
  - Toda la información ingresada en los formularios se valida y limpia antes de ser procesada, para proteger el sistema de intentos maliciosos.
  - Las funcionalidades de inicio de sesión con redes sociales o renovación automática de sesión no están contempladas en esta versión del sistema.

- **Regulaciones o Normativas:**
  - Los datos personales y credenciales se transmiten de forma cifrada, cumpliendo con las buenas prácticas de protección de información.
  - La identidad del usuario se verifica mediante un mecanismo de sesión seguro generado por el servidor, que el sistema valida sin exponer información sensible.
  - El sistema aplica políticas de seguridad en todas las pantallas para evitar la ejecución de contenido no autorizado.

---

## 4. Perfiles de Usuario y Roles

- **Perfiles o Roles de Usuario en el Sistema:**
  - **Administrador:** Personal con responsabilidades de gestión. Puede ingresar al panel principal y al módulo de turnos para ver el estado de la operación y administrar solicitudes.
  - **Empleado:** Personal operativo de la EPS. Puede ingresar al panel principal y al módulo de turnos para solicitar y consultar turnos.
  - **Visitante (sin sesión):** Cualquier persona que accede al sitio sin haber iniciado sesión. Solo puede ver la pantalla pública de turnos e inicio de sesión; no puede crear cuentas.

- **Permisos y Limitaciones de Cada Perfil:**
  - En esta versión, los empleados autorizados pueden crear cuentas de empleados a través del formulario de registro.
  - Ningún usuario, independientemente de su perfil, puede acceder a las secciones internas si no tiene una sesión válida activa.
  - El visitante no puede registrar ni consultar turnos desde el módulo interno; solo puede hacerlo una vez que haya iniciado sesión.

---

## 5. Condiciones del Entorno Técnico

- **Plataformas Soportadas:** Aplicación web accesible desde cualquier navegador moderno en computador o dispositivo móvil. No cuenta con versión instalable en iOS o Android.

- **Tecnologías o Integraciones Clave:**
  - **Interfaz de usuario:** Plataforma web moderna con actualización inmediata de pantalla sin necesidad de recargar la página.
  - **Servicio de autenticación y turnos:** Componente del sistema encargado de validar el acceso de los usuarios y recibir las solicitudes de turno.
  - **Procesamiento de turnos:** Componente encargado de atender y gestionar las solicitudes de turno recibidas de forma ordenada y continua.
  - **Cola de mensajes:** Mecanismo interno que garantiza que ninguna solicitud de turno se pierda, aunque el volumen de peticiones sea alto.
  - **Almacenamiento de datos:** Base de datos donde se guardan de forma segura los usuarios registrados y el historial de turnos.
  - **Notificaciones en tiempo real:** El sistema actualiza automáticamente la pantalla de turnos sin que el usuario tenga que refrescar la página.
  - **Gestión de sesiones:** Las sesiones de usuario se protegen mediante credenciales seguras generadas por el servidor, sin almacenar información sensible en el navegador.
  - **Tolerancia a fallos:** El sistema cuenta con mecanismos que detectan cuando un servicio no responde y evitan que el fallo se propague al usuario final, mostrando un mensaje de error controlado.
  - **Entorno de operación:** Los tres componentes del sistema (interfaz, servicio principal y procesador de turnos) se ejecutan de forma aislada y coordinada en contenedores, facilitando su despliegue y mantenimiento.

---

## 6. Casos Especiales o Excepciones

- **Escenarios Alternos o Excepciones que Deben Considerarse:**
  - **Pantalla en blanco al cargar:** Mientras el sistema verifica si el usuario tiene una sesión activa, se muestra un indicador de carga para evitar que la pantalla parpadee o muestre contenido restringido antes de la verificación.
  - **Servicio de acceso no disponible:** Si el sistema de autenticación no responde, el formulario muestra un mensaje de error genérico amigable, sin exponer detalles del problema interno, y el usuario puede reintentar.
  - **Sesión vencida o inválida:** Si la sesión del usuario expira o es inválida, el sistema detecta esto automáticamente al intentar acceder a una sección protegida y solicita al usuario que inicie sesión nuevamente.
  - **Diferencia entre creación de cuenta y registro de turnos:** La opción para crear una cuenta de usuario y el módulo para registrar turnos de atención son funciones distintas con accesos separados, para evitar confusión entre ambos procesos.
  - **Alta concurrencia de solicitudes:** El sistema está diseñado para manejar múltiples solicitudes de turno de forma simultánea sin degradar la experiencia del usuario ni perder datos.
  - **Intento de acceso directo a secciones restringidas:** Si un usuario escribe directamente en el navegador la dirección de una sección protegida sin tener sesión activa, el sistema lo redirige automáticamente a la pantalla de ingreso, tanto antes de cargar la página como durante la navegación interna.
