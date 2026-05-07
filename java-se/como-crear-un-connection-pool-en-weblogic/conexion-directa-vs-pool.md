# Conexión directa vs pool

1. > Hola antes de nada, salud para todos. Escribo esto porque tengo entendido que para establecer una conexión a una base de datos, existen dos modos:\
   > \
   > 1º Conexión directa.\
   > 2º Conexión por pool de conexiones.\
   > \
   > Quisiera saber la diferencia entre ambas, y cómo se implementan cada una de ellas en una aplicación... sobre todo de la 2ª. El lenguaje de programación si puede ser en Java mejor, pues estoy haciendo algo en WebLogic y toda la información que se me proporcione será más que bienvenida.\
   > \
   > Gracias de antemano

> Buenas y bienvenido! La diferencia entre ambas es que en la conexión directa utilizas un driver que te facilita el fabricante del motor de la base de datos para establecer la conexión, y en el pool de conexiones empleas un DataSource.\
> \
> Ambas deben llamar en Java a getConnection(). Pero una lo hace desde el driver y la otra desde el DataSource.\
> \
> En la conexión directa, a través del driver, tu debes encargarte de abrir y cerrar las conexiones, mientras que en el pool, hay un conjunto de conexiones disponibles que se van reutilizando a medida que las transacciones terminan. Normalmente es el servidor quien establece y define ese pool de conexiones abiertas. La aplicación solicita establecer una conexión con la base de datos, y se la pide a éste para que se la asigne.\
> \
> A modo de ejemplo, si tienes un servidor mysql, la forma de implementar ambos métodos en java sería algo así:\
> \
> 1º Conexion directa:\
> Código:
>
> ```
> private static Connection getConexionDirecta() throws Excepcion {
> 	Connection con = null;
> 	String conector = "com.mysql.jdbc.Driver";
>
>         String servidor = "servidorBD";
>         String puerto = "3306";
>         String usuario = "user";
>         String password = "pass";
>         String bd = "esquema_basedatos";
>
>         String cadenaConexion = "jdbc://mysql://"+servidorBD+":"+puerto+"/"+bd;
>
> 	try {
> 		Class.forName(conector);
> 		con = java.sql.DriverManager.getConnection(cadenaConexion, usuario, password);
> 	} catch (final SQLException e) {
> 		throw new Excepcion("Error conexion", e);
> 	} catch (final ClassNotFoundException e) {
> 		throw new Excepcion("Error conexion", e);
> 	}
> 	return con;
> }
> ```
>
> \
> 2º Conexion por pool:\
> Código:
>
> ```
> private static Connection getConexionPool() throws Excepcion {
> 	Connection con = null;
>         String jndi = "miJNDI";
>
> 	try {
>                 Context initContext = new InitialContext();
>                 DataSource ds = (DataSource) initContext.lookup(jndi);
>                 con = ds.getConnection();
> 	} catch (final NamingException e) {
> 		throw new Excepcion("Error configuracion DataSource", e);
> 	} catch (final SQLException e) {
> 		throw new Excepcion("Error conexion", e);
> 	}
> 	return con;
> }
> ```
>
> \
> Observa que en la conexión por pool, no necesitas saber ningún parámetro de conexión (cadena conexión, usuario, clave, etc...) con la base de datos, tal y como se hace en la conexión directa. En su lugar, lo que se pasa es el JNDI (Java Naming and Directory Interface), que es una cadena que identifica el pool a utilizar. Dicho pool, debe ser configurado en el servidor de la aplicación.\
> \
> En tu caso, dices que estás utilizando WebLogic, asi que para configurar un nuevo DataSource, lo que necesitas es crearte o definirte un nuevo "orígen de datos". Esto lo puedes hacer de dos formas, bien a través de la consola que te ofrece WebLogic:\
> \
> Código:
>
> ```
> http://localhost:7001/console
> ```
>
> , suponiendo claro está que el servidor esté en "localhost".\
> \
> O bien, a través del fichero de configuración config.xml.\
> \
> Un saludo.
