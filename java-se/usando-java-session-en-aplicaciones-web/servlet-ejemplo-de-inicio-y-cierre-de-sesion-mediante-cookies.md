# Servlet - Ejemplo de inicio y cierre de sesión mediante Cookies

Las cookies son fragmentos de información textual que se almacenan en formato de pares clave-valor en el navegador del cliente durante múltiples solicitudes.

#### ¿Por qué utilizamos cookies?

* Utilizamos cookies como una de las **técnicas de seguimiento de sesión/gestión de estado** .
* El seguimiento de sesiones es una forma de **mantener el estado (los datos) de un usuario** . También se conoce como gestión de estado.
* Utilizamos el seguimiento de sesiones porque **HTTP es un protocolo sin estado** . En un protocolo sin estado, el servidor trata cada solicitud como una nueva, ya que no recuerda que las solicitudes provienen del mismo cliente.
* Por lo tanto, mediante el uso de cookies podemos crear un módulo de inicio y cierre de sesión, y el servidor puede almacenar nuestros datos.

#### **Funcionamiento de una cookie**

* El cliente envía una solicitud “ **req1** ” al servidor. Después de procesar la solicitud “req1”, el servidor envía “ **respuesta+cookies** ”.
* Estas cookies se guardan en el navegador del cliente.
* Ahora bien, si el cliente envía otra solicitud “ **req2+cookies** ” al servidor, este primero verificará la cookie y sabrá que se trata de un usuario que ya ha iniciado sesión, por lo que no tratará esta solicitud “req2+cookies” como una nueva. Posteriormente, el servidor realizará el procesamiento correspondiente.
* Así es como se establecerá un estado.

#### **¿Cómo usar cookies en Java?**

* Para crear cookies, utilice la **clase Cookies** del paquete **javax.servlet.http** .
* Para crear una cookie, crea un objeto de la clase cookie y pásale un par nombre-valor.

#### **¿Cómo adjuntar una cookie a una respuesta?**&#x20;

* Para adjuntar una cookie a una respuesta, utilice el método **addCookie(cookie) de la interfaz de respuesta** .

#### **¿Cómo obtener una cookie cuando un cliente envía otra solicitud (es decir, req2+cookie)?** &#x20;

* La cookie llegará a través de una solicitud, por lo que utilizaremos el **objeto de solicitud** como ayuda .
* El método **request.getCookies() devolverá un array de cookies** .
* **Los métodos getName()** y **getValue()** de la **clase Cookie** se utilizan para obtener la clave y su valor correspondiente del array de cookies.
* Si **no se encuentran cookies** , devolverá null, lo que significa que el **cliente es un usuario nuevo** y la solicitud también es nueva.

#### ¿Cómo eliminar una cookie?

* Se elimina una cookie para cerrar la sesión del usuario.
* En el par clave-valor, pase una **cadena vacía** .
* Además, utilice el método **setMaxAge()** de la **clase Cookie** para indicar después de cuánto tiempo debe expirar la cookie.

> **Nota:** Para ejecutar los siguientes programas, el autor creó un proyecto web dinámico en el IDE Eclipse y lo ejecutó utilizando el servidor Apache Tomcat v9.0.&#x20;

**Ejemplo:** Módulo de inicio y cierre de sesión mediante cookies

**A.** Archivo: index.html&#x20;

* Esta página incluye enlaces a otras tres páginas para la navegación: la página de inicio de sesión, el servlet de cierre de sesión y el servlet de perfil.
* Haz clic en login.html e introduce tu nombre de usuario y contraseña (por ejemplo, gfg). Desde la página de inicio de sesión, serás redirigido a GFGLoginServlet.java.

**Ejemplo:**

\<!DOCTYPE html>\<html>\<head>\<meta charset="ISO-8859-1">\<title>GFG\</title>\</head>\<body>\<p>\<a href="login.html" style="font-size:25px;">Login |\</a>\<a href="GFGLogoutServlet" style="font-size:25px;"> Logout |\</a>\<a href="GFGProfileServlet" style="font-size:25px;"> Profile \</a>\</p>\</body>\</html>

&#x20;\
&#x20;

**Salida:** index.html es el siguiente:&#x20;

\
&#x20;

<figure><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220205081533/index.PNG" alt=""><figcaption><p>índice.html</p></figcaption></figure>

\
&#x20;

**B. Archivo:** link.html

\
&#x20;

link.html es lo mismo que index.html porque incluiremos el contenido de la página link.html usando RequestDispatcher en GFGLoginServlet.java y GFGLogoutServlet.java.

