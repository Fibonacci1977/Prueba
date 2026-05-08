# API testing con Postman y SoapUI

Cuando hablamos de herramientas para API testing o pruebas sobre API, casi inmediatamente se nos vienen a la mente Postman y SoapUI, dos de las herramientas más poderosas y reconocidas del mercado. En este post te comparto lo que [Marcos Pérez](https://www.linkedin.com/in/marcos-perez-118978142/) de [Abstracta](http://abstracta.us/) escribió, que ayuda a conocer un poco más sobre estas herramientas de API testing y comparar algunos de sus puntos más fuertes con un enfoque hacia el testing.

Si bien ambas herramientas tienen versiones pagas con interesantes funcionalidades, en este artículo nos concentraremos en las funcionalidades de sus versiones gratuitas. Para más información sobre las versiones pagas recomiendo ingresar en sus páginas oficiales: [https://www.soapui.org/](https://www.soapui.org/) y [https://www.postman.com/](https://www.postman.com/)

### SoapUI

Para comenzar, SoapUI es una herramienta desarrollada en Java, utilizada para pruebas de aplicaciones con arquitectura [SOA](https://es.wikipedia.org/wiki/Arquitectura_orientada_a_servicios) o [REST](https://es.wikipedia.org/wiki/REST). Soporta múltiples protocolos como [SOAP](https://es.wikipedia.org/wiki/Simple_Object_Access_Protocol), [REST](https://es.wikipedia.org/wiki/REST), [HTTP](https://es.wikipedia.org/wiki/HTTP), [JMS](https://es.wikipedia.org/wiki/JMS) y [JDBC](https://es.wikipedia.org/wiki/JDBC). La herramienta cuenta con una versión de código abierto y otra versión paga desarrollada por la compañía SmartBear.

La herramienta SoapUI se creó inicialmente para probar los servicios SOAP. Luego, se extendió a los servicios web RESTful.&#x20;

Para un usuario nuevo puede requerir una mediana curva de aprendizaje ya que la misma en ocasiones no resulta tan intuitiva.

Se puede encontrar documentación en su página oficial: [https://www.soapui.org/](https://www.soapui.org/)

<figure><img src="https://lh3.googleusercontent.com/dESujTod6YEdl98RuZAahWHKM6UIzgV0vShHrqy_DYSV4XE0O-abZrfrsL8fI70rTmlnWloHnH8QZOqRS2xS4SzJxOnPRK7YEYHjZZtSq11a5GKavaobGiPwhUtP2Mhustzrw1o" alt="" height="282" width="557"><figcaption><p>Pantalla principal de SoapUI</p></figcaption></figure>

Como se ve en la imagen, en el módulo ubicado a la izquierda (‘Projects’), el trabajo se organiza en proyectos. Los proyectos conforman el espacio de trabajo o “Workspace”. Un proyecto puede contener distintos tipos de pruebas, entre ellas: pruebas funcionales, de carga o simulaciones de servicios necesarios (Mocks).

SoapUI ofrece dos formatos de proyecto: ‘proyectos independientes’ (Standalone Projects) y ‘proyectos compuestos’ (Composite Projects). Los ‘proyectos independientes’ se almacenan como un archivo XML único que contiene todos los artefactos del proyecto. Los ‘proyectos compuestos’ permiten a varias personas trabajar al mismo tiempo de forma colaborativa.

Los proyectos dentro de SoapUI también se pueden clasificar en tipos:

* [Proyecto SOAP.](https://www.soapui.org/soapui-projects/soapui-projects.html#2-1-SOAP-Projects)
* [Proyecto REST.](https://www.soapui.org/soapui-projects/soapui-projects.html#2-2-REST-Projects)
* [Proyecto genérico.](https://www.soapui.org/soapui-projects/soapui-projects.html#2-3-Generic-Projects)

Esta categorización indica el tipo principal del servicio probado. Sin embargo, se pueden combinar manualmente los tipos de servicio en cualquier proyecto que se cree.

**Proyecto SOAP:**

Los proyectos SOAP se pueden crear a partir de un archivo [WSDL](https://es.wikipedia.org/wiki/WSDL) o desde una llamada de servicio particular. Estos proyectos se pueden utilizar para probar todos los aspectos de los servicios SOAP, crear pruebas funcionales, automatizadas, de carga, de concurrencia, etc.

**Proyecto REST:**

Los proyectos REST se pueden crear a partir de un archivo [WADL ](https://es.wikipedia.org/wiki/Web_Application_Description_Language)o directamente del URI y sus parámetros. Se pueden utilizar estos proyectos para probar los servicios RESTful, crear varias solicitudes y comprobar la información que recibe, probar una multitud de métodos y operaciones, etc.

**Proyectos Genéricos:**

Los proyectos genéricos son proyectos multiuso para servicios con interfaces y métodos variados. Pueden combinar pruebas que se creen para servicios REST y SOAP, con un enfoque data driven testing, mocks y todas las funciones que proporciona SoapUI.

### Postman

Postman es una herramienta que ayuda en todo el proceso de desarrollo de APIS:Se utiliza principalmente para testing. Gracias a esta herramienta, además de testear y consumir APIS, podremos monitorear, documentar, simular y escribir pruebas automatizadas sobre las mismas.

La herramienta Postman está diseñada principalmente para probar las API del tipo REST. Posee una interfaz de usuario muy fácil y agradable. Ofrece una gran cantidad de funcionalidades, por ejemplo permite realizar cualquier tipo de llamada a la API (REST, SOAP o simplemente HTTP) e inspeccionar fácilmente las respuestas. También las respuestas se pueden analizar en función del tipo de respuesta (JSON, XML o HTML).

Se puede encontrar documentación en su página oficial: [https://www.postman.com/](https://www.postman.com/)

<figure><img src="https://lh5.googleusercontent.com/oJLEBKAz8-zZ6Hy204vGRC4dpas2fu17yELpds3EBIsONEUJ1zbX2Om17Qu74iv6cujYmAGtqcmWLl2t-rXQZIB3Fxpo7STEi3cXcqEJFwKk2ArHpFtWB13hEeN8vWOv6BduqM0" alt="" height="321" width="564"><figcaption><p>Pantalla principal de Postman</p></figcaption></figure>

Como se puede observar en la imagen, a diferencia de SoapUI, en Postman se trabaja con colecciones de API. Estas colecciones funcionan como agrupadores de peticiones, lo que permite ordenar recursos y servicios y probar cada petición de una forma más rápida y fácil.

### Ventajas y desventajas

**Ventajas de Postman:**

* Permite la colaboración entre miembros del equipo.
* Tiene una interfaz más intuitiva y atractiva.
* Posee extensión para Google Chrome,  por lo tanto no es necesario instalar la aplicación de escritorio.
* Como ya mencionamos en la descripción, tiene una opción muy interesante, que son las colecciones, que funciona básicamente como una base de datos de peticiones.
* Es extensible y se puede integrar con otras herramientas, por ejemplo ejecutando las suites de prueba desde un motor  de CI/CD.
* Permite agregar scripts en lenguaje Javascript para agregar validaciones, configurar y/o automatizar pruebas (esto se realiza directamente en la petición).

**De SoapUI se pueden destacar los siguientes aspectos:**      &#x20;

* Es una aplicación muy completa, con muchas funcionalidades, con lo cual puede llegar a ser un poco complicada de utilizar para la función que queramos en cada momento.
* Tiene una mejor integración que Postman para trabajar con el protocolo SOAP (ya que inicialmente estaba pensada para eso).
* Es un proyecto más maduro y tiene más tiempo en el mercado.
* Es una aplicación más orientada a testing y no simplemente a consumir una API, documentarla y publicarla. Permite estructurar las pruebas en test suites, test cases y test steps.
* La ejecución de pruebas se puede integrar con herramientas tales como: Maven, motores de CI/CD, etc.
* Permite agregar scripts en lenguaje Groovy. Esto permite agregar validaciones, configurar y/o automatizar pruebas.

### ¿Cómo comenzar con API testing?

En mi opinión si estás por empezar a realizar pruebas sobre API y contás con poco tiempo recomendaría Postman, ya que requiere un menor tiempo de aprendizaje. Sin embargo, si lo que se busca es armar un proyecto a mediano o largo plazo recomendaría SoapUI ya que ofrece más  opciones y una mejor organización del proyecto.

Si aún no te decides por una te invito a probar ambas para descubrir cuál satisface mejor tus necesidades.
