# Acceso a Oracle desde Java

[![](https://blogdeaitor.wordpress.com/wp-content/uploads/2012/10/2012040106422914.jpg?w=630)](https://blogdeaitor.wordpress.com/wp-content/uploads/2012/10/2012040106422914.jpg)En este artículo vamos a mostrar como lo debemos hacer para conectarnos y poder trabajar con una Base de Datos Oracle desde Java. Para ello vamos a utilizar el driver odbc de Oracle.

Para descargar la el driver para la versión 11g R2 de Oracle, puedes acceder al siguiente enlace:

* [JDBC Oracle 11g Release 2 (ojdbc6.jar)](http://www.oracle.com/technetwork/database/enterprise-edition/jdbc-112010-090769.html)

Una vez descargado, debemos añadir el jar a nuestro classpath. La forma de hacerlo dependerá del IDE que estemos utilizando para el desarrollo de nuestra aplicación.

En el siguiente código se muestra una sencilla aplicación para conseguir una conexión a Oracle utilizando JDBC Thin Driver y realizar una consulta.

Si tenéis dudas o queréis profundizar en el tema, os recomiendo visitar los APIs mostrados a continuación.

* [Java SQL](http://docs.oracle.com/javase/1.4.2/docs/api/java/sql/package-summary.html)
* [Oracle ResultSet](http://docs.oracle.com/cd/E11882_01/appdev.112/e13995/oracle/jdbc/OracleResultSet.html)
* [Oracle Statement](http://docs.oracle.com/cd/E11882_01/appdev.112/e13995/oracle/jdbc/OracleStatement.html)

```
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

class Connector {

    public static void main (String args []) throws SQLException
    {
        //Registramos el driver odbc
        DriverManager.registerDriver (new oracle.jdbc.driver.OracleDriver());

        /* Creamos la conexión con la base de datos. Especificamos el driver (fijo),
         * la IP o nombre de la maquina así como su puerto y el SID 
         * (En este caso XE por ser la versión Express Edition de Oracle) y
         * el nombre de usuario y contraseña de Oracle.
         */
        Connection conn = DriverManager.getConnection
              ("jdbc:oracle:thin:@127.0.0.1:1521:XE", "aitor", "P@ssw0rd");
        //        driver         @IPdeHost :port:SID,userid  , password

        //Creamos el statement sobre el que realizaremos consultas a la base de datos
        Statement stmt = conn.createStatement();

        //Ejecutamos una consulta, en este caso, un simple select
        ResultSet rset = stmt.executeQuery("SELECT * from USUARIOS WHERE id=54");

        //Movemos el cursor a la primera fila devuelta por la consulta
        rset.next();

        //Mostramos el resultado deseado por pantalla.
        System.out.println ("ID Usuario: "+rset.getString(1) +
                     "DNI: "+rset.getString(2) + "Nombre: "+rset.getString("Nombre"));

        //cerramos la conexión
        stmt.close();
    } 
 }
```

A partir de este sencillo ejemplo ya podéis empezar a trabajar con una base de datos Oracle desde Java.
