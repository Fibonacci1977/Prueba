# Configurando la fuente de datos para WebLogic

[Configuración de la fuente de datos para WebLogic 8.1](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s01.html#setting_up_data_sources_for_WebLogic_8.1_j2ee)[Configuración de la fuente de datos para WebLogic 11g](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s01.html#setting_up_data_sources_for_WebLogic_11g_j2ee)

**Configuración de la fuente de datos para WebLogic 8.1**

[Creación de un grupo de conexiones JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s01.html#d0e2451)[Configuración de una fuente de datos JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s01.html#d0e2574)

La siguiente sección tomará como ejemplo un tipo de base de datos (base de datos ASA/SQL Anywhere con controlador JDBC jConnect) para mostrarle cómo crear una fuente de datos para WebLogic. Posteriormente, puede crear fuentes de datos para otros tipos de bases de datos siguiendo los mismos pasos que se describen a continuación, pero especificando diferentes parámetros según los [parámetros de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s07.html) .

Puede crear un grupo de conexiones y una fuente de datos utilizando la consola del servidor WebLogic o el asistente de configuración.

Nota: Appeon Server y AEM considerarán como nombre de origen de datos el nombre JNDI especificado para la fuente de datos.

**Creación de un grupo de conexiones JDBC**

1\. Inicie el servidor WebLogic para su dominio.

2\. Inicie sesión en la consola del servidor WebLogic.

3\. Vaya a **Servicios** > **JDBC** > **Grupos de conexiones** .

**Figura 2. Configurar un grupo de conexiones JDBC**

![Configurar un grupo de conexiones JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/configure_a_jdbc_connection_pool.gif)<br>

4\. Haga clic en el enlace **Configurar un nuevo grupo de conexiones JDBC** .

5\. Seleccione el tipo de base de datos y el controlador en las listas desplegables y haga clic en **Continuar** .

**Figura 3. Seleccionar base de datos**

![Seleccionar base de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/choose_database.gif)<br>

6\. Elija un nombre para el nuevo grupo de conexiones (por ejemplo, appeontutor) y complete los campos en blanco para la base de datos ASA/SQL Anywhere. Haga clic en **Continuar** .

**Tabla 14. Propiedades del grupo de conexiones**

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top">Nombre</td><td valign="top">Introduzca el nombre del nuevo grupo de conexiones.</td></tr><tr><td valign="top">Nombre de la clase del controlador</td><td valign="top">com.sybase.jdbc2.jdbc.SybDriver</td></tr><tr><td valign="top">URL</td><td valign="top">jdbc:sybase:Tds: <em>hostname</em> :2638/ <em>dbname</em> (El puerto predeterminado de la base de datos ASA/SQL Anywhere es 2638)</td></tr><tr><td valign="top">Nombre de usuario de la base de datos</td><td valign="top">Introduzca el nombre de usuario para acceder a la base de datos. El nombre de usuario se configura en el servidor de la base de datos.</td></tr><tr><td valign="top">Contraseña</td><td valign="top">Introduzca la contraseña de acceso a la base de datos. La contraseña se configura en el servidor de la base de datos.</td></tr></tbody></table>

<br>

**Figura 4. Propiedades de la fuente de datos**

![Propiedades de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/data_source_properties.gif)<br>

7\. Prueba tu conexión para verificar que puedes conectarte a tu base de datos.

8\. Cree e implemente el nuevo grupo de conexiones.

**Configuración de una fuente de datos JDBC**

1\. Vaya a **Servicios** > **JDBC** > **Fuentes de datos** .

**Figura 5. Configurar una fuente de datos JDBC**

![Configurar una fuente de datos JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/configure_a_jdbc_data_source.jpg)<br>

2\. Haga clic en el enlace **Configurar un nuevo origen de datos JDBC** .

3\. Especifique el nombre de la nueva fuente de datos y el nombre JNDI, y haga clic en **Continuar** . Puede usar los valores predeterminados para las demás opciones.

Nota: El nombre JNDI se utilizará como fuente de datos en AEM.

**Figura 6. Propiedades de la fuente de datos**

![Propiedades de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/data_source_properties.jpg)<br>

4\. Seleccione el grupo de conexiones recién creado en la lista desplegable y haga clic en **Continuar** .

**Figura 7. Seleccione el grupo de conexiones.**

![Seleccione el grupo de conexiones](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/select_the_connection_pool.gif)<br>

5\. Seleccione el servidor en el que desea implementar el origen de datos JDBC y haga clic en **Crear** .

**Figura 8. Seleccionar la fuente de datos**

![Seleccionar la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/target_the_data_source.jpg)<br>

6\. Confirme que el estado "Implementado" del origen de datos sea "verdadero" en la ventana Orígenes de datos JDBC.

**Figura 9. Estado de despliegue**

![Estado de despliegue](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/deployed_status.jpg)<br>

**Configuración de la fuente de datos para WebLogic 11g**

La siguiente sección tomará como ejemplo un tipo de base de datos (base de datos ASA/SQL Anywhere con controlador JDBC jConnect 6.0) para mostrarle cómo crear una fuente de datos para WebLogic. Posteriormente, puede crear fuentes de datos para otros tipos de bases de datos siguiendo los mismos pasos que se describen a continuación, pero especificando diferentes parámetros según los [parámetros de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s07.html) .

Puede crear un origen de datos utilizando la consola del servidor WebLogic o el asistente de configuración.

Los pasos detallados son los siguientes:

Paso 1: Inicie el servidor de administración para el dominio de WebLogic Server.

Paso 2: Inicie sesión en la consola de administración de WebLogic Server.

Paso 3: En la sección **Estructura del dominio** , seleccione **Servicios** > **JDBC** > **Orígenes de datos** .

Paso 4: En el resumen de la página **Resumen de fuentes de datos JDBC** , haga clic en **Nuevo** .

**Figura 10. Resumen de la página de fuentes de datos JDBC**

![Página de resumen de fuentes de datos JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/weblogic1.png)<br>

Paso 5: En la página **Propiedades de la fuente de datos JDBC** , introduzca o seleccione la siguiente información y, a continuación, haga clic en **Siguiente** .

**Figura 11. Página de propiedades de la fuente de datos JDBC**

![Página de propiedades de la fuente de datos JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/weblogic2.png)<br>

Complete la información solicitada en la tabla a continuación.

**Tabla 15. Propiedades de la fuente de datos JDBC**

|             Campo            |                                                                              Descripción                                                                              |                      Valor                     |
| :--------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------: |
|            Nombre            |                                                    Introduzca el nombre deseado para la nueva fuente de datos JDBC.                                                   |              Ejemplo de aplicación             |
|          Nombre JNDI         | <p>Introduzca un nombre JNDI que desee asignar a su nueva fuente de datos JDBC.</p><p>Nota: El nombre JNDI se utilizará como nombre de la fuente de datos en AEM.</p> |              Ejemplo de aplicación             |
|     Tipo de base de datos    |                                                      Seleccione el tipo de base de datos en la lista desplegable.                                                     |                      SAVIA                     |
| Controlador de base de datos |                                                     Seleccione la unidad de base de datos en la lista desplegable.                                                    | Versiones del controlador de SAP (Tipo 4): 6.X |

<br>

Paso 6: En la página **Opciones de transacciones** , marque la casilla **Admite transacciones globales** y seleccione el botón de opción **Confirmación en una fase** , y luego haga clic en **Siguiente.**

**Figura 12. Opciones de transacción**

![Opciones de transacción](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/weblogic3.png)<br>

Paso 7: En la página **Propiedades de conexión** , introduzca la siguiente información y, a continuación, haga clic en **Siguiente.**

**Figura 13. Página de propiedades de conexión**

![Página de propiedades de conexión](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/weblogic5.png)<br>

Complete la información solicitada en la tabla a continuación.

**Tabla 16. Página de propiedades de conexión**

|                 Campo                 |                                                           Descripción                                                          |         Valor         |
| :-----------------------------------: | :----------------------------------------------------------------------------------------------------------------------------: | :-------------------: |
|       Nombre de la base de datos      |                               Introduzca el nombre de la base de datos a la que desea conectarse.                              | Ejemplo de aplicación |
|            Nombre del host            |                        Introduzca el nombre de host o la dirección IP del servidor de la base de datos.                        |      192.0.3.142      |
|                 Puerto                |    Introduzca un puerto de base de datos en el servidor de base de datos que se utilice para conectarse a la base de datos.    |          2638         |
| Nombre de usuario de la base de datos | Introduzca el nombre de usuario de la cuenta de base de datos que desea utilizar para crear las conexiones a la base de datos. |          dba          |
|               Contraseña              |     Introduzca la contraseña de la cuenta de base de datos que desea utilizar para crear las conexiones a la base de datos.    |          SQL          |
|          confirmar Contraseña         |                                         Introduzca la misma contraseña para confirmar.                                         |          SQL          |

<br>

Paso 8: En la página **Probar conexión a la base de datos** , especifique el **nombre de la clase del controlador** y la **URL** , y luego haga clic en **Probar configuración** . Si la prueba es exitosa, aparecerá el mensaje "Prueba de conexión exitosa" en la parte superior de la página. Si la prueba no es exitosa, corrija los errores de configuración y vuelva a intentarla. Luego, haga clic en **Siguiente** .

**Figura 14. Página de prueba de conexión a la base de datos.**

![Página de prueba de conexión a la base de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/weblogic6.png)<br>

Complete la información solicitada en la tabla a continuación.

**Tabla 17. Especifique el nombre de la clase del controlador y la URL.**

|               Campo              |                               Descripción                              |                                                        Valor                                                       |
| :------------------------------: | :--------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------: |
| Nombre de la clase del conductor | Introduzca el nombre del controlador de la base de datos especificada. |                                           com.sybase.jdbc3.jdbc.SybDriver                                          |
|                URL               |   Introduzca el nombre del servidor de la base de datos especificada.  | <p>jdbc:sybase:Tds:Hostname:Port/ServiceName</p><p>Por ejemplo: jdbc:sybase:Tds:192.0.3.142:2638/Appeonsample.</p> |

<br>

Paso 9: En la página **Seleccionar destinos** , seleccione la casilla de verificación **AdminServer** y, a continuación, haga clic en **Finalizar** .

**Figura 15. Página de selección de objetivos**

![Seleccionar página de objetivos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/weblogic13.png)<br>

Paso 10: En la página **Resumen de fuentes de datos JDBC** , la fuente de datos que creó aparece en la lista; luego, haga clic en el enlace con el nombre de la nueva fuente de datos en la ventana **Fuentes de datos** .

**Figura 16. Resumen de la página de fuentes de datos JDBC**

![Resumen de la página de fuentes de datos JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/weblogic8.png)<br>

Paso 11: **(Importante)** En la página **Configuración del dominio base , haga clic en appeon** en la sección **Estructura del dominio** y, a continuación, seleccione la pestaña **Seguridad . Marque la casilla de verificación Búsqueda de administrador anónimo habilitada** y haga clic en **Guardar** . **Esto permitirá que AEM lea los nombres JNDI.**

**Figura 17. Configuración para la página base\_domain**

![Configuración para la página base\_domain](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/weblogic9.png)<br>

Paso 12: Seleccione **Todos los programas** > **Oracle WebLogic** > **Proyectos de usuario** > **appeon** desde el menú **Inicio de Windows** para reiniciar su servidor WebLogic para que los cambios de configuración surtan efecto.

Paso 13: Para probar la conexión, inicie sesión en Appeon AEM para configurar un objeto de transacción y, a continuación, pruébelo.
