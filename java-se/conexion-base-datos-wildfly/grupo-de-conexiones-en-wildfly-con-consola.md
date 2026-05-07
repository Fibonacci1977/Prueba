# Grupo de conexiones en Wildfly con consola

| <h3>Índice</h3><ul><li><a href="https://wiki.integrator.com.br/index.php?title=Pool_de_Conex%C3%B5es_no_Wildfly_com_Console#Antes_de_come.C3.A7ar_o_tutorial">1 Antes de comenzar el tutorial</a></li><li><a href="https://wiki.integrator.com.br/index.php?title=Pool_de_Conex%C3%B5es_no_Wildfly_com_Console#Sobre_o_material_aqui_informado">2. Respecto al material presentado aquí</a></li><li><a href="https://wiki.integrator.com.br/index.php?title=Pool_de_Conex%C3%B5es_no_Wildfly_com_Console#Upload_da_biblioteca_JDBC_no_Wildfly_Console">3. Cargar la biblioteca JDBC en la consola de Wildfly.</a></li><li><a href="https://wiki.integrator.com.br/index.php?title=Pool_de_Conex%C3%B5es_no_Wildfly_com_Console#Criando_o_Datasource">4. Creación de la fuente de datos</a></li><li><a href="https://wiki.integrator.com.br/index.php?title=Pool_de_Conex%C3%B5es_no_Wildfly_com_Console#Visualizando_a_conex.C3.A3o_criada_e_testando">5. Visualización y prueba de la conexión creada.</a></li></ul> |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

### Antes de comenzar el tutorial

