# Conectar java utilizando netbeans IDE a Oracle 11g

En esta ocasión comparto con ustedes un sencillo, pero útil tutorial sobre los procesos que deben efectuarse para establecer una conexión entre JAVA y ORACLE.\
\
En la siguiente tabla encontraras los recursos necesarios que deberas descargar e instalar en tu ordenador para poder seguir el tutorial.\
<br>

| Software o recursos                                                                                         | Versiones requeridas                                                                 |
| ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| [NetBeans IDE](http://www.netbeans.org/downloads/index.html)                                                | 7.0, 7.1, 7.2, Java EE bundle                                                        |
| [Java Development Kit (JDK)](http://java.sun.com/javase/downloads/index.jsp)                                | Version 6 or 7                                                                       |
| [Oracle Database XE](http://www.oracle.com/technetwork/database/express-edition/overview/index.html)        | 11 _g_ Express Edition                                                               |
| [Oracle JDBC driver](http://www.oracle.com/technetwork/database/enterprise-edition/jdbc-112010-090769.html) | [ojdbc6.jar](http://download.oracle.com/otn/utilities_drivers/jdbc/11202/ojdbc6.jar) |

\
Ahora que ya estas listo, pasaremos a los pasos necesarios para obtener una conexion satisfactoria al gestor de bases de datos Oracle (En este caso utilizaremos Netbeans IDE 7.1.2).\
\
La practica consistirá en conectarnos a una instancia local de Oracle, pero perfectamente es aplicable para conexiones con instancias remotas.\
\
Existen 2 categorías de drivers (conectores) para establecer una conexión con Oracle los cuales son: OCI y JDBC Thin, en nuestro caso utilizaremos la segunda opción porque en la mayoria de casos es suficiente para un uso eficiente de nuestra base de datos.\
\
ESTABLECIENDO CONEXION A BASE DE DATOS ORACLE.\
\
1-) Inicia el servicio de Oracle en tu computador.\
2- Inicia Netbeans IDE\
3-) Ve a la opción Window/Services en Netbeans, y selecciona "nueva conexión".\
\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhsuz266A0rYCgGg0XgtKoyPpa9ycVWx5riu0RjuubjWrt-iRhzAqJiMijVBTRG1ucm2kuig42L_HSiK5szrhmxDsWRc2W4wyFHMCUSC-51W5Fo9XhK_SCJM3mRDnlbP1LE3NFsV7yCFoE/s1600/tutooracle1.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhsuz266A0rYCgGg0XgtKoyPpa9ycVWx5riu0RjuubjWrt-iRhzAqJiMijVBTRG1ucm2kuig42L_HSiK5szrhmxDsWRc2W4wyFHMCUSC-51W5Fo9XhK_SCJM3mRDnlbP1LE3NFsV7yCFoE/s1600/tutooracle1.png)\
4-) Cuando te aparezca el asistente de configuración, selecciona de la lista desplegable "Oracle Thin", luego clic en "add" para agregar el driver que descargaste es decir el ojdbc6.jar luego da clic en "Next".\
\
5-) En el panel de personalización de conexión ingresa los siguientes valores y luego has clic en "Next".\
\
\
<br>

| Name             | Value                                                                                                                                                                                                  |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Driver Name      | Oracle Thin (with Service ID (SID))                                                                                                                                                                    |
| Host             | <p>localhost o 127.0.0.1.<br><em>Nota:</em> En el caso de una conexion remota, proporciona la IP o el nombre de Host para resolver la direccion de la maquina donde esta alojada la base de datos.</p> |
| Port             | 1521 (default)                                                                                                                                                                                         |
| Service ID (SID) | <p>XE (default SID para Oracle Database XE).<br><em>Nota</em>: Si estas conectado a una base de datos remota, solicita al administrador de base de datos el SID.</p>                                   |
| Username         | <p>Ingresa el nombre de usuario.<br>Para el propósito de este tutorial ingresa HR (Una de las cuentas de ejemplo de Oracle).</p>                                                                       |
| Password         | Ingresa la contraseña del usuario en este caso la contraseña de HR, tu puedes crearle una nueva clave desde Oracle\*Plus u otra IDE.                                                                   |

