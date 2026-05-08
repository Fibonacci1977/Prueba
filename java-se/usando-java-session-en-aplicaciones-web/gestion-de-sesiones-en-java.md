# Gestión de sesiones en Java

La gestión de sesiones en Java se utiliza para mantener los datos específicos del usuario entre múltiples solicitudes en una aplicación web. Dado que HTTP no tiene estado, ayuda a preservar el estado del usuario entre interacciones. Garantiza la continuidad hasta que la sesión expire o el usuario cierre sesión.

* Entre las técnicas más comunes se incluyen las cookies, la reescritura de URL, los campos ocultos y HttpSession.
* Mejora la experiencia del usuario al conservar el estado de inicio de sesión y las preferencias.
* Imprescindible para gestionar la autenticación y la entrega de contenido personalizado.

### Sesión <a href="#session" id="session"></a>

Una sesión es un mecanismo del lado del servidor que se utiliza para almacenar datos de usuario entre múltiples solicitudes en una aplicación web. Ayuda a mantener el estado del usuario y garantiza la continuidad durante la interacción.

* Se crea automáticamente cuando un usuario interactúa con la aplicación.
* Se identifica mediante un ID de sesión único almacenado en el lado del cliente.
* Caduca por inactividad o cuando se invalida explícitamente.

### Importancia de la gestión de sesiones <a href="#importance-of-session-managements" id="importance-of-session-managements"></a>

La gestión de sesiones es esencial tanto para la funcionalidad como para la seguridad en las aplicaciones web. He aquí por qué:

* Almacena de forma segura las credenciales de usuario (a menudo cifradas) para admitir funciones como el inicio de sesión automático.
* Gracias al cifrado, los datos confidenciales pueden almacenarse de forma segura.
* Las sesiones permiten tiempos de respuesta más rápidos al acceder rápidamente a los datos temporales.
* Ayudan a restringir el acceso desde fuentes no autorizadas, mejorando la seguridad de las aplicaciones y de la red.

### Función de las cookies y otros mecanismos de seguimiento <a href="#role-of-cookies-and-other-tracking-mechanisms" id="role-of-cookies-and-other-tracking-mechanisms"></a>

Las cookies y los mecanismos de seguimiento son esenciales para la gestión de sesiones. Ayudan a los sitios web a reconocer a los usuarios, almacenar preferencias y garantizar experiencias seguras y personalizadas.

#### 1. Cookies de sesión <a href="#id-1-session-cookies" id="id-1-session-cookies"></a>

* **Finalidad:** Gestionar datos temporales de la sesión, como el estado de inicio de sesión.
* **Cómo funciona:** Cuando el usuario inicia sesión, se crea un ID de sesión único que se almacena en una cookie.
* **Caducidad:** Se elimina automáticamente al cerrar el navegador.
* **Uso:** Permite el inicio de sesión automático durante una sesión sin necesidad de volver a introducir las credenciales.

#### 2. Cookies persistentes <a href="#id-2-persistent-cookies" id="id-2-persistent-cookies"></a>

* **Finalidad:** Almacenar las preferencias y la configuración del usuario a largo plazo.
* **Cómo funciona:** Permanece almacenado en el dispositivo del usuario incluso después de cerrar el navegador.
* **Uso:** Permite experiencias personalizadas en múltiples visitas.

#### 3. Mecanismos de seguimiento <a href="#id-3-tracking-mechanisms" id="id-3-tracking-mechanisms"></a>

* **Seguimiento de usuarios:** JavaScript o los píxeles de seguimiento monitorizan el comportamiento del usuario para realizar análisis y mejorar la experiencia de usuario.
* **Cookies de terceros:** Establecidas por dominios externos para el seguimiento entre sitios web y la publicidad dirigida.

#### 4. Medidas de seguridad <a href="#id-4-security-measures" id="id-4-security-measures"></a>

* **Tokens CSRF:** Evite acciones no autorizadas almacenando tokens anti-CSRF en las cookies.
* **Indicadores de seguridad y HttpOnly:**
* **Seguro:** Garantiza que las cookies solo se envíen a través de HTTPS.
* **HttpOnly:** Impide que los scripts del lado del cliente accedan a la cookie, reduciendo así los riesgos de ataque.

### ¿Cómo conseguir una sesión? <a href="#how-to-get-a-session" id="how-to-get-a-session"></a>

