# ¿Cómo se pueden utilizar las cookies en los Servlets?

#### 1

[Creación de cookies](https://es.linkedin.com/advice/3/how-can-you-use-cookies-servlets-skills-web-development-xdbxe?lang=es#creaci%C3%B3n-de-cookies)

#### 2

[Lectura de cookies](https://es.linkedin.com/advice/3/how-can-you-use-cookies-servlets-skills-web-development-xdbxe?lang=es#lectura-de-cookies)

#### 3

[Actualización de cookies](https://es.linkedin.com/advice/3/how-can-you-use-cookies-servlets-skills-web-development-xdbxe?lang=es#actualizaci%C3%B3n-de-cookies)

#### 4

[Eliminación de cookies](https://es.linkedin.com/advice/3/how-can-you-use-cookies-servlets-skills-web-development-xdbxe?lang=es#eliminaci%C3%B3n-de-cookies)

#### 5

[Uso de cookies para la gestión de sesiones](https://es.linkedin.com/advice/3/how-can-you-use-cookies-servlets-skills-web-development-xdbxe?lang=es#uso-de-cookies-para-la-gesti%C3%B3n-de-sesiones)

#### 6

[Esto es lo que hay que tener en cuenta](https://es.linkedin.com/advice/3/how-can-you-use-cookies-servlets-skills-web-development-xdbxe?lang=es#esto-es-lo-que-hay-que-tener-en-cuenta)



### 1Creación de cookies <a href="#creacion-de-cookies" id="creacion-de-cookies"></a>

Para crear una cookie en un servlet, debe utilizar la clase Cookie del paquete javax.servlet.http. Puede crear una instancia de un objeto Cookie con un nombre y un valor y, opcionalmente, establecer algunos atributos como el dominio, la ruta de acceso, la antigüedad máxima y la marca de seguridad. Por ejemplo, el código siguiente crea una cookie denominada user con el valor John y establece su antigüedad máxima en una hora:

```
Cookie cookie = new Cookie("user", "John");<br>
cookie.setMaxAge(60 * 60); // in seconds<br>
response.addCookie(cookie); // add cookie to response object        
```

El objeto de respuesta es una instancia de HttpServletResponse que se pasa como parámetro al método de servicio del servlet. Puede agregar varias cookies al objeto de respuesta antes de enviarlo al cliente.



### 2Lectura de cookies <a href="#lectura-de-cookies" id="lectura-de-cookies"></a>

Para leer una cookie en un servlet, debe utilizar el método getCookies del objeto HttpServletRequest, que también se pasa como parámetro al método service. El método getCookies devuelve una matriz de objetos Cookie que representan las cookies enviadas por el cliente en el encabezado de la solicitud. Puede recorrer la matriz y utilizar los métodos getName y getValue para acceder al nombre y al valor de la cookie. Por ejemplo, el siguiente código lee la cookie de usuario e imprime su valor en la consola:

```
Cookie[] cookies = request.getCookies(); // get cookies from request object<br>
if (cookies != null) {<br>
  for (Cookie cookie : cookies) {<br>
    if (cookie.getName().equals("user")) {<br>
      System.out.println("User cookie value: " + cookie.getValue());<br>
      break;<br>
    }<br>
  }<br>
}        
```

Si el cliente no envía ninguna cookie, el método getCookies devuelve null, por lo que debe comprobar si es null antes de recorrer la matriz.



### 3Actualización de cookies <a href="#actualizacion-de-cookies" id="actualizacion-de-cookies"></a>

Para actualizar una cookie en un servlet, debe crear un nuevo objeto Cookie con el mismo nombre que la cookie existente y un nuevo valor y, a continuación, agregarlo al objeto de respuesta. La nueva cookie sobrescribirá la anterior en el navegador del cliente. También puede cambiar otros atributos de la cookie, como la antigüedad máxima o la ruta, utilizando los métodos setter correspondientes. Por ejemplo, el siguiente código actualiza la cookie de usuario con un nuevo valor y una nueva antigüedad máxima:

```
Cookie cookie = new Cookie("user", "Jane");<br>
cookie.setMaxAge(30 * 60); // in seconds<br>
response.addCookie(cookie); // add cookie to response object        
```



### 4Eliminación de cookies <a href="#eliminacion-de-cookies" id="eliminacion-de-cookies"></a>

Para eliminar una cookie en un servlet, debe crear un nuevo objeto Cookie con el mismo nombre que la cookie existente y establecer su antigüedad máxima en cero y, a continuación, agregarlo al objeto de respuesta. Esto le indicará al navegador del cliente que elimine la cookie de inmediato. Por ejemplo, el siguiente código elimina la cookie de usuario:

```
Cookie cookie = new Cookie("user", "");<br>
cookie.setMaxAge(0); // in seconds<br>
response.addCookie(cookie); // add cookie to response object        
```



### 5Uso de cookies para la gestión de sesiones <a href="#uso-de-cookies-para-la-gestion-de-sesiones" id="uso-de-cookies-para-la-gestion-de-sesiones"></a>

Uno de los usos habituales de las cookies en las aplicaciones web es la gestión de las sesiones de usuario, que son interacciones temporales entre el cliente y el servidor. Una sesión puede almacenar información específica del usuario, como el estado de inicio de sesión, los elementos del carro de la compra o las preferencias. Para utilizar cookies para la gestión de sesiones en Servlets, debe utilizar la interfaz HttpSession del paquete javax.servlet.http. Puede obtener un objeto HttpSession del objeto request mediante el método getSession, que crea una nueva sesión si no existe o devuelve la existente si existe. El método getSession también crea una cookie denominada JSESSIONID con un identificador único para la sesión y la agrega al objeto de respuesta. Puede usar los métodos setAttribute, getAttribute y removeAttribute del objeto HttpSession para almacenar, recuperar y eliminar datos de sesión. Por ejemplo, el código siguiente crea una sesión y almacena el nombre de usuario y el rol en ella:

```
HttpSession session = request.getSession(); // get or create session<br>
session.setAttribute("name", "John"); // store name in session<br>
session.setAttribute("role", "admin"); // store role in session        
```

El siguiente código recupera los datos de la sesión y los imprime en la consola:

```
HttpSession session = request.getSession(false); // get existing session or null<br>
if (session != null) {<br>
  String name = (String) session.getAttribute("name"); // get name from session<br>
  String role = (String) session.getAttribute("role"); // get role from session<br>
  System.out.println("Name: " + name + ", Role: " + role);<br>
}        
```

El código siguiente elimina los datos de la sesión e invalida la sesión:

```
HttpSession session = request.getSession(false); // get existing session or null<br>
if (session != null) {<br>
  session.removeAttribute("name"); // delete name from session<br>
  session.removeAttribute("role"); // delete role from session<br>
  session.invalidate(); // invalidate session<br>
}        
```

El método invalidate también elimina la cookie JSESSIONID del explorador del cliente.