\
&#x20;

**Ejemplo:**

\
&#x20;

\<!DOCTYPE html>\<html>\<head>\<meta charset="ISO-8859-1">\<title>GFG\</title>\</head>\<body>\<p>\<a href="login.html" style="font-size:25px;">Login |\</a>\<a href="GFGLogoutServlet" style="font-size:25px;"> Logout |\</a>\<a href="GFGProfileServlet" style="font-size:25px;"> Profile \</a>\</p>\</body>\</html>

&#x20;\
&#x20;

**Archivo C:** login.html&#x20;

\
&#x20;

\<!DOCTYPE html>\<html>\<head>\<meta charset="ISO-8859-1">\<title>GFG\</title>\</head>\<body>\<form action="GFGLoginServlet">\<pre>User name: \<input type="text" name="user\_name" placeholder="Enter your name">Password: \<input type="password" name="password" placeholder="Enter password">\<button type="submit" value="login">Login\</button>\</pre>\</form>\</body>\</html>

&#x20;\
&#x20;

**Salida:** login.html es el siguiente **:** &#x20;

\
&#x20;

<figure><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220205081621/loginpage.PNG" alt=""><figcaption><p>login.html</p></figcaption></figure>

\
&#x20;

**Implementación:**&#x20;

\
&#x20;

#### Caso: GFGLoginServlet.java&#x20;

* Aquí se comprobará la contraseña.
  * Si la contraseña es correcta (es decir, gfg), entonces se creará **una cookie** .
  * De lo contrario, se mostrará el contenido de login.html solicitando al usuario que inicie sesión nuevamente, ya que la contraseña es incorrecta.
* El contenido de link.html se mostrará en la parte superior en ambos casos.

\
&#x20;

// Java Program to Illustrate Login in Servlets// Importing required classesimport java.io.IOException;import java.io.PrintWriter;import javax.servlet.ServletException;import javax.servlet.annotation.WebServlet;import javax.servlet.http.Cookie;import javax.servlet.http.HttpServlet;import javax.servlet.http.HttpServletRequest;import javax.servlet.http.HttpServletResponse;// Annotation@WebServlet("/GFGLoginServlet")// Class// Extending HttpServlet classpublic class GFGLoginServlet extends HttpServlet {    private static final long serialVersionUID = 1L;    protected void doGet(HttpServletRequest request,                         HttpServletResponse response)        throws ServletException, IOException    {        PrintWriter out = response.getWriter();        request.getRequestDispatcher("link.html")            .include(request,                     response); // This statement includes                                // link.html in this servlet        String name = request.getParameter("user\_name");        String password = request.getParameter("password");        if (password.equals("gfg")) {            out.println(                "\<h1>Welcome " + name                + ", you have successfully logged in!\</h1>");            // creating cookie            Cookie c = new Cookie("username", name);            // attaching cookie to response object            response.addCookie(c);        }        else {            out.println(                "Sorry invalid username or password!");            request.getRequestDispatcher("login.html")                .include(request, response);            // Above statement includes login.html for the            // user to re-login if username or password is            // invalid.        }    }    protected void doPost(HttpServletRequest request,                          HttpServletResponse response)        throws ServletException, IOException    {        // TODO Auto-generated method stub        doGet(request, response);    \}}

&#x20;\
&#x20;

**Salida:** GFGLoginServlet.java es el siguiente:

\
&#x20;

<figure><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220205081802/GFGLoginServlet.PNG" alt=""><figcaption><p>GFGLoginServlet.java</p></figcaption></figure>

#### **GFGProfileServlet.java**

* En este caso, acceder a la página de perfil implica enviar otra solicitud al usuario (es decir, req2+cookie).
  * Si la cookie no existe (es decir, es nula), se mostrará el contenido de login.html solicitando al usuario que inicie sesión.
  * De lo contrario, se recuperará la cookie mediante la función **getName()** y se buscará la cookie cuyo nombre coincida con el nombre del usuario. Una vez encontrada la cookie, se recuperará su valor mediante la función **getValue()** .
* El contenido del archivo link.html no se mostrará en esta página.

\
&#x20;

