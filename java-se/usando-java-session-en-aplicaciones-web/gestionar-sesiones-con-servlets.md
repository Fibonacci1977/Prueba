# Gestionar sesiones con servlets

Antes de seguir profundizando en las JSP, en esta entrada voy a explicar como gestionar sesiones con los servlets, para aclarar algunos conceptos introducidos en [esta entrada](https://javaparajavatos.wordpress.com/2019/06/09/directivas-jsp/).

_HTTP_ es un protocolo sin sesión, por lo que no se puede decir desde un acceso al servidor a otro si se trata de la misma persona que está accediendo repetidamente al sitio, o si se trata de una persona diferente. Se ha invertido mucho esfuerzo en mecanismos que permitirán a los desarrolladores web (como nosotros y nosotras) llevar a cabo un seguimiento de las sesiones. Las compañías no podrían hacer comercio electrónico sin mantener un seguimiento de un cliente y por ejemplo, de los elementos que éste ha introducido en su carro de compra.

Hay bastantes métodos para llevar a cabo el seguimiento de sesiones, pero uno de los más comunes es con _cookies_ persistentes, que son una parte integral de los estándares de Internet. Puedes visitar [este enlace](http://www.cookiecentral.com/) para mayor información.

Una _cookie_ no es más que una pequeña pieza de información enviada por un servidor web a un navegador. El navegador almacena la _cookie_ en el disco local y cuando se hace otra llamada a la _URL_ con la que está asociada la _cookie_, ésta se envía junto con la llamada, proporcionando así que la información deseada vuelva a ese servidor (generalmente, proporcionando alguna manera de que el servidor pueda determinar que es uno el que llama). Los clientes, sin embargo, pueden desactivar la habilidad del navegador para aceptar _cookies_. Si el sitio debe llevar un seguimiento de un cliente que ha desactivado las _cookies_, hay que incorporar otro método de seguimiento de sesiones (campos de formulario ocultos, por ejemplo).

Anuncio publicitarioAjustes de privacidad

#### La clase Cookie

El API servlet (en versiones 2.0 y superior) proporciona la clase _`Cookie`_. Esta clase incorpora todos los detalles de cabecera _HTTP_ y permite el establecimiento de varios atributos de _cookie_. Utilizar la _cookie_ es simplemente un problema de añadirla al objeto respuesta. El constructor toma un nombre de _cookie_ como primer parámetro y un valor como segundo. Las _cookies_ se añaden al objeto respuesta antes de enviar contenido.

Cookie cookiePrueba = new Cookie(«JAVA», «2020»);

res.addCookie(cookie)

Las _cookies_ suelen recubrirse invocando al método `getCookies`() de objeto **`HttpServletRequest`**, que devuelve un array de objetos _cookie_.

Cookie\[] cookies = req.getCookies

Después, se puede llamar a `getValue()` para cada cookie, para producir un String que contenga los contenidos de la cookie. En el ejemplo de arriba, `getValue("JAVA")` producirá un String de valor «2020».

#### La clase Session

Anuncio publicitarioAjustes de privacidad

Una sesión es una o más solicitudes de páginas por parte de un cliente a un sitio web durante un periodo definido de tiempo. Si compramos, por ejemplo, unos libros en línea, se desea que una sesión dure todo el periodo de tiempo desde que se añade el primer elemento a «Mi carrito de la compra» hasta el momento en que se compruebe todo el pedido. Cada elemento que se añada al carrito de la compra vendrá a producir una nueva conexión _HTTP_, que no tiene conocimiento de conexiones previas o de los elementos del carrito de la compra. Para compensar esa falta de información, los mecanismos suministrados por la especificación de _cookies_ permiten al _servlet_ llevar a cabo seguimiento de sesiones.

Un objeto **`Session`** vive en la parte servidora del canal de comunicación; su meta es capturar datos útiles sobre el cliente a medida que el cliente recorre e interactúa con el sitio web. Esta información puede ser pertinente para la sesión actual, como los elementos del carro de la compra, o pueden ser datos como la información de autentificación introducida cuando el cliente entró por primera vez en el sitio web, y que no debería ser reintroducida durante un conjunto de transacciones particular.

La clase **`Session`** del API servlet usa la clase **`Cookie`** para hacer su trabajo. Sin embargo, todo el objeto **`Session`** necesita algún tipo de identificador único almacenado en el cliente y que se pasa al servidor.

Un ejemplo que implementa seguimiento de sesión con el API servlet:

package Servlets;import java.io.IOException;import java.io.PrintWriter;import java.util.Enumeration;import javax.servlet.http.HttpServlet;import javax.servlet.http.HttpServletRequest;import javax.servlet.http.HttpServletResponse;import javax.servlet.http.HttpSession;/\*\* \* \* @author GORKA ELORDUY \*/public class SeguimientoSesion extends HttpServlet {    public void service(HttpServletRequest req, HttpServletResponse res) throws IOException {        //Retiramos el objeto Session antes de enviar ninguna salida al cliente        HttpSession sesion = req.getSession();        res.setContentType(«text/html»);        PrintWriter salida = res.getWriter();        salida.println(«\<HEAD>\<TITLE> Seguir sesion»);        salida.println(«\</TITLE>\</HEAD>\<BODY>»);        salida.println(«\<h1> Seguimiento de sesión\</h1>»);        //Un contador de accesos simple para esta petición        Integer ivalue = (Integer) sesion.getAttribute(«GorkaElorduy»);        if (ivalue == null) {            ivalue = new Integer(1);        } else {            ivalue = new Integer(ivalue.intValue() + 1);        }        sesion.setAttribute(«GorkaElorduy», ivalue);        salida.println(«Has accedido a esta página » + ivalue + » veces»);        salida.println(«\<h2>»);        salida.println(«Grabados datos de la sesión \</h2>»);        //Iteramos por todos los datos de la sesión        Enumeration nombresSesion = sesion.getAttributeNames();        while (nombresSesion.hasMoreElements()) {            String nombre = nombresSesion.nextElement().toString();            Object valor = sesion.getAttribute(nombre);            salida.println(nombre + » = » + valor + «\<br>»);        }        salida.println(«\<h3> Estadísticas de la sesión\</h3>»);        salida.println(«ID Sesion: » + sesion.getId() + «\<br>»);        salida.println(«Nueva Sesión » + sesion.isNew());        salida.println(«Hora de creación: » + sesion.getCreationTime());        salida.println(«Intervalo de inactividad de la sesión: » + sesion.getMaxInactiveInterval());        salida.println(«ID de sesion desde cookie: » + req.isRequestedSessionIdFromCookie());        salida.println(«\</BODY>»);    \}}

&#x20;

Anuncio publicitarioAjustes de privacidad

Dentro del método **`service()`**, se invoca a **`getSession()`** para el objeto petición que devuelve el objeto **`Session`** asociado con esta petición. El objeto **`Session`** no viaja a través de la red, sino que en vez de ello, vive en el servidor asociado a un cliente y sus peticiones

El método **`getSession()`** viene en dos versiones: la de sin parámetros (usada en este ejemplo) y **`getSession(boolean)`**. Usar **getSession(true)** equivale a **`getSession()`**. La única razón del boolean es para establecer si se desea crear el objeto _sesion_ si no es encontrado. La llamada más habitual es **`getSession(true)`**, razón de la existencia de **`getSession()`**.

El objeto **`Session`**, si no es nuevo, nos dará detalles sobre el cliente provenientes de sus visitas anteriores. Si el objeto **`Session`** es nuevo es nuevo, el programa empezará a recopilar información sobre las actividades del cliente en esta visita. La captura de esta información del cliente se hace mediante los métodos **`setAttribute`**() y **`getAttribute()`** del objeto de sesión.

El objeto **`Session`** utiliza un emparejamiento nombre-valor simple para cargar información. El nombre es un String, y el valor puede ser cualquier objeto derivado de java.lang.Object. **SeguimientoSesion** mantiene un seguimiento de las veces que ha vuelto el cliente durante esta sesión. Esto se hace con un objeto **`Integer`** denominado GorkaElorduy (es mi nombre, perdón por la falta de originalidad). Si no se encuentra el nombre, se crea un Integer de valor uno, si no, se crea un **`Integer`** con el valor incrementado respecto del **Integer** anteriormente guardado. Si se usa la misma clave en una llamada a **`setAttribute()`**, el objeto nuevo sobreescribe al viejo. El contador incrementado se usa para mostrar el número de veces que ha visitado el cliente durante esta sesión.

El método **`getAttributeNames()`** está relacionado con **`getAttribute()`** y **`setAttribute()`**; devuelve una enumeración de los nombres de objetos vinculados al objeto **`Session`**. Un bucle **`while`** en **SeguimientoSesion** muestra este método en acción.
