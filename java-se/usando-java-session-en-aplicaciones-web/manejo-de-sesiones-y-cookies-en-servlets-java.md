# Manejo de Sesiones y Cookies En Servlets Java

En este articulo exploraremos el manejo de _cookies_ y sesiones al utilizar [_servlets_ java](https://es.wikipedia.org/wiki/Java_Servlet). Que gracias a la variedad de APIs que java expone en sus paquetes nativos, nos ofrece gran facilidad y claridad de lenguaje al gestionar las _cookies_ y las sesiones de nuestras aplicaciones web.

### Manejando Las Cookies

Crear una _cookie_ es bastante fácil cuando utilizamos la clase _**Cookie**_ que encontramos en el paquete javax.servlet.http, simplemente hacemos una instancia de esta clase y la mandamos en la respuesta del servidor con el método _addCookie_

```
private static final void galleta(HttpServletRequest request, HttpServletResponse response) {
  Cookie galletaColor = new Cookie("color", "rojo");
  response.addCookie(galletaColor);
}
```

Y así de simple podemos ver una _cookie_ simple con todas sus opciones por defecto. Pero hay mas en este tema de lo que se habla comúnmente, y es que una cookie puede tener los siguientes parámetros:

* **Dominio:** Establece el nombre de domino (o dominios) para el cual una _cookie_ es valida. Se establece a través del método _setDomain(String dominio)_ de la clase _Cookie_
* **Path:** Establece la uri especifica en la que la _cookie_ será valida (e.g: /admin) es útil si no queremos exponer la _cookie_ en toda la aplicación. Se establece como es de esperarse con el metodo _setPath(String path)_ de la clase _Cookie_
* **Expiración:** Indica cuanto debe durar una _cookie_ en el navegador. Este valor se establece en segundos a través del método _setMaxAge(int segundos)_ de la clase _Cookie_
* **HostOnly:** Esta propiedad es muy importante en términos de seguridad, ya que establece si una _cookie_ podrá ser leída por el cliente o solo por el servidor. Piensen que si alguien logra un ataque XSS bien podrían robar las _cookies_ de sus usuarios sin mayores pormenores.  Por eso _HostOnly_ debería ser **true** siempre que el dominio desde el cual se esta intentando leer no sea igual al dominio de origen establecido. Por lo tanto la clase no expone un método para manipular esta bandera, si no que mas bien se establece automáticamente siguiendo el mecanismo establecido en la especificación [RFC-6265](https://tools.ietf.org/html/rfc6265#section-5.3) Sección 5.3 numeral 6.
* **Secure:** Otra parámetro muy importante que indica que la _cookie_ en cuestión puede ser leída únicamente a través de un protocolo seguro HTTPS o SSL. Y se establece con el metodo _setSecure(boolean isSecure)_ de la clase _Cookie._
* **HttpOnly:** Es similar a _HostOnly_ excepto que esta si se puede manipular. Funciona como una medida de seguridad extra a la especificación establecida y fue desarrollada por [microsoft en el 2002](https://msdn.microsoft.com/en-us/library/ms972826.aspx) gracias a la incapacidad del IE6 para apegarse a los estándares mundiales. Java al ser un lenguaje de clase mundial ofrece el metodo _setHttpOnly(boolean isHttpOnly)_ para estos efectos.

Finalmente si deseamos quitar una _cookie,_ basta con poner el tiempo de expiación en 0, y en la siguiente respuesta el navegador interpretara esto como que debe borrar dicha cookie.

```
private static final void galleta(HttpServletRequest request, HttpServletResponse response) {
  Cookie galletaColor = new Cookie("color", "rojo");
  galletaColor.setMaxAge(0);
  response.addCookie(galletaColor);
}
```

Para nosotros los que nos dedicamos al desarrollo de la tecnología, es necesario conocer todos los pormenores de estas cosas, ya que se están poniendo en vigencia la _Regulaciones de Protección de Datos Generales_ por sus siglas en ingles (GDPR) por parte de la unión europea y es nuestra responsabilidad apegarnos a la privacidad de las personas, y protegerla con todo lo que tenemos a la mano.

### Manejando Las Sesiones

Una buena alternativa para no manejar información sensible de nuestros usuarios del lado del cliente son las sesiones, que no es otra cosa que una estructura de datos que es accedida exclusivamente del lado del servidor. Si sus sistemas son muy concurridos o están detrás de un balanceador de carga manejar sesiones podría representar un reto interesante de resolver, sin embargo, la mayoría de las veces funciona muy bien con su configuración por defecto.

Veamos un ejemplo practico de como manipular la sesión en nuestro servlet.

```
private static final void home(HttpServletRequest request, HttpServletResponse response) {
  HttpSession sesion = request.getSession();
  session.setAttribute("usuario", "ricardogeek");
}
```

y así como si nada hemos creado una sesión y le hemos insertado un registro que describe un nombre de usuario. Luego podemos acceder a esta sesión en un _request_ completamente diferente.

```
private static final void panel(HttpServletRequest request, HttpServletResponse response) {
  HttpSession sesion = request.getSession();
  Object usuario = (String) session.getAttribute("usuario");
}
```

Aquí obtenemos el nombre de usuario. Vemos que como el getAttribute devuelve un objeto lo casteamos al tipo correcto para su posterior utilización.

Finalmente si quisiéramos borrar (_invalidar)_ la sesión, podemos hacerlo de la siguiente manera:

```
private static final void salir(HttpServletRequest request, HttpServletResponse response) {
  HttpSession sesion = request.getSession();
  sesion.invalidate();
}
```

El método _invalidate()_ destruye la sesión y sus contenidos.

### Conclusión

Es importante conocer a profundidad temas que a primera vista pueden parecer sencillos, pero que ocultan cosas que pueden convertir a nuestras aplicaciones en un nido de vulnerabilidades, y eventualmente provocar el robo de información valiosa o el engaño a nuestros usuarios por parte de terceras personas. Las _cookies_ y las sesiones son un tema que debe manejarse con la seriedad del caso.
