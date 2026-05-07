# Agregar una fuente de datos a JBoss Wildfly mediante la CLI de JBoss

{% embed url="https://www.studocu.com/pe/u/95092817?sid=01778147495&page=1" %}

![Agregar una fuente de datos a JBoss Wildfly mediante la CLI de JBoss](https://www.squins.com/images/wildfly-datasource-source.png)

Este artículo describe cómo crear una fuente de datos MySQL en el servidor de aplicaciones JBoss Wildfly mediante la interfaz de línea de comandos (CLI). También incluye un ejemplo sencillo con un servlet donde se utiliza la fuente de datos configurada.

Utilizamos JBoss Wildfly versión 8.2.

### Esquema de base de datos MySQL de ejemplo <a href="#sample-mysql-database-schema" id="sample-mysql-database-schema"></a>

Este ejemplo utiliza el siguiente esquema de MySQL:

```
    CREATE TABLE IF NOT EXISTS `books` (
      `id` int(11) NOT NULL,
      `title` varchar(255) NOT NULL
    ) ENGINE=InnoDB DEFAULT CHARSET=latin1;

    -- Some sample data.
    INSERT INTO `books` (`id`, `title`) VALUES
    (1, 'Java is cool.'),
    (2, 'Clean Code');
```

Para ejecutar el ejemplo, cree un esquema de base de datos MySQL con la siguiente configuración:

* Nombre de usuario: books\_user
* Contraseña: secreta
* Esquema: libros

### Instalación del controlador MySQL <a href="#installing-the-mysql-driver" id="installing-the-mysql-driver"></a>

El primer paso para crear una fuente de datos MySQL en Wildfly es instalar el controlador MySQL. Primero, descarga el archivo JAR del [repositorio Maven](http://search.maven.org/#search%7Cga%7C1%7Cmysql-connector-java) . Para este ejemplo, usamos la versión 5.1.34. Una vez descargado el archivo JAR, recuerda su ubicación, ya que la necesitarás en la interfaz de línea de comandos de JBoss. A continuación, abre la interfaz de línea de comandos de JBoss y asegúrate de estar conectado.

Para instalar el controlador, ejecute el siguiente comando:

```
deploy ~/Downloads/mysql-connector-java-5.1.34.jar
```

Para comprobar si la instalación del controlador se realizó correctamente, ejecute el siguiente comando:

```
/subsystem=datasources:installed-drivers-list
```

### Creación de la fuente de datos <a href="#creating-the-datasource" id="creating-the-datasource"></a>

El siguiente paso es crear la fuente de datos en JBoss. Para listar las fuentes de datos actuales presentes en Wildfly, ejecute el siguiente comando:

```
/subsystem=datasources:read-resource(recursive=true)
```

Para este ejemplo, creamos una fuente de datos con los siguientes parámetros:

* Nombre: fuente de datos de libros
* Nombre JNDI: /jdbc/books-database
* Host: 127.0.0.1
* Puerto: 3306
* Nombre de usuario: books\_user
* Contraseña: secreta
* Esquema: libros

El comando para crear esta fuente de datos es:

```
data-source add --name=books-datasource --jndi-name=java:/jdbc/books-database --driver-name=mysql-connector-java-5.1.34.jar_com.mysql.jdbc.Driver_5_1 --connection-url=jdbc:mysql://127.0.0.1:3306/books --user-name=books_user --password=secret
```

Para comprobar si el origen de datos puede conectarse a la base de datos, ejecute el siguiente comando:

```
/subsystem=datasources/data-source=books-datasource:test-connection-in-pool
```

Cuando todo esté bien, debería decir:

```
{
    "outcome" => "success",
    "result" => [true]
}
```

Si aparece el mensaje "Error al obtener el resultado", compruebe los detalles de la conexión. Para eliminar el origen de datos defectuoso, ejecute:

```
data-source remove --name=books-datasource
```

Entonces inténtalo de nuevo.

### Utilizando la fuente de datos <a href="#using-the-datasource" id="using-the-datasource"></a>

Hay un proyecto de ejemplo (el enlace de descarga está disponible al final). Tiene el siguiente servlet:

```
package com.squins;

import javax.annotation.Resource;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.sql.DataSource;
import java.io.IOException;
import java.io.PrintWriter;
import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;

public class DataSourceServlet extends HttpServlet {

    @Resource(lookup = "java:/jdbc/books-database")
    private DataSource dataSource;

    public void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

        response.setContentType("text/html");

        PrintWriter out = response.getWriter();
        out.println("<h1>Hello world!</h1>");

        try (
                Connection connection = dataSource.getConnection();
                PreparedStatement preparedStatement = connection.prepareStatement("SELECT COUNT(*) FROM books");
                ResultSet resultSet = preparedStatement.executeQuery();
        ) {

            while (resultSet.next()) {
                out.println("You have " + resultSet.getInt(1) + " record(s) in your table.");
            }
        } catch (SQLException e) {
            throw new IllegalStateException("Failed to fetch number of books", e);
        }
    }

}
```

Para continuar, incluya este servlet en su propio archivo WAR o despliegue el archivo WAR de demostración. Para desplegar el archivo WAR de ejemplo, compile el proyecto Maven y ejecute el siguiente comando en JBoss CLI:

```
deploy /path/to/project/target/demo.war
```

Cuando se haya implementado correctamente, abra un navegador y vaya a `http://localhost:8080/demo/test-datasource`. Debería mostrar:

```
Hello world!

You have 2 record(s) in your table.
```

¡Enhorabuena! Ha configurado correctamente su fuente de datos MySQL en la CLI de JBoss.

### Obtén el código para este ejemplo. <a href="#get-code-for-this-example" id="get-code-for-this-example"></a>

Descargue un ejemplo de código [WAR que utiliza la fuente de datos de JBoss](https://bitbucket.org/squins/demo-jboss-datasource/) .