* En los servlets de Java, las sesiones se gestionan mediante el objeto HttpSession.
* HttpSession forma parte del paquete javax.servlet.http.
* Permite realizar un seguimiento de la sesión del cliente y almacenar la información del usuario.
* Se utiliza para almacenar y recuperar atributos en múltiples solicitudes de clientes.
* Ayuda a gestionar el estado de la sesión y los datos del usuario de forma eficiente.

#### Recuperación de HttpSession en Servlets <a href="#retrieving-httpsession-in-servlets" id="retrieving-httpsession-in-servlets"></a>

1\. Utilice request.getSession() para obtener la sesión actual o crear una nueva si no existe.

> HttpSession sesión = solicitud.getSession();

2\. Utilice request.getSession(true) para forzar la creación de una nueva sesión si no existe ninguna.

> HttpSession sesión = solicitud.getSession(true);

3\. Utilice request.getSession(false) para obtener solo una sesión existente (devuelve null si no existe ninguna).

> HttpSession sesión = solicitud.getSession(false);

### Métodos comunes <a href="#common-methods" id="common-methods"></a>

#### 1. setAttribute(String name, Object value) <a href="#id-1-setattributestring-name-object-value" id="id-1-setattributestring-name-object-value"></a>

Esto asocia un valor con un nombre en la sesión, lo que permite almacenar y acceder a los datos en múltiples solicitudes.

> HttpSession sesión = solicitud.getSession(); sesión.setAttribute("username", "GFG");

#### 2. obtenerAtributo(Cadena nombre) <a href="#id-2-getattributestring-name" id="id-2-getattributestring-name"></a>

Devuelve el valor asociado al nombre especificado en la sesión, utilizado para recuperar datos almacenados previamente.

> HttpSession session = request.getSession(); String username = (String) session.getAttribute("username");

#### 3. removeAttribute(String name) <a href="#id-3-removeattributestring-name" id="id-3-removeattributestring-name"></a>

Elimina de la sesión el atributo con el nombre especificado.

> HttpSession sesión = solicitud.getSession(); sesión.removeAttribute("username");

#### 4. invalidar() <a href="#id-4-invalidate" id="id-4-invalidate"></a>

Una vez finalizados los servicios, es necesario destruir el objeto de sesión. La sintaxis es la siguiente.

> HttpSession sesión = solicitud.getSession(); sesión.invalidate();

**Ejemplo**

