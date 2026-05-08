# Tutorial de pruebas de carga de postman: WDSL, JSON y API

Las API están integradas en muchos de [los servicios web utilizados hoy en día](https://www.loadview-testing.com/web-application-testing-tools-load-stress/), lo que permite a los sistemas enviar y comunicar varias piezas de información de ida y vuelta. Como tales, son un poderoso vínculo entre los servicios críticos y los usuarios. Y como con cualquier parte importante de un sistema, es necesario probarlos. Utilizando soluciones de prueba de API de terceros, o Postman, podemos hacer pruebas manuales y automatizadas (incluida [la supervisión de API).](https://www.loadview-testing.com/es/mas-informacion-sobre-las-pruebas-de-carga/pruebas-de-carga-de-api/) API significa [Interfaz de programación de aplicaciones.](https://www.loadview-testing.com/api-testing/) Es una interfaz de software a software. Con las API, las aplicaciones conversan entre sí sin intervención del cliente. Pero con miles de API disponibles, Postman entra en escena para crear, probar, compartir y administrar estas API haciendo que el uso de la API sea eficiente y menos tedioso. Este artículo le ayudará a comprender qué es Postman, qué son las colecciones de Postman, las características y beneficios destacados, y cómo puede configurar pruebas de carga para colecciones de Postman y su integración con canalizaciones de CI / CD con [LoadView](https://www.loadview-testing.com/es/).Pruebas de carga postman con LoadView

Explore nuestra solución de pruebas de carga o lea a continuación los pasos sobre cómo usar Postman con LoadView

[Prueba de carga postman](https://www.loadview-testing.com/es/productos/postman/)

**What is Postman for API testing?**

**Can we use Postman for API testing?**

**How do I test a Postman POST request?**

**Why do we use Postman tool?**

**What are the methods used in Postman?**

### ¿Qué es Postman? <a href="#que-es-postman" id="que-es-postman"></a>

Postman es una popular herramienta cliente de API que facilita a los equipos de desarrollo la creación, el uso compartido, la prueba y la documentación de las API. Proporciona una [experiencia de usuario](https://www.loadview-testing.com/es/blog/por-que-su-estrategia-de-experiencia-de-usuario-debe-incorporar-pruebas-de-carga/) perfecta que ayuda a llegar a los puntos finales de la API al crear rápidamente solicitudes según la especificación de la API y diseccionar los diversos parámetros de respuesta, como el código de estado, los encabezados y el cuerpo de respuesta real. Podemos aprovechar estas características para realizar pruebas continuas y automatizadas. Se utiliza como una herramienta complementaria para desarrollar, documentar y probar contra una API y proporciona una [interfaz de usuario](https://www.loadview-testing.com/es/blog/pruebas-de-carga-de-back-end-frente-a-la-interfaz-de-usuario-web/) para realizar solicitudes de servidor de API REST (Representational State Transfer) y muestra la respuesta de los servidores. Postman es una herramienta de desarrollo de API utilizada en el ciclo de vida del desarrollo de software:

* Desarrollo de API
* Pruebas de API
* Documentación de la API

Postman no solo nos proporciona un entorno para trabajar con APIs, sino que también se puede utilizar para solicitar páginas web como un navegador. Ingrese la URL en la barra de direcciones y presione enviar para ver la respuesta HTML (HyperText Markup Language). Postman también puede ayudar a agregar [scripts](https://www.loadview-testing.com/es/blog/como-ejecutar-pruebas-de-rendimiento-de-javascript-la-guia-definitiva/) antes de que el usuario envíe la solicitud y después de obtener la respuesta. Podemos almacenar cada solicitud en una colección, que más adelante se puede utilizar para ejecutar todas las solicitudes en orden. Sin embargo, una cosa que Postman no es es una [herramienta de prueba de rendimiento](https://www.loadview-testing.com/es/). Si bien podrá ejecutar pruebas pequeñas y controladas que le brinden tiempos de respuesta de la API, no es lo mismo que ejecutar una prueba en condiciones del mundo real. No pone a la API bajo ningún tipo de estrés real, por lo que no es un buen indicador de cómo responderá su API cuando los usuarios reales estén involucrados. Para eso, necesita una [solución](https://www.loadview-testing.com/es/mas-informacion-sobre-las-pruebas-de-carga/lo-que-hace-que-una-plataforma-de-pruebas-de-carga-excepcional/) como LoadView, de la que hablaremos con más detalle más adelante en este artículo.

<img src="https://www.loadview-testing.com/wp-content/uploads/Status-Code-Weekly-200.png" alt="Interfaz de postman" height="674" width="1342">

### ¿Qué son las pruebas de API? <a href="#que-son-las-pruebas-de-api" id="que-son-las-pruebas-de-api"></a>

En las pruebas de API, usamos herramientas dedicadas para enviar llamadas al servidor que hospeda la API y recuperar la respuesta. El objetivo de las pruebas de API es confirmar la ejecución correcta y validar si la API está obteniendo, guardando o actualizando recursos según lo previsto.

Si sabemos que se supone que la API debe realizar una acción en particular, como actualizar datos, obtener datos, eliminar datos, realizar un cambio en los datos, las pruebas deben verificar [los resultados](https://www.loadview-testing.com/es/mas-informacion-sobre-las-pruebas-de-carga/pruebas-de-rendimiento-basadas-en-objetivos/) de esas acciones. ¿Se comporta de la misma manera que se supone que debe ser? ¿Qué hay de cuando no se supone que suceda? ¿Y son los resultados los que esperarías que fuera? Las pruebas de API suelen ser pruebas de cuadro negro, pero en la medida en que tenemos acceso a los resultados de las acciones de la API de antemano y sabemos la respuesta esperada que debe validarse.

&#x20;

#### Pruebas de API: Pruebas funcionales frente a pruebas de carga <a href="#pruebas-de-api-pruebas-funcionales-frente-a-pruebas-de-carga" id="pruebas-de-api-pruebas-funcionales-frente-a-pruebas-de-carga"></a>

Como mencionamos brevemente anteriormente, las pruebas funcionales, o pruebas de caja negra, se ocupan principalmente de probar funciones básicas contra un conjunto de especificaciones y observar si funcionan o no. Antes de que las API se puedan mover a través del ciclo de desarrollo y probarse más a fondo, es importante que las funcionalidades básicas de la API funcionen. Si los desarrolladores pasan de las pruebas funcionales a las pruebas de carga sin garantizar que las funciones básicas se hayan probado correctamente, se eliminarán las [pruebas de carga](https://www.loadview-testing.com/es/pruebas-de-carga/) y los resultados. Los resultados de las pruebas funcionales son simplemente observar si algo funcionó o no.

Por otro lado, las pruebas de carga son como las pruebas funcionales, pero la diferencia es que las pruebas de carga se establecen para probar cómo esas funcionalidades resisten a un gran número de [usuarios simultáneos](https://www.loadview-testing.com/es/blog/pruebas-de-carga-http-simultaneo-frente-a-navegadores-simultaneos-frente-a-usuarios-simultaneos/) o carga. Los resultados de las pruebas de carga incluyen comprender cómo responden y funcionan esos puntos de conexión de API bajo carga.

&#x20;

#### Características de Postman <a href="#caracteristicas-de-postman" id="caracteristicas-de-postman"></a>

Aparentemente no hay fin a la gran cantidad de características que Postman ofrece a los usuarios. Desde características como la API de Postman y los controles de flujo de trabajo hasta monitores integrados para pruebas de regresión, la herramienta tiene cubiertas las pruebas de API. Sin embargo, en un nivel alto hay un puñado de características principales que cada [probador de API necesitará](https://www.loadview-testing.com/es/productos/). Echemos un vistazo más de cerca a estas características.

**Solicitudes de importación**

Postman proporciona una función de importación, donde podemos pegar texto CURL sin procesar y convertirlo en una solicitud formateada con detalles como URL de solicitud, encabezados, cuerpo de solicitud, parámetros de consulta y tokens de autorización.

**Soporte de Protocolo Múltiple y Tecnología**

La función de cliente DE la API de Postman nos permite enviar solicitudes REST, SOAP, WSDL y [GraphQL](https://www.loadview-testing.com/es/blog/pruebas-de-carga-graphql-web-api/) .

**Escribir casos de prueba**

Podemos crear casos de prueba que ejecuten API agregadas y que puedan ayudar en la validación de respuestas con la afirmación de respuestas JSON/XML y validaciones de código de respuesta.

**Colecciones**

Postman nos ayuda a crear colecciones que ayudan a segregar las API con carpetas Estructura para diferentes proyectos. Proporciona compatibilidad para ejecutar Collection, que finalmente ejecutará todas las API que forman parte de la colección.

**Validación de esquema JSON**

Puede utilizar el esquema JSON (JavaScript Object Notation) para definir la estructura de sus solicitudes y respuestas. Ayuda a limpiar y estructurar el contenido JSON, lo que facilita su comprensión y lectura en Postman.

**Usar variables dinámicas y de entorno**

Podemos crear variables en Postman y en diferentes entornos, las mismas variables pueden tener diferentes valores asignados para el entorno seleccionado. Esto es útil mientras trabajamos con las mismas API, pero con varios entornos en el mundo real.

**Convertir API a código**

Postman permite que la solicitud de API se convierta en código en todos los lenguajes prominentes como JavaScript, Golang, Java, PHP, Python y muchos más.

&#x20;

#### Beneficios del cartero <a href="#beneficios-del-cartero" id="beneficios-del-cartero"></a>

Aquellos que usan Postman de forma regular estarán familiarizados con los beneficios a continuación. Sin embargo, esta no es una lista exhaustiva de capacidades y características de esta herramienta de prueba de API. Veamos algunos de los principales beneficios de Postman.

**Automatice las pruebas de API**

Este es el primer y más obvio beneficio de Postman. La herramienta le permite automatizar las pruebas de API e integrar la colección con canalizaciones de CI/CD. Y como mencionamos anteriormente, las pruebas de API utilizan formatos JSON o XML, que son independientes del marco de aplicación o los [protocolos que usan los desarrolladores](https://www.loadview-testing.com/es/blog/pruebas-de-carga-de-sitios-web-basadas-en-protocolos-un-enfoque-de-pruebas-tradicional/). No importa qué marco use (Python, JavaScript, Ruby, etc.), Postman lo admite. Puede automatizar pruebas unitarias, pruebas de integración, pruebas de regresión y [pruebas](https://www.loadview-testing.com/es/blog/pruebas-de-carga-de-ci-cd-implementacion-de-aplicaciones-optimizadas-para-el-rendimiento/) simuladas.

**Compatible con la plataforma y el sistema operativo**

Postman está disponible para Mac OS X, Windows y Linux. La aplicación web Postman también está disponible y optimizada para [Chrome](https://www.loadview-testing.com/es/blog/pruebas-de-carga-basadas-en-navegador-chrome/), Firefox, Edge y Safari.

**Informes de pruebas de cartero**

Proporciona un informe de prueba que nos ayuda con el seguimiento de los datos a través del generador de solicitudes y puede generar informes HTML para las ejecuciones de prueba.

**Integraciones**

Postman proporciona soporte técnico y se puede integrar fácilmente con todas las principales herramientas para desarrolladores como GitHub, Slack, Dropbox y GitLab.

**Precios**

Todas las principales funcionalidades de Postman son gratuitas. Puede obtener todos los beneficios anteriores de forma gratuita. También hay planes de pago para Postman Pro y Postman Enterprise para pequeñas y grandes empresas.

&#x20;

### Alternativas a Postman <a href="#alternativas-a-postman" id="alternativas-a-postman"></a>

#### Swagger <a href="#swagger" id="swagger"></a>

<img src="https://www.loadview-testing.com/wp-content/uploads/swagger_logo.svg" alt="logotipo swagger" height="117.64" width="408.77">

&#x20;

&#x20;

Swagger es una especificación de API de código abierto, es como WSDL para API REST, donde se define la estructura de las [API REST](https://www.loadview-testing.com/es/blog/la-ultima-hoja-de-trucos-para-rest-soap-api-testing/) (URL de puntos finales, modelos de entrada / salida, [esquema de autenticación](https://www.loadview-testing.com/es/blog/pruebas-de-carga-de-api-web-que-requieren-autenticacion/), etcétera). El archivo de especificación se basa en JSON y la extensión del archivo es JSON o YAML. Algunos de los aspectos más destacados de Swagger son:

* De código abierto y gratuito, sin embargo, puede ser difícil aprender o encontrar recursos para problemas.
* Swagger representa las API dentro del explorador.
* Puede generar automáticamente documentación a partir de la creación de sus servicios.

#### Soapui <a href="#soapui" id="soapui"></a>

<img src="https://www.loadview-testing.com/wp-content/uploads/SoapUI-logo.png" alt="Logotipo de SoapUI" height="139" width="416">

&#x20;

&#x20;

&#x20;

SoapUI permite a los usuarios probar rápida y fácilmente las API rest y SOAP, ya que la herramienta se creó específicamente para probar las API. SoapUI ayuda a probar combinaciones complicadas de servicios web como RESTful, SOAP, JSON y AMF. Sin embargo, debe utilizar WSDL para probar servicios web. Además, para integrar la automatización, se requiere una gran cantidad de [scripting](https://www.loadview-testing.com/es/caracteristicas/secuencias-de-comandos-de-apuntar-y-hacer-clic/), y para los usuarios que no han tenido esa experiencia, puede ser difícil y llevar mucho tiempo. Algunos de los aspectos más destacados de SoapUI son:

* La funcionalidad de apuntar y hacer clic ayuda a facilitar la usabilidad DE JSON y XML.
* Carga datos desde Excel, archivos, bases de datos, etc.
* Reutilice los casos de prueba funcionales como pruebas de carga.
* Se integra con plataformas de administración de API de terceros, admite REST, SOAP, JMS e IoT, etc.

#### &#x20;<a href="#undefined" id="undefined"></a>

#### Integrar pruebas de recogida de carteros en la canalización de CI/CD <a href="#integrar-pruebas-de-recogida-de-carteros-en-la-canalizacion-de-ci-cd" id="integrar-pruebas-de-recogida-de-carteros-en-la-canalizacion-de-ci-cd"></a>

La integración continua (CI) es una práctica de desarrollo que requiere que los desarrolladores combinen código regularmente en un repositorio compartido. Implica el proceso de automatización de la compilación y pruebas de aplicaciones cada vez que se confirma un nuevo cambio en el código fuente. El desarrollo continuo se puede explicar como una secuencia de pasos que deben realizarse en secuencia para permitir que la aplicación se ejecute en un servidor especializado y cumplir su caso de uso de atender las solicitudes de usuario.

### &#x20;<a href="#id-1" id="id-1"></a>

### Cargando colecciones de carteros usando LoadView <a href="#cargando-colecciones-de-carteros-usando-loadview" id="cargando-colecciones-de-carteros-usando-loadview"></a>

Cada vez que probamos una aplicación back-end, probar la funcionalidad es una parte estándar del proceso para asegurarnos de que las cosas funcionen como habíamos previsto que funcionen. Eso está bien, pero no para el mundo real. Sus aplicaciones serán utilizadas por muchos, si no cientos o miles de usuarios al mismo tiempo, por lo que también debemos realizar pruebas de rendimiento para ver qué tan bien resisten ese [tráfico](https://www.loadview-testing.com/es/blog/planificacion-del-aumento-del-trafico-web-planificacion-de-la-capacidad-y-pruebas-de-carga/). Necesitamos comparar y validar la aplicación con cada cambio de aplicación. Como hemos visto la visión general de Postman, sus características y cómo podemos configurar la estrategia de prueba para las pruebas funcionales de API, tendríamos que entender las herramientas que pueden ayudar a probar la aplicación.

En los casos en que estemos usando Postman para probar la funcionalidad de la API web y queremos generar una prueba de carga a partir de las colecciones de llamadas de API que tenemos, podemos optar por una herramienta de pruebas de carga especializada como LoadView. LoadView proporciona pruebas de carga reales basadas en navegador para API, así como aplicaciones web (externas e internas) y [sitios web y servidores](https://www.loadview-testing.com/es/la-guia-definitiva-para-las-pruebas-de-rendimiento-del-sitio-web/).

#### Configuración de la prueba <a href="#configuracion-de-la-prueba" id="configuracion-de-la-prueba"></a>

Examinaremos paso a paso cómo configurar una prueba de carga de aplicaciones web para una colección Postman.

#### Pruebas de la API de Postman de LoadView: Paso 1 <a href="#pruebas-de-la-api-de-postman-de-loadview-paso-1" id="pruebas-de-la-api-de-postman-de-loadview-paso-1"></a>

Antes de empezar, tendríamos que exportar la Colección Des postman. Podemos elegir la opción de obtener el vínculo Público y podemos importarlo fácilmente a LoadView (Nota: Asegúrese de que la colección Postman utiliza variables locales solo porque las variables de entorno no se almacenan en la colección).

<img src="https://www.loadview-testing.com/wp-content/uploads/Postman-Collection-Export.png" alt="Exportación de la colección Postman" height="446" width="777">

#### Pruebas de la API de Postman de LoadView: Paso 2 <a href="#pruebas-de-la-api-de-postman-de-loadview-paso-2" id="pruebas-de-la-api-de-postman-de-loadview-paso-2"></a>

Abra la plataforma LoadView y seleccione _Crear nueva_ prueba de carga.

#### Pruebas de la API de Postman de LoadView: Paso 3 <a href="#pruebas-de-la-api-de-postman-de-loadview-paso-3" id="pruebas-de-la-api-de-postman-de-loadview-paso-3"></a>

Aquí verá los distintos tipos de pruebas de carga que están disponibles en LoadView: aplicaciones web, sitios web y API. Para nuestro caso de uso, seleccionaremos la opción Postman Collection para iniciar las pruebas de API.

<img src="https://www.loadview-testing.com/wp-content/uploads/Load-testing-type-Postman.png" alt="Tipo de prueba de carga Postman" height="406" width="1024">

#### Pruebas de la API de Postman de LoadView: Paso 4 <a href="#pruebas-de-la-api-de-postman-de-loadview-paso-4" id="pruebas-de-la-api-de-postman-de-loadview-paso-4"></a>

Se abrirá una nueva ventana y aquí es donde tendremos que importar la colección Postman exportada y hacer clic en _Crear dispositivo._

<img src="https://www.loadview-testing.com/wp-content/uploads/Postman-Collection-Request.png" alt="Solicitud de recogida de carteros" height="537" width="692">

#### Pruebas de la API de Postman de LoadView: Paso 5 <a href="#pruebas-de-la-api-de-postman-de-loadview-paso-5" id="pruebas-de-la-api-de-postman-de-loadview-paso-5"></a>

Una vez que hayamos creado con éxito un dispositivo, veríamos la pantalla _Escenario de prueba,_ donde podemos establecer _el tipo de carga,_&#x71;ue diferiría en función del objetivo de nuestra prueba.

* **Curva basada en carga**. Esto es para ejecutar pruebas de carga con un número conocido de usuarios y aumentar el tráfico después de configurar el tiempo de calentamiento.
* **Curva basada en objetivos**. Esta configuración de prueba se utiliza cuando estamos buscando transacciones deseadas por segundo para nuestra API específica y queremos escalar a los usuarios simultáneos deseados.
* **Curva dinámica basada en**. Este conjunto le proporciona elegir valores dinámicos en número de usuarios, usuarios máximos y duración de la prueba, y se puede cambiar, en tiempo real, durante la prueba.

<img src="https://www.loadview-testing.com/wp-content/uploads/Postman-Collection-Load-Types.png" alt="Tipos de carga de recogida de carteros" height="557" width="620">

#### Pruebas de la API de Postman de LoadView: Paso 6 <a href="#pruebas-de-la-api-de-postman-de-loadview-paso-6" id="pruebas-de-la-api-de-postman-de-loadview-paso-6"></a>

Una vez que hemos creado un escenario de prueba con una lista de todas las API, ahora podemos ejecutar pruebas de carga y esfuerzo para nuestras API. Después de completar correctamente la ejecución de la prueba de carga, se le proporcionarán [informes, paneles y métricas](https://www.loadview-testing.com/es/caracteristicas/informes-de-rendimiento/) que muestran cómo se realizó nuestra API y los sistemas bajo carga.

&#x20;

### Integración de pruebas de carga de recogida de carteros con Jenkins <a href="#integracion-de-pruebas-de-carga-de-recogida-de-carteros-con-jenkins" id="integracion-de-pruebas-de-carga-de-recogida-de-carteros-con-jenkins"></a>

Como hemos analizado cómo podemos integrar y ejecutar pruebas de carga de recopilación de Postman mediante LoadView, podemos agregar estas pruebas como parte de CI/CD para obtener comentarios y resultados de rendimiento regulares. LoadView también proporciona integración con Jenkins, lo que ayuda a realizar pruebas de esfuerzo en sitios web, aplicaciones web y API con conexiones simultáneas en exploradores reales desde una nube totalmente administrada. Cualquier nueva actualización o características adicionales también se pueden probar con el complemento LoadView para Jenkins.

Echemos un vistazo a los pasos utilizados para el escenario de prueba de colección Postman creado anteriormente en LoadView y su integración con Jenkins.

**Paso 1**. Para integrar las pruebas con Jenkins, estaríamos usando el mismo escenario de prueba postman creado anteriormente.

**Paso 2**. Cree un UID único. Esto se utilizará como un token de seguridad para integrarse en Jenkins. Copie el UID de integración.

<img src="https://www.loadview-testing.com/wp-content/uploads/Postman-Jenkins-Integration-UID-1024x347.png" alt="Postman Jenkins Integración UID" height="347" width="1024">

**Paso 3**. Test Scenario ID para nuestra colección Postman se puede encontrar en la página de configuración de escenarios o en la página _historial de_ pruebas (Test Manager el menú acciones de > prueba > History).

<img src="https://www.loadview-testing.com/wp-content/uploads/Postman-Collection-Test-History.png" alt="Historial de pruebas de la colección de carteros" height="159" width="544">

#### &#x20;<a href="#id-2" id="id-2"></a>

#### LoadView Plugin en Jenkins <a href="#loadview-plugin-en-jenkins" id="loadview-plugin-en-jenkins"></a>

Para configurar el complemento LoadView, siga estos pasos:

1. Inicie sesión en su cuenta de Jenkins.
2. En Jenkins, vaya a _Credentials_ > _Add Credentials_ > _LoadView Security Token (UID)_. Configure y valide las credenciales.

* **Tipo**. Token de seguridad (UID) de LoadView.
* **Alcance**. Seleccione **Global**.
* **ID**. Deje el valor predeterminado o especifique un identificador único.
* **Descripción**. Especifique una descripción única para distinguir las credenciales.
* **UID**. Pegue el UID de la API web de pruebas de carga desde su cuenta de LoadView. Una vez agregado el UID, haga clic en **Validar UID** para asegurarse de que Jenkins puede tener acceso a la API LoadView.

3. A continuación, seleccione un trabajo y haga clic en **Configurar**.

<img src="https://www.loadview-testing.com/wp-content/uploads/Jenkins-LoadView-Security-Token-1024x569.png" alt="Ficha de seguridad De Jenkins LoadView" height="569" width="1024">

4. Vaya a **Crear** > **acciones posteriores a la compilación** > Agregar escenario de prueba de carga LoadView-Run de acción posterior a **la compilación** > **LoadView-Run load test scenario**. Especifique la configuración de LoadView Stress Test para la compilación:

* **Credenciales**. Seleccione la clave de API con la descripción.
* **ID de escenario**. Pegue el identificador de escenario de prueba que desea usar en la compilación. Copie el identificador de la página del escenario en LoadView.
* **Umbral de error**. Especifique un porcentaje aceptable de sesiones con errores que se produjeron durante la prueba (no se pudo acceder al recurso de destino, no se han encontrado palabras clave/imagen, etc.). Si el porcentaje de sesiones de error es mayor que el valor especificado, la compilación se marcará como un _error_ en Jenkins.
* **Tiempo promedio**. Especifique un límite para un [tiempo de respuesta medio](https://www.dotcom-monitor.com/wiki/knowledge-base/average-response-time-calculation/) medido durante la ejecución de la prueba. Si se alcanza el límite, la compilación se marcará como un _error_ en Jenkins.

5. Haga clic en **Guardar**.

#### Ver los resultados de las pruebas de LoadView <a href="#ver-los-resultados-de-las-pruebas-de-loadview" id="ver-los-resultados-de-las-pruebas-de-loadview"></a>

Por último, hemos integrado con éxito nuestra colección Postman con Jenkins utilizando LoadView como plataforma. Mientras se ejecuta nuestra prueba de esfuerzo, el estado se muestra en la salida de la **consola de** Jenkins en modo en tiempo real.

<img src="https://www.loadview-testing.com/wp-content/uploads/Postman-Jenkins-Console-Output-1024x569.png" alt="Salida de la consola de Postman Jenkins" height="569" width="1024">

<img src="https://www.loadview-testing.com/wp-content/uploads/Postman-Jenkins-LoadView-Test-Performance-Results-1024x569.png" alt="Resultados del rendimiento de las pruebas del cartero Jenkins LoadView" height="569" width="1024">

### &#x20;<a href="#id-3" id="id-3"></a>

### Monitoreo de la prueba de recogida de carteros <a href="#monitoreo-de-la-prueba-de-recogida-de-carteros" id="monitoreo-de-la-prueba-de-recogida-de-carteros"></a>

LoadView es una parte de las muchas soluciones dentro de la plataforma Dotcom-Monitor. Dotcom-Monitor también proporciona herramientas de monitoreo fáciles para nuestras colecciones Postman. Si tenemos una colección de pruebas de integración utilizadas para las pruebas internas de API con Postman, y también queremos configurar pruebas para que se ejecuten desde fuera de la red local, podemos cargar las pruebas de Postman en Dotcom-Monitor. Usando la tarea Dotcom-Monitor Postman Collection podemos crear pruebas de monitoreo automatizadas con [alertas sobre errores.](https://www.dotcom-monitor.com/wiki/knowledge-base/getting-started-with-alerts/) Podemos especificar ubicaciones de supervisión, un [programador de supervisión,](https://www.dotcom-monitor.com/wiki/knowledge-base/schedules/) [filtros](https://www.dotcom-monitor.com/wiki/knowledge-base/filters/) y configurar [informes basados](https://www.dotcom-monitor.com/wiki/knowledge-base/reports-available/) en los resultados de supervisión.

La colección de solicitudes HTTP agregadas se ejecutará repetidamente con la frecuencia definida para realizar la secuencia de llamadas a la API web de destino. Con eso tendremos las aserciones que se especificaron para las solicitudes en Postman que ayudarán a verificar las respuestas de la API. Si no se cumple alguna condición establecida por aserciones, la tarea se marcará como errónea.

### Pruebas de carga y seguridad de Postman <a href="#pruebas-de-carga-y-seguridad-de-postman" id="pruebas-de-carga-y-seguridad-de-postman"></a>

En el mundo de las pruebas de API, la seguridad es una preocupación primordial.\
Postman, reconocido por sus completas capacidades de prueba, también ofrece funciones sólidas para las pruebas de seguridad de API.\
Esta sección profundiza en cómo se puede utilizar Postman para fortalecer el aspecto de seguridad de las API, asegurando que no solo sean funcionales, sino también seguras contra posibles amenazas.

**Protocolos de seguridad y métodos de autenticación**

Postman maneja hábilmente varios protocolos de seguridad y métodos de autenticación, cruciales para probar las API en diferentes entornos.\
Es compatible con la autenticación básica, OAuth 1.0 y 2.0, tokens al portador y más, lo que permite a los evaluadores replicar escenarios del mundo real con precisión.\
Esta versatilidad es vital para probar las API que requieren autenticación, lo que garantiza que solo los usuarios autorizados tengan acceso.

**Pruebas de vulnerabilidades comunes**

Las API suelen ser susceptibles a una serie de vulnerabilidades de seguridad.\
Postman ayuda a identificar problemas comunes, como la inyección de código SQL, las secuencias de comandos entre sitios (XSS) y el acceso no autorizado a los datos.\
Al crear casos de prueba específicos dentro de Postman, los evaluadores pueden simular patrones de ataque y evaluar la resistencia de la API contra estas vulnerabilidades.

**Automatización de las pruebas de seguridad**

La automatización de las pruebas de seguridad es esencial para la integración continua y las canalizaciones de entrega.\
Postman facilita la automatización de las pruebas de seguridad, lo que permite a los equipos integrar estas pruebas en sus ciclos de desarrollo regulares.\
Este enfoque garantiza que las evaluaciones de seguridad no sean comprobaciones puntuales, sino una parte continua del proceso de desarrollo y mantenimiento de la API.

**Generación y análisis de informes de seguridad**

La capacidad de Postman para generar informes detallados después de las pruebas es invaluable.\
Estos informes proporcionan información sobre posibles fallos de seguridad, ofreciendo una visión completa de la postura de seguridad de la API.\
El análisis de estos informes ayuda a los equipos a priorizar las correcciones y mejora la seguridad general de la aplicación.

La incorporación de Postman en la estrategia de pruebas de seguridad no solo agiliza el proceso de pruebas, sino que también eleva los estándares de seguridad de las API.\
Esta integración es crucial en el panorama de desarrollo actual, donde la seguridad es tan crítica como la funcionalidad y el rendimiento.

### Pruebas de carga de su API con Postman: Pensamientos finales <a href="#pruebas-de-carga-de-su-api-con-postman-pensamientos-finales" id="pruebas-de-carga-de-su-api-con-postman-pensamientos-finales"></a>

La comunidad de desarrollo tiene opiniones muy variadas sobre las API de prueba. Hemos visto cómo Postman nos ayuda por completo en la creación, mantenimiento y prueba de API con tanta facilidad. También vimos una guía paso a paso [sobre cómo podemos simular](https://www.loadview-testing.com/es/mas-informacion-sobre-las-pruebas-de-carga/) la recopilación de Postman de pruebas de carga de usuarios simultáneos mediante LoadView. Por último, hemos analizado cómo podemos automatizar este paso utilizando la integración de Jenkins con LoadView. Las herramientas necesarias para destacar estas aplicaciones se han simplificado últimamente y proporciona una inmensa ayuda para probar sistemas complejos que dependen de aplicaciones internas y externas. Nos ayuda a detectar los cuellos de botella y los problemas con mayor claridad.

En LoadView, nuestro objetivo es ser su socio experto para todo lo relacionado con las pruebas de carga, en cada etapa de desarrollo y en cualquier nivel de complejidad. Entendemos que las pruebas de carga pueden ser una tarea, por lo que trabajamos incansablemente para facilitar el proceso para que usted y su equipo de desarrollo puedan integrar el proceso de prueba de carga en sus prácticas de DevOps existentes y dedicar la mayor parte de su tiempo y recursos a lo que importa, es decir, mejorar sus sitios web y aplicaciones web para sus usuarios. Al eliminar los dolores de cabeza de las pruebas de carga, LoadView ayuda a mejorar todo su proceso de desarrollo y, en última instancia, la experiencia de sus usuarios.

Nuestro equipo de expertos está disponible para apoyarlo a usted y a su equipo a medida que desarrolla y mejora su estrategia de pruebas de carga, y encontrará que nuestra plataforma es intuitiva y fácil de usar incluso para usuarios no técnicos. Ofrecemos pruebas reales del navegador, secuencias de comandos de apuntar y hacer clic, e informes completos y legibles que eliminan las conjeturas de las pruebas de carga y permiten una colaboración efectiva entre las funciones del desarrollador. También trabajamos para mantenernos a la vanguardia de la industria de pruebas de carga y ofrecer a nuestros usuarios herramientas nuevas y refinadas para satisfacer las demandas cambiantes del panorama digital en constante evolución. LoadView es su plataforma completa de pruebas de carga, ahora y para el futuro.

**Comience a probar la carga de sus API hoy mismo con LoadView.** [**Regístrese para la prueba gratuita** ](https://userauth.dotcom-monitor.com/Account/LoadView-FreeTrialSignUp)**y reciba pruebas de carga gratuitas. O** [**regístrese para una de nuestras demostraciones privadas**](https://www.loadview-testing.com/es/demo/) **con uno de nuestros ingenieros de rendimiento.** Nuestro ingeniero lo guiará a través de la plataforma completa de LoadView, y le mostrará cómo integrar LoadView en las colecciones de Postman y automatizar los pasos con Jenkins.