Los siguientes pasos deben realizarse en la consola web de Wildfly. Detalles para seguir este tutorial:\
1\. Para acceder a la consola, consulte el tema [Consola de Wildfly](https://wiki.integrator.com.br/index.php?title=Wildfly_Console) .\
2\. Detalles de acceso a la base de datos:<br>

* Ubicación de la conexión\*: localhost
* La base de datos: MI\_BASE\_DE\_DATOS .
* El usuario\*\*: USUARIO
* La contraseña: CONTRASEÑA .

2.1. Si necesita crear la base de datos, consulte el tema « [Creación de una base de datos PostgreSQL» en el Panel de control](https://wiki.integrator.com.br/index.php?title=Criando_Banco_de_Dados_PostgreSQL_no_Painel) .\
3\. La biblioteca JDBC que utilizamos es [postgresql-9.4.1211.jre6.jar](http://wiki.integrator.com.br/exemplos/postgresql-9.4.1211.jre6.jar) . Sin embargo, puede usar una versión más reciente.\
4\. Los pasos se realizaron en Wildfly 10. Es posible que se produzcan algunas variaciones\*\*\* en versiones anteriores o posteriores.

***

\* Utilice localhost como host de conexión solo si su plan no incluye un servidor de base de datos dedicado.\
\*\* Para bases de datos PostgreSQL, debido a la creación de tablas de Hibernate/JPA, utilice su nombre de usuario y contraseña de cPanel para conectarse a la base de datos. Esta regla no se aplica a clientes con un servidor de base de datos dedicado o MySQL.\
\*\*\* El soporte de alojamiento no se responsabiliza de las interfaces de la consola de administración de Wildfly.

***

### Respecto al material mencionado aquí

Todos los pasos descritos son técnicos y se refieren al funcionamiento de la aplicación Wildfly. Para obtener más información, consulte la documentación de Wildfly. El soporte de alojamiento se limita a nuestros paneles y servicios. Wildfly y sus funciones son responsabilidad de sus desarrolladores.<br>

<br>

### Cargando la biblioteca JDBC en la consola de Wildfly

1\. Vaya a Implementaciones y haga clic en el botón Agregar .<br>

![Texto alternativo](https://wiki.integrator.com.br/images/a/a0/Deployment-1.jpg)![](<../../.gitbook/assets/image (4).png>)

2\. Deje seleccionada la opción "Cargar una nueva implementación" en el asistente de nueva implementación . Continúe haciendo clic en el botón " Siguiente" .<br>

![Texto alternativo](https://wiki.integrator.com.br/images/8/87/Deployment-2.jpg)![](<../../.gitbook/assets/image (5).png>)

3\. En Cargar implementación , seleccione el archivo JAR JDBC que utilizará para conectarse a la base de datos. En este caso, utilizaremos postgresql-9.4.1211.jre6.jar.<br>

![Texto alternativo](https://wiki.integrator.com.br/images/6/66/Deployment-3-postgres.jpg)![](<../../.gitbook/assets/image (6).png>)

4\. Por último, en Verificar carga, asigne un nombre a su archivo JDBC, si lo desea, y confirme haciendo clic en el botón Finalizar .<br>

![Texto alternativo](https://wiki.integrator.com.br/images/e/e6/Deployment-4-postgres.jpg)![](<../../.gitbook/assets/image (7).png>)

### Creación de la fuente de datos

1\. Vaya a Configuración y seleccione Subsistemas » Fuentes de datos » No-XA y haga clic en Agregar .<br>

![Texto alternativo](https://wiki.integrator.com.br/images/e/e9/Datasource-1-nonxa.jpg)![](<../../.gitbook/assets/image (8).png>)

2\. En el cuadro de diálogo, en Elegir origen de datos , seleccione el origen de datos que utilizará. En este caso, utilizaremos el origen de datos PostgreSQL . Confirme con Siguiente .<br>

![Texto alternativo](https://wiki.integrator.com.br/images/2/2a/Datasource-2-nonxa.jpg)![](<../../.gitbook/assets/image (9).png>)

3\. En el primer paso del asistente, puede dejarlo como está o personalizarlo. Continúe con el siguiente paso .<br>

![Texto alternativo](https://wiki.integrator.com.br/images/4/40/Datasource-3-nonxa.jpg)![](<../../.gitbook/assets/image (10).png>)

4\. En el segundo paso del asistente, haga clic en Controlador detectado y luego en el archivo JAR que cargó. En Especificar controlador , puede mantener o modificar lo que necesite. Continúe haciendo clic en Siguiente .<br>

![Texto alternativo](https://wiki.integrator.com.br/images/8/88/Datasource-4-nonxa.jpg)![](<../../.gitbook/assets/image (11).png>)

5\. En el tercer y último paso del asistente, configure el nombre de la base de datos en URL de conexión , el nombre de usuario de la base de datos y su contraseña correspondiente. Continúe con Siguiente .<br>

![Texto alternativo](https://wiki.integrator.com.br/images/1/1b/Datasource-5-nonxa.jpg)![](<../../.gitbook/assets/image (12).png>)

6\. Antes de finalizar, el cuadro de diálogo le proporcionará un resumen para que pueda completar el proceso haciendo clic en el botón Finalizar .

### Visualizar la conexión creada y probarla.

1\. Vaya a Configuración y seleccione Subsistemas » Fuentes de datos » No XA » PostgreDS y haga clic en Ver .<br>

![Texto alternativo](https://wiki.integrator.com.br/images/9/91/Datasource-test.jpg)![](<../../.gitbook/assets/image (13).png>)

2\. En Fuentes de datos , haga clic en Conexión y luego en el botón Probar conexión .<br>

![Texto alternativo](https://wiki.integrator.com.br/images/7/79/Datasource-test-2.jpg)![](<../../.gitbook/assets/image (14).png>)

3\. Debería aparecer el cuadro de diálogo Probar conexión . Si está configurado correctamente, aparecerá el mensaje " Conexión JDBC creada correctamente" .

![Texto alternativo](https://wiki.integrator.com.br/images/7/7f/Datasource-test-3.jpg)![](<../../.gitbook/assets/image (15).png>)
