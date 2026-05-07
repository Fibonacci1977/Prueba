# Cómo configurar un grupo de conexiones JDBC en Glassfish

Para configurar un grupo de conexiones JDBC en GlassFish (anteriormente conocido como SUN App Server), solo tienes que seguir unos sencillos pasos. En este tutorial, crearemos un grupo de conexiones JDBC para SQL Server.

### Paso 1: Abrir la lista de grupos de conexiones JDBC

En el panel de administración de Glassfish, abra la lista de grupos de conexiones JDBC mediante el menú de navegación situado a la izquierda (Recursos -> JDBC -> Grupos de conexiones). En la sección Grupos de conexiones JDBC, haga clic en Nuevo... para crear un nuevo grupo de conexiones JDBC.

![Servicios](https://www.javaxt.com/images/glassfish/jdbc/step3.jpg)

### Paso 2: Crear un nuevo grupo de conexiones JDBC

En el cuadro de diálogo Nuevo grupo de conexiones JDBC, especifique un nombre para el grupo. Asegúrese de especificar el "Tipo de recurso" correcto y haga clic en Siguiente .

![Servicios](https://www.javaxt.com/images/glassfish/jdbc/step1.jpg)

### Paso 3: Especificar el nombre de la clase de origen de datos

En la página siguiente, especifique el nombre de la clase de origen de datos . El nombre de la clase depende del controlador. Consulte la documentación del controlador para encontrar la clase correcta. Haga clic en Finalizar para crear el grupo de conexiones JDBC.

![Servicios](https://www.javaxt.com/images/glassfish/jdbc/step2.jpg)

### Paso 4: Editar el grupo de conexiones

Una vez creado el grupo de conexiones JDBC, puede volver atrás y agregar/editar propiedades como la URL de conexión JDBC, el nombre de usuario, la contraseña, etc. Ejemplo:

![Servicios](https://www.javaxt.com/images/glassfish/jdbc/step5.jpg)

### Paso 5: Crear un recurso JDBC

Por último, deberá crear un nuevo recurso JDBC al que pueda hacer referencia en su aplicación web.

![Servicios](https://www.javaxt.com/images/glassfish/jdbc/step7.jpg)

### Utilizando la conexión

Una vez que hayas creado un pool de conexiones, puedes usarlo en tu aplicación web (por ejemplo, servlet, jsp, etc.) de esta manera:

```
//Find a database connection  javax.naming.InitialContext ctx = new javax.naming.InitialContext();  javax.sql.DataSource ds = (javax.sql.DataSource)ctx.lookup("jdbc/SQLServer");  java.sql.Connection conn = ds.getConnection();   //Do something with the connection.
```