\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgXf0ostlnWcN2f_Yf7UADTCW2uM2Qo2PhqphulXE7LSQNYpeFv2SzBtnX6szRddO1zB5wGw6p2wrpZFM-L8bJFopUEvc7B-Q7xNeVyfyYhJRgZ4PqRtUwueTeoEeCsVCp88mnc8B3TH_c/s1600/customize-conn.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgXf0ostlnWcN2f_Yf7UADTCW2uM2Qo2PhqphulXE7LSQNYpeFv2SzBtnX6szRddO1zB5wGw6p2wrpZFM-L8bJFopUEvc7B-Q7xNeVyfyYhJRgZ4PqRtUwueTeoEeCsVCp88mnc8B3TH_c/s1600/customize-conn.png)\
6-) Haz clic en Test Connection para confirmar que la IDE esta habilitada para conectarse a la base de datos, has clic en Next y se te desplegara un mensaje confirmando la conexión.\
\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhnYiNi96DjU8U1Bq5KJlEOfN71VwbrPDJ6Yx4EV65R168oz2oD-vclKsJmXf2otjzESIwssCwxjaMm7MfjLD2UgZ15OKTj79F6FM6SSenZpk8Mlcx7r1oZ2amq0ou68yV06b8d0GRVv_w/s1600/connection.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhnYiNi96DjU8U1Bq5KJlEOfN71VwbrPDJ6Yx4EV65R168oz2oD-vclKsJmXf2otjzESIwssCwxjaMm7MfjLD2UgZ15OKTj79F6FM6SSenZpk8Mlcx7r1oZ2amq0ou68yV06b8d0GRVv_w/s1600/connection.png)\
COMPROBANDO LA CONEXIÓN DESDE UNA APLICACIÓN JAVA\
\
Ahora comprobaremos la conexion al esquema HR de Oracle desde una aplicacion Java.\
\
1-) Selecciona en Netbeans File/New Project/JavaAplication\
2-) Le nombraremos al proyecto OracleConection\
3-) Se creara la clase por defecto y el método Main que es donde ejecutaremos las instrucciones necesarias para establecer la conexión.\
4-) Importaremos los paquetes "java.sql.Connection" y "java.sql.DriverManager" necesarios en este caso.\
5-) Crearemos un objeto de tipo conexión "private Connection conexion;"\
6-) Desarrollaremos los respectivos Getter y Setter para el objeto conexion.\
\
&#x20;public Connection getConexion() {\
&#x20;       return conexion;\
&#x20;   }\
\
&#x20;  \
&#x20;   public void setConexion(Connection conexion) {\
&#x20;       this.conexion = conexion;\
&#x20;   }\
\
7-) Luego crearemos un método del tipo OracleConection. En dicho método utilizaremos la dirección que tenemos especificada en la conexión que realizamos con anterioridad. Con una condición verificaremos si la conexión es diferente de nulo es porque hemos logrado acceder al esquema HR.\
\
\
public OracleConection Conectar()\
&#x20;   {\
&#x20;       try{\
&#x20;       Class.forName("oracle.jdbc.OracleDriver");\
&#x20;       String BaseDeDatos = "jdbc:oracle:thin:@localhost:1521:XE";\
&#x20;       conexion= DriverManager.getConnection(BaseDeDatos,"HR","HR");\
&#x20;       if(conexion!=null)\
&#x20;       {\
&#x20;       System.out.println("Conexion exitosa a esquema HR");\
&#x20;       }\
&#x20;       else{System.out.println("Conexion fallida");}\
&#x20;       }\
&#x20;       catch(Exception e)\
&#x20;       {e.printStackTrace();}\
&#x20;    \
&#x20;   return this;\
&#x20;   }\
\
8-) Para finalizar en el metodo MAIN crearemos un objeto para invocar al metodo conectar.\
\
\
public static void main(String\[] args) {\
&#x20;   OracleConection conexion = new OracleConection();\
&#x20;   conexion.Conectar();\
}\
\
\
9-) Le damos clic derecho "Run" a nuestro proyecto y debería enviarnos el mensaje respectivo como en la siguiente imagen.\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiM0_ts08G_1hLX7_3C004eMTzNFsiHcmL84zJuiB4zGBuv9WmbLyzjSBWeFDODDfMZq37elgdTMVIGHyGPh4WIM4MP4lPkIhu_wer4qlrvehfSviEOz_sTJMH9moN0eaRzcWUkmu_aMxM/s1600/final.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiM0_ts08G_1hLX7_3C004eMTzNFsiHcmL84zJuiB4zGBuv9WmbLyzjSBWeFDODDfMZq37elgdTMVIGHyGPh4WIM4MP4lPkIhu_wer4qlrvehfSviEOz_sTJMH9moN0eaRzcWUkmu_aMxM/s1600/final.png)\
Fácilmente podemos adaptar la lógica para conectarnos a una aplicación Swing o JSP con lo practicado en este tutorial, recuerda que este blog sobrevive gracias a tus donaciones o clics en los anuncios, ya sabes como apoyar este recurso para continuar subiendo mas tutoriales. Gracias.
