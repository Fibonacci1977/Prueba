# SOA vs. SOAP y REST

{% embed url="https://ccia.esei.uvigo.es/docencia/SCS/" %}

SOAP vs REST Web Services 👨🏫

Existen muchas diferencias entre SOAP y REST Web Services.\
Las 10 diferencias importantes entre SOAP y REST se dan a continuación:

1. SOAP es un protocolo.   \
   REST es un estilo arquitectónico.
2. SOAP significa Protocolo simple de acceso a objetos.   \
   REST significa Transferencia de estado representacional.
3. SOAP no puede usar REST porque es un protocolo.   \
   REST puede usar servicios web SOAP porque es un concepto y puede usar cualquier protocolo como HTTP, SOAP.
4. SOAP utiliza interfaces de servicios para exponer la lógica empresarial.   \
   REST usa URI para exponer la lógica empresarial.
5. JAX-WS es la API de Java para servicios web SOAP.   \
   JAX-RS es la API de Java para servicios web RESTful.
6. SOAP define los estándares que deben seguirse estrictamente.   \
   REST no define demasiados estándares como SOAP.
7. SOAP requiere más ancho de banda y recursos que REST.   \
   REST requiere menos ancho de banda y recursos que SOAP.
8. SOAP define su propia seguridad.   \
   Los servicios web RESTful heredan las medidas de seguridad del transporte subyacente.
9. SOAP solo permite el formato de datos XML.   \
   REST permite diferentes formatos de datos, como texto sin formato, HTML, XML, JSON, etc.
10. SOAP es menos preferido que REST.    \
    REST más preferido que SOAP.

En este tutorial intentaremos explicar qué diferencias existen entre una arquitectura SOA y el desarrollo de servicios web basados en SOAP o REST, cómo se relacionan y los beneficios esperados de cada uno.

### SOA vs. SOAP y REST.

#### 0. Índice de contenidos.

