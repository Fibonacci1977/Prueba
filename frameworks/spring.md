# Spring

{% embed url="https://docs.spring.io/spring-framework/docs/current/javadoc-api/" %}

## Frameworks de desarrollo de Aplicaciones - Spring

* [Presentación](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/index.html#Presentaci%C3%B3n)
* [Número de horas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/index.html#N%C3%BAmero+de+horas)
* [Profesores](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/index.html#Profesores)
* [Libro de apuntes](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/index.html#Libro+de+apuntes)
* [Sesiones](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/index.html#Sesiones)

### Presentación

En este módulo veremos _stacks_ de tecnologías alternativas a las estándares en JavaEE, centrándonos en Spring. Este _framework_ de desarrollo de aplicaciones se ha convertido en un completo ecosistema en el que caben tecnologías para todas las capas de nuestro proyecto, desde el acceso a datos hasta la presentación, pasando por supuesto por el negocio e incluyendo aspectos transversales como la seguridad o la integración. Finalizaremos con una introducción al desarrollo rápido de aplicaciones con Spring Roo, que nos permite montar de manera rápida la estructura básica de nuestra aplicación Spring.

### Número de horas

20 horas (8 sesiones)

### Profesores

[Otto Colomina Pardo](mailto:otto.at.dccia.ua.es)

### Libro de apuntes

[Libro de apuntes](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/wholesite.pdf)![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/pdf.gif)

{% file src="../.gitbook/assets/wholesite (2).pdf" %}

## 1. Introducción a Spring

{% file src="../.gitbook/assets/sesion01-traspas (1).pdf" %}



* [¿Qué es Spring?](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#%C2%BFQu%C3%A9+es+Spring%3F)
* [Estereotipos configurables](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#Estereotipos+configurables)
  * [Solicitarle beans al contenedor](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#Solicitarle+beans+al+contenedor)
  * [Ámbito de los beans](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#%C3%81mbito+de+los+beans)
  * [Configurar el estereotipo](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#Configurar+el+estereotipo)
  * [Control del ciclo de vida](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#Control+del+ciclo+de+vida)
* [Inyección de dependencias](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#Inyecci%C3%B3n+de+dependencias)
  * [Uso de anotaciones estándar](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#Uso+de+anotaciones+est%C3%A1ndar)
  * [Uso de anotaciones Spring](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#Uso+de+anotaciones+Spring)
  * [Inyectando expresiones](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#Inyectando+expresiones)
  * [Dependencias de recursos externos](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#Dependencias+de+recursos+externos)
* [Alternativas a las anotaciones para la configuración](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#Alternativas+a+las+anotaciones+para+la+configuraci%C3%B3n)
  * [Configuración en XML](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#Configuraci%C3%B3n+en+XML)
  * [Configuración Java](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html#Configuraci%C3%B3n+Java)

### ¿Qué es Spring?

Spring es un _framework_ alternativo al _stack_ de tecnologías estándar en aplicaciones JavaEE. Nació en una época en la que las tecnologías estándar JavaEE y la visión "oficial" de lo que debía ser una aplicación Java Enterprise tenían todavía muchas aristas por pulir. Los servidores de aplicaciones eran monstruosos devoradores de recursos y los EJB eran pesados, inflexibles y era demasiado complejo trabajar con ellos. En ese contexto, Spring popularizó ideas como la inyección de dependencias o el uso de objetos convencionales (POJOs) como objetos de negocio, que suponían un soplo de aire fresco. Estas ideas permitían un desarrollo más sencillo y rápido y unas aplicaciones más ligeras. Eso posibilitó que de ser un _framework_ inicialmente diseñado para la capa de negocio pasara a ser un completo _stack_ de tecnologías para todas las capas de la aplicación.

Las ideas "innovadoras" que en su día popularizó Spring se han incorporado en la actualidad a las tecnologías y herramientas estándar. Así, ahora mismo no hay una gran diferencia entre el desarrollo con Spring y el desarrollo JavaEE "estándar", o al menos no tanta como hubo en su día. No obstante, Spring ha logrado aglutinar una importante comunidad de desarrolladores en torno a sus tecnologías y hoy por hoy sigue constituyendo una importante alternativa al estándar que merece la pena conocer. En la actualidad, las aportaciones más novedosas de Spring se centran en los campos de Big Data/NoSQL, HTML5/móviles y aplicaciones sociales.

Básicamente, la mayor diferencia práctica que podemos encontrar hoy en día entre desarrollar con Spring y con JavaEE estándar es la posibilidad de usar un servidor web convencional al estilo Tomcat para desplegar la aplicación. Las tecnologías JavaEE más sofisticadas requieren del uso de un servidor de aplicaciones, ya que los APIs los implementa el propio servidor, mientras que Spring no es más que un conjunto de librerías portables entre servidores. En otras palabras, usando JavaEE estándar, nos atamos al servidor de aplicaciones y usando Spring nos atamos a sus APIs. Eso sí, los desarrolladores de Spring se han preocupado bastante de armonizar con el estándar en la medida de lo posible, por ejemplo dando la posibilidad de usar anotaciones estándar aun con implementaciones propias por debajo. La idea es obstaculizar lo menos posible una posible portabilidad a JavaEE, idea que es de agradecer en un mundo en que todos los fabricantes intentan de una forma u otra mantener un público cautivo.

Hay una abundante bibliografía sobre Spring, aunque la [documentación del propio proyecto](http://static.springsource.org/spring-framework/docs/) es excelente y bastante exhaustiva, pudiéndose utilizar perfectamente no solo como manual de referencia sino como tutorial detallado. La hemos tomado como referencia básica para la elaboración de estos apuntes.

Desde un punto de vista genérico, Spring se puede ver como un soporte que nos proporciona tres elementos básicos:

* **Servicios&#x20;**_**enterprise**_**:** podemos hacer de manera sencilla que un objeto sea transaccional, o que su acceso esté restringido a ciertos roles, o que sea accesible de manera remota y transparente para el desarrollador, o acceder a otros muchos servicios más, sin tener que escribir el código de manera manual. En la mayoría de los casos solo es necesario anotar el objeto.
* **Estereotipos configurables** para los objetos de nuestra aplicación: podemos anotar nuestras clases indicando por ejemplo que pertenecen a la capa de negocio o de acceso a datos. Se dice que son configurables porque podemos definir nuestros propios estereotipos "a medida": por ejemplo podríamos definir un nuevo estereotipo que indicara un objeto de negocio que además sería cacheable automáticamente y con acceso restringido a usuarios con determinado rol.
* **Inyeccion de dependencias:**: ya hemos visto este concepto cuando se hablaba de CDI de JavaEE. La inyección de dependencias nos permite solucionar de forma sencilla y elegante cómo proporcionar a un objeto cliente acceso a un objeto que da un servicio que este necesita. Por ejemplo, que un objeto de la capa de presentación se pueda comunicar con uno de negocio. En Spring las dependencias se pueden definir con anotaciones o con XML.

### Estereotipos configurables

Spring puede gestionar el ciclo de vida de los objetos que queramos. Los objetos gestionados por el framework se denominan genéricamente _beans_ de Spring (no confundir con el concepto estándar de bean en Java). Esto no es nada extraño, es lo que sucede por ejemplo con los servlets, normalmente no los instancia el desarrollador sino que lo hace el contenedor web cuando es necesario. Spring extiende esta idea permitiéndonos gestionar el ciclo de vida de cualquier objeto. Para ello tendremos que anotarlo (o crear un fichero de configuración XML, aunque esta opción tiende a estar en desuso).

Spring ofrece una serie de anotaciones estándar para los objetos de nuestra aplicación: por ejemplo, **@Service** indica que la clase es un bean de la capa de negocio, mientras que **@Repository** indica que es un DAO. Si simplemente queremos especificar que algo es un bean sin decir de qué tipo es podemos usar la anotación **@Component**. Por ejemplo:

```java
package es.ua.jtech.spring.negocio;
 
import org.springframework.stereotype.Service;
 
@Service("usuariosBO")
public class UsuariosBOSimple implements IUsuariosBO {
   public UsuarioTO login(String login, String password) {
     ...
   }
   public bool logout() {
     ...
   }
   ...
}
```

El parámetro "usuariosBO" de la anotación sirve para darle un nombre o identificador al bean, que deberá ser único. Veremos ejemplos de su uso en el apartado siguiente. Si no le diéramos uno, el identificador por defecto sería el nombre de la clase pero con la inicial en minúscula.

@Service vs. @Repository vs. @Component

***

Nótese que en la versión actual de Spring la anotación @Service no tiene una semántica definida distinta a la de @Component. Es decir, simplemente le ayuda al que lee el código a saber que el bean pertenece a la capa de negocio y por lo demás es indiferente usar una u otra. La anotación @Repository sí tiene efecto sobre la transaccionalidad automática, como veremos en la siguiente sesión. No obstante, el equipo de desarrollo de Spring se reserva la posibilidad de añadir semántica a estas anotaciones en futuras versiones del _framework_.

Para que nuestro bean funcione, falta un pequeño detalle. Spring necesita de un fichero XML de configuración mínimo. Cuando los beans no se definen con anotaciones sino con XML, aquí es donde se configuran, en lugar de en el fuente Java. Pero aunque usemos anotaciones en el fuente, como en nuestro caso, el XML de configuración mínimo sigue siendo necesario. En él debemos decirle a Spring que vamos a usar anotaciones para definir los beans.

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans 
         http://www.springframework.org/schema/beans/spring-beans.xsd
         http://www.springframework.org/schema/context
         http://www.springframework.org/schema/context/spring-context.xsd">
                
     <context:component-scan base-package="es.ua.jtech.spring"/>
</beans>
```

La etiqueta **\<context:component-scan>** es la que especifica que usaremos anotaciones para la definición de los beans, y que las clases que los definen van a estar en una serie de paquetes (todos van a ser subpaquetes de **base-package**). Por ejemplo, el propio es.ua.jtech.spring o paquetes como es.ua.jtech.spring.negocio o es.ua.jtech.spring.base.to

¡Cuidado!

***

Las anotaciones puestas en clases que no estén definidas en el paquete "base-package" o en alguno de sus subpaquetes no tendrán ningún efecto. Es un error muy típico olvidarse de esto y desesperarse ante el hecho de que Spring "ignora" las anotaciones.

#### Solicitarle beans al contenedor

Evidentemente, para que la gestión del ciclo de vida funcione, tiene que haber "alguien" que se encargue de realizarla. En el caso de los servlets el encargado es el contenedor web (por ejemplo Tomcat). En Spring existe un concepto equivalente: el contenedor de beans, que hay que configurar e instanciar en nuestra aplicación (el contenedor web es algo estándar de JavaEE y por tanto su arranque es "automático", pero Spring no es más que una librería Java y por tanto no goza de ese privilegio). El contenedor implementa la interfaz ApplicationContext. Spring ofrece diferentes implementaciones de este interfaz, algunas apropiadas para aplicaciones de escritorio y otras para aplicaciones web.

En **aplicaciones de escritorio** es común usar la clase ClassPathXmlApplicationContext, a la que hay que pasarle el nombre del fichero de configuración que vimos en el apartado anterior. Como su propio nombre indica, esta clase buscará el archivo en cualquier directorio del _classpath_.

```java
ApplicationContext contenedor =
    new ClassPathXmlApplicationContext("configuracion.xml");
```

El application context actúa como si fuera una factoría de beans, de modo que podemos obtener de él el objeto deseado:

```java
ApplicationContext contenedor =
    new ClassPathXmlApplicationContext("configuracion.xml");
IUsuariosBO iub = contenedor.getBean(IUsuariosBO.class); 
UsuarioTO uto = igu.login("javaee", "javaee");   
```

El context nos permite recuperar los beans por clase (o interfaz, como en el ejemplo), pero también podríamos recuperarlos por su identificador (recordar que habíamos asignado un identificador en la anotación @Service).

```java
...
IUsuariosBO iub = contenedor.getBean("usuariosBO", IUsuariosBO.class);
...
```

El acceso por identificador nos será útil si hemos definido distintos beans de la misma clase, con distintas propiedades cada uno (aunque esto no se puede hacer únicamente con anotaciones, necesitaríamos usar la configuración XML o Java).

A primera vista parece que no hemos obtenido nada con Spring que no hubiéramos podido conseguir de manera mucho más sencilla con un modesto new UsuariosBOSimple(), pero esta forma de hacer las cosas presenta ciertas ventajas:

* El _application context_ se puede ver como una implementación del patrón _factory_. Este patrón nos independiza de la clase concreta que use nuestra implementación. El código que hace uso del application context para obtener el gestor de usuarios no necesita saber qué clase concreta se está usando ni debe cambiar si cambia ésta. Todo esto, como ya se ha visto, a costa de introducir complejidad adicional en el proyecto (¡nada es gratis!).
* Podemos cambiar ciertos aspectos del ciclo de vida del bean de manera declarativa. Por ejemplo, el ámbito: es muy posible que un solo objeto pueda hacer el trabajo de todos los clientes que necesiten un IGestorUSuarios (un _singleton_, en argot de patrones). O al contrario, podría ser que cada vez hiciera falta un objeto nuevo. O también podría ser que si estuviéramos en una aplicación web, cada usuario que va a hacer login necesitara su propia instancia de IGestorUSuarios. Todo esto lo podemos configurar en Spring de manera declarativa, sin necesidad de programarlo, y que sea el contenedor el que se ocupe de estas cuestiones del ciclo de vida.

En **aplicaciones web** la configuración del contenedor se hace con la clase WebApplicationContext, definiéndola como un _listener_ en el fichero descriptor de despliegue, web.xml.

```java
<?xml version="1.0" encoding="ISO-8859-1"?>
<web-app ...>
  <context-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>/WEB-INF/misBeans.xml</param-value>
  </context-param>
   
  <listener>
     <listener-class>
        org.springframework.web.context.ContextLoaderListener
     </listener-class>
  </listener>
   
  <!--  resto de etiquetas del web.xml -->
  ...
</web-app>
```

La clase ContextLoaderListener carga el fichero o ficheros XML especificados en el \<context-param> llamado contextConfigLocation (suponemos que el fichero misBeans.xml está en el directorio WEB-INF). Como \<param-value> se puede poner el nombre de varios ficheros XML, separados por espacios o comas.

Una vez arrancado el contenedor, podemos acceder a un bean a través de la clase WebApplicationContext, que funciona de manera prácticamente igual que la ya vista ClassPathXmlApplicationContext. El WebApplicationContext es accesible a su vez a través del contexto del servlet, por lo que en un JSP podríamos hacer algo como:

```java
<%@ page import ="org.springframework.web.context.*" %> 
<%@ page import ="org.springframework.web.context.support.*" %>
<%@ page import ="es.ua.jtech.spring.negocio.*" %>    
<html>
<head>
   <title>Acceso a beans de spring desde un JSP</title>
</head>
<body>
<%
  ServletContext sc = getServletContext();
  WebApplicationContext wac = 
          WebApplicationContextUtils.getWebApplicationContext(sc);
  IUsuariosBO iub = wac.getBean(IUsuariosBO.class);
  UsuarioTO uto = iub.login("javaee", "javaee");
%>
</body>
</html>
```

Pero esto es demasiado complicado, ¿no?...

***

Toda esta parafernalia para obtener objetos parece excesiva. ¿No sería mejor que los objetos se obtuvieran automáticamente cuando los necesitáramos?. De ese modo, en una aplicación web, cuando se recibiera una determinada petición HTTP se obtendría automáticamente un bean de la capa de presentación, que a su vez podría acceder automáticamente al/los que necesitara de negocio, y éstos a su vez a otros de acceso a datos, y... Efectivamente, esa es la forma habitual de trabajar en aplicaciones web con Spring: el web application context está presente pero no es necesario acudir a él de manera explícita. Lo que ocurre es que para poder hacer esto necesitamos dos elementos que todavía no hemos visto: la inyección de dependencias y el framework para la capa web, Spring MVC. El primero de ellos lo abordaremos en breve, y el segundo en la sesión 3.

#### Ámbito de los beans

Por defecto, los beans en Spring son _singletons_. Esto significa que el contenedor solo instancia un objeto de la clase, y cada vez que se pide una instancia del bean en realidad se obtiene una referencia al mismo objeto. Recordemos que se solicita una instancia de un bean cuando se llama a getBean() o bien cuando se "inyecta" una dependencia del bean en otro.

El ámbito _singleton_ es el indicado en muchos casos. Probablemente una única instancia de la clase GestorPedidos pueda encargarse de todas las tareas de negocio relacionadas con pedidos, si la clase no tiene "estado" (entendiendo por esto que no tiene variables miembro y que por tanto varios hilos independientes que accedan concurrentemente al mismo objeto no van a causar problemas). Los DAO son otro ejemplo típico de objetos apropiados que se suelen definir en Spring como singletons, ya que no suelen guardar estado.

Podemos asignar otros ámbitos para el bean usando la anotación @Scope. Por ejemplo, para especificar que queremos una nueva instancia cada vez que se solicite el bean, se usa el valor prototype

```java
package es.ua.jtech.spring.negocio;
 
import org.springframework.context.annotation.Scope;
import org.springframework.stereotype.Service;
...
 
@Scope("prototype")
@Service
public class UsuariosBOSimple implements IUsuariosBO {
   ...
}   
```

En **aplicaciones web**, se pueden usar además los ámbitos de request y session (hay un tercer ámbito llamado globalSession para uso exclusivo en portlets). Para que el contenedor pueda gestionar estos ámbitos, es necesario usar un listener especial cuya implementación proporciona Spring. Habrá que definirlo por tanto en el web.xml

```java
...
<web-app>
  ...
  <listener>
    <listener-class>
       org.springframework.web.context.request.RequestContextListener
     </listener-class>
  </listener>
  ...
</web-app>
```

Ahora ya podemos usar los ámbitos especiales para aplicaciones web. Por ejemplo para definir un bean que tenga como ámbito la sesión HTTP simplemente usaremos "session" como valor de la anotación @Scope.

#### Configurar el estereotipo

Podemos aprovechar la posibilidad de definir anotaciones Java a medida para definir nuestros propios estereotipos, combinando anotaciones de Spring. Por ejemplo para un objeto de negocio con ámbito de sesión y con transaccionalidad automática podríamos definir la siguiente anotación:

```java
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
 
import org.springframework.context.annotation.Scope;
import org.springframework.stereotype.Service;
 
@Service
@Scope("session")
@Transactional
@Retention(RetentionPolicy.RUNTIME)
public @interface ServicioTransaccional {
}
```

Una vez hecho esto, el compilador reconocerá la anotación @ServicioTransaccional como propia, por ejemplo:

```java
@ServicioTransaccional
public class UsuariosDAO implements IUsuariosDAO {
   public void UsuarioTO leer(String login) {
      ...
   }
   ...
}
```

#### Control del ciclo de vida

En algunos casos puede ser interesante llamar a un método del bean cuando éste se inicializa o destruye. Para ello se usan respectivamente las anotaciones @PostConstruct y @PreDestroy. Por ejemplo:

```java
@Component 
public class MiBean {
   @PostConstruct
   public void inicializa() {
    
   }
 
   @PreDestroy
   public void libera() {
   }
 
}
```

Ambos deben ser métodos sin parámetros. El método de inicialización se llama justo después de que Spring resuelva las dependencias e inicialice las propiedades del bean.

### Inyección de dependencias

La inyección de dependencias es uno de los pilares fundamentales en que se basa Spring. Aunque no fue el primer _framework_ que usaba este concepto, sí fue el que lo popularizó en el mundo Java enterprise. Durante mucho tiempo era una de las diferencias más destacadas entre el "enfoque Spring" y el JavaEE estándar. En este último, cuando un objeto necesitaba de otro o de un recurso debía localizarlo él mismo mediante el API JNDI. No obstante, en la actualidad, como ya se ha visto en otros módulos, el estándar ha ido incorporando la inyección de dependencias en múltiples tecnologías (JPA, JSF, web,...).

#### Uso de anotaciones estándar

Spring permite el uso de anotaciones de JSR330, para reducir el acoplamiento con los APIs de Spring y mejorar la portabilidad. Veremos en primer lugar el uso de estas anotaciones con Spring y luego las propias del _framework_.

Para anotar componentes, en el estándar se usa @Named, que sería la equivalente a la @Component de Spring (un bean, sin especificar si es de presentación, negocio o acceso a datos).

Para las dependencias ya se vio en otros módulos, por ejemplo en el de componentes web, el uso de @Inject. En Spring es idéntico. Continuando con los ejemplos ya vistos, supongamos que nuestro IUsuariosBO necesita de la colaboración de un bean auxiliar IUsuariosDAO para hacer su trabajo:

```java
@Named("usuariosBO")
public class UsuariosBOSimple implements IUsuariosBO {
  @Inject
  IUsuariosDAO udao;
 
  public UsuarioTO login(String login, String password) {
    UsuarioTO uto = udao.recuperar(login);
    if (uto.getPassword().equals(password)) {
       ...
    }
  }
   
  ...
}
```

Evidentemente, para que esto funcione tiene que existir alguna clase que implemente el interfaz IUsuariosDAO y que esté anotada como un bean de Spring

Hay que destacar que la inyección se puede hacer en las variables miembro pero también en métodos o constructores. Esto posibilita resolver las dependencias "manualmente" sin el concurso de Spring. Por ejemplo:

```java
@Named("usuariosBO")
public class UsuariosBOSimple implements IUsuariosBO {
  IUsuariosDAO udao;
 
  @Inject
  public setUsuariosDAO(UsuariosDAO udao) {
    this.udao = udao;
  }
 
  public UsuarioTO login(String login, String password) {
    UsuarioTO uto = udao.recuperar(login);
    if (uto.getPassword().equals(password)) {
       ...
    }
  }
   
  ...
}
```

Así, si no pudiéramos o quisiéramos usar Spring (por ejemplo, para pruebas), podríamos hacer:

```java
IUsuariosBO ubo = new UsuariosBOSimple();
ubo.setUsuariosDAO(new UsuariosDAOJPA());
```

Mientras que "dentro" de Spring la dependencia se seguiría resolviendo e instanciando automáticamente.

Por defecto, la creación de todos los beans y la inyección de dependencias se efectúa cuando se arranca el contenedor (el Application Context). Se crea un bean de cada clase (ya que el ámbito por defecto es singleton) y se "enlazan" de modo apropiado. Si no fuera posible resolver alguna dependencia el arranque de la aplicación fallaría. Si queremos que algún bean no se inicialice cuando arranca el contenedor, sino en el momento que se solicite con getBean, podemos anotarlo con @Lazy.

No es necesario añadir Weld al proyecto ni ninguna otra implementación externa de JSR330 porque en realidad se está usando la implementación propia de Spring, por lo que basta con añadir la dependencia del artefacto que define las anotaciones en sí:

```java
<dependency>
    <groupId>javax.inject</groupId>
    <artifactId>javax.inject</artifactId>
    <version>1</version>
</dependency>
```

JSR330 vs. JSR299

***

Spring no permite el uso de anotaciones JSR299, _Contexts and Dependency Injection_. Estas últimas son, de hecho, más sofisticadas en ciertos aspectos que las que ofrece actualmente Spring de manera nativa.

#### Uso de anotaciones Spring

Usando las anotaciones propias de Spring para la inyección de dependencias perdemos portabilidad pero podemos aprovechar todas las posibilidades del framework.

El equivalente Spring a @Inject sería @Autowired. La anotación de Spring es algo más flexible, ya que nos permite especificar dependencias opcionales. En ese caso la aplicación no fallará si no es posible resolver la dependencia.

```java
@Service("usuariosBO")
public class UsuariosBOSimple implements IUsuariosBO {
  @Autowired(required=false)
  IUsuariosDAO udao;
 
  public UsuarioTO login(String login, String password) {
    if (udao==null) {
      throw new Exception("No es posible realizar la operación");
    }
    else {
      ...
    }
  }
  ...
}
```

En el ejemplo anterior la aplicación arrancaría correctamente, aunque no fuera posible resolver la dependencia. Lo que ocurriría es que el valor miembro udao quedaría a null.

El problema contrario a no ser capaz de resolver una dependencia es **encontrar varios beans candidatos a resolverla**, ya que hay que elegir uno de ellos. Por ejemplo, supongamos que tuviéramos dos implementaciones distintas de IUsuariosDAO: UsuariosDAOJPA y UsuariosDAOJDBC. ¿Cuál deberíamos seleccionar para inyectarle al UsuariosBOSimple?. La opción es la misma que se usa en el estándar: la anotación @Qualifier. Con ella marcaremos el bean al definirlo y al inyectarlo, por ejemplo:

```java
@Repository
@Qualifier("JDBC")
public class UsuariosDAOJDBC implements IUsuariosDAO {
    ...
}

```

```java
@Service
public class UsuariosBOSimple implements IUsuariosBO {
  @Autowired
  @Qualifier("JDBC")
  IUsuariosDAO udao;
  ...
}
```

Al igual que vimos en el módulo de componentes web, podríamos crearnos nuestras propias anotaciones @Qualifier personalizadas, por ejemplo una @JDBCDAO.

#### Inyectando expresiones

Con la anotación @Value, podemos inyectar valores en variables miembro o parámetros de métodos. En su variante más simple este sería un valor constante, por ejemplo:

```java
@Component MiBean {
  @Value(100)
  private creditoInicial;
 
}  
```

Evidentemente inyectar un valor constante no es muy útil, es más sencillo hacer la inicialización directamente con código Java. Lo interesante de @Value es que podemos usar expresiones en **SpEL** (_Spring Expression Language_), un lenguaje de expresiones similar en concepto al JSP o JSF EL pero propio de Spring, y que nos permite, entre otras cosas:

* Realizar operaciones aritméticas y lógicas
* Llamar a métodos y acceder a propiedades de objetos. Podemos acceder a beans referenciándolos por su id.
* Hacer _matching_ con expresiones regulares
* Acceso a las propiedades del sistema y a variables de entorno

A continuación se muestran algunos ejemplos de uso.

```java
//acceso al bean con id "miConfig" y llamada al método "getLocale" 
//(supuestamente este método devuelve el objeto Locale que aquí inyectamos)
@Value("#{miConfig.defaultLocale}")
private Locale locale;
 
//otro acceso a un getter de un bean, ahora usando también operadores lógicos
@Value("#{almacen.stock>0")
private boolean hayStock
 
//acceso a las propiedades del sistema. 
//Las variables de entorno son accesibles con "systemEnvironment"
@Value("#{systemProperties['user.name']}")
private String userName;
```

El uso detallado de SpEL queda fuera del ámbito de estos apuntes introductorios. Se recomienda consultar la documentación de Spring para obtener más información sobre el lenguaje.

#### Dependencias de recursos externos

El API estándar de JavaEE para el acceso a recursos externos (conexiones con bases de datos, colas de mensajes, etc) es JNDI. Este API no se basa en inyección de dependencias, todo lo contrario: el objeto cliente del servicio es el que debe "hacer el esfuerzo" para localizar por él mismo los objetos de los que depende. La "solicitud" o búsqueda de dichos objetos se le pide a un servicio de directorio que tiene un registro de servicios por nombre. Spring hace lo posible por integrar su mecanismo estándar de dependencias con este modo de funcionamiento y nos permite un acceso relativamente sencillo a recursos JNDI

Primero hay que asociar el recurso con su nombre JNDI en el .xml de configuración. Lo más sencillo es usar el espacio de nombres jee. Para usar este espacio de nombres hay que definir el siguiente preámbulo en el XML de configuración (en negrita aparece la definición del espacio de nombres propiamente dicho)

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xmlns:jee="http://www.springframework.org/schema/jee"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
            http://www.springframework.org/schema/beans/spring-beans.xsd
            http://www.springframework.org/schema/jee
      http://www.springframework.org/schema/jee/spring-jee.xsd">
   ...
</beans>
```

Hacer que un DataSource cuyo nombre JNDI es jdbc/MiDataSource se "convierta" en un bean de Spring (y por tanto sea inyectable en otros) es muy sencillo con la etiqueta jee:jndi-lookup

```java
<jee:jndi-lookup id="miBean" jndi-name="jdbc/MiDataSource"
       resource-ref="true"/>
```

Nótese que el atributo identificador (id) del nuevo bean es un valor requerido en la etiqueta XML, aunque es arbitrario. Simplemente debemos asegurarnos de que sea único.

Donde el atributo resource-ref="true" indica que el DataSource lo gestiona un servidor de aplicaciones y que por tanto al nombre JNDI del objeto hace falta precederlo de java:comp/env/

Podemos mejorar un poco el ejemplo: cuando se introducen valores en el XML de configuración susceptibles de cambios, como los nombres JNDI, es mejor externalizarlos, ya que el XML es bastante crítico y no conviene andar editándolo sin necesidad. Por ello, Spring prevé la posibilidad de usar constantes, con la sintaxis ${nombre.constante}, y tomar sus valores de ficheros .properties estándar. Por ejemplo:

```java
<jee:jndi-lookup id="miBean" jndi-name="${datasource}"
        resource-ref="true"/>
<context:property-placeholder
        location="classpath:es/ua/jtech/ds.properties"/>
```

donde la etiqueta property-placeholder especifica la localización física del fichero.properties, en este caso, en el classpath en un fichero llamado ds.properties dentro de las carpetas es/ua/jtech.

Finalmente, podemos inyectar nuestro DataSource, ahora convertido en un bean de Spring y por tanto inyectable, usando @Autowired como de costumbre:

```java
@Repository
public class UsuariosDAOJDBC implements IUsuariosDAO {
  @Autowired
  DataSource ds;
  ...
}  
```

Spring es lo suficientemente "hábil" para deducir el tipo de un objeto a partir de su nombre JNDI, y por tanto sabrá que el recurso JNDI llamado jdbc/MiDataSource es un candidato válido para ser inyectado en esta variable.

### Alternativas a las anotaciones para la configuración

Aunque es el tipo de configuración más usado actualmente, las anotaciones no son el único método de configuración en Spring. Se pueden definir beans con XML y también con código Java. Vamos a ver muy brevemente las ventajas de estas alternativas y su forma de uso.

#### Configuración en XML

En lugar de anotaciones, se puede hacer uso del XML de configuración para definir los beans. Esto tiene dos ventajas básicas: eliminar toda referencia a Spring de nuestro código, lo que mejora la portabilidad, y permitir la definición de más de un bean de la misma clase con distintas propiedades. No obstante, el XML resultante es bastante farragoso, por ejemplo, el caso del GestorUsuarios, un BO que depende del DAO UsuariosDAO se haría en notación XML:

```java
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans.xsd">
     
    <!-- definimos un bean de la clase UsuariosDAO 
         y le damos nombre -->
    <bean id="miUsuariosDAO"
        class="es.ua.jtech.spring.datos.UsuariosDAO">        
    </bean>
     
    <!-- definimos otro bean de la clase UsuariosDAO 
         pero con ámbito "prototype", 
         solo para que veas que se pueden definir varios beans
         de la misma clase con propiedades distintas -->
    <bean id="otroUsuariosDAO"
          class="es.ua.jtech.spring.datos.UsuariosDAO"
                scope="prototype">        
    </bean>
     
    <bean id ="miGestorUsuarios"
      class="es.ua.jtech.spring.negocio.GestorUsuarios">
        <!-- la propiedad "udao" referencia al bean antes definido -->
        <!-- Cuidado, la propiedad debe llamarse igual que en el fuente Java -->
        <property name="udao" ref="miUsuariosDAO"/>
    </bean>        
```

Hay varias cosas a notar de este código: la más evidente es que la etiqueta bean es la que se usa para definir cada uno de los beans gestionados por el contenedor. Además, para especificar que una variable de un bean es otro bean que Spring debe instanciar se usa la etiqueta property con el atributo ref referenciando al bean.

Aunque por supuesto todo lo que hemos hecho con anotaciones se puede hacer con XML (y más cosas, además) no vamos a ver la sintaxis, salvo para ver cómo definir propiedades de los beans. Se recomienda consultar la documentación de Spring, en concreto el capítulo 3, _The IoC Container_.

**Podemos especificar valores iniciales para las propiedades de un bean**. Así podremos cambiarlos sin necesidad de recompilar el código. Lógicamente esto no se puede hacer con anotaciones sino que se hace en el XML. Las propiedades del bean se definen con la etiqueta \<property>. Pueden ser Strings, valores booleanos o numéricos y Spring los convertirá al tipo adecuado, siempre que la clase tenga un método setXXX para la propiedad. Podemos convertir otros tipos de datos (fechas, expresiones regulares, URLs, ...) usando lo que en Spring se denomina un PropertyEditor. Spring incorpora varios predefinidos y también podemos definir los nuestros.

Por ejemplo, supongamos que tenemos un buscador de documentos DocsDAO y queremos almacenar en algún sitio las preferencias para mostrar los resultados. La clase Java para almacenar las preferencias sería un _JavaBean_ común:

```java
package es.ua.jtech.spring.datos;
 
 
public class PrefsBusqueda {
    private int maxResults;
    private boolean ascendente;
    private String idioma;
     
    //Aquí faltarían los getters y setters
    ...
}
```

No se muestra cómo se define la relación entre DocsDAO y PrefsBusqueda. Ya conocemos cómo hacerlo a partir de los apartados anteriores.

Los valores iniciales para las propiedades pueden configurarse en el XML dentro de la etiqueta bean

```java
...
   <bean id="prefsBusqueda" class="es.ua.jtech.spring.datos.PrefsBusqueda">
      <property name="maxResults" value="100"/>
      <property name="ascendente" value="true"/>
      <property name="idioma" value="es"/>      
   </bean>
...  
```

A partir de la versión 2 de Spring se añadió una forma alternativa de especificar propiedades que usa una sintaxis mucho más corta. Se emplea el espacio de nombres http://www.springframework.org/schema/p, que permite especificar las propiedades del bean como atributos de la etiqueta bean

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:p="http://www.springframework.org/schema/p"
       xsi:schemaLocation="http://www.springframework.org/schema/beans 
                http://www.springframework.org/schema/beans/spring-beans.xsd">
   <bean id="misPrefs" class="es.ua.jtech.spring.datos.PrefsBusqueda"
       p:maxResults="100" p:ascendente="true">
   </bean>
</beans>
```

Las propiedades también pueden ser colecciones: Lists, Maps, Sets o Properties. Supongamos que en el ejemplo anterior queremos una lista de idiomas preferidos:

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans 
                http://www.springframework.org/schema/beans/spring-beans.xsd">
   <bean id="prefsBusqueda" class="es.ua.jtech.spring.datos.PrefsBusqueda">
    <property name="listaIdiomas">
      <list>
       <value>es</value>
       <value>en</value>
      </list>
    </property>
    <!-- resto de propiedades -->
    ...  
   </bean>
```

Para ver cómo se especifican los otros tipos de colecciones, acudir a la documentación de referencia de Spring.

#### Configuración Java

El último "formato" que podemos usar para configurar los beans es el propio lenguaje Java. La idea básica es definir un método por cada bean y que éste devuelva el objeto instanciado con las propiedades y dependencias que deseemos. Aquí tenemos el ejemplo del IUsuariosBO y el IUsuariosDAO con configuración Java:

```java
@Configuration
public class SampleConfig {
  @Bean
  public IUsuariosDAO udao() {
    return new UsuariosDAOJPA();
  }
   
  @Bean
  public IUsuariosBO ubo() {
    IUsuariosBO ubo = new UsuariosBOSimple();
    ubo.setCredito(100);
    ubo.setIUsuariosDAO(udao());
    return ubo;
  }
}
```

Como se ve, cada bean se define mediante un método anotado con @Bean y que devuelve una instancia del objeto deseado (simplemente usando new()). La clase que agrupa estos métodos se anota con @Configuration. Nótese además que:

* Spring toma como identificador del bean el nombre del método que lo genera. Por ejemplo, el identificador del bean de tipo IUsuariosDAO será "udao".
* Si queremos asignarle una propiedad al bean simplemente lo hacemos con código Java. En el ejemplo anterior, hemos supuesto que el IUsuariosBO tiene un _setter_ para una propiedad llamada "credito".
* Igualmente, para establecer una dependencia entre beans lo hacemos con código Java convencional. Esto nos obliga a pasar el bean "colaborador" como un parámetro en el constructor o en un setter del bean "dependiente". Esto es lo que hemos hecho al construir el IUsuariosBO.

En el código de la configuración Java hay más cosas de las que se aprecian a simple vista. La más destacable es que Spring no ejecuta "textualmente" el código cada vez que se solicita un bean. Si lo hiciera, cada vez que le pidiéramos al contenedor un bean IUsuariosDAO, nos estaría dando una nueva instancia, mientras que ya hemos visto que en Spring por defecto los beans son _singletons_. ¿Qué sucede entonces?: lo que ocurre es que Spring intercepta la llamada al método udao y si ya se ha creado una instancia del bean devuelve la misma. Esto lo hace usando una técnica denominada programación orientada a aspectos o AOP.

La AOP y Spring

***

La AOP o Programación Orientada a Aspectos es una tecnología básica en Spring y que explica cómo funcionan internamente casi todas las capacidades que ofrece el _framework_. La AOP permite interceptar la ejecución en ciertos puntos del código para ejecutar en ellos nuestras propias tareas antes o después del código original. En el caso de la configuración Java, antes de crear el bean se comprueba si existe ya otra instancia creada. Como se ha dicho, la AOP se usa de manera extensiva en Spring. Es la que permite que se gestionen de manera automática las transacciones, la seguridad, la cache, y otros muchos aspectos. Para saber algo más de qué es la AOP y cómo funciona en Spring puedes consultar el apéndice de estos apuntes.

¿Por qué puede interesarnos usar la configuración Java en nuestros proyectos?: frente a la basada en anotaciones tiene la ventaja de que la configuración está centralizada y por tanto es más fácil de entender y modificar. Frente al XML ofrece la ventaja de que al ser código Java podemos usar las capacidades de chequeo de código de nuestro IDE y del compilador para verificar que todo es correcto. Por ejemplo, en el XML no podemos saber si nos hemos equivocado en el identificador de un bean "colaborador" o en el nombre de la clase del bean. Si esto pasa en la configuración Java nos daremos cuenta porque el código no compilará.

Por supuesto esta es una introducción muy básica a la configuración Java, podemos hacer muchas más cosas como configurar distintos grupos de beans en distintas clases @Configuration e importar en cada @Configuration las configuraciones que necesitemos que sean visibles. Para más información,como siempre, consultar la documentación del framework.

## Ejercicios del contenedor de beans de Spring

* [Configuración del proyecto](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-ejercicios.html#Configuraci%C3%B3n+del+proyecto)
* [Estructura de la aplicación](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-ejercicios.html#Estructura+de+la+aplicaci%C3%B3n)
* [Crear la capa de negocio (1 punto)](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-ejercicios.html#Crear+la+capa+de+negocio+%281+punto%29)
* [Crear la capa de acceso a datos y enlazarla con la de negocio (1.5 puntos)](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-ejercicios.html#Crear+la+capa+de+acceso+a+datos+y+enlazarla+con+la+de+negocio+%281.5+puntos%29)
* [Configurar beans en el XML (0.5 puntos)](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-ejercicios.html#Configurar+beans+en+el+XML+%280.5+puntos%29)

### Configuración del proyecto

SpringSource Tool Suite

***

En el módulo de Spring usaremos como IDE SpringSource Tool Suite, que es una versión de Eclipse con un conjunto de plugins instalados que facilitan bastante el trabajo con Spring. Os podéis bajar la versión actual de STS de [la web de SpringSource](http://www.springsource.com/products/springsource-tool-suite-download) (en la máquina virtual no es necesario, ya la tenéis preinstalada). Como en el módulo vamos a desarrollar básicamente aplicaciones web necesitamos un servidor donde desplegarlas. STS viene ya con una instancia preconfigurada del "VMWare vFabric tc server" que es una versión de Tomcat modificada por SpringSource. No obstante, vamos a usar Tomcat tal cual ya que es algo más ligero. Por tanto tendréis que crea una nueva instancia del servidor File > New > Other... > Server. Recordad que Tomcat está instalado en /opt/apache-tomcat-7.0.29

1. En las plantillas de la sesión hay un proyecto Spring ya creado que usa Maven. Para importarlo en STS usar (como siempre) File > Import... > Existing Maven Projects. En el "pom.xml" se incluye una dependencia del módulo "spring-context" porque éste, a su vez, depende del resto de módulos básicos de Spring, que así Maven incluirá automáticamente. Además, para poder instanciar beans desde la capa web necesitamos el módulo "spring-web".
2.  Lo primero que vamos a hacer es **Crear el fichero XML de configuración de Spring**. La localización del fichero es libre, pero nosotros vamos a colocarlo en la carpeta "src/main/resources". Hacer clic con botón derecho sobre esta carpeta, y en el menú contextual, seleccionar "New > Spring Bean Configuration File". Darle como nombre "beans.xml". Asegurarse de que está marcada la casilla de "Add Spring Project Nature if required", que activará el soporte de Spring para el proyecto. **No pulsar sobre Finish, sino sobre Next**, para poder ir al siguiente paso del asistente.

    <img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/imagenes/sesion01/crear_beans_xml_1.jpg" alt="Crear beans.xml. Paso 1" width="400">

    En el segundo paso marcamos los espacios de nombres que necesitamos: "context", "jee" y "p".

    <img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/imagenes/sesion01/crear_beans_xml_2.jpg" alt="Crear beans.xml. Paso 2" width="400">
3. Ahora tenemos que **referenciar el fichero de configuración de Spring en el web.xml** (recordad que está en src/main/webapp/WEB-INF), para que Spring arranque cuando arranque la aplicación web. Introduciremos en el web.xml el siguiente código:

```java
<context-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>classpath:beans.xml</param-value>
</context-param>
 
<listener>
    <listener-class>
    org.springframework.web.context.ContextLoaderListener
    </listener-class>
</listener>
```

Vamos a hacer una pequeña aplicación con acceso a base de datos, por lo que tenemos que preparar la conexión y la propia base de datos:

1. Asegurarse de que el .jar con el driver de mysql está en el directorio "lib" de Tomcat (/opt/apache-tomcat-7.0.29/lib). Si no lo está, copiarlo allí (se incluye en las plantillas de la sesión).
2. Recuerda que en Tomcat la configuración del DataSource se hace en el context.xml (en src/main/webapp/META-INF). Este archivo ya está creado, no tienes que modificar nada.
3.  Crear la propia base de datos: en las plantillas de la sesión se incluye un script SQL con la base de datos. Se puede ejecutar con el programa "MySQL Query Browser" o bien desde un terminal con la orden

    ```
    (nos pedirá el password de root de mysql)
    mysql -u root -p < pedidos.sql
    ```

### Estructura de la aplicación

La aplicación servirá para hacer pedidos de productos, funcionando según las siguientes reglas:

* La capa de negocio debe chequear que el número de unidades pedidas no supere un cierto límite. Si lo hace, el pedido no se puede procesar automáticamente, por lo que se genera una excepción.
* En la capa de acceso a datos cuando se haga un pedido correctamente se insertará la información en la tabla "pedidos".

<img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/imagenes/sesion01/diagrama_UML.jpg" alt="diagrama UML de la aplicación de pedidos" width="700">

En la figura anterior se muestra el diagrama UML de la aplicación

### Crear la capa de negocio (1 punto)

Vamos a empezar por crear la capa de negocio, aunque de momento no funcionará del todo al faltar el DAO.

1. Crear el interfaz IPedidosBO y la clase que lo implementa PedidosBOSimple en el paquete es.ua.jtech.spring.negocio. Usad como guía el diagrama UML para ver la signatura de los métodos.
   * Por el momento no hay DAO, así que no es necesario que definas el campo "pdao" del objeto.
   * Define el campo "cantidadMaxima" como static con un valor de 50.
   * Define un constructor y en él simplemente imprime un mensaje en la consola. Así podrás ver el momento en que Spring crea el bean y si lo crea más de una vez.
   * Implementa el método "insertarPedido": debe comprobar que la cantidad pedida no supera "cantidadMaxima". Si se supera, se lanzará una PedidosException (ya incluida en la plantilla). En caso contrario se llamaría al DAO, pero esta parte todavía no la vamos a hacer, simplemente si no se supera la cantidad máxima imprime un mensaje en la consola con "Pedido realizado".
2. Convertir la clase PedidosBOSimple en un bean de Spring añadiéndole la anotación @Service.
3. Modificar el fichero de configuración XML de Spring (beans.xml) para que busque las anotaciones Spring en el paquete que queremos, y en sus subpaquetes (es decir, en es.ua.jtech.spring). Recuerda que se usa la etiqueta \<context-component-scan/>.

Ayudas del STS

***

Usa el autocompletar de STS siempre que puedas, por ejemplo en el valor del atributo "base-package", para no tener que teclear manualmente el nombre del paquete y no cometer errores. Es posible que tengas que introducir la primera letra del nombre del paquete para que el autocompletar funcione.

***

4. En el servlet HacerPedido del paquete es.ua.jtech.spring.web hay que obtener un bean de tipo IPedidosBO y llamar al método insertarPedido con los valores de idCliente, idProducto y unidades.
5. Comprueba que cada vez que insertas un pedido de menos de 50 unidades el servlet muestra el mensaje, y que cuando se piden más salta la excepción. Finalmente comprueba que Spring solo crea una instancia del bean (solo se llama una vez al constructor), aunque obtengas varias veces el bean haciendo varios pedidos. Esto sucede porque usamos el ámbito por defecto, o sea "singleton". Además la creación se hace por defecto cuando se arranca el contenedor de Spring, no cuando se hace el primer pedido.

### Crear la capa de acceso a datos y enlazarla con la de negocio (1.5 puntos)

1. en el "beans.xml", configura el Datasource para acceder a la BD con Spring. Consulta los apuntes o transparencias para ver el uso de la etiqueta "jee:jndi-lookup". El id que le des al bean es indiferente si luego usas @Autowired para acceder a él.
2. Crea el interface IPedidosDAO y la clase PedidosDAOJDBC en el paquete es.ua.jtech.spring.datos.
   * Debes convertir la clase PedidosDAOJDBC en un bean de Spring anotándola con @Repository
   * Anota la variable miembro ds con @Autowired para que Spring busque el DataSource en el "beans.xml".
   * El codigo del método insertarPedido de PedidosDAOJDBC lo podéis tomar de las plantillas de la sesión para ahorrar tiempo
3. Modifica el PedidoBOSimple para que haga uso del DAO
   * Debes definir en PedidoBOSimple un campo de tipo IPedidosDAO y anotarlo con @Autowired, para que Spring resuelva e instancie automáticamente la dependencia

```java
@Autowired
IPedidosDAO pdao;
```

* Haz uso de este DAO en el insertarPedido. Es decir, el gestor de pedidos debe hacer uso del objeto "pdao" para insertar el pedido en la BD. Aunque el DAO devuelve el id del pedido, por el momento no es necesario que hagas nada con él. **No hagas un new() para inicializar "pdao"**. Si todo está correctamente configurado Spring inicializará esta variable, ya que la has marcado con @Autowired.

4. Finalmente, comprueba que ahora cuando haces un pedido a través del servlet HacerPedido éste se inserta en la base de datos.

### Configurar beans en el XML (0.5 puntos)

Tal y como está el código de PedidoBOSimple, hay que cambiar el código fuente para cambiar la cantidad máxima de unidades por pedido (50). Es mucho mejor usar Spring para externalizar este valor a través del "beans.xml" y poder cambiar la cantidad sin recompilar el código. El problema es que entonces la anotación @Service de PedidoBOSimple debe ser sustituida por una configuración completa del bean en el XML.

1. Comenta la anotación @Service de PedidoBOSimple.
2. Usando la etiqueta "bean", configura en el "beans.xml" un bean de la clase PedidoBOSimple. Cuidado: debes poner el nombre completo de la clase, incluyendo "packages".
3. Consulta los apuntes o transparencias para ver cómo fijar en el XML el valor de la propiedad "cantidadMaxima".
4. Comprueba que se inicializa la propiedad correctamente imprimiendo un mensaje desde el método "setCantidadMaxima", al que Spring llamará automáticamente para darle valor a la propiedad.

{% file src="../.gitbook/assets/sesion01-ejercicios.zip" %}

### 2. Acceso a datos

{% file src="../.gitbook/assets/sesion02-traspas (1).pdf" %}

* [La filosofía del acceso a datos en Spring](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html#La+filosof%C3%ADa+del+acceso+a+datos+en+Spring)
* [Uso de JDBC](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html#Uso+de+JDBC)
  * [JDBCTemplate](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html#JDBCTemplate)
  * [Consultas de selección](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html#Consultas+de+selecci%C3%B3n)
  * [Consultas de actualización](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html#Consultas+de+actualizaci%C3%B3n)
* [Uso de JPA](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html#Uso+de+JPA)
  * [Formas de acceder a la "EntityManagerFactory"](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html#Formas+de+acceder+a+la+%22EntityManagerFactory%22)
  * [JpaTemplate](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html#JpaTemplate)
* [Transaccionalidad declarativa](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html#Transaccionalidad+declarativa)
  * [El "Transaction Manager"](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html#El+%22Transaction+Manager%22)
  * [La anotación @Transactional](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html#La+anotaci%C3%B3n+%40Transactional)
  * [Transaccionalidad y uso directo de JDBC](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html#Transaccionalidad+y+uso+directo+de+JDBC)

En este tema veremos las facilidades que proporciona Spring para implementar nuestros objetos de la capa de acceso a datos. Veremos que nos permite simplificar el código, reduciendo el código repetitivo, y uniformizar el tratamiento independientemente de la implementación subyacente (JPA, JDBC, ...). Finalmente abordaremos la transaccionalidad, que es un aspecto íntimamente ligado con el acceso a datos, aunque su gestión no suele estar localizada en el código de los DAOs sino en la capa de negocio.

Debido al auge en los últimos años del _big data_ en la web, la "punta de lanza" de Spring en la capa de acceso a datos se ha movido más hacia la integración en Spring de bases de datos no relacionales (NoSQL). El proyecto Spring que se ocupa de estos aspectos es Spring Data, que, no obstante, queda fuera del ámbito de estos apuntes.

### La filosofía del acceso a datos en Spring

Spring proporciona básicamente dos ventajas a la hora de dar soporte a nuestros DAOs:

* Simplifica las operaciones de acceso a datos en APIs tediosos de utilizar como JDBC, proporcionando una capa de abstracción que reduce la necesidad de código repetitivo. Para ello se usan los denominados _templates_, que son clases que implementan este código, permitiendo que nos concentremos en la parte "interesante".
* Define una rica jerarquía de excepciones que modelan todos los problemas que nos podemos encontrar al operar con la base de datos, y que son independientes del API empleado.

Un **template** de acceso a datos en Spring es una clase que encapsula los detalles más tediosos (como por ejemplo la necesidad de abrir y cerrar la conexión con la base de datos en JDBC), permitiendo que nos ocupemos únicamente de la parte de código que hace realmente la tarea (inserción, consulta, ...)

Spring ofrece diversas _templates_ entre las que elegir, dependiendo del API de persistencia a emplear. Dada la heterogeneidad de los distintos APIs La implementación del DAO variará según usemos un API u otro , aunque en todos ellos Spring reduce enormemente la cantidad de código que debemos escribir, haciéndolo más mantenible.

Por otro lado, en APIs de acceso a datos como JDBC hay dos problemas básicos con respecto a la **gestión de excepciones**:

* Hay muy pocas excepciones distintas definidas para acceso a datos. Como consecuencia, la más importante, SQLException, es una especie de "chica para todo". La misma excepción se usa para propósitos tan distintos como: "no hay conexión con la base de datos", "el SQL de la consulta está mal formado" o "se ha producido una violación de la integridad de los datos". Esto hace que para el desarrollador sea tedioso escribir código que detecte adecuadamente el problema. Herramientas como Hibernate tienen una jerarquía de excepciones mucho más completa, pero son excepciones propias del API, y referenciarlas directamente va a introducir dependencias no deseadas en nuestro código.
* Las excepciones definidas en Java para acceso a datos son _comprobadas_. Esto implica que debemos poner try/catch o throws para gestionarlas, lo que inevitablemente llena _todos_ los métodos de acceso a datos de bloques de gestión de excepciones. Está bien obligar al desarrollador a responsabilizarse de los errores, pero en acceso a datos esta gestión se vuelve repetitiva y propensa a fallos, descuidos o a caer en "malas tentaciones" (¿quién no ha escrito _nunca_ un bloque catch vacío?). Además, muchos métodos de los DAO generalmente poco pueden hacer para recuperarse de la mayoría de excepciones (por ejemplo, "violación de la integridad"), lo que lleva al desarrollador a poner también throws de manera repetitiva y tediosa.

La solución de Spring al primer problema es la definición de una completa jerarquía de excepciones de acceso a datos. Cada problema tiene su excepción correspondiente, por ejemplo DataAccessResourceFailureException cuando no podemos conectar con la BD, DataIntegrityViolationException cuando se produce una violación de integridad en los datos, y así con otras muchas. Un aspecto fundamental es que estas excepciones _son independientes del API usado para acceder a los datos_, es decir, se generará el mismo DataIntegrityViolationException cuando queramos insertar un registro con clave primaria duplicada en JDBC que cuando queramos persistir un objeto con clave duplicada en JPA. La raíz de esta jerarquía de excepciones es DataAccessException.

En cuanto a la necesidad de gestionar las excepciones, Spring opta por eliminarla haciendo que todas las excepciones de acceso a datos sean _no comprobadas_. Esto libera al desarrollador de la carga de los try-catch/throws repetitivos, aunque evidentemente no lo libera de su responsabilidad, ya que las excepciones tendrán que gestionarse en algún nivel superior.

### Uso de JDBC

JDBC sigue siendo un API muy usado para el acceso a datos, aunque es tedioso y repetitivo. Vamos a ver cómo soluciona Spring algunos problemas de JDBC, manteniendo las ventajas de poder trabajar "a bajo nivel" si así lo deseamos. Probablemente las ventajas quedarán más claras si primero vemos un ejemplo con JDBC "a secas" y luego vemos el mismo código usando las facilidades que nos da Spring. Por ejemplo, supongamos un método que comprueba que el login y el password de un usuario son correctos, buscándolo en la base de datos con JDBC:

```java
private String SQL ="select * from usuarios where login=? and password=?";
     
public UsuarioTO login(String login, String password) throws DAOException {
    Connection con=null;
    try {
        con = ds.getConnection();   
           PreparedStatement ps = con.prepareStatement(SQL);
        ps.setString(1, login);
        ps.setString(2, password);
        ResultSet rs = ps.executeQuery();
        if (rs.next()) {
            UsuarioTO uto = new UsuarioTO();
            uto.setLogin(rs.getString("login"));
            uto.setPassword(rs.getString("password"));
            uto.setFechaNac(rs.getDate("fechaNac"));
            return uto;
        }
        else
            return null;
    } catch(SQLException sqle) {
        throw new DAOException(sqle);
    }
    finally {
        if (con!=null) {
            try {
                con.close();
            }
            catch(SQLException sqle2) {
                throw new DAOException(sqle2);                    
            }
        }
    }
}        
```

Se destacan las líneas de código que hacen realmente el trabajo de buscar el registro y devolver la información. El resto es simplemente la infraestructura necesaria para poder hacer el trabajo y gestionar los errores, y que, curiosamente _ocupa más líneas que el código "importante"_. Evidentemente la gestión de errores se habría podido "simplificar" poniendo en la cabecera del método un throws SQLException, pero entonces ya estaríamos introduciendo dependencias del API JDBC en la capa de negocio.

Veamos cómo nos puede ayudar Spring a simplificar nuestro código, manteniendo la flexibilidad que nos da SQL. El primer paso será elegir el _template_ apropiado.

#### JDBCTemplate

Como ya hemos dicho, los _templates_ son clases que encapsulan el código de gestión de los detalles "tediosos" del API de acceso a datos. En Spring, para JDBC tenemos varios templates disponibles, según queramos hacer consultas simples, con parámetros con nombre,... Vamos a usar aquí JdbcTemplate, que aprovecha las ventajas de Java 5 (autoboxing, genéricos, ...) para simplificar las operaciones. El equivalente si no tenemos Java 5 sería JdbcTemplate, que tiene una sintaxis mucho más complicada.

Lo primero que necesitamos es instanciar el _template_. El constructor de JdbcTemplate necesita un DataSource como parámetro. Como se vio en el tema anterior, los DataSource se pueden definir en el fichero XML de los beans, gracias al espacio de nombres jee:

```java
<jee:jndi-lookup id="ds" jndi-name="jdbc/MiDataSource" resource-ref="true"/>
```

Con lo que el DataSource se convierte en un bean de Spring llamado ds. La práctica habitual es inyectarlo en nuestro DAO y con él inicializar el _template_, que guardaremos en el DAO:

```java
import org.springframework.jdbc.core.simple.JbcTemplate;
import org.springframework.stereotype.Repository;
//Resto de imports...
...
 
@Repository("JDBC")
public class UsuariosDAOJDBC implements IUsuariosDAO {
    private JdbcTemplate jdbcTemplate;
     
    @Autowired
    public void setDataSource(DataSource ds) {
        this.jdbcTemplate = new JdbcTemplate(ds);
    }
 
    ...
}    
```

Recordemos que la anotación @Repository se usa para definir un DAO. Recordemos también que @Autowired inyecta la dependencia buscándola por tipo. En este caso no hay ambigüedad, ya que solo hemos definido un DataSource.

SimpleJdbcTemplate

***

Antes de Spring 3, la funcionalidad más "simple" de JDBC en Spring la implementaba SimpleJdbcTemplate, mientras que el API de JdbcTemplate era más complicado y por tanto solo recomendable para operaciones más complejas que las que vamos a ver aquí. A partir de la versión 3, SimpleJdbcTemplate está _deprecated_.

***

#### Consultas de selección

Normalmente en un SELECT se van recorriendo registros y nuestro DAO los va transformando en objetos Java que devolverá a la capa de negocio. En Spring, el trabajo de tomar los datos de un registro y empaquetarlos en un objeto lo hace RowMapper. Este es un interface, por lo que nuestro trabajo consistirá en escribir una clase que lo implemente. Realmente el único método estrictamente necesario es mapRow, que a partir de un registro debe devolver un objeto. En nuestro caso podría ser algo como:

```java
//esto podría también ser private y estar dentro del DAO
 //ya que solo lo necesitaremos dentro de él
 public class UsuarioTOMapper implements RowMapper<UsuarioTO> {
 
     public UsuarioTO mapRow(ResultSet rs, int numRow) throws SQLException {
          UsuarioTO uto = new UsuarioTO();
          uto.setLogin(rs.getString("login"));
          uto.setPassword(rs.getString("password"));
          uto.setFechaNac(rs.getDate("fechaNac"));
          return uto;
     }
}
```

Ahora solo nos queda escribir en el DAO el código que hace el SELECT:

```java
private static final String LOGIN_SQL = "select * " +
 "from usuarios where login=? and password=?";
 
public UsuarioTO login(String login, String password) {
    UsuarioTOMapper miMapper = new UsuarioTOMapper();
        
    return this.jdbcTemplate.queryForObject(LOGIN_SQL, miMapper,
                                              login, password);
}
```

Como se ve, no hay que gestionar la conexión con la base de datos, preocuparse del Statement ni nada parecido. El _template_ se ocupa de estos detalles. El método queryForObject hace el SELECT y devuelve un UsuarioTO ayudado del _mapper_ que hemos definido antes. Simplemente hay que pasarle el SQL a ejecutar y los valores de los parámetros.

Tampoco hay gestión de excepciones, porque Spring captura todas las SQLException de JDBC y las transforma en excepciones no comprobadas. Por supuesto, eso no quiere decir que no podamos capturarlas en el DAO si así lo deseamos. De hecho, en el código anterior hemos cometido en realidad un "descuido", ya que podría no haber ningún registro como resultado del SELECT. Para Spring esto es una excepción del tipo EmptyResultDataAccessException. Si queremos seguir la misma lógica que en el ejemplo con JDBC, deberíamos devolver null en este caso.

```java
private static final String LOGIN_SQL = "select * " + 
        "from usuarios where login=? and password=?";
 
public UsuarioTO login(String login, String password) {
   UsuarioTOMapper miMapper = new UsuarioTOMapper();
        
   try {
       return this.jdbcTemplate.queryForObject(LOGIN_SQL, miMapper, 
                                                login, password);
   }
   catch(EmptyResultDataAccessException erdae) {
       return null;
   }
}   
```

La amplia variedad de excepciones de acceso a datos convierte a Spring en un _framework_ un poco "quisquilloso" en ciertos aspectos. En un queryForObject Spring espera obtener _un registro y sólo un registro_, de modo que se lanza una excepción si no hay resultados, como hemos visto, pero también si hay más de uno: IncorrectResultSizeDataAccessException. Esto tiene su lógica, ya que queryForObject solo se debe usar cuando esperamos como máximo un registro. Si el SELECT pudiera devolver más de un resultado, en lugar de llamar a queryForObject, emplearíamos **query**, que usa los mismos parámetros, pero devuelve una lista de objetos.

#### Consultas de actualización

Las actualizaciones se hacen con el método update del _template_. Por ejemplo, aquí tenemos el código que da de alta a un nuevo usuario:

| 1234567 | `private` `static` `final` `String REGISTRAR_SQL =        "insert into usuarios(login, password, fechaNac) values (?,?,?)";` `public` `void` `registrar(UsuarioTO uto) {        this.jdbcTemplate.update(REGISTRAR_SQL, uto.getLogin(),             uto.getPassword(), uto.getFechaNac());}`    |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

### Uso de JPA

Veamos qué soporte ofrece Spring al otro API de persistencia que hemos visto durante el curso: JPA. El caso de JPA es muy distinto al de JDBC, ya que es de mucho más alto nivel y más conciso que este último. Por eso, aunque Spring implementa un _template_ para JPA, también se puede usar directamente el API sin escribir mucho más código. Además otra decisión que debemos tomar es quién gestionará los Entity Managers, si lo haremos "manualmente", al estilo Java SE, o bien a través del servidor de aplicaciones.

#### Formas de acceder a la "EntityManagerFactory"

Para poder trabajar con JPA lo primero que necesitamos es una EntityManagerFactory a través de la que crear los _Entity Managers_. Spring nos da tres posibilidades para acceder a ella:

* Como se hace en Java SE. Es decir, Entity Managers gestionados por la aplicación. En este caso, la mayor parte de la configuración se hace en el persistence.xml. Esta forma no se recomienda en general, solo para pruebas.
* Usando el soporte del servidor de aplicaciones. Evidentemente esto no funcionará en servidores que no tengan soporte JPA, como Tomcat, pero es la forma recomendada de trabajo en los que sí lo tienen. El acceso a la factoría se hace con JNDI.
* Usando un soporte propio de Spring. Esto funciona incluso en servidores sin soporte "nativo", como Tomcat. La configuración se hace sobre todo en el fichero de configuración de beans de Spring. El problema es que depende del servidor y también de la implementación JPA que estemos usando, pero está explicada con detalle en la documentación de Spring para varios casos posibles (sección 7.8.4.5).

Estas dos últimas posibilidades serían lo que en JPA se conoce como Entity Managers gestionados por el contenedor, con la diferencia de que una de ellas es una implementación nativa y la otra proporcionada por Spring. En cualquier caso, en realidad como desarrolladores todo esto nos da casi igual: elijamos la opción que elijamos Spring va a gestionar la EntityManagerFactory por nosotros. Esta se implementa como un bean de Spring, que podemos inyectar en nuestro código usando la anotación estándar de @PersistenceUnit. También podemos inyectarlo con @Autowired o @Resource, como vimos en el tema anterior. Dicho bean debemos definirlo en el fichero XML de configuración. Aquí tenemos un ejemplo usando JPA gestionado por el contenedor pero en Tomcat (es decir, gestionado en realidad por Spring)

| 12345678910111213141516171819202122232425262728 | `<?xml` `version="1.0"` `encoding="UTF-8"?><beans` `xmlns="`[`http://www.springframework.org/schema/beans`](http://www.springframework.org/schema/beans)`"       xmlns:xsi="`[`http://www.w3.org/2001/XMLSchema-instance`](http://www.w3.org/2001/XMLSchema-instance)`"       xmlns:context="`[`http://www.springframework.org/schema/context`](http://www.springframework.org/schema/context)`"       xsi:schemaLocation="`[`http://www.springframework.org/schema/beans`](http://www.springframework.org/schema/beans)         [`http://www.springframework.org/schema/beans/spring-beans.xsd`](http://www.springframework.org/schema/beans/spring-beans.xsd)         [`http://www.springframework.org/schema/context`](http://www.springframework.org/schema/context)         [`http://www.springframework.org/schema/context/spring-context.xsd`](http://www.springframework.org/schema/context/spring-context.xsd)`">` `<context:component-scan` `base-package="es.ua.jtech"/>` `<jee:jndi-lookup` `id="miDS"` `jndi-name="jdbc/MiDataSource"       resource-ref="true"/>` `<bean` `id="miEMF"` `class="org.springframework.orm.jpa.                    LocalContainerEntityManagerFactoryBean">      <property` `name="dataSource"` `ref="miDS"/>      <property` `name="jpaVendorAdapter">         <bean` `class="org.springframework.orm.jpa.vendor.                  HibernateJpaVendorAdapter">        <property` `name="showSql"` `value="true"/>            <property` `name="generateDdl"` `value="true"/>            <property` `name="databasePlatform"                    value="org.hibernate.dialect.HSQLDialect"/>        </bean>                    </property>    </bean></beans>` |
| ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Como vemos el bean es una clase propia de Spring, de ahí que no podamos definirlo mediante anotaciones.El identificador del bean (miEMF) es arbitrario e irrelevante para nuestro ejemplo. Especificamos dos propiedades del bean: el datasource que se usará para conectar con la BD (aquí definido con JNDI) y la implementación JPA que estamos usando, en nuestro caso Hibernate. Finalmente, la etiqueta "component-scan" es necesaria para que Spring reconozca y procese las anotaciones @PersistenceUnit y @PersistenceContext.

Cuidado con la implementación JPAEn nuestro caso la configuración se simplifica porque usamos Hibernate, pero otras implementaciones JPA requieren _load time weaving_, una técnica que manipula el _bytecode_ de las clases JPA en tiempo de ejecución y que es necesaria para que funcione la gestión por el contenedor. Si usáramos otra implementación JPA para la que fuera necesario el _load time weaving_ habría que configurarlo, configuración que es además dependiente del servidor web en que hagamos el despliegue. Consultad la documentación de Spring para más información.

Con esto ya podemos inyectar el EntityManager o bien la factoría de EntityManagers en nuestro código:

| 1234567891011121314151617 | `package` `es.ua.jtech.datos;` `//faltan los import...@Repository("JPA")public` `class` `UsuariosDAOJPA implements` `IUsuariosDAO {` `@PersistenceContext    EntityManager em;` `public` `UsuarioTO login(String login, String password) {        UsuarioTO uto = em.find(UsuarioTO.class, login);        if` `(uto!=null` `&& password.equals(uto.getPassword()))            return` `uto;        else            return` `null;    }}` |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

#### JpaTemplate

Esta clase facilita el trabajo con JPA, haciéndolo más sencillo. No obstante, al ser JPA un API relativamente conciso, no es de esperar que ahorremos mucho código. De hecho, los propios diseñadores de Spring recomiendan usar directamente el API JPA para aumentar la portabilidad del código. No obstante, vamos a verlo brevemente.

Aquí tenemos el esqueleto de una nueva implementación de IUsuariosDAO usando ahora JpaTemplate en lugar de JdbcTemplate:

| 1234567891011121314151617181920212223242526 | `package` `es.ua.jtech.spring.datos;` `import` `es.ua.jtech.spring.dominio.UsuarioTO;import` `javax.persistence.EntityManagerFactory;import` `org.springframework.beans.factory.annotation.Autowired;import` `org.springframework.orm.jpa.JpaTemplate;import` `org.springframework.stereotype.Repository;` `@Repository("JPATemplate")public` `class` `UsuariosDAOJPATemplate implements` `IUsuariosDAO {    private` `JpaTemplate template;` `@Autowired    public` `void` `setEntityManagerFactory(EntityManagerFactory emf) {        this.template = new` `JpaTemplate(emf);    }` `//Falta la implementación de este método    public` `UsuarioTO login(String login, String password) {        ...    }` `//Falta la implementación de este método    public` `void` `registrar(UsuarioTO uto) {        ...    }`    |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Como se ve, para instanciar un JpaTemplate necesitamos un EntityManagerFactory (de ahí el trabajo que nos habíamos tomado en la sección anterior). En este caso usamos la anotación @Autowired para que Spring resuelva automáticamente la dependencia y la inyecte a través del _setter_. También podríamos haber usado @PersistenceUnit, que al ser estándar hace nuestro código más portable. Una vez creado el Template, se puede reutilizar en todos los métodos ya que es _thread-safe_, al igual que en JDBC.

Ahora veamos cómo implementar los métodos del DAO. En lugar de ver sistemáticamente el API de JpaTemplate, nos limitaremos a mostrar un par de ejemplos. Primero, una consulta de selección:

| 1234567 | `private` `static` `String LOGIN_JPAQL = "SELECT u FROM UsuarioTO u                                   WHERE u.login=?1` `AND u.password=?2";public` `UsuarioTO login(String login, String password) {   List<UsuarioTO> lista;     lista = this.template.find(LOGIN_JPAQL, login, password);   return` `(UsuarioTO) lista.get(0);}`    |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Obsérvese que en el ejemplo anterior **no es necesario instanciar ni cerrar ningún Entity Manager**, ya que la gestión la lleva a cabo el _template_. En cuanto al API de acceso a datos, como se ve, el método find nos devuelve una lista de resultados y nos permite pasar parámetros a JPAQL gracias a los _varargs_ de Java 5. En el ejemplo anterior hemos "forzado un poco" el API de JpaTemplate ya que find devuelve siempre una lista y en nuestro caso está claro que no va a haber más de un objeto como resultado. Se ha hecho así para mantener el paralelismo con el ejemplo JDBC, aunque aquí quizá lo más natural sería buscar por clave primaria. Tampoco se han tratado adecuadamente los errores, como que no haya ningún resultado en la lista.

Otros métodos de JpaTemplate nos permiten trabajar con parámetros con nombre y con _named queries_.

Las actualizaciones de datos no ofrecen gran ventaja con respecto al API directo de JPA, salvo la gestión automática del Entity Manager, por ejemplo:

| 123 | `public` `void` `registrar(UsuarioTO uto) {   this.template.persist(uto);}` |
| --- | --------------------------------------------------------------------------- |

¡Cuidado con la transaccionalidad!Spring gestiona automáticamente los Entity Manager en función de la transaccionalidad de los métodos. Si no declaramos ningún tipo de transaccionalidad, como en el ejemplo anterior, podemos encontrarnos con que al hacer un persist no se hace el commit y el cambio no tiene efecto. En el último apartado del tema veremos cómo especificar la transaccionalidad, pero repetimos que es importante darse cuenta de que _si no especificamos transaccionalidad, la gestión automática de los entity manager no funcionará adecuadamente_.

Una ventaja del uso de _templates_ es la jerarquía de excepciones de Spring. En caso de usar directamente el API JPA nos llegarán las propias de la implementación JPA que estemos usando. Si queremos que Spring capture dichas excepciones y las transforme en excepciones de Spring, debemos definir un bean de la clase PersistenceExceptionTranslationPostProcessor en el XML de definición de beans:

| 12 | `<bean` `class="org.springframework.dao. <!--Esto debería estar en 1 sola línea-->                      annotation.PersistenceExceptionTranslationPostProcessor"/>`        |
| -- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Como se ve, lo más complicado de la definición anterior ¡es el nombre de la clase!

### Transaccionalidad declarativa

Abordamos aquí la transaccionalidad porque es un aspecto íntimamente ligado al acceso a datos, aunque se suele gestionar desde la capa de negocio en lugar de directamente en los DAOs. Vamos a ver qué facilidades nos da Spring para controlar la transaccionalidad de forma declarativa.

#### El "Transaction Manager"

Lo primero es escoger la estrategia de gestión de transacciones: si estamos en un servidor de aplicaciones podemos usar JTA, pero si no, tendremos que recurrir a la implementación nativa del API de acceso a datos que estemos usando. Spring implementa clases propias para trabajar con JTA o bien con transacciones JDBC o JPA. Estas clases gestionan las transacciones y se denominan "Transaction Managers". Necesitaremos definir uno de ellos en el fichero XML de definición de beans.

Por ejemplo, en el caso de estar usando JDBC sin soporte JTA, como en Tomcat, necesitaríamos una implementación de Transaction Manager que referencia un DataSource.

| 12345678910111213141516171819202122232425262728 | `<?xml` `version="1.0"` `encoding="UTF-8"?><beans` `xmlns="`[`http://www.springframework.org/schema/beans`](http://www.springframework.org/schema/beans)`"       xmlns:xsi="`[`http://www.w3.org/2001/XMLSchema-instance`](http://www.w3.org/2001/XMLSchema-instance)`"       xmlns:jee="`[`http://www.springframework.org/schema/jee`](http://www.springframework.org/schema/jee)`"       xmlns:context="`[`http://www.springframework.org/schema/context`](http://www.springframework.org/schema/context)`"       xmlns:tx="`[`http://www.springframework.org/schema/tx`](http://www.springframework.org/schema/tx)`"       xsi:schemaLocation="`[`http://www.springframework.org/schema/beans`](http://www.springframework.org/schema/beans)        [`http://www.springframework.org/schema/beans/spring-beans.xsd`](http://www.springframework.org/schema/beans/spring-beans.xsd)        [`http://www.springframework.org/schema/jee`](http://www.springframework.org/schema/jee)        [`http://www.springframework.org/schema/jee/spring-jee.xsd`](http://www.springframework.org/schema/jee/spring-jee.xsd)        [`http://www.springframework.org/schema/context`](http://www.springframework.org/schema/context)        [`http://www.springframework.org/schema/context/spring-context.xsd`](http://www.springframework.org/schema/context/spring-context.xsd)        [`http://www.springframework.org/schema/tx`](http://www.springframework.org/schema/tx)        [`http://www.springframework.org/schema/tx/spring-tx.xsd`](http://www.springframework.org/schema/tx/spring-tx.xsd)`">`      `<!-- el DataSource que usará el Transaction Manager -->    <jee:jndi-lookup` `id="miDataSource"` `jndi-name="DStestSpring"` `resource-ref="true"` `/>` `<!-- Elegimos el tipo apropiado de "Transaction Manager" (JDBC) -->    <bean` `id="miTxManager"          class="org.springframework.jdbc.datasource.DataSourceTransactionManager">        <property` `name="dataSource"` `ref="miDataSource"/>    </bean>` `<!-- Decimos que para este Transaction Manager vamos a usar anotaciones -->    <tx:annotation-driven` `transaction-manager="miTxManager"/> </beans>`    |
| ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

#### La anotación @Transactional

Para entender mejor el uso de esta anotación, vamos a plantear un ejemplo. Supongamos que al registrar un nuevo usuario, además de introducir sus datos en la tabla de usuarios, también lo debemos dar de alta en otra tabla para enviarle publicidad, pero si no es posible este alta de publicidad por lo que sea (dirección de email no válida, digamos) hay que anular toda la operación. Supongamos que al detectar el error nuestro DAO lanzaría un DataAccessException que, recordemos, es la raíz de la jerarquía de excepciones de acceso a datos en Spring.

Colocaremos @Transactional delante de los métodos que queramos hacer transaccionales. Si la colocamos delante de una clase, estamos diciendo que **todos** sus métodos deben ser transaccionales. En nuestro caso:

| 123456789101112131415161718 | `//Faltan los imports, etc....@Servicepublic` `class` `GestorUsuarios {  @Autowired  @Qualifier("JPA")  private` `IUsuariosDAO udao;` `public` `void` `setUdao(IUsuariosDAO udao) {      this.udao = udao;  }` `@Transactional  public` `void` `registrar(UsuarioTO uto) {      udao.registrar(uto);      udao.altaPublicidad(uto);  }}` |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

El comportamiento por defecto de @Transactional es **realizar un&#x20;**_**rollback**_**&#x20;si se ha lanzado alguna excepción no comprobada**. Recordemos que, precisamente, DataAccessException era de ese tipo. Por tanto, se hará automáticamente un _rollback_ en caso de error.

¡Cuidado con los métodos no públicos!Todos los métodos que deseamos hacer transaccionales deben ser públicos, no es posible usar @Transactional en métodos protected o private. La razón es que cuando hacemos un método transaccional y lo llamamos desde cualquier otra clase quien está recibiendo la llamada en realidad es el gestor de transacciones. El gestor comienza y acaba las transacciones y "entre medias" llama a nuestro método de acceso a datos, pero eso no lo podrá hacer si este no es public. Por la misma razón, la anotación no funcionará si el método transaccional es llamado desde la misma clase que lo define, aunque esto último se puede solucionar haciendo la configuración adecuada.

@Transactional tiene varias implicaciones por defecto (aunque son totalmente configurables, como ahora veremos):

* La propagación de la transacción es REQUIRED. Esto significa que se requiere una transacción abierta para que el método se ejecute en ella. Si no hubiera ninguna, Spring automáticamente la crearía. Esto funciona igual que los EJBs del JavaEE estándar.Transaccionalidad declarativa en JavaEEEn el bloque de Aplicaciones Enterprise se verá con mucho más detalle todo el tema de la transaccionalidad declarativa, y los diferentes tipos de gestión de la transacción típicos en JavaEE. Por el momento nos limitaremos a casos relativamente simples.
* Cualquier excepción no comprobada dispara el _rollback_ y cualquiera comprobada, no.
* La transacción es de lectura/escritura (en algunos APIs de acceso a datos, por ejemplo, Hibernate, las transacciones de "solo lectura" son mucho más eficientes).
* El _timeout_ para efectuar la operación antes de que se haga _rollback_ es el que tenga por defecto el API usado (no todos soportan _timeout_).

Todo este comportamiento se puede configurar a través de los atributos de la anotación, como se muestra en la siguiente tabla:

| Propiedad              | Tipo                                   | Significado                                                 |
| ---------------------- | -------------------------------------- | ----------------------------------------------------------- |
| propagation            | enum: Propagation                      | nivel de propagación (opcional)                             |
| isolation              | enum: Isolation                        | nivel de aislamiento (opcional)                             |
| readOnly               | boolean                                | solo de lectura vs. de lectura/escritura                    |
| timeOut                | int (segundos)                         |                                                             |
| rollbackFor            | array de objetos Throwable             | clases de excepción que deben causar rollback               |
| rollbackForClassName   | array con nombres de objetos Throwable | nombres de clases de excepción que deben causar rollback    |
| noRollbackFor          | array de objetos Throwable             | clases de excepción que no deben causar rollback            |
| noRollbackForClassName | array con nombres de objetos Throwable | nombres de clases de excepción que no deben causar rollback |

Por ejemplo supongamos que al producirse un error en la llamada a altaPublicidad() lo que se genera es una excepción propia de tipo AltaPublicidadException, que es comprobada pero queremos que cause un _rollback_:

| 12345 | `@Transactional(rollbackFor=AltaPublicidadException.class)public` `void` `registrar(UsuarioTO uto) {      udao.registrar(uto);      udao.altaPublicidad(uto);}` |
| ----- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Finalmente, destacar que podemos poner transaccionalidad "global" a una clase y en cada uno de los métodos especificar atributos distintos:

| 12345678910111213141516171819202122232425262728293031 | `//Faltan los imports, etc....@Service//Vale, el REQUIRED no haría falta ponerlo porque es la opción//por defecto, pero esto es solo un humilde ejemplo!@Transactional(propagation=Propagation.REQUIRED)public` `class` `GestorUsuarios {  @Autowired  @Qualifier("JPA")  private` `IUsuariosDAO udao;` `public` `void` `setUdao(IUsuariosDAO udao) {      this.udao = udao;  }` `@Transactional(readOnly=true)  public` `UsuarioTO login(String login, String password) {      return` `udao.login(login, password);  }` `@Transactional(rollbackFor=AltaPublicidadException.class)  public` `void` `registrar(UsuarioTO uto) {      udao.registrar(uto);      udao.altaPublicidad(uto);  }` `public` `void` `eliminarUsuario(UsuarioTO uto) {       udao.eliminar(uto);  }}`  |
| ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Nótese que eliminarUsuario es también transaccional, heredando las propiedades transaccionales de la clase.

#### Transaccionalidad y uso directo de JDBC

Si usamos el API JDBC directamente, sin ninguna de las facilidades que nos da Spring, se nos va a plantear un problema con la transaccionalidad declarativa: si cada método del DAO abre y cierra una conexión con la BD (lo más habitual), va a ser imposible hacer un rollback de las operaciones que hagan distintos métodos, ya que la conexión ya se habrá cerrado. Para evitar este problema, Spring nos proporciona la clase DataSourceUtils, que nos permite "liberar" la conexión desde nuestro punto de vista, pero mantenerla abierta automáticamente gracias a Spring, hasta que se cierre la transacción y no sea necesaria más. Su uso es muy sencillo. Cada vez que queremos obtener una conexión hacemos:

| 123456 | `//El DataSource se habría resuelto por inyección de dependencias@Autowiredprivate` `DataSource ds;` `...Connection con = DataSourceUtils.getConnection(ds);` |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Y cada vez que queremos liberarla:

| 1 | `DataSourceUtils.releaseConnection(con, ds);`    |
| - | ------------------------------------------------ |

Nótese que al liberar la conexión no se puede generar una SQLException, al contrario de lo que pasa cuando cerramos con el close de JDBC, lo que al menos nos ahorra un catch.

&#x20;

### Sesiones

| Número y nombre de sesión                          | Materiales                                                                                                                                                                                                        |                                                                                                                                                                                                                     |                                                                                                                                                                                                                     |                                                                                                                                                                                                                              |   |
| -------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | - |
| 1. Introducción a Spring. Spring core              | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) apuntes](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-apuntes.html)     | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/pdf.gif) traspas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/traspas/sesion01-traspas.pdf) | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) ejercicios](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion01-ejercicios.html) | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/zip.gif) plantillas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/ejercicios/sesion01-ejercicios.zip) |   |
| 2. Acceso a datos                                  | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) apuntes](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-apuntes.html)     | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/pdf.gif) traspas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/traspas/sesion02-traspas.pdf) | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) ejercicios](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion02-ejercicios.html) | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/zip.gif) plantillas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/ejercicios/sesion02-ejercicios.zip) |   |
| 3. Spring MVC                                      | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) apuntes](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion03-apuntes.html)     | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/pdf.gif) traspas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/traspas/sesion03-traspas.pdf) | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) ejercicios](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion03-ejercicios.html) | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/zip.gif) plantillas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/ejercicios/sesion03-ejercicios.zip) |   |
| 4. Aplicaciones AJAX y REST con Spring MVC         | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) apuntes](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion04-apuntes.html)     | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/pdf.gif) traspas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/traspas/sesion04-traspas.pdf) | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) ejercicios](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion04-ejercicios.html) |                                                                                                                                                                                                                              |   |
| 5. Validación e internacionalización en Spring MVC | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) apuntes](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion05-apuntes.html)     | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/pdf.gif) traspas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/traspas/sesion05-traspas.pdf) | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) ejercicios](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion05-ejercicios.html) | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/zip.gif) plantillas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/ejercicios/sesion05-ejercicios.zip) |   |
| 6. Acceso remoto. Pruebas                          | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) apuntes](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion06-apuntes.html)     | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/pdf.gif) traspas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/traspas/sesion06-traspas.pdf) | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) ejercicios](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion06-ejercicios.html) |                                                                                                                                                                                                                              |   |
| 7. Seguridad con Spring Security                   | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) apuntes](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion07-apuntes.html)     | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/pdf.gif) traspas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/traspas/sesion07-traspas.pdf) | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) ejercicios](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion07-ejercicios.html) |                                                                                                                                                                                                                              |   |
| 8. Desarrollo rápido de aplicaciones con Roo       | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) apuntes](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion08-apuntes.html)     | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/pdf.gif) traspas](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/traspas/sesion08-traspas.pdf) | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) ejercicios](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/sesion08-ejercicios.html) |                                                                                                                                                                                                                              |   |
| Apéndice: AOP en Spring                            | [![](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/images/html.gif) apuntes](https://expertojavaua.github.io/www.jtech.ua.es/j2ee/publico/spring-2012-13/apendice_AOP-apuntes.html) |                                                                                                                                                                                                                     |                                                                                                                                                                                                                     |                                                                                                                                                                                                                              |   |
