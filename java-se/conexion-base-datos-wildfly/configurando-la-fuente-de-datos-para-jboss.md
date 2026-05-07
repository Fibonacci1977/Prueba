# Configurando la fuente de datos para JBoss

[Configuración de la fuente de datos para JBoss 7](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s03.html#setting_up_data_sources_for_JBoss_7_j2ee)[Configuración de la fuente de datos para JBoss 5](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s03.html#setting_up_data_sources_for_JBoss_5_j2ee)

**Configuración de la fuente de datos para JBoss 7**

[Método 1](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s03.html#d0e4123)[Método 2](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s03.html#d0e4183)

La configuración de la fuente de datos en JBoss AS 7 es diferente a la de las versiones anteriores. Siga las instrucciones a continuación para crear la fuente de datos en JBoss AS 7 (o consulte el sitio web [http://community.jboss.org/wiki/DataSourceConfigurationInAS7](http://community.jboss.org/wiki/DataSourceConfigurationInAS7) ).

La siguiente sección tomará como ejemplo un tipo de base de datos (base de datos ASA/SQL Anywhere con controlador JDBC SAP jConnect) para mostrarle cómo crear una fuente de datos para JBoss AS 7. Posteriormente, puede crear fuentes de datos para otros tipos de bases de datos siguiendo los mismos pasos que se describen a continuación, pero especificando diferentes parámetros según los [parámetros de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s07.html) .

Para definir un origen de datos en JBoss AS 7, debe realizar dos tareas principales. Primero, debe poner el controlador JDBC a disposición del servidor de aplicaciones; luego, debe configurar el origen de datos que haga referencia al controlador que instaló.

**Método 1**

[Instalación de un controlador JDBC a través del archivo de configuración](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s03.html#d0e4126)[Configuración de la fuente de datos para JBoss AS 7 a través del archivo de configuración.](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s03.html#d0e4171)

**Instalación de un controlador JDBC a través del archivo de configuración**

Paso 1: Vaya al directorio "modules\com" en el directorio raíz del servidor de aplicaciones JBoss (por ejemplo, jboss-as-7.1.1.Final\modules\com), cree un subdirectorio "asa" y un subdirectorio "asa\main", de modo que el directorio quede como sigue: jboss-as-7.1.1.Final\modules\com\asa\main.

Paso 2: Vaya al directorio "main", pegue allí el archivo JAR del controlador, en este ejemplo, el archivo jconn3.jar.

Paso 3: Vaya al directorio "main", cree un archivo module.xml y defina el archivo de la siguiente manera.

```
<?xml version="1.0" encoding="UTF-8"?>
<module xmlns="urn:jboss:module:1.0" name="com.asa">
  <recursos>
    <resource-root path="jconn3.jar"/>
        <!-- Insertar recursos aquí -->
  </recursos>
  <dependencias>
    <module name="javax.api"/>
  </dependencias>
</módulo>
```

Como puede ver arriba, en este ejemplo, establezca el nombre del módulo como "com.asa", que coincide con la estructura de directorios que creó dentro del directorio "modules". Establezca la ruta raíz del recurso al nombre del archivo JAR; la ruta parece ser relativa y, por defecto, al directorio "main" dentro de la estructura de directorios que creó, que en este ejemplo es "com/asa".

Por último, define las dependencias que puedas tener. En este caso, como ocurre con todas las fuentes de datos JDBC, dependeríamos de las API de Java JDBC, que en este caso se definen en otro módulo llamado javax.api, que puedes encontrar en modules/javax/api/main, como cabría esperar.

Los distintos controladores de bases de datos pueden requerir distintas dependencias. Por ejemplo, la base de datos IBM DB2 que funciona con el controlador IBM JDBC requiere las siguientes dependencias:

```
  <dependencias>
    <module name="javax.api"/>
    <module name="javax.transaction.api"/>
    <module name="javax.servlet.api" optional="true"/>
  </dependencias>
```

Y el siguiente nombre de clase (especificado en el archivo standalone.xml más adelante en la siguiente sección):

```
          <driver name="db2jdbc" module="com.ibm.db2">
                 <driver-class>com.ibm.db2.jcc.DB2Driver</driver-class>
                 <xa-datasource-class>com.ibm.db2.jcc.DB2XADataSource</xa-datasource-class>
          </driver>
```

Puedes consultar la documentación proporcionada por el proveedor del controlador de base de datos correspondiente para averiguar las dependencias y el nombre de la clase.

Paso 4: Modificar el archivo JAR.

1. En el mismo directorio que el archivo jconn3.jar, cree un subdirectorio llamado "META-INF" y otro llamado "META-INF\services".
2. En el directorio "META-INF\services", cree un archivo java.sql.Driver que contenga una línea: el nombre de clase completo del controlador JDBC; en este ejemplo, com.sybase.jdbc3.jdbc.SybDriver.
3.  Ejecute el comando "jar" para actualizar el archivo JAR: "jar -uf jconn3.jar META-INF/services/java.sql.Driver". También puede usar WinRAR para agregar el archivo java.sql.Driver al directorio "MEAT-INF\services" dentro de jconn3.jar, como se muestra en la siguiente figura.

    **Figura 51. Modificar el archivo jar**

    ![Modificar el archivo jar](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/modify_the_jar_file.png)<br>

**Configuración de la fuente de datos para JBoss AS 7 a través del archivo de configuración.**

Paso 5: Abra el archivo standalone.xml en la carpeta \<jboss\_installation\_root>\standalone\configuration, busque la fuente de datos relacionada y luego agregue el prefijo "java:/" al valor **jndi-name** si no existe dicho prefijo, como se muestra en el siguiente código de ejemplo.

Deberá consultar la documentación proporcionada por el proveedor del controlador de base de datos correspondiente para averiguar el nombre de la clase.

```
<fuentes de datos>
      <datasource jndi-name="java:/AppeonSample" pool-name="AppeonSample" enabled="true" jta="true" use-java-context="true" use-ccm="true">
          <connection-url>jdbc:sybase:Tds:192.0.3.150:2638/AppeonSample
          </connection-url>
                 <driver>jconnect3</driver>
                 <seguridad>
                      <nombre-de-usuario>dba</nombre-de-usuario>
                      <contraseña>sql</contraseña>
                 </seguridad>
      </fuente de datos>
      <conductores>
          <driver name="jconnect3" module="com.asa">
                 <driver-class>com.sybase.jdbc3.jdbc.SybDriver</driver-class>
          </driver>
          ...
      </controladores>
      ...
</fuentes de datos>
```

**Método 2**

[Instalación de un controlador JDBC a través de la consola web](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s03.html#d0e4186)[Configuración del origen de datos para JBoss AS 7 a través de la consola web](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s03.html#d0e4292)

**Instalación de un controlador JDBC a través de la consola web**

Paso 1: Para acceder directamente a la consola de administración, dirija su navegador a: http://localhost:8080/ o http://127.0.0.1:8080/. Si desea acceder a la consola a través de LAN o WAN (o llamar a EJB), deberá modificar el archivo standalone.xml para agregar una nueva interfaz. Por ejemplo:

<pre><code>&#x3C;interfaces>
        &#x3C;interface name="management">
            &#x3C;inet-address value="127.0.0.1"/>
        &#x3C;/interface>
        &#x3C;interface name="public">
            &#x3C;inet-address value="127.0.0.1"/>
        &#x3C;/interface>

       &#x3C;!-- Equivalente a -b 0.0.0.0 -->
<strong>        &#x3C;interface name="any"> 
</strong><strong>            &#x3C;any-address/> 
</strong><strong>        &#x3C;/interface> 
</strong>&#x3C;/interfaces>
</code></pre>

Y utilice esta nueva interfaz en el grupo de enlace de sockets:

<pre><code>&#x3C;!-- Usar la interfaz "cualquiera" -->
<strong>&#x3C;socket-binding-group name="standard-sockets" default-interface="any">
</strong>        &#x3C;socket-binding name="http" port="8080"/>
        &#x3C;socket-binding name="https" port="8443"/>
        &#x3C;socket-binding name="jmx-connector-registry" port="1090"/>
        &#x3C;socket-binding name="jmx-connector-server" port="1091"/>
        &#x3C;socket-binding name="jndi" port="1099"/>
        &#x3C;socket-binding name="osgi-http" port="8090"/>
        &#x3C;socket-binding name="remoting" port="4447"/>
        &#x3C;socket-binding name="txn-recovery-environment" port="4712"/>
        &#x3C;socket-binding name="txn-status-manager" port="4713"/>
&#x3C;/socket-binding-group>
</code></pre>

Paso 2: Si aún no ha agregado al menos un usuario de administración, se mostrará una página de error que le pedirá que agregue un nuevo usuario. Puede ejecutar el archivo add-user.bat (add-user.sh para Linux) en la carpeta jboss-as-7.1.1.Final\bin. Para obtener más detalles, consulte la sección **«Administración de su servidor de aplicaciones JBoss 7** | **Autenticación** » en [https://docs.jboss.org/author/display/AS71/Getting+Started+Guide](https://docs.jboss.org/author/display/AS71/Getting+Started+Guide) .

**Figura 52. Agregar un nuevo usuario**

![Agregar un nuevo usuario](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/add_a_new_user.png)

<br>

Paso 3: Inicie sesión en la consola de administración de JBoss AS, como se muestra en la siguiente figura.

**Figura 53. Página de configuración de fuentes de datos**

![Página de configuración de fuentes de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/configuration_page.png)<br>

Paso 4: Haga clic en **Implementaciones** > **Administrar implementaciones** , como se muestra en la siguiente figura.

**Figura 54. Página de gestión de implementaciones**

![Página de gestión de implementaciones](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/management_deployments_page.png)

<br>

Paso 5: Modifique el archivo JAR. Consulte el [paso 4](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s03.html#step_4_modify_the_jar_file) de "Instalación de un controlador JDBC mediante el archivo de configuración" para obtener más detalles. Haga clic en **Agregar contenido** para implementar este archivo .jar.

1.  Cargue el archivo jconn3.jar y haga clic en **Siguiente** .

    **Figura 55. Cargar el archivo jar**

    ![Sube el archivo jar](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/deployments_selection_step_1.png)

    <br>
2.  Verifique los nombres de implementación y haga clic en **Guardar** .

    **Figura 56. Verificar el nombre de la implementación**

    ![Verifique el nombre de la implementación](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/deployments_selection_step_2.png)

    <br>

Paso 6: Haga clic en **Habilitar** para activar jconn3.jar, como se muestra en la siguiente figura.

**Figura 57. Habilitar el archivo jar**

![Habilitar el archivo jar](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/enable_jar_file.png)

<br>

**Configuración del origen de datos para JBoss AS 7 a través de la consola web**

Paso 7: Configure la base de datos de destino como un servicio e inicie el servicio SQLAnywhere-appeonsample introduciendo las siguientes líneas de comando en el archivo sqlAnywhere.bat:

"C:\Archivos de programa\SQL Anywhere 12\Bin32\dbsrv12.exe" -x tcpip(puerto=2698) -n duanserv2 "D:\jboss711-hsqldb-2\AppeonSample.db".

Paso 8: Cambie a la pestaña **Perfil** y haga clic en **Agregar** para crear una nueva fuente de datos, como se muestra en la siguiente figura.

**Figura 58. Agregar una nueva fuente de datos**

![Agregar una nueva fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/add_a_new_datasource.png)

<br>

1.  Introduzca cualquier texto como nombre de la fuente de datos y nombre JNDI. Por ejemplo, "java:/appeonsample". Haga clic en **Siguiente** .

    **Nota** : El nombre JNDI se utilizará como nombre de la fuente de datos en AEM.

    **Figura 59. Especificar los atributos de la fuente de datos.**

    ![Especificar los atributos de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/create_datasource_step_1.png)<br>
2.  Seleccione el controlador JDBC, en este ejemplo, jconn3.jar. Haga clic en **Siguiente** .

    **Figura 60. Especificar el controlador JDBC**

    ![Especificar el controlador JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/create_datasource_step_2.png)

    <br>
3.  Especifique la información de conexión y haga clic en **Listo** .

    La siguiente tabla describe cómo especificar la información de conexión para las bases de datos SAP ASA/SQL Anywhere. Los valores varían según el tipo de base de datos. Consulte [los parámetros de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s07.html) .

    **Tabla 24. Propiedades de conexión**

    | URL de conexión   | Por ejemplo, jdbc:sybase:Tds:192.0.2.204:2698?ServiceName=appeonsample                                                                 |
    | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
    | Nombre de usuario | Introduzca el nombre de usuario para acceder a la base de datos. El nombre de usuario se configura en el servidor de la base de datos. |
    | Contraseña        | Introduzca la contraseña de acceso a la base de datos. La contraseña está configurada en el servidor de la base de datos.              |

    <br>

    **Figura 61. Especificar la información de conexión.**

    ![Especifique la información de conexión.](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/create_datasource_step_3.png)

    <br>

Paso 9: Una vez que la fuente de datos se haya creado correctamente, se le redirigirá a la página **Fuentes de datos** y podrá ver la nueva fuente de datos en la lista.

**Figura 62. Lista de fuentes de datos**

![Lista de fuentes de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/jboss_console_5.gif)<br>

**Configuración de la fuente de datos para JBoss 5**

La siguiente sección tomará como ejemplo un tipo de base de datos (base de datos Oracle con controlador JDBC de Oracle) para mostrarle cómo crear una fuente de datos para JBoss 5. Posteriormente, puede crear fuentes de datos para otros tipos de bases de datos siguiendo los mismos pasos que se describen a continuación, pero especificando diferentes parámetros según los [parámetros de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s07.html) .

Los pasos detallados son los siguientes:

Paso 1: Inicie JBoss AS 5 e inicie sesión en la consola de administración de JBoss AS.

Paso 2: Haga clic en **Recursos** > **Fuentes de datos** > **Fuentes de datos de transacciones locales** , como se muestra en la figura siguiente.

Paso 3: Haga clic en **Agregar un nuevo recurso** .

**Figura 63. Agregar una nueva fuente de datos**

![Agregar una nueva fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/jboss1.jpg)<br>

Paso 4: En la **plantilla de recursos** , seleccione **Oracle Local Tx** y, a continuación, haga clic en **Continuar** .

Si utiliza otro tipo de base de datos, seleccione la opción predeterminada.

**Figura 64. Seleccionar plantilla de recursos**

![Seleccione la plantilla de recursos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/jboss2.jpg)<br>

Paso 5: Especifique la información de conexión y haga clic en **Guardar** .

**Figura 65. Especificar la información de conexión.**

![Especifique la información de conexión.](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/jboss3.jpg)<br>

La siguiente tabla describe cómo especificar las propiedades para la información de conexión.

**Tabla 25. Propiedades de la fuente de datos**

| Nombre JNDI             | Introduzca cualquier texto como nombre de la fuente de datos. Por ejemplo, "oracle\_datasource1". Este nombre será reconocido como el nombre de la fuente de datos en AEM.                                                                                                                                                                                                |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nombre de usuario       | Introduzca el nombre de usuario para acceder a la base de datos. El nombre de usuario se configura en el servidor de la base de datos.                                                                                                                                                                                                                                    |
| Contraseña              | Introduzca la contraseña de acceso a la base de datos. La contraseña está configurada en el servidor de la base de datos.                                                                                                                                                                                                                                                 |
| Clase de conductor JDBC | oracle.jdbc.driver.OracleDriver                                                                                                                                                                                                                                                                                                                                           |
| URL de conexión         | <p>jdbc:oracle:thin:@ <em>hostname</em> : <em>puerto</em> : <em>DBName</em> para Oracle 9i, 10g y 11g</p><p>jdbc:oracle:thin:@// <em>hostname</em> : <em>puerto</em> / <em>DBName</em> para Oracle 12c</p><p>Por ejemplo:</p><p>jdbc:oracle:thin:@192.0.0.51:1521:pruebas para Oracle 9i, 10g y 11g</p><p>jdbc:oracle:thin:@//192.0.0.51:1521/pruebas para Oracle 12c</p> |

<br>

Paso 6: Para probar la conexión, inicie sesión en Appeon AEM para configurar un objeto de transacción y, a continuación, pruébelo.
