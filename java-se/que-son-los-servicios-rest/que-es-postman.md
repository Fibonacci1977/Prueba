# Qué es Postman

Tabla de contenidos

* [Qué es Postman](https://openwebinars.net/blog/que-es-postman/#qu%C3%A9-es-postman)
* [Para qué sirve Postman](https://openwebinars.net/blog/que-es-postman/#para-qu%C3%A9-sirve-postman)
* [Métodos más utilizados y posibles errores](https://openwebinars.net/blog/que-es-postman/#m%C3%A9todos-m%C3%A1s-utilizados-y-posibles-errores)
* [Primeros pasos con Postman](https://openwebinars.net/blog/que-es-postman/#primeros-pasos-con-postman)
* [Comparativa de Postman con otras herramientas similares](https://openwebinars.net/blog/que-es-postman/#comparativa-de-postman-con-otras-herramientas-similares)
* [Conclusiones](https://openwebinars.net/blog/que-es-postman/#conclusiones)

¿Eres desarrollador web y trabajas en diversos proyectos construyendo arquitecturas de microservicios? Si tu respuesta es afirmativa, quiere decir que has estado en la situación de gestionar APIs tanto propias de tu sistema o APIs de integración con sistemas tercerizados, las cuales han de requerir mantenimiento eficiente y rápido.

Sí aún no conoces una herramienta potente que te permita realizar este tipo de manejo, te invito que continúes leyendo este artículo donde te presentaremos a “Postman” una herramienta que hará que tu trabajo con APIs sea muy emocionante.

### Qué es Postman <a href="#que-es-postman" id="que-es-postman"></a>

**Postman** en sus inicios nace como una extensión que podía ser utilizada en el navegador Chrome de Google y básicamente nos permite realizar peticiones de una manera simple para testear **APIs** de tipo **REST** propias o de terceros.

Gracias a los avances tecnológicos, Postman ha evolucionado y ha pasado de ser de una extensión a una aplicación que dispone de herramientas nativas para diversos sistemas operativos como lo son Windows, Mac y Linux.

Cuenta con una versión libre de pago y con tres planes (básico, profesional y empresarial), si deseas consultar el detalle entre cada plan y sus precios puedes verlo en su [web oficial](https://www.postman.com/pricing/).

### Para qué sirve Postman <a href="#para-que-sirve-postman" id="para-que-sirve-postman"></a>

Postman sirve para múltiples tareas dentro de las cuales destacaremos en esta oportunidad las siguientes:

* Testear colecciones o catálogos de APIs tanto para Frontend como para Backend.
* Organizar en carpetas, funcionalidades y módulos los servicios web.
* Permite gestionar el ciclo de vida (conceptualización y definición, desarrollo, monitoreo y mantenimiento) de nuestra **API**.
* Generar documentación de nuestras APIs.
* Trabajar con entornos (calidad, desarrollo, producción) y de este modo es posible compartir a través de un entorno **cloud** la información con el resto del equipo involucrado en el desarrollo.

### Métodos más utilizados y posibles errores <a href="#metodos-mas-utilizados-y-posibles-errores" id="metodos-mas-utilizados-y-posibles-errores"></a>

Postman cuenta con una serie de métodos que nos permiten tomar acción ante nuestras peticiones, a continuación, te dejamos los más utilizados:

* **GET**: Obtener información
* **POST**: Agregar información
* **PUT**: Reemplazar la información
* **PATCH**: Actualizar alguna información
* **DELETE**: Borrar información

En cuanto a los posibles errores que podemos apreciar en la respuesta que nos ofrece la herramienta, lo resumiremos en que si la respuesta dada se encuentra en el rango de “200” quiere decir que toda la petición ha salido sin inconvenientes; mientras que el rango de los códigos de error “400” hacen referencia a errores con el cliente y aquellos errores en la línea de los “500” tienen que ver con fallos en el servidor.

### Primeros pasos con Postman <a href="#primeros-pasos-con-postman" id="primeros-pasos-con-postman"></a>

Si deseas iniciar con esta herramienta lo primero que debes hacer es instalarla y para ello deberás descargar el software según el sistema operativo que tengas (Linux, Mac o Windows) en la [web oficial de Postman](https://www.postman.com/downloads/), así mismo puedes elegir descargar la aplicación o probar con la versión web.

Una vez que hayas descargado y ejecutado el archivo instalador tienes dos opciones ingresar en modo free o utilizando los datos (usuario y clave) con los cuales te has registrado en el portal, esto con la finalidad de sincronizar todas tus colecciones y el historial de tu cuenta. Si aún no cuentas con un usuario, este paso es muy simple sólo deberás hacer el registro en [este enlace](https://identity.getpostman.com/).

Ahora bien, si ya utilizabas esta herramienta de forma free (sin tener una cuenta de usuario creada) no hay mayor inconveniente sólo tienes que exportar la data y una vez que crees tú cuenta e inicies sesión en ella procedes a importar la información.

En este mismo orden de ideas, una vez que ingresamos al sistema apreciaremos un **IDE** acompañado de un panel lateral, a través del cual podremos navegar tanto por el historial como por las colecciones, aunado a esto contamos con un navegador con un visor ordenado por pestañas.

<img src="https://dc722jrlp2zu8.cloudfront.net/media/uploads/2022/05/12/postman-inicio.png" alt="Imagen 0 en Qué es Postman y primeros pasos" height="657" width="1366">

A continuación, daremos un breve recorrido por la interface al realizar una petición. Para este ejemplo haremos una búsqueda del siguiente link de muestra que nos ofrece la plataforma web: [https://postman-echo.com/get](https://postman-echo.com/get)

Para ello haremos los siguiente:

1. Colocaremos la URL que analizaremos en el panel de búsqueda superior, dejamos marcada el método **“GET”** .
2. Presionamos el botón “enviar” **(Send)**.

Una vez enviada nuestra petición podremos observar el detalle de la respuesta que nos devuelve el servidor en el panel inferior, tal como se aprecia en la siguiente imagen:

<img src="https://dc722jrlp2zu8.cloudfront.net/media/uploads/2022/05/12/postman-respuesta.png" alt="Imagen 1 en Qué es Postman y primeros pasos" height="657" width="1366">

Cabe destacar que si deseas puedes ir guardando tus ejecuciones con tan sólo presionar el botón **“Save”** que se encuentra en la parte superior.

<img src="https://dc722jrlp2zu8.cloudfront.net/media/uploads/2022/05/12/postman-ide.png" alt="Imagen 2 en Qué es Postman y primeros pasos" height="95" width="934">

Adicionalmente, en el panel izquierdo podemos crear colecciones lo que nos permitirá tener una especie de lista con todas las peticiones que hayamos realizados, se recomienda que las colecciones las hagamos por API o por las categorías de testing que llevemos a cabo.

### Comparativa de Postman con otras herramientas similares <a href="#comparativa-de-postman-con-otras-herramientas-similares" id="comparativa-de-postman-con-otras-herramientas-similares"></a>

En el mercado existe una gran cantidad de herramientas con las cuales podemos realizar pruebas sobre APIs (**APIs Testing**), para que tengas una mejor visión al momento de elegir con cuál realizar tus pruebas a continuación te haremos una comparación entre Postman y dos grandes de estas.

#### Postman vs SoapUI <a href="#postman-vs-soapui" id="postman-vs-soapui"></a>

**SoapUI** es una herramienta que ha sido desarrollada en Java y es mayormente utilizada para llevar a cabo pruebas de sistemas cuya arquitectura sea **REST** o **SOAP**. Esta soporta múltiples protocolos como lo son:

* JMS
* JDBC
* HTTP
* REST
* SOAP

Al igual que Postman, cuenta con una versión libre y otra de pago. Posee una gran comunidad de usuarios y su curva de aprendizaje es de nivel medio.

A diferencia de Postman, con SoapUI trabajamos en base a proyectos, los cuales pueden ser independientes o compuestos y a su vez se encuentra clasificados en tres tipos de proyectos:

* **SOAP**: Los proyectos de este tipo se crean a partir de un archivo **WSDL** o simplemente con realizar un llamado a un servicio en particular y van dirigidos generalmente a crear pruebas de concurrencia, de pruebas de carga, pruebas funcionales y automatizadas.
* **REST**: Estos proyectos nacen directamente desde el URI (con sus parámetros) o a partir de un archivo **WADL** y son utilizados para validar servicios de tipo **RESTful**, con este tipo de proyecto mediremos cantidad de métodos por peticiones, operaciones, demanda de múltiples peticiones, así como la información que arroja el servicio.
* **Genéricos**: Los proyectos genéricos aplican para aquellos métodos y servicios variados que implican interfaces, con ellos podemos combinar pruebas para servicios SOAP y REST.

Esta categorización simplemente lo que nos va a indicar es el tipo de servicio principal a ser probado. Los proyectos pueden incluir varios tipos de pruebas, es decir podemos ejecutar pruebas de carga, pruebas funcionales e inclusive ejecutar simulaciones de servicios.

Si deseas consultar un poco más la documentación oficial que cuenta SoapUI puedes ingresar en su [sitio web](https://www.soapui.org/).

Ahora que conoces un poco sobre SoapUI y Postman te dejaremos un resumen de las ventajas de cada una de estas herramientas:

#### Ventajas de Postman <a href="#ventajas-de-postman" id="ventajas-de-postman"></a>

* Cuenta con una comunidad grande de usuarios.
* Es posible llevar a cabo trabajos de colaboración con el resto de los miembros de un equipo.
* Su interface es sencilla, atractiva a la vista del usuario e intuitiva.
* Cuenta con una extensión para el navegador web **Google Chrome**.
* Es posible agregar scripts (**JavaScript**) para añadir validaciones, automatizar y/o configurar pruebas.
* Es posible integrarla con otras herramientas.
* Y como se mencionó en el inicio del artículo permite trabajar con colecciones, que vienen siendo nuestra base de datos con las peticiones realizadas.

#### Ventajas de SoapUI <a href="#ventajas-de-soapui" id="ventajas-de-soapui"></a>

* Por tener más tiempo en el mercado **SoapUI** es considerado un proyecto con mayor madurez y comunidad sólida.
* Es un sistema bastante completo, con toda una gama de funcionalidades.
* Dada su naturaleza posee una mejor integración con **SOAP**.
* Es posible integrarla con otras herramientas para llevar a cabo la ejecución de las pruebas como lo son motores CI/CD, con **Maven**, entre otras.
* Permite configurar, automatizar y agregar validaciones.
* Es posible incluir scripts en base al lenguaje **Groovy**.
* Esta herramienta se encuentra orientada a pruebas (testing) y no a tan sólo consumir, documentar y publicar APIs.
* Admite la estructuración de pruebas en test steps, suites y cases.

#### Postman vs Swagger <a href="#postman-vs-swagger" id="postman-vs-swagger"></a>

Como hemos podido ver a lo largo de este post, ya conocemos qué es, para qué sirve, sus ventajas y otros aspectos de Postman. Por lo que, en esta comparación, a continuación destacaremos los puntos clave que nos ofrece Swagger.

* Swagger es un framework **Open Source** (de código abierto) a través de la cual podemos documentar APIs REST mediante una serie de reglas y especificaciones desde diversas fuentes como, por ejemplo: Java, PHP, JavaScript, Ruby, C#, entre otros.
* Cuenta con una serie de módulos que permiten su simple interacción con el proyecto en el cual se desee integrar como **Swagger UI**, **Swagger Core**, entre otros.
* Es posible consumir, visualizar, producir y describir las APIs.
* Desde la interface de **Swagger** es posible autenticar con **OAuth** para consumir los **endpoints** del proyecto.
* Soporta **JSON** y **XML**.

### Conclusiones <a href="#conclusiones" id="conclusiones"></a>

Postman es una herramienta que sirve de gran ayuda al equipo de desarrollo, permitiendo mantener las colecciones actualizadas, ahorrando los tiempos de respuesta al momento de realizar los test o las llamadas a los servicios. Es potente gracias a su fácil integración con APIs de terceros y cuenta con una gran comunidad.

Si estás dando tus primeros pasos en este mundo te recomendamos utilizar esta herramienta, por su sencillez, practicidad y simplicidad para llevar a cabo los procesos.
