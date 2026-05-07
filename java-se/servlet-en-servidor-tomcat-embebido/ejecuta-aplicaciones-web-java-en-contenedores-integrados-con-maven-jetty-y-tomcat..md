# Ejecuta aplicaciones web Java en contenedores integrados con Maven, Jetty y Tomcat.

***

***

Al desarrollar aplicaciones web Java, resulta muy práctico obtener retroalimentación rápida de un entorno real. En esta publicación, exploraré cómo ejecutar una aplicación web Java con Maven en un contenedor integrado, ya sea Jetty o Tomcat. Mostraré cómo los configuré para el desarrollo del proyecto [Podcastpedia,](https://github.com/CodepediaOrg/podcastpedia) que da soporte al sitio web [Podcastpedia.org](https://github.com/CodepediaOrg/podcastpedia) .

![Octocat](https://www.codepedia.org/wp-content/uploads/2015/06/Octocat-smaller.png)El código fuente de esta publicación está disponible en [Github](https://github.com/CodepediaOrg/podcastpedia) ; podcastpedia.org es un proyecto de código abierto.

### Requisitos previos <a href="#prerequisites" id="prerequisites"></a>

Debes tener [Maven](https://maven.apache.org/download.cgi) y al menos [Java 7](https://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html) instalados. Lo ideal sería que [configuraras](https://github.com/CodepediaOrg/podcastpedia) tú mismo el proyecto Podcastpedia para verlo en funcionamiento.

### Plugin Jetty Maven <a href="#jetty-maven-plugin" id="jetty-maven-plugin"></a>

```
<!-- https://www.eclipse.org/jetty/documentation/current/jetty-maven-plugin.html -->
<plugin>
	<groupId>org.eclipse.jetty</groupId>
	<artifactId>jetty-maven-plugin</artifactId>
	<version>${jetty.version}</version>
	<configuración>
		<jettyConfig>${project.basedir}/src/main/resources/config/jetty9.xml</jettyConfig>
		<stopKey>DETENER</stopKey>
		<stopPort>9999</stopPort>
		<scanIntervalSeconds>5</scanIntervalSeconds>
		<scanTargets>
			<scanTarget>${project.basedir}/src/main</scanTarget>
			<scanTarget>${project.basedir}/src/test</scanTarget>
		</scanTargets>
		<contextXml>${project.basedir}/src/test/resources/jetty-context.xml</contextXml>
		<webAppConfig>
			<contextPath>/</contextPath>
		</webAppConfig>
	</configuración>
	<dependencias>
		<dependencia>
			<groupId>mysql</groupId>
			<artifactId>mysql-connector-java</artifactId>
			<version>${mysql.connector.java.version}</version>
		</dependencia>
		<dependencia>
			<groupId>javax.mail</groupId>
			<artifactId>correo electrónico</artifactId>
			<version>${java.mail.version}</version>
		</dependencia>
		<dependencia>
			<groupId>org.apache.tomcat</groupId>
			<artifactId>tomcat-jdbc</artifactId>
			<version>${tomcat.jdbc.version}</version>
		</dependencia>
	</dependencias>
</plugin>
```

**Notas:**

* **jettyConfig** apunta al archivo de configuración de Jetty; consulte la siguiente sección para obtener más explicaciones.
* carpetas definidas ( **scanTargets** ) donde Jetty busca cambios cada 5 segundos ( **scanInterval** )
* **Se definieron dependencias** externas para conectarse a la base de datos y enviar correos electrónicos.

#### Archivo de configuración Jetty.xml <a href="#jettyxml-configuration-file" id="jettyxml-configuration-file"></a>

```
<?xml version="1.0" encoding="UTF-8"?>
<Configure class="org.eclipse.jetty.webapp.WebAppContext">
	<New id="pcmdbDS" class="org.eclipse.jetty.plus.jndi.Resource">
		<Arg>jdbc/pcmDB</Arg>
		<Arg>
			<New class="com.mysql.jdbc.jdbc2.optional.MysqlConnectionPoolDataSource">
				<Set name="Url">jdbc:mysql://localhost:3307/pcmDB?allowMultiQueries=true
				</Set>
				<Set name="User">pcm</Set>
				<Set name="Password">pcm_pw</Set>
			</Nuevo>
		</Arg>
	</Nuevo>
	<New id="mailSessionId" class="org.eclipse.jetty.plus.jndi.Resource">
		<Arg>correo/sesión</Arg>
		<Arg>
			<New class="org.eclipse.jetty.jndi.factories.MailSessionReference">
				<Set name="user">test-dev@podcastpedia.org</Set>
				<Set name="password">test-dev</Set>
				<Conjunto nombre="propiedades">
					<New class="java.util.Properties">
						<Put name="mail.host">mail.podcastpedia.org</Put>
						<Put name="mail.debug">true</Put>
						<Put name="mail.transport.protocol">smtp</Put>
						<Put name="mail.smtp.port">25</Put>
						<Put name="mail.smtp.auth">true</Put>
					</Nuevo>
				</Set>
			</Nuevo>
		</Arg>
	</Nuevo>
</Configurar>
```

En el [archivo de configuración de Jetty (jetty.xml)](https://www.eclipse.org/jetty/documentation/current/jetty-xml-config.html) tienes configurado lo siguiente:

* La clase Server (o subclase si es extendida) y las opciones globales.
* Un grupo de subprocesos (subproceso mínimo y máximo).
* Conectores (puertos, tiempos de espera, tamaños de búfer, protocolo).
* La estructura del manejador (manejadores predeterminados y/o una colección de manejadores de contexto).
* El gestor de despliegue que busca y despliega aplicaciones web y contextos.
* Servicios de inicio de sesión que proporcionan verificación de autenticación.
* Un registro de solicitudes.

### Plugin Maven para Apache Tomcat <a href="#apache-tomcat-maven-plugin" id="apache-tomcat-maven-plugin"></a>

```
<!-- https://tomcat.apache.org/maven-plugin-trunk/index.html -->
<plugin>
	<groupId>org.apache.tomcat.maven</groupId>
	<artifactId>complemento tomcat7-maven</artifactId>
	<version>2.2</version>
	<configuración>
		<!-- puerto http -->
		<puerto>8080</puerto>
		<!-- La ruta de la aplicación siempre comienza con /-->
		<ruta>/</ruta>
		<!-- ruta opcional a un archivo de contexto -->
		<contextFile>context.xml</contextFile>
		<!-- Propiedades del sistema opcionales que desea agregar -->
		<systemProperties>
			<appserver.base>${project.build.directory}/appserver-base</appserver.base>
			<appserver.home>${project.build.directory}/appserver-home</appserver.home>
			<derby.system.home>${project.build.directory}/appserver-base/logs</derby.system.home>
			<java.io.tmpdir>${project.build.directory}</java.io.tmpdir>
		</systemProperties>
		<!-- si desea utilizar dependencias de prueba en lugar de solo las de tiempo de ejecución -->
		<useTestClasspath>false</useTestClasspath>
		<!-- opcional si desea agregar algunos directorios adicionales al cargador de clases -->
		<directorios de ruta de clases adicionales>
			<additionalClasspathDir></additionalClasspathDir>
		</additionalClasspathDirs>
	</configuración>
	<!-- Para cualquier dependencia adicional necesaria al ejecutar Tomcat integrado (no dependencias WAR), agréguelas a continuación -->
	<dependencias>
		<dependencia>
			<groupId>mysql</groupId>
			<artifactId>mysql-connector-java</artifactId>
			<version>${mysql.connector.java.version}</version>
		</dependencia>
		<dependencia>
			<groupId>javax.mail</groupId>
			<artifactId>correo electrónico</artifactId>
			<version>${java.mail.version}</version>
		</dependencia>
		<dependencia>
			<groupId>org.apache.tomcat</groupId>
			<artifactId>tomcat-jdbc</artifactId>
			<version>${tomcat.jdbc.version}</version>
		</dependencia>
	</dependencias>
</plugin>
```

**Notas**

* Especifica **el puerto** donde se ejecuta Tomcat.
* Especifique **el archivo de contexto** donde Tomcat busca la configuración.
* **Se definieron dependencias** externas para conectarse a la base de datos y enviar correos electrónicos.

#### Contexto.xml <a href="#contextxml" id="contextxml"></a>

```
<Contexto>
  <Recurso
            nombre="jdbc/pcmDB"
            auth="Contenedor"
            tipo="javax.sql.DataSource"
            factory="org.apache.tomcat.jdbc.pool.DataSourceFactory"
            initialSize="5"
            maxActivo="55"
            maxIdle="21"
            minIdle="13"
            timeBetweenEvictionRunsMillis="34000"
            minEvictableIdleTimeMillis="55000"
            validationQuery="SELECT 1"
            intervalo de validación="34"
            testOnBorrow="true"
            removeAbandoned="true"
            removeAbandonedTimeout="233"
            nombredeusuario="pcm"
            contraseña="pcm_pw"
            driverClassName="com.mysql.jdbc.Driver"
            url="jdbc:mysql://localhost:3307/pcmDB?allowMultiQueries=true"
   />

	<Resource name="mail/Session" auth="Container"
	            tipo="javax.mail.Session"
		        nombredeusuario="test-dev@podcastpedia.org"
		        contraseña="test-dev"
	            correo.smtp.host="mail.podcastpedia.org"
	            correo.smtp.port="25"
	            mail.smtp.user="test-dev@podcastpedia.org"
	            correo.transporte.protocolo="smtp"
	            correo.smtp.auth="true"
	/>
</Context>
```

En context.xml se definen los recursos de la base de datos y del correo electrónico.

**Nota:**\
Estas son configuraciones sencillas, pero suficientes para el desarrollo actual. Le recomiendo consultar la documentación correspondiente para obtener opciones y funcionalidades más avanzadas.

***

Ahí lo tienen… Aplicaciones web Java basadas en [Spring Framework](https://projects.spring.io/spring-framework/) que ejecutan contenedores de servlets ligeros, lo que representa una verdadera alternativa a los servidores JAVA EE y todos los costos que conllevan.
