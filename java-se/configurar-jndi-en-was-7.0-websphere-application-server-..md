# Configurar JNDI en WAS 7.0 (Websphere Application Server).

Que tal. Nuevamente aca posteando. Esta vez es para mostrarle los pasos para configurar un JNDI en WAS 7.0(Websphere Application Server). ¿Qué me impulso a escribir este artículo? la cantidad de chichones que me quedó en la cabeza luego de darme contra la pared varias veces al intentar obtener la conexión. Ya que la ubicación de algunos pasos era sutilmente diferente a versiones anteriores de WAS.

Por lo mencionado anteriormente este post no intenta explicar que hace cada pantalla del wizard, sino ejecutarlos paso a paso como decia el Mostaza Merlo :P.

Otra cosa importante para comenzar es que deben tener claro los siguientes datos:

* Nombre del Servidor de Base de Datos
* Nombre de la Base de Datos
* Usuario y Pass de Base de Datos
* Nombre del JNDI
* Driver de SQLServer(jtds.jar), ya que la conexión será a un Motor MSSQLServer.
* Por lo tanto debemos dejar esta librería jtds.jar en el lib del servidor, el path en mi caso sería:

/home/castudillo/servers/IBM/WebSphere/AppServer/lib/ext/jtds-1.2.2.jar

Una vez que hayan hecho este paso reinicien su server.&#x20;

Comencemos:

Vamos a través de un browser a la consola de WAS([https://localhost:9043/ibm/console](https://localhost:9043/ibm/console)) y hacemos click en la opción «Proveedores de JDBC» que se encuentra en el menu lateral izquierdo(Recursos–>JDBC–>Proveedores de JDBC)

[![screenshot\_0014](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_0014.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_0014.png)

Se cargara la página de proveedores de JDBC.

[![screenshot\_002](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_002.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_002.png)

Presionamos el botón llamado «Nuevo» para crear nuestro proveedor JDBC.

[![screenshot\_003](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_003.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_003.png)

* En el combo «Tipo de base de datos» seleccionamos el valor «Definido por el usuario»
* Agregamos el nombre de clase de implementación correspondiente al driver JTDS(net.sourceforge.jtds.jdbcx.JtdsDataSource).
* Y agregamos un nombre de nuestro gusto, para este caso el nombre es «JDBC Provider Test»

Presionamos botón «Siguiente» y se desplegará la página donde tenemos que definir la ubicación de nuestro Driver en este caso el jtds-1.2.2.jar.

[![screenshot\_004](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_004.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_004.png)

Definan entonces la ruta de acceso al jar y luego presionen el boton «siguiente». Aparecerá una página con el resumen de los valores que hemos definido hasta el momento.

[![screenshot\_005](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_005.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_005.png)

Una vez que se deleiten con ver esta página queridas criaturas presionen el botón «Finalizar», aparecerá el tipico mensaje de guardar la configuración maestra. No se uds, pero yo siempre guardo.

[![screenshot\_006](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_006.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_006.png)

Una vez guardado veremos que aparece en la lista nuestro proveedor JDBC recien creado («JDBC Provider Test»).

[![screenshot\_007](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_007.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_007.png)

Vamos al listado y presionamos sobre su Link.

Aparecerá una nueva página llamada «JDBC Provider Test» pero por el momento no estamos en condiciones de testear nada, primero debemos definir el origen de datos. Para esto debemos presionar el link que aparece en la izquierda de la pantalla, llamado «Orígenes de datos».

[![screenshot\_008](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_008.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_008.png)

Una vez que hayamos clickeado en «Origenes de Datos» seremos direccionados a la página donde podemos definir este origen. Para esto presionen el botón «Nuevo»

[![screenshot\_009](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_009.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_009.png)

Aparecerá la página donde debemos definir:

* Nombre de origen de datos: DataSource Test en este caso
* Nombre JNDI : jdbc/testdb

[![screenshot\_010](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_010.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_010.png)

Presionemos el boton «Siguiente», después aparecerá otra página donde ¿adivinen que? SI! presionen botón siguiente nuevamente.

[![screenshot\_0111](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_0111.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_0111.png)

Siguiente

[![screenshot\_012](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_012.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_012.png)

[![screenshot\_013](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_013.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_013.png)

En esta página paramos con los botones siguiente y presionamos Finalizar. aparecerá el mensaje de guardar en configuracion maestra.

[![screenshot\_0142](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_0142.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_0142.png)

Tenemos nuestro Origen de datos. Entonces ahora vamos al listado y clickeamos sobre nuestro «DataSourceTest».

Seremos direccionados hacia una nueva página, es aquí en esta página donde debemos dar click al link «Propiedades Personalizadas»(a la derecha de la pantalla)  donde podremos definir el nombre del **Servidor de base de datos** y el nombre de la **Base de datos**

[![screenshot\_016](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_016.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_016.png)

En esta página de propiedadades personalidas debemos buscar la propiedad **databaseName** y **serverName** clickeamos estas propiedades por separado y modificamos su valor:

* **databaseName:** test\_database
* **serverName:** test\_server

[![screenshot\_019](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_019.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_019.png)[![screenshot\_020](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_020.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_020.png)

Una vez que definimos estos 2 valores vamos al link «DataSource Test» que se encuentra en la zona superior de la página.

[![screenshot\_021](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_021.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_021.png)

Estando en esta página de «DataSource Test» hacemos click sobre el link «JAAS – Datos de autenticación J2C»(zona derecha de la pantalla).

[![screenshot\_022](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_022.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_022.png)

Seremos enviados a la página donde presionaremos el boton «nuevo» para definir nuestro Usuario y Password para acceder a la base de base de datos

[![screenshot\_024](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_024.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_024.png)

Presionamos aceptar.

[![screenshot\_026](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_026.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_026.png)

Luego vamos al link «DataSource Test» que aparece en la zona superior de la página para asociar nuestro «test\_conn» recien creado.

Seremos enviados nuevamente a la página de «DataSource Test», vamos al final de la página y en el combo «Alias de autenticación gestionado por componentes» seleccionamos el «test\_conn» creado en el paso anterior. Aceptamos y ya estamos en condiciones de realizar una prueba de conexión.

Podemos hacerlo en esta misma página con el botón «Conexión de prueba» o tambien podemos testear desde la página de «Orígenes de datos»

[![screenshot\_030](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_030.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_030.png)

Seleccionamos nuestro «DataSource Test» y luego presionamos el botón «Conexión de prueba». Debería aparecer el siguiente mensaje:

[![screenshot\_032](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_032.png?w=640)](https://kcobuntu.wordpress.com/wp-content/uploads/2009/03/screenshot_032.png)

Bueno señores con esto ya estamos en condiciones de usar este JNDI desde una app. Espero que esto les sea de ayuda y que les funcione el test de conexión :P.

Hasta otra oportunidad.
