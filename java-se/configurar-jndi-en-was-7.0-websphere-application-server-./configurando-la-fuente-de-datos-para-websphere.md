# Configurando la fuente de datos para WebSphere



[Configuración de la fuente de datos para WebSphere 6.1](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#setting_up_data_sources_for_WebSphere_6.1_j2ee)[Configuración de la fuente de datos para WebSphere 8.0](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#setting_up_data_sources_for_Websphere_8.0_j2ee)[Configuración del origen de datos para WebSphere Application Server CE](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#setting_up_data_sources_for_Websphere_Community_j2ee)[Configuraciones necesarias cuando la seguridad global está activada](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#required_configurations_when_global_security_is_on)

**Configuración de la fuente de datos para WebSphere 6.1**

[Actualizando la ruta del controlador JDBC en la configuración maestra](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#d0e3059)[Creación de una nueva entrada de datos de autenticación J2C](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#Creating_a_new_J2C_authentication_data_entry)[Creación y configuración de un proveedor JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#d0e3158)[Creación de una fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#d0e3205)

La siguiente sección tomará como ejemplo un tipo de base de datos (base de datos Oracle con controlador JDBC de Oracle) para mostrarle cómo crear una fuente de datos para WebSphere. Posteriormente, puede crear fuentes de datos para otros tipos de bases de datos siguiendo los mismos pasos que se describen a continuación, pero especificando diferentes parámetros según [los parámetros de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s07.html) .

**Nota:**

1. El nombre JNDI especificado para la fuente de datos será considerado como el nombre de la fuente de datos por Appeon Server y AEM.
2. Si el **modo de seguridad global** está activado en WebSphere, AEM no podrá acceder a las fuentes de datos de WebSphere. Consulte [la sección «Configuraciones necesarias cuando la seguridad global está activada»](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#required_configurations_when_global_security_is_on) para obtener soluciones.

**Actualizando la ruta del controlador JDBC en la configuración maestra**

1\. Inicie el servidor WebSphere e inicie sesión en la consola del servidor WebSphere.

2\. Haga clic en **Entorno** > **Administrar variables de WebSphere** en la consola.

3\. Establezca la ruta del controlador JDBC de Oracle al valor de la variable ORACLE\_JDBC\_DRIVER\_PATH.

Como se requiere para [la preparación del controlador JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s02s04.html) , la ruta del controlador JDBC de Oracle es %WAS\_HOME%\lib\ (Windows) o $WAS\_HOME/lib/ (Unix/Linux). WAS\_HOME es la carpeta de instalación de la plataforma WebSphere.

4\. Guarde los cambios en la variable ORACLE\_JDBC\_DRIVER\_PATH en la configuración maestra.

**Creación de una nueva entrada de datos de autenticación J2C**

1\. Haga clic en **Seguridad** > Configuración de JAAS en la consola administrativa de WebSphere y, a continuación, haga clic en Datos de autenticación J2C.

2\. Haga clic en **Nuevo** para crear una nueva entrada de datos de autenticación J2C.

**Figura 18. Nueva entrada de datos de autenticación J2C**

![Nueva entrada de datos de autenticación J2C](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/new_j2c_authentication_data_entry.jpg)<br>

Complete la información solicitada en la tabla a continuación.

**Tabla 18. Detalles para la nueva entrada de datos de autenticación.**

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top">Alias</td><td valign="top">Introduzca un nombre adecuado (corto), como por ejemplo "UDDIAlias".</td></tr><tr><td valign="top">ID de usuario</td><td valign="top">Introduzca el ID de usuario de la base de datos que se utiliza para leer y escribir en la base de datos del registro UDDI.</td></tr><tr><td valign="top">Contraseña</td><td valign="top">Introduzca la contraseña asociada al ID de usuario especificado anteriormente.</td></tr><tr><td valign="top">Descripción</td><td valign="top">Introduzca una descripción adecuada del ID de usuario elegido o déjelo en blanco.</td></tr></tbody></table>

<br>

3\. Haga clic en **Aplicar** y guarde los cambios en la configuración maestra.

**Creación y configuración de un proveedor JDBC**

1\. Haga clic en **Recursos** | **Proveedores JDBC** en la consola administrativa de WebSphere.

2\. Haga clic en **Nuevo** . Se abrirá la ventana de configuración de proveedores JDBC.

**Figura 19. Ventana de configuración de proveedores JDBC**

![Ventana de configuración de proveedores JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/jdbc_providers_configuration_window.jpg)<br>

3\. Seleccione el tipo de proveedor JDBC correcto. Por ejemplo, Controlador JDBC de Oracle.

**Figura 20. Seleccionar tipo de proveedor JDBC**

![Seleccione el tipo de proveedor JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/select_jdbc_provider_type.jpg)<br>

4\. Seleccione el proveedor del controlador y el archivo del controlador.

**Figura 21. Proveedor de controlador JDBC y archivo del controlador.**

![Proveedor de controladores JDBC y archivo de controlador](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/jdbc_driver_provider_and_driver_file.jpg)<br>

El campo Classpath muestra la ruta al archivo JDBC que está configurado en la variable de WebSphere, por ejemplo, el controlador ORACLE\_JDBC\_DRIVER\_PATH.

5\. Haga clic en **Aceptar** para volver a la página de proveedores JDBC, donde el nuevo controlador JDBC aparecerá en la lista.

6\. Guarda la configuración.

**Creación de una fuente de datos**

1\. Haga clic en **Recursos** > **Proveedores JDBC** en la consola de administración.

2\. Elija el proveedor de recursos JDBC bajo el cual desea crear la fuente de datos.

3\. Haga clic en el enlace **Fuentes de datos** en **Propiedades adicionales** . Se mostrará la página Fuentes de datos.

**Figura 22. Página de origen de datos**

![Página de origen de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/data_source_page.jpg)<br>

4\. Haga clic en **Nuevo** para mostrar la página de configuración de la fuente de datos.

5\. Especifique el nombre de la fuente de datos y el nombre JNDI de la fuente de datos.

**Nota:**

* El nombre JNDI especificado para la fuente de datos será considerado como el nombre de la fuente de datos por Appeon Server y AEM.
* Si el **modo de seguridad global** está activado en WebSphere, AEM no podrá acceder a las fuentes de datos de WebSphere. Consulte [la sección «Configuraciones necesarias cuando la seguridad global está activada»](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#required_configurations_when_global_security_is_on) para obtener soluciones.

**Figura 23. Propiedades de la fuente de datos**

![Propiedades de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/data_source_properties_websphere_6.1.jpg)<br>

6\. Seleccione la entrada de datos de autenticación J2C configurada en la [sección "Creación de una nueva entrada de datos de autenticación J2C"](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#Creating_a_new_J2C_authentication_data_entry) en el cuadro de lista "Alias ​​de autenticación administrados por el contenedor".

7\. Haga clic en **Aplicar** y **Aceptar** para volver a la ventana Orígenes de datos. El nombre del nuevo origen de datos se mostrará en la ventana.

8\. Haga clic en el nombre de la nueva fuente de datos en la ventana Fuentes de datos.

9\. Haga clic en el enlace Propiedades personalizadas en la ventana Propiedades adicionales de la configuración de la fuente de datos.

**Figura 24. Propiedades adicionales**

![Propiedades adicionales](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/additional_properties.jpg)<br>

10\. Configure todos los campos requeridos según las instrucciones de la ventana. Por ejemplo, establezca la propiedad URL en jdbc:oracle:thin:@192.0.0.51:1521:testing si Oracle 9i, 10g y 11g, o jdbc:oracle:thin:@//192.0.0.51:1521/testing si Oracle 12c.

**Figura 25. Propiedad URL de la fuente de datos**

![Propiedad URL de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/data_source_url_property.jpg)<br>

11\. Haga clic en **Aceptar** para volver a la ventana de configuración de la fuente de datos.

12\. Haga clic en Probar conexión para la nueva fuente de datos. Asegúrese de que la conexión sea exitosa antes de continuar.

13\. Guarda la configuración maestra.

**Configuración de la fuente de datos para WebSphere 8.0**

[Creación y configuración de un proveedor JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#d0e3326)[Creación de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#d0e3498)

La siguiente sección tomará como ejemplo un tipo de base de datos (base de datos Teradata con controlador JDBC de Teradata) para mostrarle cómo crear una fuente de datos para WebSphere. Posteriormente, puede crear fuentes de datos para otros tipos de bases de datos siguiendo los mismos pasos que se describen a continuación, pero especificando diferentes parámetros según los [parámetros de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s07.html) .

**Nota:**

1. El nombre JNDI especificado para la fuente de datos será considerado como el nombre de la fuente de datos por Appeon Server y AEM.
2. Si el **modo de seguridad global** está activado en WebSphere, AEM no podrá acceder a las fuentes de datos de WebSphere. Consulte [la sección «Configuraciones necesarias cuando la seguridad global está activada»](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#required_configurations_when_global_security_is_on) para obtener soluciones.

**Creación y configuración de un proveedor JDBC**

Paso 1: Inicie el servidor WebSphere e inicie sesión en la consola del servidor WebSphere.

Paso 2: Haga clic en **Recursos** > **JDBC** > **Proveedores JDBC** . En el panel derecho, seleccione el ámbito apropiado para el proveedor JDBC. (Este ámbito se convierte en el ámbito de su origen de datos). Puede elegir una celda, un nodo, un clúster o un servidor. A continuación, haga clic en **Nuevo** .

**Figura 26. Página de proveedores JDBC**

![Página de proveedores de JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_003.png)<br>

Paso 3: En la página Crear nuevo proveedor JDBC, introduzca o seleccione la siguiente información y, a continuación, haga clic en **Siguiente** .

**Figura 27. Crear una nueva página de proveedor JDBC**

![Crear nueva página de proveedor JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_004.png)<br>

Complete la información solicitada en la tabla a continuación.

**Tabla 19. Crear un nuevo proveedor JDBC**

|                 Campo                |                                                                                                         Descripción                                                                                                         |                      Valor                     |
| :----------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------: |
|         Tipo de base de datos        | Seleccione el tipo de base de datos del proveedor JDBC que necesita crear en la lista desplegable. Nota: Si la lista de tipos de base de datos no incluye el tipo que desea utilizar, seleccione "Definido por el usuario". |             Definido por el usuario            |
| Nombre de la clase de implementación |                                                                Introduzca el nombre del controlador del grupo de conexiones de la base de datos especificada.                                                               | com.teradata.jdbc.TeraConnectionPoolDataSource |
|                Nombre                |                                                                                  Introduzca el nombre deseado para el nuevo proveedor JDBC.                                                                                 |              Controlador Teradata              |
|              Descripción             |                                                                         Introduzca la descripción que desee para describir su nuevo proveedor JDBC.                                                                         |              Controlador Teradata              |

<br>

Paso 4: En la página Introducir información de la ruta de clases de la base de datos, introduzca la ruta de clases de la base de datos y, a continuación, haga clic en **Siguiente** .

**Figura 28. Página de información de la ruta de clases de la base de datos**

![Ingrese la página de información de la ruta de clases de la base de datos.](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_005.png)<br>

Complete la información solicitada en la tabla a continuación.

**Tabla 20. Información de la ruta de clases de la base de datos**

|      Campo     |                                                                                                                    Descripción                                                                                                                   |                                    Valor                                   |
| :------------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------: |
| Ruta de clases | El nombre completo de los archivos JAR que componen el controlador JDBC de Teradata. El ejemplo asume que ha copiado estos archivos al directorio C:\teradatajdbc de su sistema. En un sistema Unix, la ruta se separaría con barras diagonales. | <p>C:\teradatajdbc\terajdbc4.jar</p><p>C:\teradatajdbc\tdgssconfig.jar</p> |

<br>

Paso 5: En la página Resumen, puede revisar la configuración y, cuando termine, haga clic en **Finalizar** .

**Figura 29. Página de resumen**

![Página de resumen](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_006.png)<br>

Paso 6: En la página de proveedores JDBC, haga clic en **Guardar** para confirmar estos cambios en la configuración maestra y que se apliquen en el servidor.

**Figura 30. Página de proveedores JDBC**

![Página de proveedores de JDBC](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_007.png)<br>

Ahora, el "Controlador Teradata" aparece en la lista de proveedores JDBC.

**Figura 31. La página de proveedores JDBC recién creada.**

![La página de proveedores JDBC recién creada](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_008.png)<br>

**Creación de la fuente de datos**

Paso 1: Inicie el servidor WebSphere e inicie sesión en la consola del servidor WebSphere.

Paso 2: Haga clic en **Recursos** > **JDBC** > **Orígenes de datos** . En el panel derecho, seleccione el ámbito apropiado para el origen de datos. (Este ámbito se convierte en el ámbito de su origen de datos). Puede elegir una celda, un nodo, un clúster o un servidor. A continuación, haga clic en **Nuevo** .

**Figura 32. Crear la página de origen de datos**

![Crear la página de origen de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_009.png)<br>

Paso 3: En la página «Introducir información básica de la fuente de datos», introduzca la siguiente información. A continuación, haga clic en **Siguiente.**

**Figura 33. Página de introducción de información básica de la fuente de datos.**

![Introduzca la página de información básica sobre la fuente de datos.](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_010.png)<br>

Complete la información solicitada en la tabla a continuación.

**Tabla 21. Información básica sobre la fuente de datos.**

|             Campo            |                                  Descripción                                 |         Valor        |
| :--------------------------: | :--------------------------------------------------------------------------: | :------------------: |
| Nombre de la fuente de datos |       Introduzca el nombre deseado para la nueva fuente de datos JDBC.       | pruebaTeradataJdbcDS |
|          Nombre JNDI         | Introduzca un nombre JNDI que desee asignar a su nueva fuente de datos JDBC. | pruebaTeradataJdbcDS |

<br>

**Nota:**

* El nombre JNDI especificado para la fuente de datos será considerado como el nombre de la fuente de datos por Appeon Server y AEM.
* Si el **modo de seguridad global** está activado en WebSphere, AEM no podrá acceder a las fuentes de datos de WebSphere. Consulte [la sección «Configuraciones necesarias cuando la seguridad global está activada»](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#required_configurations_when_global_security_is_on) para obtener soluciones.

Paso 4: En la página **Seleccionar proveedor JDBC , haga clic en Seleccionar un proveedor JDBC existente** y seleccione **Controlador Teradata** en la lista desplegable. A continuación, haga clic en **Siguiente** .

**Figura 34. Seleccionar página del proveedor JDBC**

![Seleccione la página del proveedor JDBC.](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_011.png)<br>

Paso 5: En la página Introduzca las propiedades específicas de la base de datos para el origen de datos, haga clic en **Siguiente** .

**Figura 35. Introduzca las propiedades específicas de la base de datos para la página de origen de datos.**

![Introduzca las propiedades específicas de la base de datos para la página de origen de datos.](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_012.png)<br>

Complete la información solicitada en la tabla a continuación.

**Tabla 22. Propiedades específicas de la base de datos para la fuente de datos.**

|                       Campo                      |                                 Descripción                                |                                                        Valor                                                       |
| :----------------------------------------------: | :------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------: |
| nombre de la clase auxiliar del almacén de datos | Clases auxiliares de almacenamiento de datos proporcionadas por WebSphere. |              Seleccione el valor predeterminado "com.ibm.websphere.rsadapter.GenericDataStoreHelper".              |
|     Persistencia gestionada por contenedores     |        Configurar si se utiliza la fuente de datos para CMP de EJB.        | Marque esta casilla si la fuente de datos se utiliza con beans de entidad CMP. De lo contrario, déjela sin marcar. |

<br>

Paso 6: En la página **Configurar alias de seguridad** , mantenga los valores predeterminados como "ninguno" y, a continuación, haga clic en **Siguiente.**

**Figura 36. Página de configuración de alias de seguridad**

![Página de configuración de alias de seguridad](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_013.png)<br>

Paso 7: En la página **Resumen** , puede revisar la configuración y, cuando termine, haga clic en **Finalizar** .

**Figura 37. Página de resumen**

![Página de resumen](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_014.png)<br>

Paso 8: En la página **Fuentes de datos , haga clic en Guardar** para confirmar estos cambios en la configuración maestra y que se apliquen en el servidor.

**Figura 38. Página de fuentes de datos**

![Página de fuentes de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_015.png)<br>

Paso 9: En la página siguiente, haga clic en **testTeradataJdbcDS** en la ventana **Fuentes de datos** .

**Figura 39. La página de información de la fuente de datos recién creada.**

![La página de información de la fuente de datos recién creada](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_016.png)<br>

Paso 10: En la página siguiente, haga clic en el enlace Propiedades personalizadas en Propiedades adicionales de la ventana de configuración de la fuente de datos.

**Figura 40. Detalles de la página de información de la fuente de datos recién creada.**

![Los detalles de la página de información de la fuente de datos recién creada](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_017.png)<br>

Paso 11: En la página **Propiedades personalizadas** , especifique las propiedades personalizadas y haga clic en **Guardar** .

**Figura 41. Página de propiedades personalizadas**

![Página de propiedades personalizadas](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_018.png)<br>

Complete la información solicitada en la tabla a continuación.

**Tabla 23. Propiedades personalizadas**

|     Nombre    |                                                                          Descripción                                                                         |    Valor   |
| :-----------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------: |
| Nombre del DS |                                       Introduzca el nombre de host o la dirección IP del servidor de la base de datos.                                       | 192.0.2.54 |
|    USUARIO    |                Introduzca el nombre de usuario de la cuenta de base de datos que desea utilizar para crear las conexiones a la base de datos.                |     DBC    |
|   CONTRASEÑA  |                    Introduzca la contraseña de la cuenta de base de datos que desea utilizar para crear las conexiones a la base de datos.                   |     DBC    |
|    CHARSET    | Introduzca el conjunto de caracteres de sesión utilizado para asignar caracteres bidireccionalmente desde la aplicación cliente y la base de datos Teradata. |    UTF8    |
|     MODO T    |                                         Acceda al modo de sesión en un sistema Teradata Database V2R2.0 o posterior.                                         |    ANSI    |
|     cuenta    |                      Introduzca el nombre de la cuenta de base de datos que desea utilizar para crear las conexiones a la base de datos.                     |     DBC    |

<br>

Paso 12: Haga clic en **Probar conexión** para la nueva fuente de datos. Si la fuente de datos se crea correctamente, aparecerá el siguiente mensaje.

**Figura 42. Prueba de conexión para la fuente de datos.**

![Pruebe la conexión con la fuente de datos.](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/teradata_024.png)<br>

**Configuración del origen de datos para WebSphere Application Server CE**

[Agregar bibliotecas Java al repositorio del servidor](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#d0e3835)[Creando grupo de base de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s02.html#d0e3886)

La siguiente sección tomará como ejemplo un tipo de base de datos (base de datos ASA/SQL Anywhere con controlador JDBC) para mostrarle cómo crear una fuente de datos para WASCE (WebSphere Application Server Community Edition). Posteriormente, puede crear fuentes de datos para otros tipos de bases de datos siguiendo los mismos pasos que se describen a continuación, pero especificando diferentes parámetros según los [parámetros de la fuente de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/ch03s03s07.html) .

**Agregar bibliotecas Java al repositorio del servidor**

Existen dos maneras de agregar bibliotecas Java al repositorio del servidor. En esta guía, se utilizará como ejemplo el método mediante la consola WASCE. Para conocer el otro método, consulte la documentación de WASCE correspondiente.

Paso 1: Abra su navegador web e inicie sesión en la consola web del servidor.

Paso 2: En la página de inicio de sesión, acceda a la consola web introduciendo el nombre y la contraseña de un usuario autorizado para acceder a la consola web. Inicialmente, el nombre de usuario es **system** y la contraseña es **manager** .

Paso 3: En la página de la consola web, busque la navegación de la consola y, a continuación, seleccione el botón de opción **Avanzado** .

Paso 4: Navegue a **Agregar archivo al repositorio** desde **Recursos** > **Repositorio** .

Paso 5: Haga clic en **Examinar** para agregar el archivo de archivo; especifique la **cadena de artefacto** y el **nombre del componente reemplazado** y, a continuación, haga clic en el botón **Instalar** , como se muestra en la siguiente figura.

**Figura 43. Agregar archivo al repositorio**

![Agregar archivo al repositorio](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/add_archive_to_reporsitory.png)<br>

**Creando grupo de base de datos**

Paso 1: En la consola de WASCE, navegue hasta **Grupos de bases de datos** en **Recursos** > **Orígenes de datos** y, a continuación, haga clic en **Usar el asistente de grupo de bases de datos de WebSphere CE** .

**Figura 44. Creación de grupos de bases de datos**

![Crear grupos de bases de datos](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/wasce_database_pools.png)<br>

Paso 2: En el **Paso 1: Seleccionar nombre y base de datos** del asistente del grupo de bases de datos, especifique un nombre para el grupo de bases de datos en el cuadro de texto **Nombre del grupo de bases de datos** y seleccione un tipo de base de datos en la lista desplegable **Tipo de base de datos .**

**Figura 45. Especificar nombre y base de datos**

![Especifique el nombre y la base de datos.](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/create_database_pool.png)<br>

Paso 3: Haga clic en **Siguiente** .

Paso 4: En el **Paso 2: Seleccionar unidad, archivo JAR y parámetros** del asistente del grupo de bases de datos, haga lo siguiente:

* Especifique el controlador en el cuadro de texto **Clase de controlador JDBC** ;
* Seleccione el archivo JAR del controlador en el cuadro de lista **Archivo JAR del controlador** ;
* Introduzca un nombre de usuario de la base de datos en el cuadro de texto **Nombre de usuario de la base de datos ;**
* Introduzca una contraseña en el cuadro de texto **Contraseña de la base de datos** y vuelva a introducirla en el cuadro de texto **Confirmar contraseña** ;
* Introduzca la URL del host en el cuadro de texto **Host ;**
* Especifique un nombre de base de datos en el cuadro de texto **Base de datos ;**
* Deje el puerto como está por defecto;
* Haz clic **en Siguiente.**

**Figura 46. Seleccionar controlador, archivo JAR y parámetros.**

![Seleccione Controlador, Jar, Parámetros](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/create_database_pool_step2.png)<br>

Paso 5: En el **Paso 3: Configuración final** del grupo del asistente del grupo de bases de datos, especifique los elementos de acuerdo con sus necesidades reales y, a continuación, haga clic en **Probar conexión** .

Para bases de datos ASA/SQL Anywhere, asegúrese de seleccionar **NINGUNO** en el campo **Tipo de transacción** .

**Figura 47. Final**

![Final](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/create_database_pool_step3.png)<br>

Paso 6: En el **Paso 4: Probar conexión** del asistente del grupo de bases de datos, haga clic en **Implementar** .

**Figura 48. Prueba de conexión e implementación.**

![Prueba la conexión y despliega.](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/create_database_pool_step4.png)<br>

Paso 7: Vuelva a **Fuentes de datos** en la Consola de administración y verá la _AppeonSample implementada, como se muestra en la siguiente figura._

**Figura 49. Visualización de los grupos de conexiones desplegados en las fuentes de datos.**

![Vea los grupos de conexiones implementados en Fuentes de datos.](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/wasce_database_pools1.png)<br>

Paso 8: Para verificar si el grupo de bases de datos se creó correctamente, vaya a **Objetos de transacción** ( **AEM** > **Aplicación** > **Transacción** > **Objetos de transacción** > _Nombre de la aplicación_ ) en AEM y, a continuación, consulte el grupo de conexiones implementado en la lista desplegable **Origen de datos** , como se muestra en la siguiente figura. Si el grupo de bases de datos aparece en la lista desplegable **Origen de datos** , significa que se creó correctamente.

**Figura 50. Visualización de los grupos de conexiones desplegados en AEM.**

![Visualice los grupos de conexiones implementados en AEM.](https://docs.appeon.com/2015/server_configuration_guide_for_j2ee/images/view_deployed_connection_pools_in_aem.png)<br>

**Configuraciones necesarias cuando la seguridad global está activada**

**Nota** : Esta sección no es necesaria para las ediciones comunitarias de WebSphere Application Server.

Si el modo de seguridad global está activado en WebSphere, AEM no podrá acceder a las fuentes de datos de WebSphere. Puede realizar las siguientes configuraciones para solucionar este problema.

Paso 1: Vaya al directorio %user.install.root%\properties (%user.install.root% indica el directorio de instalación de la instancia de WebSphere, por ejemplo, C:\Program Files\IBM\WebSphere\AppServer\profiles\AppSrv01\\), abra el archivo sas.client.props en un editor de texto y modifique las siguientes tres propiedades:

* com.ibm.CORBA.loginUserid: se establece con el nombre de usuario de la cuenta de WebSphere.
* com.ibm.CORBA.loginPassword: se establece con la contraseña de la cuenta de WebSphere.
* com.ibm.CORBA.securityServerPort: establézcalo en el puerto de WebSphere IIOP, si no es el puerto predeterminado 2809. Puede averiguar y modificar este número de puerto mediante la propiedad BOOTSTRAP\_ADDRESS en la consola de WebSphere.

Paso 2: Guarde los cambios en sas.client.props y luego reinicie WebSphere.

Nota: Después de realizar los cambios anteriores, cada vez que se cree un origen de datos, deberá reiniciar WebSphere para que el nuevo origen de datos sea accesible para AEM.

Si el modo de seguridad global está desactivado, deberá eliminar la configuración de com.ibm.CORBA.loginUserid y com.ibm.CORBA.loginPassword del archivo sas.client.props.
