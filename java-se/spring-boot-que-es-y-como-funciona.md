# Spring Boot ¿Qué es y cómo funciona?

Tabla de Contenidos



* [Primeros pasos sin Spring Boot](https://www.arquitecturajava.com/spring-boot-que-es/#Primeros_pasos_sin_Spring_Boot)
  * [Problemas](https://www.arquitecturajava.com/spring-boot-que-es/#Problemas)
* [Spring Boot](https://www.arquitecturajava.com/spring-boot-que-es/#Spring_Boot)
* [String Boot Starter y simplificaciones](https://www.arquitecturajava.com/spring-boot-que-es/#String_Boot_Starter_y_simplificaciones)
  * [Starters y ventajas](https://www.arquitecturajava.com/spring-boot-que-es/#Starters_y_ventajas)
* [Construyendo la aplicación](https://www.arquitecturajava.com/spring-boot-que-es/#Construyendo_la_aplicacion)
* [Spring Boot Controller](https://www.arquitecturajava.com/spring-boot-que-es/#Spring_Boot_Controller)
  * [Spring Boot Tomcat y Docker](https://www.arquitecturajava.com/spring-boot-que-es/#Spring_Boot_Tomcat_y_Docker)
* [Spring Boot WAR](https://www.arquitecturajava.com/spring-boot-que-es/#Spring_Boot_WAR)
* [Spring Boot vs. Quarkus: ¿Cuál elegir?](https://www.arquitecturajava.com/spring-boot-que-es/#Spring_Boot_vs_Quarkus_%C2%BFCual_elegir)
  * [1. Propósito y enfoque](https://www.arquitecturajava.com/spring-boot-que-es/#1_Proposito_y_enfoque)
  * [2. Rendimiento](https://www.arquitecturajava.com/spring-boot-que-es/#2_Rendimiento)
  * [3. Ecosistema y compatibilidad](https://www.arquitecturajava.com/spring-boot-que-es/#3_Ecosistema_y_compatibilidad)
  * [4. Compatibilidad con GraalVM](https://www.arquitecturajava.com/spring-boot-que-es/#4_Compatibilidad_con_GraalVM)
  * [5. Cuándo usar cada uno](https://www.arquitecturajava.com/spring-boot-que-es/#5_Cuando_usar_cada_uno)
  * [Conclusión](https://www.arquitecturajava.com/spring-boot-que-es/#Conclusion)
    * [Otros artículos relacionados](https://www.arquitecturajava.com/spring-boot-que-es/#Otros_articulos_relacionados)

**Spring Boot** es una de las tecnologías dentro del mundo de Spring de las que más se usa actualmente .**¿Qué es y cómo funciona Spring Boot?** . Para entender el concepto primero debemos reflexionar sobre cómo construiamos aplicaciones con Spring Framework antiguamente.



### Primeros pasos sin Spring Boot <a href="#h-primeros-pasos-sin-spring-boot" id="h-primeros-pasos-sin-spring-boot"></a>

**Fundamentalmente existian tres pasos a realizar** . El primero es crear un proyecto Maven/Gradle y descargar las dependencias necesarias. En segundo lugar esta el proceso de crear la aplicación , pero para ello nos guste o no debemos abordar un proceso amplio de configuración de la aplicación , con ficheros XML o anotaciones y configuraciones muy especificas que muchas veces **solo un experto era capaz de abordar con garantias.** Por último debiamos desplegarla en un servidor.

#### Problemas <a href="#h-problemas" id="h-problemas"></a>

Si nos ponemos a pensar un poco a detalle en el tema , **únicamente el paso dos es una tarea de desarrollo** y dentro de esa tarea 2 incluso la parte de configuración no esta claro que sea desarrollo en sí. Son cosas que están más orientados a infraestructura que al desarrollo en sí mismo.

<figure><img src="https://www.arquitecturajava.com/wp-content/uploads/springbootpartes.png" alt="Spring Depedencias y sus problemas a la hora de configurar una aplicación Java Standard" height="313" width="687"><figcaption></figcaption></figure>

No deberíamos tener que estar eligiendo continuamente las dependencias y el servidor de despliegue así como realizar una configuración inicial .Esto es un tema solo para expertos y que aporta realmente poco debería ser automatico.

### Spring Boot <a href="#h-spring-boot" id="h-spring-boot"></a>

SpringBoot nace con la intención de simplificar **los pasos 1 y 3** . Simplificar la configuración , que nos podamos centrar en el desarrollo de nuestra aplicación. **¿Cómo funciona?.** El enfoque es sencillo y lo entenderemos realizando un ejemplo. Para ello nos vamos a conectarnos al asistente de Boot que se [denomina Spring Initializer.](https://start.spring.io/)

<figure><img src="https://www.arquitecturajava.com/wp-content/uploads/springboot2-1024x522.png" alt="" height="522" width="1024"><figcaption></figcaption></figure>

### String Boot Starter y simplificaciones <a href="#h-string-boot-starter-y-simplificaciones" id="h-string-boot-starter-y-simplificaciones"></a>

El asistente es intuitivo , elegimos el package al que queremos que nuestras clases pertenezcan , elegimos el nombre del proyecto y por último las dependencias. Eso sí ya no se trata de elegir JAR por **JAR** **sino por tipo de aplicación que necesitamos a este concepto** [**se le denomina Spring Starter.**](https://www.arquitecturajava.com/spring-boot-starter-un-concepto-fundamental/) Por lo tanto en vez de tener que elegir 10 o 20 dependencias es mucho más cómodo elegir 2 starters y Spring Boot se encarga del resto.

<figure><img src="https://www.arquitecturajava.com/wp-content/uploads/starterssimplificacion.png" alt="El concepto de Starter dentro de Boot y su importancia a la hora de configurar una aplicación" height="352" width="542"><figcaption></figcaption></figure>

#### Starters y ventajas <a href="#h-starters-y-ventajas" id="h-starters-y-ventajas"></a>

La ventaja es abismal ya que no solo reduzco las dependencias sino también los temas a configurar ya que los starter pueden encargarse de añadir carpetas etc.

### Construyendo la aplicación <a href="#h-construyendo-la-aplicacion" id="h-construyendo-la-aplicacion"></a>

En este caso voy a construir una aplicación **Spring MVC y elijo la dependencia web o Starter Web.** Pulsamos generar proyecto y nos descargará un proyecto Maven en formato zip . Descomprimimos el proyecto y este es su contenido.



Una aplicación de Spring **con estructura Maven totalmente configurada y carpetas adicionales para cubrir nuestras necesidades .** El siguiente paso importar esta aplicación a nuestro Eclipse. Vamos a ver el contenido de la clase **HolaSpringBootApplication**

package com.arquitecturajava;import org.springframework.boot.SpringApplication;import org.springframework.boot.autoconfigure.SpringBootApplication;@SpringBootApplicationpublic class HolaSpringBootApplication {public static void main(String\[] args) {SpringApplication.run(HolaSpringBootApplication.class, args);\}}

Esta clase es la encargada de arrancar nuestra aplicación de Spring a diferencia de un enfoque clásico no hace falta desplegarla en un servidor web **ya que Spring Boot provee de uno (contiene un Tomcat embebido)**

### Spring Boot Controller <a href="#h-spring-boot-controller" id="h-spring-boot-controller"></a>

Vamos a construir un controlador de HolaMundo sencillo:

import org.springframework.stereotype.Controller;import org.springframework.web.bind.annotation.RequestMapping;import org.springframework.web.bind.annotation.ResponseBody;@RestControllerpublic class ControladorHola {@RequestMapping("/")String hola() {return "HolaMundo";\}}

Este controlador registra la url de / para que nos devuelva “HolaMundo” . Es momento de ejecutar nuestra aplicación como una aplicación de consola utilizando botón derecho run as Java Application en el fichero de HolaSpringBootApplication. Esto abrirá un servidor web y accederemos a la url.



SpringBoot nos ha simplificado toda la operativa a la hora de construir la aplicación prácticamente no hemos tenido que seleccionar dependencias de Spring y no ha hecho falta definir ningun servidor Tomcat en nuestro entorno de desarrollo ya que Spring Boot trae uno integrado. Vamos a ver un ejemplo desde cero con un video del curso gratuito de Spring Boot ;).

Rewind 10sPlayForward 10s00:0007:17MuteEnter fullscreenPlay

#### Spring Boot Tomcat y Docker <a href="#h-spring-boot-tomcat-y-docker" id="h-spring-boot-tomcat-y-docker"></a>

¿Porque Spring Boot trae integrado Tomcat? . Muy sencillo porque a partir de ahora los despliegues no se van a realizar en Servidores Web Standard que almacenan decenas de aplicaciones sino que cada una de las aplicaciones se va a desplegar [en un contenedor Docker](https://www.arquitecturajava.com/que-es-docker-y-para-que-sirve/) completamente aislada del resto e independiente . **El contenedor necesita que la aplicación sea completamente operativa por si sola.**

<figure><img src="https://www.arquitecturajava.com/wp-content/uploads/boottomcat.png" alt="Webapps vs Docker y el mundo de los containers a nivel de Spring Boot en donde el aislamiento mejora" height="499" width="700"><figcaption></figcaption></figure>





### Spring Boot WAR <a href="#h-spring-boot-war" id="h-spring-boot-war"></a>

Si tu problema es que hoy por hoy no tienes contenedores Docker ni tienes Kubernetes entre tus herramientas de despliegue , no hay problema . Puedes seguir usando Spring Boot y desplegarlo en un entorno de Tomcat o JBoss directamente simplemente modificando el arranque y haciendo que nuestra aplicación en vez de desplegarse como JAR se despliegue como WAR.

<figure><img src="https://www.arquitecturajava.com/wp-content/uploads/war.png" alt="Inicio de una aplicación de Boot" height="495" width="747"><figcaption></figcaption></figure>

Esto no cambiara en gran manera la clase principal

@SpringBootApplicationpublic class HolaSpringBootApplication {public static void main(String\[] args) {SpringApplication.run(HolaSpringBootApplication.class, args);\}}

Pero añadirá una nueva clase que se encarga de integrarlo con Tomcat de forma transparente:

package com.arquitecturajava.HolaMundo;import org.springframework.boot.builder.SpringApplicationBuilder;import org.springframework.boot.web.servlet.support.SpringBootServletInitializer;public class ServletInitializer extends SpringBootServletInitializer {@Overrideprotected SpringApplicationBuilder configure(SpringApplicationBuilder application) {return application.sources(HolaMundoApplication.class);\}}

### Spring Boot vs. Quarkus: ¿Cuál elegir?

Tanto **Spring Boot** como [**Quarkus**](https://es.quarkus.io/) son frameworks populares para el desarrollo de aplicaciones Java, pero tienen enfoques diferentes. Aquí te presentamos una comparación clave entre ambos.

#### 1. **Propósito y enfoque**

* **Spring Boot**: Facilita la creación de aplicaciones empresariales con mínima configuración. Es ideal para monolitos y microservicios, con un ecosistema robusto.
* **Quarkus**: Optimizado para microservicios y entornos cloud-native, se destaca por su rapidez y bajo consumo de memoria, ideal para contenedores y funciones serverless.

#### 2. **Rendimiento**

* **Spring Boot**: Es flexible, pero su arranque puede ser más lento debido a su sistema de auto-configuración.
* **Quarkus**: Con GraalVM, Quarkus permite compilar imágenes nativas, ofreciendo tiempos de arranque más rápidos y menor consumo de memoria.

#### 3. **Ecosistema y compatibilidad**

* **Spring Boot**: Ofrece un ecosistema muy maduro y amplio, con soporte para muchas bibliotecas.
* **Quarkus**: Aunque es más nuevo, su integración con herramientas como Hibernate es sólida, aunque su ecosistema aún está en crecimiento.

#### 4. **Compatibilidad con GraalVM**

* **Spring Boot**: Tiene soporte en desarrollo para GraalVM, pero requiere ajustes.
* **Quarkus**: Optimizado para GraalVM desde su creación, facilitando la generación de imágenes nativas.

#### 5. **Cuándo usar cada uno**

* **Usa Spring Boot si…**: Necesitas flexibilidad y un ecosistema probado para aplicaciones empresariales.
* **Usa Quarkus si…**: Buscas rapidez en el arranque, menor consumo de recursos y desplegar microservicios en entornos cloud-native.

#### Conclusión

Elige **Spring Boot** para proyectos empresariales robustos y flexibles. Opta por **Quarkus** si tu prioridad es el rendimiento en la nube y los entornos serverless.