import javax.servlet.http.\*;@WebServlet("/api")public class GFG extends HttpServlet {    protected void doGet(HttpServletRequest request, HttpServletResponse response) {        // Retrieve the HttpSession object        HttpSession session = request.getSession();        // Use HttpSession methods        session.setAttribute("username", "GFG");        String value = (String) session.getAttribute("username");    \}}

**Explicación:** En el ejemplo anterior, se llama al método getSession() del objeto HttpServletRequest para recuperar la HttpSession. Una vez que se tiene el objeto HttpSession, se pueden usar sus métodos para establecer y recuperar los atributos de la sesión.

### Mecanismos de seguimiento de sesiones en servlets <a href="#session-tracking-mechanisms-in-servlets" id="session-tracking-mechanisms-in-servlets"></a>

Para mantener la sesión entre un servidor web y un cliente web, se pueden utilizar los siguientes métodos.

#### 1. Galletas <a href="#id-1-cookies" id="id-1-cookies"></a>

* El servidor asigna un ID de sesión único al cliente en forma de cookie.
* En las solicitudes posteriores, el cliente envía esta cookie, lo que ayuda al servidor a identificar la sesión.
* Este método depende del navegador y puede que no funcione si las cookies están deshabilitadas o bloqueadas.
* Ejemplo de sintaxis:

> Cookie cookie = new Cookie("sessionId", "123456");\
> response.addCookie(cookie);

#### 2. Campos de formulario ocultos <a href="#id-2-hidden-form-fields" id="id-2-hidden-form-fields"></a>

* El servidor inserta un campo de entrada oculto con un ID de sesión en el formulario HTML:

> \<input type = "hidden" name = "sessionId" value = "12345">

* Esto envía el ID de sesión con cada envío de formulario, lo que permite al servidor realizar un seguimiento de la sesión.
* Solo funciona con envíos de formularios, no con hipervínculos estándar (\<a href="">), por lo tanto, no es adecuado para el seguimiento general de sesiones.

#### 3. Reescritura de URL <a href="#id-3-url-rewriting" id="id-3-url-rewriting"></a>

* El ID de sesión se añade a la URL como parámetro de consulta.
* Esto ayuda al servidor a identificar la sesión y procesar la solicitud del cliente.
* Funciona independientemente de la configuración del navegador (a diferencia de las cookies).
* No es adecuado para páginas estáticas, ya que las URL se generan dinámicamente.

**Ejemplo:**

> String urlWithSessionId = response.encodeURL("/api");

### Ciclo de vida de la sesión <a href="#session-lifecycle" id="session-lifecycle"></a>

Las etapas por las que pasa una sesión de usuario, desde su creación hasta su expiración, completan el ciclo de vida de la sesión. En el contexto de las aplicaciones web, este ciclo implica la gestión de datos específicos del usuario a lo largo de múltiples solicitudes de sesión. A continuación, se describen las etapas clave del ciclo de vida de la sesión.

#### 1. Creación de sesión <a href="#id-1-session-creation" id="id-1-session-creation"></a>

* **Activador:** La sesión se crea cuando el usuario inicia sesión por primera vez.
* **Acción:** El servidor crea una nueva HttpSession, genera un ID de sesión único y lo almacena (normalmente como una cookie) en el navegador del cliente.

#### 2. Configuración de atributos <a href="#id-2-attribute-setting" id="id-2-attribute-setting"></a>

* **Activador:** Tras la creación de la sesión, se añaden los atributos necesarios.
* **Acción:** Los atributos se almacenan utilizando setAttribute() de HttpSession, lo que permite acceder a ellos en múltiples solicitudes.

**Ejemplo:**

> HttpSession sesión = solicitud.getSession();\
> sesión.setAttribute("username", "GFG");

#### 3. Interacción con el cliente <a href="#id-3-client-interaction" id="id-3-client-interaction"></a>

* **Desencadenante:** El usuario realiza solicitudes adicionales mientras interactúa con la aplicación.
* **Acción:** El ID de sesión se envía con cada solicitud, lo que permite recuperar los datos mediante getAttribute().

**Ejemplo:**

> HttpSession session = request.getSession();\
> String username = (String) session.getAttribute("username");

#### 4. Invalidación de sesión <a href="#id-4-session-invalidation" id="id-4-session-invalidation"></a>

* **Desencadenante:** La sesión finaliza manualmente o tras un tiempo de inactividad.
* **Acción:** invalidate() elimina todos los datos de la sesión o esta caduca automáticamente después de un tiempo determinado.

> HttpSession sesión = solicitud.getSession(); sesión.invalidate();

#### 5. Caducidad de la sesión <a href="#id-5-session-expiration" id="id-5-session-expiration"></a>

* **Disparador:** Podemos configurar el tiempo de espera de la sesión, que es un tiempo máximo de existencia definido.
* **Acción:** Una vez finalizada la navegación, podemos eliminar los datos y las preferencias del usuario en función del intervalo máximo de tiempo de inactividad.

> HttpSession session = request.getSession();\
> // La sesión se invalidará después de 30 minutos de inactividad session.setMaxInactiveInterval(1800);

### Ejemplo de gestión de sesiones <a href="#example-of-session-management" id="example-of-session-management"></a>

El siguiente ejemplo muestra cómo crear una sesión, establecer y recuperar atributos y, finalmente, invalidar la sesión.

import java.io.IOException;import javax.servlet.ServletException;import javax.servlet.annotation.WebServlet;import javax.servlet.http.HttpServlet;import javax.servlet.http.HttpServletRequest;import javax.servlet.http.HttpServletResponse;import javax.servlet.http.HttpSession;@WebServlet("/api")public class GFG extends HttpServlet {    protected void doGet(HttpServletRequest request, HttpServletResponse response)            throws ServletException, IOException {        // Get the HttpSession object. If it doesn't exist, a new one will be created.        HttpSession session = request.getSession();        // Set a session attribute        session.setAttribute("username", "GFG");        // Retrieve the session attribute        String username = (String) session.getAttribute("username");        // Display the attribute value in the response        response.getWriter().println("Username from Session: " + username);                // Invalidate the session after displaying the attribute        session.invalidate();    \}}

**Explicación:** Un servlet/api gestiona la solicitud mediante doGet() y crea o recupera la sesión mediante request.getSession(). Almacena y obtiene el atributo "username", lo muestra en la respuesta y, finalmente, invalida la sesión mediante invalidate().