* [1. Introducción.](https://adictosaltrabajo.com/2014/01/10/soavs-soap-rest/#01)
* [2. Entorno.](https://adictosaltrabajo.com/2014/01/10/soavs-soap-rest/#02)
* [3. ¿Por qué servicios web basados en SOAP o REST?.](https://adictosaltrabajo.com/2014/01/10/soavs-soap-rest/#03)
* [4. ¿Por qué SOA?.](https://adictosaltrabajo.com/2014/01/10/soavs-soap-rest/#04)
* [5. La relación entre SOA y los servicios web basados en SOAP o REST.](https://adictosaltrabajo.com/2014/01/10/soavs-soap-rest/#05)
* [6. Referencias.](https://adictosaltrabajo.com/2014/01/10/soavs-soap-rest/#06)
* [7. Conclusiones.](https://adictosaltrabajo.com/2014/01/10/soavs-soap-rest/#07)

<br>

#### 1. Introducción

SOA y SOAP suelen ser términos que, a menudo, suelen generar bastante confusión (supongo que por la semejanza de sus siglas). Parece que muchas veces no tenemos del todo claro dónde empieza y acaba cada cosa aunque, en el fondo, sabemos que existe relación entre ambos términos. Incluso es común encontrar por ahí algunos artículos donde se refieren a SOA cuando realmente quieren decir SOAP.

Con el desarrollo de servicios web basados en REST también puede ocurrir algo parecido.

En este tutorial intentaremos explicar qué diferencias existen entre una arquitectura SOA y el desarrollo de servicios web basados en SOAP o REST, cómo se relacionan y los beneficios esperados de cada uno.

<br>

#### 2. Entorno.

El tutorial está escrito usando el siguiente entorno:

* Hardware: Portátil MacBook Pro 15′ (2.2 Ghz Intel Core I7, 8GB DDR3).
* Sistema Operativo: Mac OS X Mavericks 10.9

#### 3. ¿Por qué servicios web basados en SOAP o REST?.

Nótese que este punto no pretende ser una comparativa entre SOAP y REST, lo que intentaremos es destacar los objetivos y características comunes del desarrollo de servicios web basados en SOAP o REST.

SOAP y REST son siglas asociadas a estándares para el diseño y desarrollo de web services o servicios RESTful. El uso más común que se suele dar a estos servicios es el de integrar diferentes sistemas o componentes de una o varias plataformas. Mediante el uso de estándares conseguimos que esa integración se convierta en interoperabilidad. La interacción se consigue mediante el intercambio de mensajes entre sistemas.

Es muy común ver cómo se emplean tanto SOAP como REST para exponer parte de la funcionalidad (o recursos) de diferentes aplicativos. Tenemos ejemplos muy claros de esto en dos excelentes herramientas como son Sonar y [Jenkins](https://builds.apache.org/api/). En este caso exponen recursos a través de un API REST (imagino que por sencillez y porque los requisitos lo permiten) para que otros sistemas puedan interoperar con ellos. Lógicamente, esta misma filosofía es aplicable dentro de una plataforma empresarial.

![](https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/SOAvsSOAPREST/WS1.png)

También puede ser bastante común crear un web service cuya lógica funcionalidad sea requerida por distintos aplicativos o componentes dentro de una plataforma (el típico [servicio de utilidad](https://adictosaltrabajo.com/tutoriales/tutoriales.php?pagina=SOATiposServicios)). Este enfoque ya se va acercando a SOA, pero eso será en el siguiente punto. Además, podríamos tener un servicio de más alto nivel para ser consumido desde diferentes frontales: ej. una aplicación web y una aplicación móvil.

![](https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/SOAvsSOAPREST/WS2.png)

Y un ejemplo clásico en el uso de servicios web es el de integrar diferentes sistemas o plataformas como puede ser el caso de diferentes departamentos dentro de una organización o diferentes organizaciones.

![](https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/SOAvsSOAPREST/WS3.png)

Además de la interoperabilidad, otra gran ventaja que ofrecen estas alternativas es la flexibilidad a la hora de elegir la tecnología con la que queremos implementar la lógica de negocio que queremos exponer. De esta forma, podemos comunicar diferentes sistemas o componentes independientemente de la tecnología con la que están implementados.

Pero, ¿qué tiene que ver todo esto con SOA?. Lo vemos a continuación…

#### 4. ¿Por qué SOA?.

SOA es un modelo de arquitectura tecnológica que surge de la aplicación del paradigma de orientación a servicios. Dicho paradigma no es una idea revolucionaria, sino que surge de la influencia de diferentes modelos como pueden ser: la orientación a objetos, BPM, orientación a aspectos, web services…

La idea subyacente consiste en descomponer la lógica de negocio de una organización (o partes de ella) en pequeñas unidades de funcionalidad. Estas pequeñas unidades son los servicios. Con esto conseguimos romper con el concepto de aplicaciones «silo», donde se creaba una aplicación para resolver una necesidad de negocio concreta, otra para resolver otra, etc… Lo que tendremos será una plataforma transversal formada por un inventario de servicios (o varios) de forma que no solventaremos las necesidades cambiantes del negocio creando nuevas aplicaciones sino combinando diferentes servicios (y creando nuevos servicios cuando corresponda). De esta forma conseguimos que los departamentos de IT y negocio estén alineados de forma que el primero pueda responder de manera ágil a las exigencias del segundo.

Dicho esto, alguien puede pensar: _«Entonces para tener una SOA lo que tengo que hacer es crear web services a lo bestia»_. Pues no, ójala fuese tan fácil :).

Es cierto que para poder tener una arquitectura SOA necesitamos tener una buena base de servicios. Pero no vale con crearlos de cualquier manera. Estas son algunas consideraciones que debemos tener en cuenta:

* Debemos contar con una buena base de servicios reutilizables o muli-propósito. Servicios no diseñados para resolver una necesidad de negocio específica. Los [servicios de utilidad y entidad](https://adictosaltrabajo.com/tutoriales/tutoriales.php?pagina=SOATiposServicios) son perfectos en este sentido. De esta forma podremos crear múltiples composiones basadas en ellos conforme las necesidades de negocio van cambiando.
* Nuestros servicios deben contar con un contrato estandarizado (ya sea WSDL, un documento o ambos) con un modelo de datos normalizado dentro de todo nuestro inventario. De esta manera facilitamos la interacción entre servicios. Sustituimos el concepto de integración por interoperabilidad intrínseca.
* Debemos categorizar y registrar todos nuestros servicios (recursos de plataforma) de forma que, en cualquier momento, podamos consultar con qué recursos contamos, qué funcionalidades encapsulan y cómo interacturar con ellos.
* Debemos evitar el solapamiento de funcionalidades entre servicios como parte de la labor de gobierno SOA que debemos ejercer sobre nuestra plataforma.
* Debemos evitar «casarnos» con una tecnología en concreto (Java, .Net, etc…) a la hora de crear nuestros servicios. Los servicios deben poder implementarse con la tecnología que consideremos necesaria en cada momento sin que esto afecte al resto de la plataforma.

![](https://adictosaltrabajo.com/wp-content/uploads/tutorial-data/SOAvsSOAPREST/SOA.png)

Como vemos, no resulta tan fácil diseñar una arquitectura orientada a servicios. Sin embargo, los servicios web bastados tanto en SOAP como REST son excelentes opciones a la hora de crear los servicios que conformarán nuestra plataforma ya que, sin lugar a dudas, reunen las condiciones ideales para poder diseñar servicios que cumplan con los principios de diseño alineados con SOA.

#### 5. La relación entre SOA y los servicios web basados en SOAP o REST.

Como comentamos anteriormente, SOA gira en torno a los servicios o recursos de plataforma. Dichos servicios deben cumplir con una serie de principios de diseño como pueden ser: una alta capacidad de reutilización, abstracción, bajo acoplamiento, autonomía, capacidad de composición, contar con un contrato estandarizado (WSDL en caso de SOAP, convenciones en caso de REST y posiblidad de complementarlos con documentación en ambos casos)…

Tanto SOAP como REST pueden cumplir a la perfección con cualquiera de estos principios. Sin embargo, son especificaciones totalmente independientes a SOA. De la correcta aplicación del paradigma de orientación a servicios y, sobre todo, del cumplimiento de los principios de diseño de servicios surgirá el éxito o el fracaso de esta relación.

Lógicamente, no vale únicamente con tener servicios web para tener una SOA. Como vimos en el punto anterior, los servicios que exponen Jenkins y Sonar son servicios de muy alto nivel ([servicios de tarea](https://adictosaltrabajo.com/tutoriales/tutoriales.php?pagina=SOATiposServicios)). Si todo nuestro inventario se basase en este tipo de servicios, no podríamos realizar composiciones complejas ni, por tanto, modelar de forma ágil diferentes procesos cuando el negocio así lo requiriese.

Un fallo conceptual muy común en algunos equipos de IT es el de asegurar que tienen una fabulosa arquitectura SOA cuando realmente lo que tienen son unos cuantos servicios de alto nivel orquestados por un bus. Pero eso no es SOA, en todo caso es integración.

#### 6. Referencias.

* [SOA: Principles of Service Design](http://servicetechbooks.com/psd)

<br>

#### 7. Conclusiones.

Construir una arquitectura SOA es un trabajo relativamente complejo, laborioso y siempre a medio/largo plazo. No todas las plataformas u organizaciones son las mejores candidatas para ello. Es muy importante conocer bien el paradigma de orientación a servicios antes de barajar esta posibilidad. Debemos conocer antes sus ventajas, inconvenientes, objetivos, beneficios, cambios a nivel organizativo, etc…

Podemos diseñar excelentes arquitecturas basadas en REST de una manera bastante más sencilla. Incluso podemos basarnos en aplicaciones silo, que tienen sus inconvenientes pero también sus ventajas, para la integración entre ellas (si fuese necesaria) ya tenemos muchas alternativas como los servicios web. No todo debe pasar por SOA. SOA simplemente es un medio para obtener una serie de beneficios, nunca debe ser un fin en sí mismo. Todo depende del tamaño de la organización, presupuesto, lo cambiante del negocio y, sobre todo, del sentido común :-).

Espero que este tutorial os haya sido de ayuda. Un saludo.

## SOAP vs REST ¿cual es mejor?



<figure><img src="https://www.oscarblancarteblog.com/wp-content/uploads/2017/03/SOAP-vs-REST-1024x576.png" alt="SOAP vs REST"><figcaption></figcaption></figure>

SOAP vs REST es una comparación que muchos programadores o incluso arquitectos de software suelen preguntarse a la hora de desarrollar las API para sus sistemas, pero cual es realmente la diferencia que existe entre ellas, ¿Será que una es superior a la otra? ¿Será que REST llego para remplazar a SOAP? Pues bien, en este artículo trataremos de resolver esta gran duda.

Primero que nada, me gustaría aclarar un error muy común que puede hacer que distorsione por completo tu entendimiento con respecto a los Web Services y es que **SOA no es igual que SOAP y tener Web Services no significa que tenemos SOA**. Hace un tiempo publique un artículo donde hablaba acerca de la [Arquitectura SOA](https://www.oscarblancarteblog.com/2014/07/23/que-es-service-oriented-architecture-soa/) por si quieres darle una repasada al tema.\
Pues bien, ya con este punto aclaro, debemos entender que SOA (Service-Oriented Architecture) es un _**tipo de Arquitectura de Software**_ y no una tecnología o producto. SOA es una arquitectura que se base en la integración de aplicaciones mediante Servicios, los servicios representan la medida más granular de la arquitectura, sobre la que se construyen otros artefactos como: composiciones, proxys, fachadas, BPM e incluso API completas. Ahora bien, si SOA tiene como médula espinal los servicios, ¿no son SOAP y REST servicios? ¡Revelador no!!\
Entonces si REST y SOAP son en realidad servicios, entonces que diferencia existe entre las dos, cual es el propósito de que existan dos tecnologías que aparentemente hacen lo mismo. Primero entendamos que SOAP y REST siguen la misma Arquitectura (SOA), por lo que las dos deberían de apegarse a los mismos principios.

<figure><img src="https://www.oscarblancarteblog.com/wp-content/uploads/2017/03/SOAP_VS_REST_SOA.png" alt="SOAP vs REST"><figcaption></figcaption></figure>

En este punto nos debe de quedar claro que tanto SOAP como REST son tecnologías que implementan la arquitectura SOA.

### &#x20;

### Que es SOAP:

Los servicios SOAP o mejor conocimos simplemente como Web Services, son servicios que basan su comunicación bajo el protocolo SOAP (Simple Object Access Protocol) el cual este definido por Wikipedia como “protocolo estándar que define cómo dos objetos en diferentes procesos pueden comunicarse por medio de intercambio de datos XML”. Por lo tanto, queda claro que la comunicación se realiza mediante XML, lo cual nos debe de quedar muy claro, pues es en este aspecto donde radican las principales diferencias contra REST. Los servicios SOAP funcionan por lo general por el protocolo HTTP que es lo más común cuando invocamos un Web Services, sin embargo, SOAP no está limitado a este protocolo, si no que puede ser enviado por FTP, POP3, TCP, Colas de mensajería (JMS, MQ, etc). Pero como comentaba, HTTP es el protocolo principal.

<figure><img src="https://www.oscarblancarteblog.com/wp-content/uploads/2017/03/soap-services.png" alt="SOAP vs REST"><figcaption></figcaption></figure>

Si bien, me gustaría poner una sección de ventajas y desventajas, la realidad es que estas pueden ser lo contrario dependiendo del punto de vista y la situación concreta del problema a resolver por lo que me gustaría dejar un breve análisis de cuando utilizar SOAP. A mi parecer SOAP sigue siendo el mejor protocolo para **la comunicación de Server to Server o Partner to Partner** pues es un protocolo mucho más robusto, tiene un tipiado mucho más fuerte, permite agregar _**metadatos**_ mediante los atributos (cosa que JSON no tiene), permite definir _**espacios de nombre**_, evitando la ambigüedad. Por lo mismo, SOAP es un formato más pesado, tanto en tamaño como en procesamiento, pues los XML tiene que ser parseado a un árbol DOM, resolver espacios de nombre (namespaces) antes de poder empezar a procesar el documento. Los XML además tienen métodos de validación muy potentes y ampliamente utilizados, a diferencia de JSON, el cual, si tiene forma de validar, pero no son tan potente y su utilización es pobremente utilizada (no significa que en el futuro no se estandarice su uso).

Nótese que, SOAP solo soporta formato XML, por lo que cuando lo que necesitamos es flexibilidad y un performance superior, podemos optar por REST. Tengo otro artículo donde hablo de [XML vs JSON](https://www.oscarblancarteblog.com/2014/07/18/json-vs-xml/) por si quieres profundizar en el tema.

### Que es REST

Por otra parte, tenemos REST, el chico nuevo de la cuadra. REST ya tiene unos años, pero en realidad tiene poco que se le empezó a dar la importancia que hoy tiene. REST es una tecnología mucho más flexible que transporta datos por medio del protocolo HTTP, pero este permite utilizar los diversos métodos que proporciona HTTP para comunicarse, como lo son GET, POST, PUT, DELETE, PATCH y a la vez, utiliza los códigos de respuesta nativos de HTTP (404,200,204,409). REST es tan flexible que permite transmitir prácticamente _**cualquier tipo de datos**_, ya que el tipo de datos está definido por el Header Content-Type, lo que nos permite mandar, XML, JSON, Binarios (imágenes, documentos), Text, etc. que contrasta con SOAP que solo permite la transmisión de datos en formato XML. A pesar de la gran variedad de tipos de datos que podemos mandar con REST, la gran mayoría transmite en JSON por un motivo muy importante, _**JSON es interpretado de forma natural por JavaScript**_, lo que ha hecho que frameworks como Angular y React se aprovechen al máximo, pues pueden enviar peticiones directas al servidor por medio de AJAX y obtener los datos de una forma nativa. Los formularios de HTML pueden ser apuntados a los servicios REST sin ningún problema (por ejemplo).

<figure><img src="https://www.oscarblancarteblog.com/wp-content/uploads/2017/03/rest-services.png" alt="SOAP vs REST"><figcaption></figcaption></figure>

Otra de las grandes ventajas que presenta JSON sobre SOAP es el _**performance**_, ya que los JSON son considerablemente más livianos en peso y mucho más rápido en su procesamiento. Pero como ya vimos, el performance tiene un costo, y es la robustez del mensaje como tal.\
<br>



Ahora bien, desde mi punto de vista REST debería ser utilizado para obtener datos en aplicaciones WEB que funcionan principalmente con el Modelo MVC del lado del cliente, es decir, que todos los procesamientos se realizan desde el navegador y que solo va al backend para obtener o actualiza la base de datos. Otra de las situaciones es cuando tenemos aplicaciones donde los recursos de procesamiento son bajos y con ancho de banda limitado, como sería el caso de las aplicaciones móviles o robótica.

Te invito a que vas mi articulo “[Construir un API REST con NodeJS](https://www.oscarblancarteblog.com/2018/01/11/construir-api-rest-nodejs-primera-parte/)“, en el cual hablo desde cero como implementar un API REST de la forma más simple y clara, utilizando NodeJS y Express. O puedes puedes ver la guia completa de cómo implementar un [API REST con Java](https://www.oscarblancarteblog.com/api-rest-java-jax-rs/) desde cero.

Te puede interesar mi video de Youtube”[**Qué es API REST? – 🚀Y por que es importante aprenderlo 🚀**](https://youtu.be/RbBPuMlgdUU)“

{% embed url="https://youtu.be/RbBPuMlgdUU?si=LuG2Fek_yaUZFsAk" %}

### SOAP vs REST Conclusiones

Como vimos en este análisis, no hay un claro ganador, pues tanto SOAP como REST siguen siendo muy útiles en condiciones diferentes, incluso existen aplicaciones que ya exponente todas sus API’s en SOAP y REST para asegurar que la integración con ellas sea lo más natural posible sin importar la aplicación con la que se estén integrado.

Cabe mencionar que REST ha estado tomando fuerza a una velocidad impresionante y más con la llegada de NodeJS y las bases de datos NoSQL como MongoDB. Sin embargo, el hecho de que REST tome fuerza, no significa que le esté quitando protagonismo a SOAP, pues recordemos que con la llegada del Internet de las cosas (IOT) cada vez se conectan más dispositivos a internet que necesitan ser integrados (una gran oportunidad para REST) y es donde REST está tomando la delantera.

La verdad es que el futuro no se ve claro, pero lo que, si es que a pesar de que REST siga tomando fuerza, SOAP sigue siendo una tecnología muy robusta y extremadamente utilizada por lo que una cosa si es segura, a SOAP todavía le queda un largo camino.

A pesar de todo este análisis, lo importante es tu qué opinas, ¿cuál crees que sea el futuro?, ¿crees que REST poco a poco matara a SOAP? O ¿simplemente SOAP seguirá funcionando a la par con REST?.