import java.io.IOException;import java.io.PrintWriter;import javax.servlet.ServletException;import javax.servlet.annotation.WebServlet;import javax.servlet.http.Cookie;import javax.servlet.http.HttpServlet;import javax.servlet.http.HttpServletRequest;import javax.servlet.http.HttpServletResponse;@WebServlet("/GFGProfileServlet")public class GFGProfileServlet extends HttpServlet {    private static final long serialVersionUID = 1L;    protected void doGet(HttpServletRequest request,                         HttpServletResponse response)        throws ServletException, IOException    {        PrintWriter out = response.getWriter();        String name = "";        // request object will return an array of cookies        Cookie\[] cookies = request.getCookies();        if (cookies == null) {            out.println(                "\<h1> You are a new user, kindly login. \</h1>");            request.getRequestDispatcher("login.html")                .include(request, response);            // Above statement includes login.html for the            // user to re-login if username or password is            // invalid.        }        else {            for (Cookie c : cookies) {                String tempName                    = c.getName(); // For every cookie, add                                   // cookie name to the                                   // tempName.                              if (tempName.equals("username"))                // If tempName and username (that we had set                // in the cookie c in GFGLoginServlet) are                // same, then this is an already logged in                // user and the request is not from a new                // user. So let the user access profile page.                {                    name = c.getValue(); // From the (name,                                         // value) pair of                                         // cookie, fetch                                         // value                    out.println(                        "\<a href='GFGLogoutServlet' style='font-size:25px;'>Logout \</a>");                    out.println(                        "\<h1>Welcome to your profile, "                        + name);                }            }        }    }    protected void doPost(HttpServletRequest request,                          HttpServletResponse response)        throws ServletException, IOException    {        // TODO Auto-generated method stub        doGet(request, response);    \}}

&#x20;\
&#x20;

**Salida:** GFGProfileServlet.java es el siguiente:

\
&#x20;

<figure><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220205081858/profileservlet.PNG" alt=""><figcaption><p>GFGProfileServlet.java</p></figcaption></figure>

#### Caso: GFGLogoutServlet.java

* Aquí se eliminará la cookie para finalizar la sesión.
  * Junto con el nombre de la cookie (es decir, el nombre de usuario), se pasará un valor nulo.
  * Dentro de la función setMaxAge(), estableceremos la fecha de caducidad de la cookie, para especificar después de cuánto tiempo caducará la cookie.
  * Utilizando la función response.addCookie(), adjuntaremos esta cookie a la respuesta para enviarla al navegador del cliente.

\
&#x20;

**Ejemplo**

\
&#x20;

// Java Program to Illustrate Logout in Servlets// Importing required classesimport java.io.IOException;import java.io.PrintWriter;import javax.servlet.ServletException;import javax.servlet.annotation.WebServlet;import javax.servlet.http.Cookie;import javax.servlet.http.HttpServlet;import javax.servlet.http.HttpServletRequest;import javax.servlet.http.HttpServletResponse;// Annotation@WebServlet("/GFGLogoutServlet")// Class// Extending HttpServlet classpublic class GFGLogoutServlet extends HttpServlet {    private static final long serialVersionUID = 1L;    protected void doGet(HttpServletRequest request,                         HttpServletResponse response)        throws ServletException, IOException    {        PrintWriter out = response.getWriter();        request.getRequestDispatcher("link.html")            .include(request,                     response); // This statement includes                                // link.html in this servlet        // cookie with blank value is used to delete        // a cookie to sign out the user        Cookie c = new Cookie("username", "");              // setMaxAge will set the expiration of cookie.        // This cookie will expire in 0seconds        c.setMaxAge(0);              // Attach cookie to response        response.addCookie(c);        out.println("\<h1>You have logged out!\</h1>");    }    protected void doPost(HttpServletRequest request,                          HttpServletResponse response)        throws ServletException, IOException    {        // TODO Auto-generated method stub        doGet(request, response);    \}}

&#x20;\
&#x20;

**Salida:** GFGLogoutServlet.java es el siguiente:&#x20;

\
&#x20;

<figure><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220205082003/logoutpage.PNG" alt=""><figcaption><p>GFGLogoutServlet.java</p></figcaption></figure>

> **Nota:** Si durante la ejecución del módulo el usuario hace clic en "Perfil" sin haber iniciado sesión, será redirigido a login.html y no podrá acceder a su perfil, ya que la sesión no estará creada.&#x20;
>
> **Excepciones**
>
> * \<space> **no está permitido** en las cookies.
> * Si intentamos enviar "Geeks" como valor de cookie, es aceptable.
> * Pero “Geeks for Geeks” generará una **excepción IllegalArgumentException** porque \<space> no está permitido en las cookies.
> * Se permite “Geeks\_for\_Geeks”.
