# Aplicación web independiente con Tomcat ejecutable

Cuando se trata de desplegar tu aplicación, la simplicidad es la mayor ventaja. Lo entenderás especialmente cuando el proyecto evolucione y necesite algunos cambios en el entorno. Empaquetar toda tu aplicación en un único JAR independiente y autosuficiente parece una buena idea, especialmente en comparación con instalar y actualizar Tomcat en el entorno de destino. En el pasado, solía incluir los JAR de Tomcat en mi aplicación web y escribir un ejecutor de línea de comandos ligero usando la API de Tomcat. Por suerte, existe un [`tomcat7:exec-war`objetivo de Maven](http://tomcat.apache.org/maven-plugin-2.0/tomcat7-maven-plugin/exec-war-mojo.html) que hace precisamente eso. Toma tu artefacto WAR y lo empaqueta junto con todas las dependencias de Tomcat. Al final, también incluye [`Tomcat7RunnerCli`la clase principal](http://tomcat.apache.org/maven-plugin-2.0/apidocs/org/apache/tomcat/maven/runner/Tomcat7RunnerCli.html) para el manifiesto.\
\
¿Tienes curiosidad por probarlo? Toma tu proyecto WAR existente y agrega lo siguiente a tu `pom.xml`:\
<br>

```
<plugin> 
    <groupId>org.apache.tomcat.maven</groupId> 
    <artifactId>tomcat7-maven-plugin</artifactId> 
    <version>2.0</version> 
    <executions> 
        <execution> 
            <id>tomcat-run</id> 
            <goals> 
                <goal>exec-war-only</goal> 
            </goals> 
            <phase>package</phase> 
            <configuration> 
                <path>/standalone</path> 
                <enableNaming>false</enableNaming> 
                <finalName>standalone.jar</finalName> 
                <charset>utf-8</charset> 
            </configuration> 
        </execution> 
    </executions> 
</plugin>
```

Ejecuta el programa `mvn package`y, unos segundos después, encontrarás shiny `standalone.jar`en tu `target`directorio. Ejecutar tu aplicación web nunca fue tan sencillo:\
\
<br>

```
$ java -jar target/standalone.jar
```

...y puedes navegar `localhost:8080/standalone`. Aunque la [documentación del `path`parámetro](http://tomcat.apache.org/maven-plugin-2.0/tomcat7-maven-plugin/exec-war-mojo.html#path) dice (énfasis mío):\
<br>

> La ruta de contexto de la aplicación web que se utilizará para la aplicación web que se está ejecutando. El nombre para almacenar la aplicación web en el archivo JAR ejecutable. No utilice /

Solo entre nosotros dos, `<path>/</path>`parece que funciona después de todo. Resulta que la `main`clase integrada es en realidad un poco más flexible. Por ejemplo, puedes decir (espero que se explique por sí solo):\
<br>

```
$ java -jar standalone.jar -httpPort=7070
```

Lo que hace este JAR ejecutable es descomprimir primero el archivo WAR que contiene en un directorio ( `.extract`por defecto, <sup>el 1</sup> ) y desplegarlo en Tomcat; también incluye todos los JAR de Tomcat necesarios. El JAR vacío `standalone.jar`(con unos pocos KiB de WAR en su interior) pesa alrededor de 8,5 MiB, lo cual no es mucho si se considera que incluir todo el Tomcat con cada lanzamiento junto con la aplicación es un desperdicio.\
\
Hablando de JAR de Tomcat, cabe preguntarse cómo elegir la versión de Tomcat incluida en este ejecutable. Desafortunadamente, no encontré ninguna opción sencilla, por lo que debemos recurrir a la redefinición explícita de las dependencias del plugin (la versión 2.0 tiene codificada la versión 7.0.30 de Tomcat). Es bastante tedioso, pero no demasiado complicado y podría ser útil para futuras referencias.\
<br>

```
<properties> 
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding> 
    <tomcat7Version>7.0.33</tomcat7Version> 
</properties> 

<build> 
    <plugins> 
        <plugin> 
            <groupId>org.apache.tomcat.maven</groupId> 
            <artifactId>tomcat7-maven-plugin</artifactId> 
            <version>2.0</version> 
            <executions> 
                <execution> 
                    <id>tomcat-run</id> 
                    <goals> 
                        <goal>exec-war-only</goal> 
                    </goals> 
                    <phase>package</phase> 
                    <configuration> 
                        <path>/standalone</path> 
                        <enableNaming>false</enableNaming> 
                        <finalName>standalone.jar</finalName> 
                        <charset>utf-8</charset> 
                    </configuration> 
                </execution> 
            </executions> 
            <dependencies> 
                <dependency> 
                  <groupId>org.apache.tomcat.embed</groupId> 
                  <artifactId>tomcat-embed-core</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependency> 
                <dependency> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-util</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependency> 
                <dependency> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-coyote</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependency> 
                <dependency> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-api</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependency> 
                <dependency> 
                  <groupId>org.apache.<dependency> <groupId> 
                  tomcat-jdbc</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependency> 
                <dependency> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-dbcp</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependency>
                <dependencia> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-servlet-api</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependencia> 
                <dependencia> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-jsp-api</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependencia> 
                <dependencia> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-jasper</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependencia> 
                <dependencia> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-jasper-el</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependencia> 
                <dependencia> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-el-api</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependency> 
                <dependency> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-catalina</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependency> 
                <dependency> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-tribes</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependency> 
                <dependency> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-catalina-ha</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependency> 
                <dependency> 
                  <groupId>org.apache.tomcat</groupId> 
                  <artifactId>tomcat-annotations-api</artifactId> 
                  <version>${tomcat7Version}</version> 
                </dependency> 
            </dependencies> 
        </plugin> 
    </plugins> 
</build>
```

En el próximo artículo aprenderemos cómo controlar estos molestos registros internos de Tomcat que aparecen en la terminal ( `java.util.logging`...) Mientras tanto, descubrí e informé sobre [_MTOMCAT-186: Cerrar el JAR ejecutable no llama a ServletContextListener.contextDestroyed()_](https://issues.apache.org/jira/browse/MTOMCAT-186) . Échale un vistazo si esto es un problema grave para ti.\
\
<sup>1</sup> - Podría ser una buena idea especificar un directorio diferente usando `-extractDirectory`y limpiarlo antes de cada reinicio con `-resetExtract`. Etiquetas: maven, tomcat
