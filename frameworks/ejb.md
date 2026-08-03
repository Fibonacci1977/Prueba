# EJB

<table data-header-hidden><thead><tr><th></th></tr></thead><tbody><tr><td><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/images/cabecera.gif" alt="" data-size="original"></p><p><br> </p></td></tr><tr><td><h3>Presentación</h3><p>En este módulo se realiza una introducción a la arquitectura Enterprise JavaBeans para el desarrollo de aplicaciones distribuidas y transaccionales.</p><p>Número de horas: 25</p><blockquote><p><a href="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/index.htm">Sesiones del módulo</a></p></blockquote><p></p><h3>Temario</h3><p>Tema 1. Introducción a la tecnología Enterprise JavaBeans</p><blockquote><p>1.1 Arquitecturas de aplicaciones de empresa<br>1.2 La arquitectura Enterprise JavaBeans</p></blockquote><p></p><h2>Tema 1. Introducción a la tecnología Enterprise JavaBeans</h2><p>La tecnología Enterprise JavaBeans es la propuesta del mundo Java (Sun y un amplio grupo de empresas colaboradoras entre las que no se encuentra, evidentemente, Microsoft) para el desarrollo de aplicaciones de empresa. Entendemos por aplicaciones de empresa las aplicaciones informáticas de gestión que se implantan en grandes corporaciones con múltiples oficinas distribuidas por toda la geografía nacional (o internacional). Suelen ser aplicaciones distribuidas, usadas por múltiples clientes, que hacen un uso intensivo de transacciones, bases de datos y políticas de seguridad.</p><p>La arquitectura Enterprise JavaBeans es el núcleo de un conjunto de tecnologías Java que recibe el nombre de J2EE (Java 2 Enterprise Edition) y hace uso intensivo de librerías incluidas en esta plataforma. Algunos ejemplos de APIs Java usados por la arquitectura EJB son los siguientes:</p><ul><li>JNDI para acceder a recursos<br></li><li>JMS para tratar con mensajes<br></li><li>JTA para programar explícitamente las transacciones<br></li></ul><p>La tecnología Enterprise JavaBeans esta siendo apoyada por la mayor parte de las empresas de informática que se orientan al mundo de la empresa (IBM, ORACLE, SUN,...) y también por los clientes de estas empresas, que valoran de forma muy positiva, entre otros aspectos, el carácter abierto de la arquitectura.</p><p>En este tema veremos una introducción a las distintas arquitecturas que se han ido proponiendo para las aplicaciones de empresa, y situaremos en este contexto la propuesta de arquitectura Enterprise JavaBeans. Comentaremos las características principales de la propuesta, dando algunos ejemplos prácticos de componentes Enterprise JavaBeans (EJB). Como parte práctica, explicaremos cómo realizar un despliegue de componentes EJB en el servidor de aplicaciones Weblogic.</p><h3>1.1. Arquitecturas de aplicaciones de empresa</h3><p>Las aplicaciones de empresa han sufrido una transformación extensa. La primera generación de aplicaciones de empresa consistían en aplicaciones centralizadas usando computadores mainframes. A finales de 1980 y comienzos de 1990, la mayoría de las nuevas aplicaciones de empresa se construyeron siguiendo una arquitectura de dos capas (también conocida como arquitectura cliente/servidor). Después, las aplicaciones de empresa evolucionaron a arquitecturas de tres capas, después a arquitecturas basadas en Web. El estado de evolución actual está representado por la arquitectura de aplicaciones J2EE.</p><p>El párrafo anterior se aplica a países con un alto grado de desarrollo tecnológico (léase Estados Unidos, y poco más). En países como España nos encontramos en la mayoría de los casos todavía usando aplicaciones cliente/servidor, y comenzando a implantar soluciones basadas en Web.</p><h4>1.1.1. Arquitectura de dos capas</h4><p>Con una aplicación de dos capas, un sistema de negocio se estructura como un conjunto de aplicaciones a nivel de sistema operativo que se ejecutan en la máquina cliente, típicamente un PC. Las aplicaciones se comunican a través de la red con el servidor de bases de datos, que almacena la información corporativa y que es el que implementa el manejo de transacciones y la seguridad. La comunicación entre las aplicaciones y el servidor de base de datos se realiza normalmente usando el lenguaje SQL.</p><p>Las aplicaciones cliente implementan uno o varios procesos de negocio, junto con la interfaz de usuario que proporciona la lógica de presentación que realiza la interacción entre el usuario y el proceso de negocio. El concepto de proceso de negocio encapsula una interacción del usuario con alguna información de la empresa.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion11.png" alt="" data-size="original"></p><p>Figura 1: arquitectura de aplicaciones de dos capas.</p><p>Entre las ventajas de esta arquitectura se encuentra la facilidad de desarrollo debido a que la presentación y la lógica de negocio residen en la misma aplicación. Los inconvenientes son mucho más numerosos. Entre ellos destacan :</p><ul><li>Dificultad de administrar las aplicaciones en grandes empresas<br></li><li>La integridad de la base de datos se puede comprometer fácilmente<br></li><li>Dificultad de mantener el código<br></li><li>Expone las aplicaciones a violaciones de seguridad<br></li><li>Su escalabilidad es limitada, es difícil escalar a un alto número de usuarios<br></li><li>Requiere una estructura homogénea de las máquinas cliente<br></li><li>Liga una aplicación a un tipo particular de presentación<br></li><li>Incompatibilidad con la Web (uno de los inconvenientes más importantes en la actualidad)<br></li></ul><h4>1.1.2. Arquitectura de tres capas</h4><p>El avance fundamental de las arquitecturas de tres capas es la separación de la lógica de presentación de la lógica de negocio. Para ello se introduce una capa intermedia que se encarga específicamente de la lógica de negocio y de la gestión de transacciones y de seguridad. Se introducen monitores de procesamiento de transacciones (TP, transaction processing, monitors) como CICS o Tuxedo que dan soporte a esta capa intermedia. La mayoría de los sistemas ERP* (Enterprise Resource Planning) usan esta arquitectura.</p><p>*ERP (Enterprise resource planning) es un término de la industria para un amplio conjunto de actividades soportadas por software de aplicación que facilitan a un fabricante o a otro negocio manejar partes importantes de su negocio, incluyendo planificación de productos, compra de material, mantenimiento de inventario, interacción con suministradores, servicios al cliente y seguimiento de pedidos. Los ERP también incluyen módulos de aplicación para los aspectos de finanzas y de recursos humanos del negocio. Normalmente, un sistema ERP usa o está integrado con una base de datos relacional. El despliegue de sistemas ERP obliga normalmente a realizar un considerable análisis de los procesos de negocio, así como la formación de los empleados y nuevos procedimientos de trabajo. Entre las empresas que desarrollan y despliegan ERP se encuentran SAP o Peoplesoft. (definición cortesía de whatis.com).</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion12.png" alt="" data-size="original"></p><p>Figura 2: Arquitectura de aplicaciones de tres capas</p><p>Aunque esta arquitectura elimina algunos de los inconvenientes de la arquitectura de dos capas, todavía sufre de inconvenientes:</p><ul><li>Complejidad<br></li><li>Ausencia de portabilidad de la aplicación<br></li><li>Incompatibilidad entre fabricantes<br></li><li>Falta de difusión y compartición de conocimientos y experiencias<br></li><li>Incompatibilidad con la Web<br><br></li></ul><h4>1.1.3 Arquitectura de tres capas con componentes distribuidos</h4><p>Los sistemas de componentes distribuidos representan un enfoque más moderno a la arquitectura de tres capas. Estos sistemas definen objetos o componentes que se ejecutan en la capa intermedia y que están disponibles para servir a otros procesos a través de proxies remotos. Estos proxies remotos comunican peticiones a los componentes distribuidos a lo largo de la red. Ejempo de sistemas de componentes distribuidos son RMI, CORBA y DCOM.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion13.png" alt="" data-size="original"></p><p>Figura 3: Arquitectura de tres capas con componentes distribuidos</p><p>Los componentes distribuidos son más reusables y flexibles que las aplicaciones basadas en procedimientos usadas en los monitores TP tradicionales, debido a que pueden ser ensamblados en una gran variedad de combinaciones para el desarrollo de aplicaciones de negocio, pero pueden ser complicados de programar y carecen de la infraestructura robusta que ofrecen los monitores TP.</p><h4>1.1.4 Arquitectura inicial de Aplicaciones Web</h4><p>La introducción de la Web lo cambió todo. El modelo simplificado de funcionamiento consiste en incorporar extensiones a los servidores Web. Estas extensiones invocan programas en el servidor que construyen dinámicamente documentos HTML a partir de la información almacenada en la base de datos corporativa. Además, estas extensiones en el servidor también introducen cambios en las bases de datos corporativas a partir de la información de formularios HTML.</p><p>Un ejemplo de estas extensiones son los scripts cgi-bin. Aunque estos mecanismos han permitido a los desarrolladores corporativos construir aplicaciones Web simples, el enfoque no escala bien para aplicaciones de empresa más complejas por las siguientes razones:</p><ul><li>Los scripts cgi-bin no proporcionan una buena encapsulación de los procesos o entidades de negocio.<br></li><li>Los scripts cgi-bin son complicados de desarrollar, probar y mantener. Las herramientas de desarrollo de alto nivel no soportan bien estos scripts.<br></li><li>Los scripts cgi-bin mezclan la lógica de negocio con la lógica de presentación.<br></li><li>Los scripts cgi-bin no proporcionan soporte para el manejo de transacciones ni de seguridad.<br></li><li>Los scripts cgi-bin no promueven el mantenimiento de la integridad de las reglas de negocio.<br></li></ul><p>(hacer una pequeña ronda de debate sobre qué tipo de sistemas da cada una de las clases conocen los alumnos).</p><h4>1.1.5 Arquitectura de aplicaciones J2EE</h4><p>J2EE es una arquitectura estándar orientada específicamente hacia el desarrollo y el despliegue de aplicaciones de empresa orientadas a Web usando el lenguaje de programación Java. Las empresas y los vendedores independientes de software (ISV, en inglés) pueden usar la arquitectura J2EE tanto para el desarrollo y despliegue de aplicaciones intranet, sustituyendo de esta forma las aplicaciones de dos capas y de tres capas, y para el desarrollo de aplicaciones Web, sustituyendo el enfoque basado en cgi.</p><p>La siguiente figura ilustra el modelo de programación propuesto por J2EE para el desarrollo de aplicaciones cliente/servidor. La Máquina Virtual Java hace de Contenedor de Aplicaciones Cliente.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion14.png" alt="" data-size="original"></p><p>Figura 4: Modelo de programación cliente/servidor de las aplicaciones J2EE</p><p>La siguiente figura ilustra el modelo de programación propuesto por J2EE para el desarrollo de aplicaciones de tres capas.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion15.png" alt="" data-size="original"></p><p>Figura 5: Modelo de programación de tres capas de las aplicaciones J2EE</p><p>La siguiente figura ilustra el modelo de programación para las aplicaciones basadas en Web:</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion16.png" alt="" data-size="original"></p><p>Figura 6: Modelo de programación de aplicaciones J2EE para aplicaciones basadas en Web.</p><p>La plataforma J2EE consiste en cuatro entornos de programación, llamados contenedores:</p><ul><li>El contenedor EJB: proporciona el entorno para el desarrollo, despliegue, y manejo en tiempo de ejecución de enterprise beans. Los enteprise beans son componentes que implementan los procesos y las entidades de negocio.<br></li><li>El contenedor Web: proporciona el entorno para el desarrollo, despliegue y manejo en tiempo de ejecución de servlets y páginas JSP (JavaServer Pages). Los servelts y las páginas JSP se agrupan en unidades desplegables llamadas aplicaciones Web. Una aplicación Web implementa la lógica de presentación de una aplicación de empresa.<br></li><li>El contenedor de aplicaciones cliente: se trata de la máquina virtual Java. Proporciona el entorno para la ejecución de aplicaciones cliente J2EE.<br></li><li>El contenedor de applets: proporciona el entorno para ejecutar applets Java. Este entorno está embebido típicamente en un navegador Web.<br></li></ul><p>En módulos anteriores del curso hemos estudiado las partes de J2EE que configuran una aplicación Web. Vamos a centrarnos en este modulo en el estudio de los componentes enterprise beans y de los contenedores EJB.</p><h3>1.2. La arquitectura Enterprise JavaBeans</h3><p>La arquitectura de componentes Enterprise JavaBeans (arquitectura EJB) es el núcleo de la plataforma J2EE. Esta arquitectura de componentes combina lo mejor de los monitores de procesamiento de transacciones y de los componentes distribuidos, proporcionando un entorno al estilo de los monitores de transacciones orientado a componentes distribuidos. La arquitectura EJB está constituida por un conjunto de componentes software llamados enterprise beans y un contenedor EJB que da soporte de ejecución a estos componentes.</p><p>En este apartado realizaremos una breve introducción a las características generales de la arquitectura.</p><h4>1.2.1 Especificaciones de la arquitectura Enterprise JavaBeans</h4><p>En Marzo de 1998 Sun Microsystems propone la especificación 1.0 de la arquitectura Enterprise JavaBeans. Esta especificación comienza con la siguiente definición:</p><blockquote><p><em>La arquitectura Enterprise JavaBeans es una arquitectura de componentes para el desarrollo y despliegue de aplicaciones de empresa distribuidas y orientadas a objetos. Las aplicaciones escritas usando la arquitectura Enterprise JavaBeans son escalables, transaccionales y seguras para multi usuarios. Estas aplicaciones pueden escribirse una vez, y luego desplegarse en cualquier servidor que soporte la especificación Enterprise JavaBeans.</em></p></blockquote><p>Aunque se han introducido nuevas versiones de la especificación, que incorporan muchas mejoras a la propuesta inicial, la definición de la arquitectura sigue siendo la misma. La siguiente tabla muestra las distintas revisiones que ha sufrido la especificación de la arquitectura EJB.</p><p>Tabla 1: Evolución de las especificaciones de la arquitectura Enterprise JavaBeans</p><p>Entre los objetivos que se enumeraban en ese primer documento de especificación 1.0 se encuentran los siguientes:</p><ul><li>Definir una arquitectura de componentes estándar con la que construir aplicaciones de gestión (business applications) distribuidas y orientadas a objetos en el lenguaje de programación Java. Enterprise JavaBeans permitirá construir aplicaciones combinando componentes desarrollados por herramientas de distintas compañías.<br></li><li>La arquitectura Enterprise JavaBeans hará fácil la construcción de aplicaciones. Los desarrolladores de aplicaciones no tendrán que entender los detalles de bajo nivel referidos al manejo de transacciones, manejo de estado, multi threading, pooling de recursos y otras APIs complejas de bajo nivel.<br></li><li>Las aplicaciones Enterprise JavaBeans seguirán la filosofía “escribe una vez, ejecuta en cualquier sitio” del lenguaje de programación Java. Un enterprise bean puede desarrollarse una vez, y después desplegado en múltiples plataformas sin necesidad de recompilarlo o modificar su código fuente.<br></li></ul><h4>1.2.2 Roles en la arquitectura Enterprise JavaBeans</h4><p>La arquitectura EJB define seis papeles principales. Brevemente, son:</p><ul><li>Desarrollador de beans: desarrolla los componentes enterprise beans.<br></li><li>Ensamblador de aplicaciones: compone los enterprise beans y las aplicaciones cliente para conformar una aplicación completa<br></li><li>Desplegador: despliega la aplicación en un entorno operacional particular (servidor de aplicaciones)<br></li><li>Administrador del sistema: configura y administra la infraestructura de computación y de red del negocio<br></li><li>Proporcionador del Contenedor EJB y Proporcionador del Servidor EJB: un fabricante (o fabricantes) especializado en manejo de transacciones y de aplicaciones y otros servicios de bajo nivel. Desarrollan el servidor de aplicaciones.<br></li></ul><h4>1.2.3. Contendor de beans</h4><p>Los enterprise beans (que también se denominan beans) son componentes software que se ejecutan en un entorno especial denominado contenedor EJB. El contenedor hospeda y maneja un enterprise bean de la misma forma que un servidor web Java hospeda un servlet o un navegador hospeda un applet. Un enterprise bean no puede funcionar fuera de un contenedor EJB. El contenedor EJB maneja cualquier aspecto del bean en tiempo de ejecución, incluyendo acceso remoto al bean, seguridad, persistencia, transacciones, concurrencia y acceso y pooling de recursos. El contenedor EJB también suele proporcionar servicios relacionados con la escalabilidad de la aplicación, como son la definición de clusters de contenedores, el balanceo de carga o la tolerancia a fallos.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion17.png" alt="" data-size="original"></p><p>Figura 7: El contenedor EJB captura la petición del cliente y realiza servicios de bajo nivel antes y después de pedir al bean que ejecute la lógica de negocio de la petición.</p><p>El contenedor aisla el enterprise bean del acceso directo de las aplicaciones cliente. Cuando una aplicación cliente invoca un método remoto en un enterprise bean, el contenedor intercepta la invocación para asegurar que la persistencia, transacciones y seguridad se aplican correctamente. De esta forma, el desarrollador de beans puede concentrarse en encapsular correctamente la lógica de negocio, mientras que el contenedor se encarga de todo lo demás.</p><p>El contenedor EJB se ejecuta a su vez en una máquina virtual Java, con lo que tiene acceso a toda la infraestructura proporcionada por este lenguaje de programación.</p><p>Los contenedores manejan muchos beans simultáneamente, en la misma forma que un servidor web Java maneja muchos servlets. Para reducir el consumo de memoria y el procesamiento, los contenedores almacenan (pool) los recursos y los ciclos de vida de los beans de forma muy cuidadosa. Cuando un bean no está siendo usado, el contenedor lo colocará en un almacén para ser reusado por otro cliente, o lo eliminará de la memoria y sólo lo recuperará cuando sea necesario. Debido a que las aplicaciones clientes no tienen acceso a los beans, la aplicación cliente desconoce completamente las actividades de manejo de recursos del bean. Por ejemplo, un bean que no está siendo usado puede ser eliminado de la memoria, mientras que su referencia remota en el cliente permanece intacta. Cuando el cliente invoca un método sobre la referencia remota, el contenedor simplemente recupera el bean para dar servicio a la petición. La aplicación cliente no se da cuenta de todo este proceso.</p><p>Un enterprise bean depende del contenedor para todo lo que necesita. Si un enterprise bean tiene que acceder a una conexión JDBC o a otro enterprise bean, lo hace a través del contenedor; si un enterprise bean tiene que acceder a la identidad de su llamador, obtener una referencia a él mismo, o acceder a propiedades, lo hace a través del contenedor.</p><p>En las próximas sesiones veremos cómo se implementa todo este funcionamiento. Veremos cómo el contenedor EJB intercepta las llamadas y cómo los beans pueden acceder a los servicios que proporciona el contenedor.</p><h4>1.2.4. Componentes enterprise beans</h4><p>Los componentes enterprise bean encapsulan típicamente un proceso o una entidad de negocio. Un enterprise bean, por ejemplo, podría calcular los pagos de interés de un préstamo, o encapsular la información sobre una cuenta bancaria que se encuentra físicamente en una base de datos relacional. Un cliente que necesita información llama a los métodos de negocio en el bean y esta llamada provoca una invocación remota que llega al contenedor EJB.</p><p>Hay tres tipos de enterprise beans: beans de sesión, beans de entidad y beans dirigidos por mensajes. En la siguiente sesión los presentaremos con más detalle. Por ahora, vamos a adelantar sólo algunas de sus características</p><p>En la especificación 2.0 de la arquitectura EJB se definen tres tipos de beans: beans de sesión, beans de entidad y beans dirigidos por mensaje:</p><ul><li>Los beans de sesión realizan una tarea a petición de un cliente, pero no se corresponden con ninguna entidad persistente de negocio. Pueden ser a su vez de dos tipos: con estado y sin estado. El estado lo almancenan localmente en la memoria, no en almacenamiento secundario, y dura el tiempo que está activa la sesión con el cliente.<br></li><li>Los beans de entidad representan objetos persistentes de negocio, normalmente datos existentes en alguna o algunas bases de datos del negocio. Típicamente, un bean de entidad representa una fila de una tabla de una base de datos relacional.<br></li><li>Los beans dirigidos por mensajes permiten procesar mensajes asíncronos generados por otros beans o por aplicaciones externas que necesitamos conectar al sistema.<br></li></ul><p>El cliente que usa los beans es una aplicación Java independiente, un servlet o una página JSP. En cualquier caso se trata de código Java que tiene acceso a las interfaces definidas para cada bean. También lo veremos con más detalle en la próxima sesión, pero adelantemos que existen dos tipos de acceso a los beans:</p><ul><li>Acceso remoto. El cliente usa RMI-IIOP para comunicarse con el bean. El desarrollador del bean define dos tipos de interfaces: la mencionada interfaz remota, en la que se definen la interfaz de los procesos de negocio, y la interfaz home, en la que se definen la interfaz de los métodos de gestión (creación, borrado, etc.) de las instancias del bean.<br></li><li>Acceso local. Si el cliente se ejecuta en la misma máquina virtual Java que el bean, puede acceder a versiones locales de las interfaces. De esta forma no es necesario serializar los parámetros ni los valores devueltos por el bean, mejorándose la eficiencia de las llamadas.<br></li></ul><h4>1.2.6.Ventajas de la arquitectura Enterprise JavaBeans</h4><p>La arquitectura EJB proporciona beneficios a todos los papeles que hemos mencionado previamente (desarrolladores, ensambladores de aplicaciones, administradores, desplegadores, fabricantes de servidores). Vamos en enumerar las ventajas que obtendrán los desarrolladores de aplicaciones y los clientes finales.</p><p>Las ventajas que ofrece la arquitectura Enterprise JavaBeans a un desarrollador de aplicaciones se listan a continuación.</p><ul><li>Simplicidad. Debido a que el contenedor de aplicaciones libera al programador de realizar las tareas del nivel del sistema, la escritura de un enterprise bean es casi tan sencilla como la escritura de una clase Java. El desarrollador no tiene que preocuparse de temas de nivel de sistema como la seguridad, transacciones, multi-threading o la programación distribuida. Como resultado, el desarrollador de aplicaciones se concentra en la lógica de negocio y en el dominio específico de la aplicación.<br></li><li>Portabilidad de la aplicación. Una aplicación EJB puede ser desplegada en cualquier servidor de aplicaciones que soporte J2EE.<br></li><li>Reusabilidad de componentes. Una aplicación EJB está formada por componentes enterprise beans. Cada enterprise bean es un bloque de construcción reusable. Hay dos formas esenciales de reusar un enterprise bean a nivel de desarrollo y a nivel de aplicación cliente. Un bean desarrollado puede desplegarse en distintas aplicaciones, adaptando sus características a las necesidades de las mismas. También un bean desplegado puede ser usado por múltiples aplicaciones cliente.<br></li><li>Posibilidad de construcción de aplicaciones complejas. La arquitectura EJB simplifica la construcción de aplicaciones complejas. Al estar basada en componentes y en un conjunto claro y bien establecido de interfaces, se facilita el desarrollo en equipo de la aplicación.<br></li><li>Separación de la lógica de presentación de la lógica de negocio. Un enterprise bean encapsula típicamente un proceso o una entidad de negocio. (un objeto que representa datos del negocio), haciéndolo independiente de la lógica de presentación. El programador de gestión no necesita de preocuparse de cómo formatear la salida; será el programador que desarrolle la página Web el que se ocupe de ello usando los datos de salida que proporcionará el bean. Esta separación hace posible desarrollar distintas lógicas de presentación para la misma lógica de negocio o cambiar la lógica de presentación sin modificar el código que implementa el proceso de negocio.<br></li><li>Despliegue en muchos entornos operativos. Entendemos por entornos operativos el conjunto de aplicaciones y sistemas (bases de datos, sistemas operativos, aplicaciones ya en marcha, etc.) que están instaladas en una empresa. Al detallarse claramente todas las posibilidades de despliegue de las aplicaciones, se facilita el desarrollo de herramientas que asistan y automaticen este proceso. La arquitectura permite que los beans de entidad se conecten a distintos tipos de sistemas de bases de datos.<br></li><li>Despliegue distribuido. La arquitectura EJB hace posible que las aplicaciones se desplieguen de forma distribuida entre distintos servidores de una red. El desarrollador de beans no necesita considerar la topología del despliegue. Escribe el mismo código independientemente de si el bean se va a despleguar en una máquina o en otra (cuidado: con la especificación 2.0 esto se modifica ligeramente, al introducirse la posibilidad de los interfaces locales).<br></li><li>Interoperabilidad entre aplicaciones. La arquitectura EJB hace más fácil la integración de múltiples aplicaciones de diferentes vendedores. El interfaz del enterprise bean con el cliente sirve como un punto bien definido de integración entre aplicaciones.<br></li><li>Integración con sistemas no-Java. Las APIs relacionadas, como las especificaciones Connector y Java Message Service (JMS), así como los beans manejados por mensajes, hacen posible la integración de los enterprise beans con sistemas no Java, como sistemas ERP o aplicaciones mainframes.<br></li><li>Recursos educativos y herramientas de desarrollo. El hecho de que la especificación EJB sea un estándar hace que exista una creciente oferta de herramientas y formación que facilita el trabajo del desarrollador de aplicacioines EJB.<br></li></ul><p>Entre las ventajas que aporta esta arquitectura al cliente final, destacamos la posibilidad de elección del servidor, la mejora en la gestión de las aplicaciones, la integración con las aplicaciones y datos ya existentes y la seguridad.</p><ul><li>Elección del servidor. Debido a que las aplicaciones EJB pueden ser ejecutadas en cualquier servidor J2EE, el cliente no queda ligado a un vendedor de servidores. Antes de que existiera la arquitectura EJB era muy difícil que una aplicación desarrollada para una determinada capa intermedia (Tuxedo, por ejemplo) puediera portarse a otro servidor. Con la arquitectura EJB, sin embargo, el cliente deja de estar atado a un venededor y puede cambiar de servidor cuando sus necesidades de escalabilidad, integración, precio, seguridad, etc.lo requieran.<br>Existen en el mercado algunos servidores de aplicaciones gratuitos (JBOSS, el servidor de aplicaciones de Sun, etc.) con los que sería posible hacer unas primeras pruebas del sistema, para después pasar a un servidor de aplicaciones con más funcionalidades.<br></li><li>Gestión de las aplicaciones. Las aplicaciones son mucho más sencillas de manejar (arrancar, parar, configurar, etc.) debido a que existen herramientas de control más elaboradas.<br></li><li>Integración con aplicaciones y datos ya existentes. La arquitectura EJB y otras APIs de J2EE simplifican y estandarizan la integración de aplicaciones EJB con aplicaciones no Java y sistemas en el entorno operativo del cliente. Por ejemplo, un clliente no tiene que cambiar un esquema de base de datos para encajar en una aplicación. En lugar de ello, se puede construir una aplicación EJB que encaje en el esquema cuando sea desplegada.<br></li><li>Seguridad. La arquitectura EJB traslada la mayor parte de la responsabilidad de la seguridad de una aplicación de el desarrollador de aplicaciones al vendedor del servidor, el Administrador de Sistemas y al Desplegador (papeles de la especificación EJB) La gente que ejecuta esos papeles están más cualificados que el desarrollador de aplicaciones para hacer segura la aplicación. Esto lleva a una mejor seguridad en las aplicaciones operacionales.<br></li></ul><h3>1.3. Bibliografía</h3><ul><li>Platform de Vlada Matena y Beth Stearns: <em>Appliying Enterprise JavaBeans: Component-Based Development for the J2EE</em> . Ed. Addison Wesley.<br></li><li>Gail Anderson y Paul Anderson: <em>Enterprise JavaBeans Componente Architecture: Designing and Codign Enterprise Applications</em>. Ed. Prentice Hall.<br></li><li><em>Short Course Enterprise JavaBeans Technology Fundamentals</em> (URL:http://developer.java.sun.com/developer/onlineTraining/EJBIntro/EJBIntro.html)<br></li><li>Especificaciones oficiales de la arquitectura Enterprise JavaBeans (URL:http://java.sun.com/products/ejb/docs.html#specs)</li></ul><h2>Ejercicios sesión 1</h2><p>En los ejercicios de esta primera sesión vamos a:</p><ul><li>Configurar el servidor de aplicaciones BEA WebLogic (<a href="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/ejercicios1.htm#ejercicio1">ejercicio 1</a>)<br></li><li>Compilar, desplegar y probar el primer EJB de ejemplo (<a href="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/ejercicios1.htm#ejercicio2">ejercicio 2</a>)<br></li><li>Realizar una sencilla modificación del código fuente del bean (<a href="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/ejercicios1.htm#ejercicio3">ejercicio 3</a>)<br></li></ul><h3 id="ejercicio1">Ejercicio 1: Instalación de WebLogic 7.0</h3><p>Suponemos que el servidor de aplicaciones está instalado en el directorio del usuario. Por ejemplo, en el directorio</p><pre><code>/home/domingo/bea
</code></pre><p>Denominaremos este directorio <code>WL_INSTALL</code>. Vamos a necesitar que las variables de entorno tengan los valores que aparecen en la siguiente tabla<br><br></p><p>1. Edita el fichero <code>$WORK/bin/setEnv</code> y modifica <code>$WL_INSTALL</code> con el valor donde está instalado el servidor de aplicaciones</p><p>2. Actualiza las variables de entorno ejecutando el scipt <code>setEnv</code></p><pre><code>% cd $WORK/bin
% . ./setEnv
</code></pre><h4>Crear el dominio vacío <em>moduloejb</em></h4><p>El servidor WebLogic 7.0 proporciona un Asistente de Configuración de Dominio que debe usarse para crear dominios vacíos. Ejecuta el asistente con los comandos</p><pre><code>% cd $WL_INSTALL/weblogic70/common/bin
% ./dmwiz.sh
</code></pre><p>y crea un dominio vacío de un Standalone Server llamado <em>moduloejb</em> siguiendo los sencillos pasos ilustrados en las siguientes figuras:</p><p>1. Define el tipo de dominio (WLS Domain sin aplicaciones) y el nombre (moduloejb):</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion18.png" alt="" data-size="original"></p><p>2. Define el funcionamiento del servidor. Por sencillez, vamos a preferir que sea standalone. Después, todo lo que probemos de esta forma va a poder funcionar en modo gestionado o incluso en clusters de servidores.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion19.png" alt="" data-size="original"></p><p>3. Define la localización del directorio donde se va a instalar el dominio. Acepta la opción por defecto (<code>$WL_INSTALL/user_projects/moduloejb</code>)</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion110.png" alt="" data-size="original"></p><p>4. Define un nombre del servidor y unos puertos de escucha del mismo. Acepta la opción por defecto.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion111.png" alt="" data-size="original"></p><p>5. Define el login y password del administrador. Por ejemplo login: <code>system</code>, password: <code>weblogic</code>.</p><p>6. Termina aceptando las dos pantallas informativas que vienen a continuación. El dominio habrá sido creado en el directorio <code>/home/domingo/bea/user_projects/moduloejb</code> y en ese directorio estará instalado el servidor de aplicaciones preparado para ese dominio.</p><p>En su momento, cuando los ejercicios lo requieran, deberás crear los recursos: pool JDBC, TX DataSource y JMS.</p><h4>Arrancar el servidor de aplicaciones</h4><p>Una vez creado el dominio, ya puedes arrancar el servidor de aplicaciones, con los siguientes comandos en una ventana del sistema:</p><pre><code>% cd $WL_INSTALL/user_projects/moduloejb
% ./startWebLogic.sh
</code></pre><p>En la misma ventana del sistema te pedirá el login y contraseña de administrador. Teclea lo mismo que en la ventana de inicialización.</p><h4>Comprobar que el servidor está en marcha</h4><p>1. Desde un ordenador cualquiera lanza un navegador y conéctarte a la URL <em>http://servidor:7001/console</em>, siendo servervidor el ordenador en el que acabamos de arracar el servidor de aplicaciones. Por ejemplo:</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion112.png" alt="" data-size="original"></p><p><br></p><p>2. Introduce el login y la contraseña con la que hemos instalado el servidor de aplicaciones. Entrarás en la aplicación web con la que podemos administrar el servidor de aplicaciones.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion113.png" alt="" data-size="original"></p><p><br></p><h3 id="ejercicio2">Ejercicio 2: Compilar y desplegar el bean de sesión</h3><p>El proceso de compilación, empaquetamiento, despliegue y prueba de un EJB de sesión y una aplicación cliente consta de los siguientes pasos:</p><ol><li>Compilar los ficheros JAVA que forman el EJB y la aplicación cliente</li><li>Empaquetar los ficheros CLASS y el descriptor de despliegue en un fichero EJB JAR</li><li>Personalizar el fichero EJB JAR para el WebLogic con el WebLogic Builder</li><li>Desplegar el EJB JAR en el servidor de aplicaciones</li><li>Probar la aplicación cliente</li></ol><p>Pasos previos:</p><ul><li>Chequear las variables de entorno<br></li><li>Descargar el fichero ZIP con los ejemplos y descomprimirlo<br></li></ul><h4>Chequear las variables de entorno</h4><p>Asegurate de que las variables de entorno tienen los valores que aparecen en la siguiente tabla. Si no es así, actualízalas de nuevo tal y como se indica en el ejercicio 1.</p><h4>Obtener el código fuente con los ejemplos</h4><p>El código fuente para los componentes se encuentra en la misma página donde se encuentran estos apuntes, en el fichero <em>ejercicio1.zip</em>.</p><p>1. Supongamos que el directorio de trabajo es</p><pre><code>/home/domingo/ejb
</code></pre><p>Creamos una variable de entorno para definir el directorio de trabajo.</p><pre><code>% export WORK=/home/domingo/ejb
</code></pre><p>2. Copiamos y descomprimimos el directorio de ejemplos en el directorio de trabajo</p><pre><code>% cp ejercicio1.zip $WORK
% cd $WORK
% unzip ejercicio1.zip
</code></pre><p>Los ficheros que se han descomprimido son:</p><pre><code>HelloWorldSLBean/HelloWorldBean.java
HelloWorldSLBean/HelloWorldRemoteHome.java
HelloWorldSLBean/HelloWorldRemote.java
HelloWorldClient.java
ejb-jar.xml
</code></pre><p>En la próxima sesión explicaremos con más detalle el contenido de todos estos ficheros. Todos ellos implementan un bean de sesión sin estado con un único método, hi(), que devuelve un string con el típico saludo “Hello, world”. Vamos a ver en los pasos siguientes cómpilar los ficheros, empaquetar el bean, desplegarlo en el servidor de aplicaciones y probarlo desde una aplicación cliente. Aunque se pueden utilizar herramientas avanzadas, como el ant, para compilar los beans, hemos preferido hacerlo de la manera más simple posible. Así sabemos en todo momento qué es lo que estamos haciendo.</p><p>1. Para compilar los ficheros vamos al directorio de ejemplo y llamamos a <code>javac</code> (ya hemos actualizado el <code>CLASSPATH</code> en un paso anterior):</p><pre><code>% cd $WORK/HelloWorld
% javac HelloWorldSLBean/*.java
</code></pre><p>2. Compilar y ejecutar la aplicación cliente. Si miramos el código fuente de la aplicación, lo único que hace es conectarse con el bean (la llamada clase Home del bean), crear una instancia del bean y pedir el método <code>hi()</code> de esa instancia. Al no estar el bean desplegado en el servidor de aplicaciones, la aplicación cliente generará un error:</p><pre><code>% javac HelloWorldClient.java
% java HelloWorldClient
javax.naming.NameNotFoundException: Unable to resolve 'HelloWorldEJB' Resolved: '' 
Unresolved:'HelloWorldEJB' ; remaining name 'HelloWorldEJB'
        at weblogic.rmi.internal.BasicOutboundRequest.sendReceive(BasicOutboundRequest.java:109)
        at weblogic.rmi.cluster.ReplicaAwareRemoteRef.invoke(ReplicaAwareRemoteRef.java:262)
        at weblogic.rmi.cluster.ReplicaAwareRemoteRef.invoke(ReplicaAwareRemoteRef.java:229)
        at weblogic.jndi.internal.ServerNamingNode_WLStub.lookup(Unknown Source)
        at weblogic.jndi.internal.WLContextImpl.lookup(WLContextImpl.java:337)
        at weblogic.jndi.internal.WLContextImpl.lookup(WLContextImpl.java:332)
        at javax.naming.InitialContext.lookup(InitialContext.java:350)
        at HelloWorldClient.main(HelloWorldClient.java:15)
</code></pre><h4>Empaquetar el bean</h4><p>Debemos construir un fichero JAR, que llamaremos <code>helloworld-ejb.jar</code>, con el bean compilado. Para ello:</p><pre><code>% mkdir META-INF
% mv ejb-jar.xml META-INF/
% jar cvf helloworld-ejb.jar META-INF/* HelloWorldSLBean/*.class
manifest agregado
agregando: META-INF/ejb-jar.xml(entrada = 663) (salida= 330)(desinflado 50%)
agregando: HelloWorldSLBean/HelloWorld.class(entrada = 240) (salida= 182)(desinflado 24%)
agregando: HelloWorldSLBean/HelloWorldBean.class(entrada = 710) (salida= 363)(desinflado 48%)
agregando: HelloWorldSLBean/HelloWorldHome.class(entrada = 288) (salida= 199)(desinflado 30%)
</code></pre><h4>Desplegar el bean de sesión usando el WebLogic Builder</h4><p>El WebLogic Builder es una aplicación Java que se distribuye junto con el servidor WebLogic y que tiene como principal utilidad la configuración de ficheros JAR, WAR y EAR para el posterior despliegue en el servidor. Vamos a ver cómo funciona, desplegando el fichero <code>helloworld-ejb.jar</code></p><p>1. Lanzar la aplicación WebLogic Builder:</p><pre><code>% cd $WL_INSTALL/weblogic700/server/bin
% ./startWLBuilder.sh
</code></pre><p>2. Abrir el fichero <code>helloworld-ejb.jar</code> con el programa WebLogic Builder</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion114.png" alt="" data-size="original"></p><p>Aceptar cuando pregunta si debe crear el fichero de descripciones <code>weblogic-ejb-jar.xml</code> (IMPORTANTE: el fichero <code>weblogic-ejb-jar.xml</code> es necesario para que el bean se despliegue correctamente en el servidor de aplicaciones. Salvar el paquete con la opción File > Save para que el fichero <code>helloworld-ejb.jar</code> se actualize con este fichero).</p><p>3. Cambiar el nombre JNDI del bean. Por defecto, el nombre JNDI es el mismo que el nombre del bean (<code>HelloWorld</code>). Vamos a cambiarlo, poniendo como nombre <code>HelloWorldEJB</code>. Este nombre es al que se hace referencia en la aplicación cliente. Para cambiar el nombre pincha en el bean HelloWorld que aparece en la parte superior derecha de la ventana. La ventana principal de la aplicación cambiará y te permitirá modificar ciertas propiedades del bean, entre ellas el nombre JNDI. Pon como nombre HelloWorldEJB y a continuación salva el bean.<br><br></p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion115.png" alt="" data-size="original"></p><p>3. Para desplegar el bean en el servidor, primero hay que conectarse a él con la aplicación. Selecciona la opción Tools > Connect to server. Aparece una ventana de diálogo en la que puedes dar la dirección de red donde se encuentra el servidor, el nombre del servidor, puerto, login y password. Completa el login y password de administrador.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion116.png" alt="" data-size="original"></p><p>4. Selecciona la opción Tools > Deploy Module.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion117.png" alt="" data-size="original"></p><p>Pulsa el botón Deploy Module. Si todo funciona correctamente el bean se desplegará en el servidor.</p><p>5. Comprueba que el bean se ha desplegado en el servidor de aplicaciones. Para ello conéctate con el navegador a la dirección <em>http://localhost:7001/console</em> y selecciona el apartado EJB. Allí debes encontrar el bean que acabas de desplegar.</p><h4>Probar la aplicación cliente</h4><p>Ahora la aplicación cliente debe funcionar correctamente. ¡Pruébala!:</p><pre><code>cd $WORK/ejb/HelloWorld
% java HelloWorldClient
Voy a llamar al bean
Hola; soy Domingo
He llamado al bean
</code></pre><h4>Desplegar el bean usando la consola de administración</h4><p>Vamos a ver otra forma de desplegar el bean; ahora usando la consola de administración.</p><p>1. Vamos a volver al instante en que el fichero EJB JAR no estaba desplegado en el servidor de aplicaciones. Para ello elimina el bean desplegado usando la consola de administración. Debes pinchar en el cubo de basura que hay a la derecha del nombre del bean, en la pantalla moduloejb > EJB Deployments</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion118.png" alt="" data-size="original"></p><p>Acepta en la pantalla de confirmación. Con ello el EJB se habrá eliminado del servidor de aplicaciones. Si ejecutas la aplicación cliente, verás que aparece el mismo error que la primera vez que lo hicimos.</p><p>2. En la consola de administración escoger la opción EJB y Configure a new EJB. Entrarás en la pantalla Locate Application or Component to Configure. En esta pantalla puedes subir un EJB JAR al servidor y después seleccionarlo para desplegarlo. Como el fichero EJB JAR ya está en el propio servidor (la máquina localhost) sólo debes seleccionarlo.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion119.png" alt="" data-size="original"></p><p>Selecciona ahora el servidor en el que quieres desplegar el bean (myserver), acepta el nombre por defecto de la aplicación y pulsa en Configure and Deploy:</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion120.png" alt="" data-size="original"></p><p>3. Prueba la aplicación cliente. Te seguirá dando error. ¿Porqué?</p><p>4. Para cambiar el nombre JNDI desde la consola de administración, selecciona la opción de Edit Deployment Descriptor. Se abrirá una nueva ventana del navegador en la que podrás modificar los distintos aspectos de configuración del EJB. Despliega el árbol WebLogic EJB Jar, WebLogic Enterprise Beans y selecciona el objeto HelloWorld. Aparece una pantalla en la que podrás modificar el JNDI Name. Escribe HelloWorldEJB y Apply Changes:</p><pre><code>
</code></pre><p>Comenzará a parpadear el icono con la admiración. Eso significa que debes reiniciar el servidor. Pero primero debes grabar la nueva configuración del EJB: pulsa en el árbo helloworld-ejb.jar y cambiará la pantalla de la derecha. Pulsa la opción “Persist”, con lo que se estará grabando el fichero <code>helloworld-ejb.jar</code> modificado. Para no tener que personalizar más este fichero, puedes descomprimirlo con el comando:</p><pre><code>% jar xvf helloworld-ejb.jar
</code></pre><p>Si ahora miras en el directorio META-INF verás que está el fichero <code>weblogic-ejb-jar.xml</code>. Este fichero es el que ha creado el WebLogic Builder y ha modificado la consola de administración. Si lo editas, verás que el elemento XML <code>jndi-name</code> tiene el valor HelloWorldEJB.</p><p>Reinicia el servidor y prueba la aplicación cliente. Ahora sí que debe funcionar.</p><h4 id="ejercicio3">Ejercicio 3: Modificar el código fuente del bean</h4><p>Modifica el código fuente del bean para que en lugar de devolver el mensaje “Hola, soy Domingo”, devuelva tu nombre. Para ello:</p><ul><li>Edita el fichero HelloWorldBean.java<br></li><li>Compila todos los ficheros del bean<br></li><li>Empaqueta el bean, ahora en el directorio META-INF ya está el fichero de personalización para el servidor WebLogic<br></li><li>Arranca el WebLogic Builder<br></li><li>Carga el EJB JAR<br></li><li>Conecta el servidor y despliega el EJB JAR en el servidor<br></li><li>Prueba la aplicación cliente<br></li></ul><p>Por último, modifica la aplicación cliente, para que en lugar de conectarse al bean de tu propio servidor de aplicaciones se conecte al de un compañero.</p><div data-gb-custom-block data-tag="file" data-src="../.gitbook/assets/ejercicio1.zip"></div><p></p><p>Tema 2. Introducción a los Enterprise JavaBeans</p><blockquote><p>2.1 Tipos de EJBs<br>2.2 Implementación de un EJB<br>2.3 Aplicaciones clientes<br>2.4 Acceso remoto y local a los EJB</p></blockquote><h2>Tema 2. Introducción a los Enteprise Beans</h2><p>Un enterprise bean es un componente (objeto) distribuido gestionado por un servidor, escrito en el lenguaje Java y que implementa la lógica de negocio de una aplicación. Por ejemplo, en una aplicación de control de inventario, un enterprise bean podría implementar la lógica de negocio mediante métodos llamados <code>checkInventoryLevel</code> y <code>orderProduct</code>. Mediante la invocación de estos productos, los clientes remotos podrían acceder a los servicios de inventario proporcionados por la aplicación.</p><p>Los enterprise beans simplifican el desarrollo de aplicaciones distribuidas de gran tamaño por varias razones:</p><ul><li>Debido a que el contenedor EJB proporciona servicios de nivel de sistema a los enterprise beans, el desarrollador de los beans puede concentrarse en la resolución de los problemas de negocio. El contenedor EJB se responsabiliza de servicios de nivel de sistema como gestión de transacciones o seguridad.</li><li>Debido a que los beans, y no el cliente, contienen la lógica de negocio de la aplicación, el desarrollador de la aplicación cliente puede concentrarse en la presentación del cliente y no se debe preocupar de acceder a bases de datos ni de reglas de negocio. Como resultado, los clientes son más ligeros, un beneficio que es particularmente importante en clientes que corren en dispositivos pequeños (palm computers o teléfonos Java).</li><li>Debido a que los enterprise beans son componentes portables, el ensamblador de aplicaciones puede construir nuevas aplicaciones a partir de los beans existentes. Estas aplicaciones pueden ejecutarse en cualquier servidor J2EE compatible.</li></ul><p>Es recomendable usar enterprise beans cuando la aplicación que deseamos desarrollar cumple alguno de los siguientes requisitos:</p><ul><li>La aplicación debe escalable. Si se hace necesario mejorar la eficiencia de la aplicación para cubrir las necesidades de un número creciente de clientes, es muy útil poder distribuir la aplicación entre múltiples máquinas. La arquitectura EJB está especialmente indicada para esto, ya que los enterprise beans pueden moverse de una máquina a otra y replicarse, todo ello de forma totalmente transparente a los clientes finales.</li><li>Se requieren transacciones para asegurar la integridad de los datos. Los enterprise beans soportan transacciones para gestionar el acceso concurrente a objetos compartidos.</li><li>La aplicación tendrá una variedad de clientes. Con sólo unas pocas líneas de código, los clientes remotos pueden localizar fácilmente enterprise beans en el contenedor. Estos clientes pueden ser ligeros, variados y numerosos.</li></ul><p>Existen tres tipos de enterprise beans:</p><ul><li>Beans de sesión: ejecutan una tarea para un cliente.<br></li><li>Beans de entidad: representan un objeto entidad de negocio que existe en un almacenamiento persistente.<br></li><li>Beans dirigidos por mensajes: actúan cómo escuchadores (listeners) del API Java Message Service, procesando mensajes asíncronamente.<br></li></ul><h3>2.1 Tipos de enterprise beans</h3><h4>2.1.1 Beans de sesión</h4><p>Los beans de sesión representan sesiones interactivas con uno o más clientes. Los bean de sesión pueden mantener un estado, pero sólo durante el tiempo que el cliente interactua con el bean. Esto significa que los beans de sesión no almacenan sus datos en una base de datos después de que el cliente termine el proceso. Por ello se suele decir que los beans de sesión no son persistentes.</p><p>A diferencia de los bean de entidad, los beans de sesión no se comparten entre más de un cliente, sino que existe una correspondencia uno-uno entre beans de sesión y clientes. Por esto, el contenedor EJB no necesita implementar mecanismos de manejo de concurrencia en el acceso a estos beans.</p><p>Existen dos tipos de beans de sesión: con estado y sin él.</p><p><strong>Beans de sesión sin estado</strong></p><p>Los beans de sesión sin estado no se modifican con las llamadas de los clientes. Los métodos que ponen a disposición de las aplicaciones clientes son llamadas procedurales que reciben datos y devuelven resultados, pero que no modifican internamente el estado del bean. Esta propiedad permite que el contenedor EJB pueda crear un almacén (<em>pool</em>) de instancias, todas ellas del mismo bean de sesión sin estado y asignar cualquier instancia a cualquier cliente. Incluso un único bean puede estar asignado a múltiples clientes, ya que la asignación sólo dura el tiempo de invocación del método solicitado por el cliente.</p><p>Cuando un cliente invoca un método de un bean de sesión sin estado, el contenedor EJB obtiene una instancia del almacén. Cualquier instancia servirá, ya que el bean no puede guardar ninguna información referida al cliente. Tan pronto como el método termina su ejecución, la instancia del bean está disponible para otros clientes. Esta propiedad hace que los beans de sesión sin estado sean muy escalables para un gran número de clientes. El contenedor EJB no tiene que mover sesiones de la memoria a un almacenamiento secundario para liberar recursos, simplemente puede obtener recursos y memoria destruyendo las instancias.</p><p>Es apropiado usar beans de sesión sin estado cuando una tarea no está ligada a un cliente específico:<br></p><ul><li>Para enviar una confirmación por correo electrónico o calcular unas cuotas de un préstamo.<br></li><li>Como un puente de acceso a una base de datos o a un bean de entidad. En una arquitectura cliente-servidor, el bean de sesión podría proporcionar al interfaz de usuario del cliente los datos necesarios, así como modificar objetos de negocio (base de datos o bean de entidad) a petición de la interfaz.</li></ul><p>Algunos ejemplos de bean de sesión sin estado podrían ser:<br></p><ul><li>Un enterprise bean que comprueba si un símbolo de compañía está disponible en el mercado de valores y devuelve la última cotización registrada.</li><li>Un enterprise bean que calcula la cuota del seguro de un cliente, basándose en los datos que se le pasa del cliente.</li></ul><p><strong>Beans de sesión con estado</strong></p><p>En un bean de sesión con estado, las <em>variables de instancia</em> del bean almacenan datos específicos obtenidos durante la conexión con el cliente. Cada bean de sesión con estado, por tanto, almacena el estado conversacional de un cliente que interactua con el bean. Este estado conversacional se modifica conforme el cliente va realizando llamadas a los métodos de negocio del bean. El estado conversacional no se guarda cuando el cliente termina la sesión.</p><p>Algunos ejemplos de beans de sesión con estado podrían ser:<br></p><ul><li>Un ejemplo típico es un carrito de la compra, en donde el cliente va guardando uno a uno los items que va comprando.<br></li><li>Un enterprise bean que reserva un vuelo y alquila un coche en un sitio Web de una agencia de viajes.<br></li></ul><p>Debido a que el bean guarda el estado conversacional con un cliente determinado, no le es posible al contenedor crear un almacen de instancias y compartirlo entre muchos clientes. Por ello, el manejo de beans de sesión con estado es más pesado que el de beans de sesión sin estado.</p><p><strong>Uso de beans de sesión</strong></p><p>En general, se debería usar un bean de sesión con estado si se cumplen las siguientes circunstancias:</p><ul><li>El estado del bean representa la interacción entre el bean y un cliente específico.</li><li>El bean necesita mantener información del cliente a lo largo de un conjunto de invocaciones de métodos.</li><li>El bean hace de intermediario entre el cliente y otros componentes de la aplicación, presentando una vista simplificada al cliente.<br></li></ul><p>Para mejorar la eficiencia de la aplicación, se debería usar beans de sesión sin estado si se cumple alguna de las siguientes condiciones:</p><ul><li>El estado del bean no tiene ningún dato para un cliente específico.</li><li>En una única invocación de un método, el bean realiza una tarea genérica que puede ser solicitada por cualquier cliente. Por ejemplo, se podría usar un bean sin estado para enviar un e-mail que confirme un pedido on-line.</li><li>El bean obtiene de una base de datos un conjuntos de datos de sólo lectura que se usan a menudo por los clientes. Un bean de este tipo, por ejemplo, podría obtener las filas de tabla que representan los productos que están a la venta esta semana.</li></ul><h4>2.1.2 Beans de entidad</h4><p>Los beans de entidad modelan conceptos de negocio que puede expresarse como nombres. Esto es una regla sencilla más que un requisito formal, pero ayuda a determinar cuándo un concepto de negocio puede ser implementado como un bean de entidad. Los beans de entidad representan “cosas”: objetos del mundo real como hoteles, habitaciones, expedientes, estudiantes, y demás. Un bean de entidad puede representar incluso cosas abstractas como una reserva. Los beans de entidad describen tanto el estado como la conducta de objetos del mundo real y permiten a los desarrolladores encapsular las reglas de datos y de negocio asociadas con un concepto específico. Por ejemplo un EJB Estudiante encapsula los datos y reglas de negocio asociadas a un estudiante. Esto hace posible manejar de forma consistente y segura los datos asociados a un concepto.</p><p>Los beans de entidad se corresponden con datos en un almacenamiento persistente (base de datos, sistema de ficheros, etc.). Las variables de instancia del bean representan los datos en las columnas de la base de datos. El contenedor debe sincronizar las variables de instancia del bean con la base de datos. Los beans de entidad se diferencian de los beans de sesión en que las variables de instancia se almacenan de forma persistente.</p><p>Son muchas las ventajas de usar beans de entidad en lugar de acceder a la base de datos directamente. El uso de beans de entidad para transformar en objetos los datos proporciona a los programadores un mecanismo más simple para acceder y modificar los datos. Es mucho más fácil, por ejemplo, cambiar el nombre de un estudiante llamando a <code>student.setName()</code> que ejecutando un comando SQL contra la base de datos. Además, el uso de objetos favorece la reutilización del software. Una vez que un bean de entidad se ha definido, su definición puede usares a lo largo de todo el sistema de forma consistente. Un EJB Estudiante proporciona un forma completa de acceder a la información del estudiante y eso asegura que el acceso a la información es consistente y simple.</p><p>La representación de los datos como beans de entidad puede hacer que el desarrollo sea más sencillo y menos costoso.</p><p><strong>Diferencias con los beans de sesión</strong></p><p>Los beans de entidad se diferencian de los beans de sesión, principalmente, en que son persistentes, permiten el acceso compartido, tienen clave primaria y pueden participar en relaciones con otros beans de entidad:</p><p><br>Persistencia</p><blockquote><p>Debido a que un bean de entidad se guarda en un mecanismo de almacenamiento se dice que es persistente. Persistente significa que el estado del bean de entidad existe más tiempo que la duración de la aplicación o del proceso del servidor J2EE. Un ejemplo de datos persistentes son los datos que se almacenan en una base de datos.</p><p>Los beans de entidad tienen dos tipos de persistencia: Persistencia Gestionada por el Bean (BMP, <em>Bean-Managed Persistence</em>) y Persistencia Gestionada por el Contenedor (CMP, <em>Container-Managed Persistence</em>). En el primer caso (BMP) el bean de entidad contiene el código que accede a la base de datos. En el segundo caso (CMP) la relación entre las columnas de la base de datos y el bean se describe en el fichero de propiedades del bean, y el contenedor EJB se ocupa de la implementación.</p></blockquote><p>Acceso compartido<br></p><blockquote><p>Los clientes pueden compartir beans de entidad, con lo que el contenedor EJB debe gestionar el acceso concurrente a los mismos y por ello debe usar transacciones. La forma de hacerlo dependerá de la política que se especifique en los descriptores del bean.</p></blockquote><p>Clave primaria<br></p><blockquote><p>Cada bean de entidad tiene un identificador único. Un bean de entidadad alumno, por ejemplo, puede identificarse por su número de expediente. Este identificador único, o <em>clave primaria</em>, permite al cliente localizar a un bean de entidad particular.</p></blockquote><p>Relaciones<br></p><blockquote><p>De la misma forma que una tabla en una base de datos relacional, un bean de entidad puede estar relacionado con otros EJB. Por ejemplo, en una aplicación de gestión administrativa de una universidad, el bean <code>alumnoEJB</code> y el bean <code>actaEBJ</code> estarían relacionados porque un alumno aparece en un acta con una calificación determinada.</p><p>Las relaciones se implementan de forma distinta según se esté usando la persistencia manejada por el bean o por el contenedor. En el primer caso, al igual que la persistencia, el desarrollador debe programar y gestionar las relaciones. En el segundo caso es el contenedor el que se hace cargo de la gestión de las relaciones. Por ello, estas últimas se denominan a veces relaciones gestionadas por el contenedor.</p></blockquote><p><strong>Persistencia manejada por el contenedor</strong></p><p>El término persistencia manejadad por el contenedor significa que el contenedor EJB maneja todos los accesos a bases de datos requeridos por el bean. El código del bean no contiene ninguna llamada SQL. Como resultado, el código del bean no está atado a un tipo específico de almacenamiento persistente. A causa de esta flexibilidad, incluso si se vuelve a desplegar el bean en un servidor distinto de J2EE que use una base de datos distinta, no hará falta recompilar el código del bean. En breve, los beans son más portables.</p><p>Para poder generar las llamadas de acceso a los datos, el contenedor necesita información que se proporciona en el esquema abstracto del bean de entidad</p><p><strong>Esquema abstracto</strong></p><p>El esquema abstracto es una parte del descriptor de despliegue de un bean de entidad. El término abstracto distingue este esquema del esquema físico del sistema de almacenamiento de datos subyacente. En una base de datos relacional, por ejemplo, el esquema físico está formado por estructuras como tablas y columnas.</p><p>En el esquema abstracto se define un nombre del enterprise bean. Este nombre puede ser usado luego como referencia en preguntas escritas en el lenguaje EJB QL (<em>Enterprise JavaBeans Query Language</em>). Es necesario definir una consulta EJB QL para cada método de búsqueda del bean (excepto <code>findByPrimaryKey</code>). Esta consulta EJB QL es ejecutada por el contenedor EJB cada vez que se invoca el método de búsqueda.</p><p>La siguiente figura muestra un esquema abstracto sencillo que describe las relaciones entre cuatro beans de entidad.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion21.png" alt="" data-size="original"></p><p><strong>Campos persistentes</strong></p><p>Los campos persistentes de un bean de entidad se almacenan en el almacén de datos subyacente. El conjunto de campos persistentes representa el estado del bean. En tiempo de ejecución, el contenedor EJB sincroniza automáticamente este estado con la base de datos. Durante el despliegue, el contenedor suele hacer corresponder el bean de entidad con una tabla de la base de datos y hacer corresponder los campos persistentes con las columnas de la tabla.</p><p>Por ejemplo, el bean <code>ClienteEJB</code> podría tener campos persistentes como nombre, apellidos, direcciónCorreo y telefono. En persistencia gestionada por el contenedor estos campos son virtuales. Se declaran en el esquema abstracto, pero no se codifican como variables de instancia en el bean. En su lugar, los campos persistentes se identifican en el código con métodos de acceso (de tipo <em>get</em> y <em>set</em>).</p><p><strong>Campos de relación</strong></p><p>Un campo de relación es como una clave externa en una base de datos: identifica a un bean relacionado. Al igual que un campo persistente, un campo de relación es virtual y se define en el enterprise bean con un método de acceso. Pero a diferencia de los campos persistentes, un campo de relación no representa el estado del bean.</p><h4>2.1.3 Beans dirigidos por mensajes</h4><p>Son el tercer tipo de beans propuestos por la última especificación de EJB. Estos beans permiten que las aplicaciones J2EE reciban mensajes JMS de forma asíncrona. Así, el hilo de ejecución de un cliente no se bloquea cuando está esperando que se complete algún método de negocio de otro enterprise bean. Los mensajes pueden enviarse desde cualquier componente J2EE (una aplicación cliente, otro enterprise bean, o un componente Web) o por una aplicación o sistema JMS que no use la tecnología J2EE.</p><p><strong>Diferencias con los beans de sesión y de entidad</strong></p><p>La diferencia más visible es que los clientes no acceden a los beans dirigidos por mensajes mediante interfaces (explicaremos esto con más detalle más adelante), sino que un bean dirigido por mensajes sólo tienen una clase bean.</p><p>En muchos aspectos, un bean dirigido por mensajes es parecido a un bean de sesión sin estado.</p><ul><li>Las instancias de un bean dirigido por mensajes no almacenan ningún estado conversacional ni datos de clientes.<br></li><li>Todas las instancias de los beans dirigidos por mensajes son equivalentes, lo que permite al contenedor EJB asignar un mensaje a cualquier instancia. El contenedor puede almacenar estas instancias para permitir que los streams de mensajes sean procesados de forma concurrente.<br></li><li>Un único bean dirigido por mensajes puede procesar mensajes de múltiples clientes.<br></li></ul><p>Las variables de instancia de estos beans pueden contener algún estado referido al manejo de los mensajes de los clientes. Por ejemplo, pueden contener una conexión JMS, una conexión de base de datos o una referencia a un objeto enterprise bean.</p><p>Cuando llega un mensaje, el contenedor llama al método onMessage del bean. El método onMessage suele realizar un casting del mensaje a uno de los cinco tipos de mensajes de JMS y manejarlo de forma acorde con la lógica de negocio de la aplicación. El método onMessage puede llamar a métodos auxiliares, o puede invocar a un bean de sesión o de entidad para procesar la información del mensaje o para almacenarlo en una base de datos.</p><p>Un mensaje puede enviarse a un bean dirigido por mensajes dentro de un contexto de transacción, por lo que todas las operaciones dentro del método onMessage son parten de un única transacción.</p><h3>2.2 Implementación de un enterprise bean</h3><p>Para implementar un enterprise bean, el desarrollador debe proporcionar cuatro elementos: una interfaz remota del bean, una interfaz home, una clase enterprise bean y un fichero de descripción del despliegue. La interfaz home declara métodos de fábricación (factory methods) que usan los clientes Java para crear nuevos enterprise beans, localizar enterprise beans existentes y destruir los beans. La interfaz remota declara los métodos de negocio del enterprise bean, que usan los clientes Java en tiempo de ejecución. La clase enterprise bean encapsula la lógica del bean e implementa los métodos de negocio definidios en la interfaz remota. El descriptor de despliegue es un fichero de configuración XML que describe al servidor EJB el enterprise bean y sus atributos de tiempo de ejecución. Es responsabilidad del desarrollador del bean crear estos cuatro elementos y empaquetarlos en un fichero JAR listo para el despliegue.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion22.png" alt="" data-size="original"></p><p>Cuando se despliega un enterprise bean, el desplegador usa las herramientas proporcionadas por el servidor EJB para abrir el fichero JAR y leer el ficher XML descriptor del despliegue. La información de este fichero se usa para configurar la conducta en tiempo de ejecución del enterprise bean y distintos elementos relacionados con el servidor. El enterprise bean se despliega en un contenedor, que es el nombre que recibe la parte del servidor de aplicaciones que almacena instancias de enterprise beans. El contenedor se responsabiliza de gestionar las transacciones, seguridad, concurrencia, persistencia y recursos que usa el enterprise bean en tiempo de ejecución. Además, el contenedor genera los proxies EJBHome y EJBObject que implementan las interfaces home y remota del bean (los stub, usando la terminología de RMI). Estos proxies proporcionan a los clientes Java distribuidos que se encuentran en la capa de presentación un acceso a los enterprise beans de la capa intermedia.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/sesion23.png" alt="" data-size="original"></p><p>Los clientes Java usan JNDI para obtener una referencia remota al EJBHome de un enterprise bean. Después usa el EJBHome para crear o encontrar enterprise beans específicos en el contenedor EJB. Cuando lo consigue, recibe una referencia remota a un EJBObject. El EJBObject implementa la interfaz remota del enterprise bean.</p><p>Los clientes Java acceden al enterprise bean a través de sus proxies remotos EJBHome y EJBObject, en lugar de directamente. El contenedor EJB intercepta las invocaciones de los métodos realizadas sobre los proxies remotos, de forma que pueda manejar el entorno de ejecución del bean asociado con la invocación. Las invocaciones de métodos sobre el EJBHome hacen que el contenedor localice o cree una instancia del bean y proporcione una referencia remota EJBObject del mismo al cliente. Las invocaciones de métodos sobre el EJBObject se delegan a una instancia del enterprise bean, que contiene la lógica de negocio necesaria para dar servicio a la petición. El contenedor EJB puede usar muchas instancias de la clase enterprise bean para dar soporte a los clientes, lo cual permite que sobrellevar incrementos puntuales de carga de clientes aumentando el número de instancias gestionandas e incluso construyendo clusters de contenedores y distribuyendo las instancias.</p><p>A continuación explicamos un poco más cada uno de los componentes del bean, dando también indicaciones de nomenclatura de los nombres de ficheros. Usaremos como ejemplo el bean HelloWorldEJB.</p><h4>Interfaz remota o local</h4><p>La interfaz remota (<code>HelloWorld.java</code>) o local (<code>HelloWorldLocal.java</code>) del bean son las interfaces que definen los métodos de acceso que un enterprise bean ofrece a sus clientes. Estas interfaces pueden definir un acceso remoto al bean, usando la interfaz Remote de RMI, o pueden definir un acceso local al bean para aquellos casos en que el bean va a ser usado por clientes en la misma máquina virtual Java. Esta interfaz será implementada por los métodos de negocio que se definen en el fichero de definición de la clase del bean y por el contenedor EJB, que añade los aspectos del nivel de sistema.</p><pre><code>HelloWorld.java

  package HelloWorldSLBean;

  import java.rmi.*;
  import javax.ejb.*;

  public interface HelloWorld extends EJBObject {
     public String sayHello() throws RemoteException;
}

 HelloWorldLocal.java

   package HelloWorldSLBean;

   import java.rmi.*;
   import javax.ejb.*;

   public interface HelloWorldLocal extends EJBLocalObject {
      public String hi() throws EJBException;
}
</code></pre><h4>Interfaz Home</h4><p>La interfaz home (<code>HelloWorldHome.java</code>) o la interfaz home local (<code>HelloWorldHomeLocal.java</code>) son las interfaces que definen los métodos de gestión del ciclo de vida de las instancias del bean. Si recordamos el módulo de RMI, esta interfaz es lo que en RMI se denomina una <em>clase factoría</em>. Algunos ejemplos de métodos de esta interfaz son los métodos <code>create</code>, <code>remove</code> o <code>findByPrimaryKey</code> que crean, eliminan o buscan una instancia de bean. Esta interfaz es implementada por el contenedor EJB. La interfaz home también puede ser remota o local, dependiendo si el acceso al bean va a ser desde otra máquina virtual Java o desde la misma.</p><pre><code>HelloWorldHome.java

  package HelloWorldSLBean;

  import java.rmi.*;
  import javax.ejb.*;
 
  public interface HelloWorldHome extends EJBHome {
     public HelloWorldRemote create() throws RemoteException, CreateException;
  }

HelloWorldHomeLocal.java

  package HelloWorldSLBean;

  import java.rmi.*;
  import javax.ejb.*;

  public interface HelloWorldHomeLocal extends EJBLocalHome {
    public HelloWorld create() throws CreateException, EJBException;
  }
</code></pre><h4>Clase enterprise bean</h4><p>La clase enterprise bean (<code>HelloWorld.java</code>) implementa los métodos de negocio del bean. El fichero es el mismo, independientemente de que la implementación del bean sea local o remota.</p><pre><code>HelloWorldBean.java

  package HelloWorldSLBean;

  import javax.ejb.*;
 
  public class HelloWorldBean implements SessionBean {
     public String sayHello() {
        String ret = new String("Hola; soy Domingo");
        return ret;
     }
   
     public void ejbCreate(){}
     public void ejbActivate(){}
     public void ejbPassivate(){}
     public void ejbRemove(){}
     public void setSessionContext(SessionContext cntx) {}
  }
</code></pre><h4>Fichero XML descriptor del despliegue</h4><p>El fichero de descripción del despliegue (<code>ejb-jar.xml</code>) es el fichero XML que especifica información declarativa sobre el enterprise bean que será usada por el contenedor EJB para manejar los aspectos de nivel de sistema (seguridad, transacciones, persistencia, etc.).</p><pre><code>ejb-jar.xml

  &#x3C;?xml version="1.0" encoding="UTF-8"?>
  &#x3C;!DOCTYPE ejb-jar PUBLIC
  '-//Sun Microsystems, Inc.//DTD Enterprise JavaBeans 1.1//EN'
  'http://java.sun.com/j2ee/dtds/ejb-jar_1_1.dtd'>
 
  &#x3C;ejb-jar>
  &#x3C;display-name>Hello World&#x3C;/display-name>
  &#x3C;enterprise-beans>
  &#x3C;session>
  &#x3C;description>Hello World EJB&#x3C;/description>
  &#x3C;display-name>HelloWorld&#x3C;/display-name>
  &#x3C;ejb-name>HelloWorldEJB&#x3C;/ejb-name>
  &#x3C;home>HelloWorldSLBean.HelloWorldHome&#x3C;/home>
  &#x3C;remote>HelloWorldSLBean.HelloWorld&#x3C;/remote>
  &#x3C;ejb-class>HelloWorldSLBean.HelloWorldBean&#x3C;/ejb-class>
  &#x3C;session-type>Stateless&#x3C;/session-type>
  &#x3C;transaction-type>Container&#x3C;/transaction-type>
  &#x3C;/session>
  &#x3C;/enterprise-beans>
  &#x3C;/ejb-jar>
</code></pre><h4>Fichero EJB JAR que empaqueta el bean</h4><p>Como hemos visto en el tema anterior, todos los ficheros que constituyen el bean se empaquetan en un único fichero con la utilidad JAR. La estructura del fichero JAR es:</p><pre><code>/META-INF/ejb-jar.xml
/META-INF/weblogic-ejb-jar.xml
/HelloWorldSLBean/HelloWorld.class
/HelloWorldSLBean/HelloWorldHome.class
/HelloWorldSLBean/HelloWorldBean.class
</code></pre><p>En el directorio META-INF se incluyen los ficheros de descripción del despliegue: el fichero estándar (ejb-jar.xml) y el personalizado para el servidor de aplicaciones (weblogic-ejb-jar.xml). La mayoría de servidores EJB proporcionan herramientas gráficas que crean el fichero de descripción y empaquetan el bean de forma automática. El resto de directorio comprende los paquetes que definen beans.</p><h3>2.3 Aplicaciones clientes</h3><h4>2.3.1 Cliente Java</h4><p>Un cliente puede acceder a un bean de sesión o bean de entidad a través de los métodos definidos en las interfaces del bean. Estas interfaces definen la vista que el cliente tiene del bean. El resto de aspectos del bean, como implementaciones de los métodos, características definidas por los descriptores de despliegue, esquemas abstractos o llamadas de acceso a las bases de datos, se esconden de los clientes.</p><p>Los clientes que acceden a los enterprise beans pueden ser aplicaciones Java usando JNDI y Java RMI-IIOP, componentes Web (páginas JSP o servlets) o también otros beans. En todos los casos el funcionamiento es el mismo:</p><ul><li>En primer lugar se obtiene un contexto JNDI del contenedor EJB.</li><li>Después se debe localizar en este contexto la interfaz Home del bean, que implementa los métodos de búsqueda y creación de beans.</li><li>Una vez obtenido el objeto de la interfaz <code>home</code> del bean, se invoca el método <code>create</code> (para obtener una instancia nueva del bean) o <code>findByPrimaryKey</code> (para obtener una instancia concreta, en el caso de un bean de entidad). Estos métodos devuelven un objeto que implementa la clase <code>Remote</code> de Java RMI.</li><li>Una vez obtenido el objeto remoto que hace referencia al bean, ya se puede invocar cualquier operación definida en su interfaz remota.<br></li></ul><p>Es fundamental esforzarse en realizar un buen diseño de las interfaces. El desarrollo y el mantenimiento de las aplicaciones J2EE dependen de ello. Unos interfaces limpios y claros permitirán ocultar a las aplicaciones clientes las complejidades internas de la capa EJB y también permitirán internamente cambiar la implementación de los beans sin afectar a esas aplicaciones. Por ejemplo, si se cambia el método de persistencia de persistencia gestionada por el bean a persistencia gestionada por el contenedor, no será necesario modificar el código de las aplicaciones clientes. Pero si se cambia la definición de los métodos de las interfaces, entonces será necesario modificar también el código de las aplicaciones clientes. Por ello, para aislar las aplicaciones clientes de posibles cambios en los beans, es importante que se diseñen las interfaces de forma cuidadosa.</p><pre><code>HelloWorldClient.java

  mport java.io.*;
  import java.text.*;
  import java.util.*;
  import javax.servlet.*;
  import javax.servlet.http.*;
  import javax.naming.*;
  import javax.rmi.*;
 
  public class HelloWorldClient {
 
     public static void main(String [] args) {
        try {
           Context jndiContext = getInitialContext();
           Object ref = jndiContext.lookup("HelloWorldEJB");
           HelloWorldRemoteHome home = (HelloWorldRemoteHome)
           PortableRemoteObject.narrow(ref, HelloWorldRemoteHome.class);
           HelloWorldRemote hw = home.create();
           System.out.println("Voy a llamar al bean");
           System.out.println(hw.sayHello());
           System.out.println("Ya he llamado al bean");
        } catch (Exception e) {e.printStackTrace();}
  }

  public static Context getInitialContext()
  throws javax.naming.NamingException {
     Properties p = new Properties();
     p.put(Context.INITIAL_CONTEXT_FACTORY, "weblogic.jndi.WLInitialContextFactory");
     p.put(Context.PROVIDER_URL, "t3://localhost:7001");
     return new javax.naming.InitialContext(p);
  }
}
</code></pre><h4>2.3.2 Clientes Web: Servlet y JSP</h4><p>La diferencia fundamental entre un cliente Web (Servlet y JSP) y un cliente Java es que, en general, los clientes web se ejecutan en el mismo servidor de aplicaciones en donde reside en el EJB. Por ello, cambia la forma de localizar el bean: en lugar de usar el contexto genérico JNDI, se usa un contexto específico llamado JNDI ENC (Environment Naming Context). Para colocar una referencia al bean en este contexto se usa la entrada &#x3C;ejb-ref> en el fichero de descripción de despliegue de la aplicación web.</p><pre><code>HelloWorldServlet.java

import java.io.*;
import java.text.*;
import java.util.*;
import javax.servlet.*;
import javax.servlet.http.*;
import javax.naming.*;
import javax.rmi.*;
import HelloWorldSLBean.*;

public class HelloWorldServlet extends HttpServlet {
private HelloWorld hw = null;
public HelloWorldServlet() throws NamingException {
  try {
     Context jndiContext = getInitialContext();
     Object ref = jndiContext.lookup("java:comp/env/ejb/HelloWorldEJB");
     HelloWorldHome home = (HelloWorldHome) 
     PortableRemoteObject.narrow(ref, HelloWorldHome.class);
     this.hw = home.create();
  } catch (java.rmi.RemoteException re){re.printStackTrace();}
    catch (javax.naming.NamingException ne){ne.printStackTrace();}
    catch (javax.ejb.CreateException ce){ce.printStackTrace();}
  }

public void doGet(HttpServletRequest request, HttpServletResponse response)
  throws IOException, ServletException {
  response.setContentType("text/html");
  PrintWriter out = response.getWriter();
  out.println("&#x3C;html>");
  out.println("&#x3C;head>");
  out.println("&#x3C;title>Hola&#x3C;/title>");
  out.println("&#x3C;/head>");
  out.println("&#x3C;body bgcolor=\"white\">");
  out.println("&#x3C;h1> HelloWorldEJB dice: ");
  out.println(this.hw.hi());
  out.println("&#x3C;/h1>");
  out.println("&#x3C;/body>");
  out.println("&#x3C;/html>");
  }

public static Context getInitialContext()
  throws javax.naming.NamingException {
  Properties p = new Properties();
  return new javax.naming.InitialContext(p);
  }
}

HelloWorld.jsp 

&#x3C;%@ page import="HelloWorldSLBean.*, javax.naming.*,
javax.rmi.PortableRemoteObject,java.rmi.RemoteException,
javax.ejb.CreateException" %>
&#x3C;% response.addHeader("Cache-Control", "no-cache, must-revalidate"); %>
&#x3C;%@ include file="CommonFunctions.jsp" %>

&#x3C;%!
  HelloWorld helloWorld = null;
%>

&#x3C;html>
&#x3C;head>
&#x3C;title>HelloWorld>&#x3C;/title>
&#x3C;/head>
&#x3C;body bgcolor="#ffffff" LEFTMARGIN="10" RIGHTMARGIN="10"
  link="#3366cc" vlink="#9999cc" alink="#0000cc">

&#x3C;%
  try {
     Context jndiContext = getInitialContext();
     Object ref = jndiContext.lookup("java:comp/env/ejb/HelloWorldEJB");
     HelloWorldHome home = (HelloWorldHome)
     PortableRemoteObject.narrow(ref,HelloWorldHome.class);
     helloWorld = home.create();
  } catch (Throwable t) {
  t.printStackTrace();
  out.print(t.getMessage()+"&#x3C;br>Stacktrace:&#x3C;br>");
  t.printStackTrace(new PrintWriter(out,true));
  }
%>

&#x3C;h1> HelloWorld bean dice: &#x3C;%= helloWorld.hi()%> &#x3C;/h1>

&#x3C;/body>
&#x3C;/html>

web.xml

&#x3C;web-app>
&#x3C;display-name>Hello World&#x3C;/display-name>
  &#x3C;description>Hello World&#x3C;/description>

&#x3C;servlet>
  &#x3C;servlet-name>HelloWorldJSP&#x3C;/servlet-name>
  &#x3C;jsp-file>HelloWorld.jsp&#x3C;/jsp-file>
&#x3C;/servlet> 

&#x3C;servlet>
   &#x3C;servlet-name>HelloWorldServlet&#x3C;/servlet-name>
   &#x3C;servlet-class>HelloWorldServlet&#x3C;/servlet-class>
&#x3C;/servlet>
 
&#x3C;servlet-mapping>
   &#x3C;servlet-name>HelloWorldServlet&#x3C;/servlet-name>
   &#x3C;url-pattern>/HolaMundo&#x3C;/url-pattern>
&#x3C;/servlet-mapping>
 
&#x3C;servlet-mapping>
   &#x3C;servlet-name>HelloWorldJSP&#x3C;/servlet-name>
   &#x3C;url-pattern>/HolaMundo.jsp&#x3C;/url-pattern>
&#x3C;/servlet-mapping>
...
 
&#x3C;ejb-ref>
  &#x3C;ejb-ref-name>ejb/HelloWorldEJB&#x3C;/ejb-ref-name>
  &#x3C;ejb-ref-type>Session&#x3C;/ejb-ref-type>
  &#x3C;home>HelloWorldSLBean.HelloWorldHome&#x3C;/home>
  &#x3C;remote>HelloWorldSLBean.HelloWorld&#x3C;/remote>
&#x3C;/ejb-ref>
&#x3C;/web-app>

weblogic.xml

&#x3C;weblogic-web-app>
  &#x3C;reference-descriptor>
   &#x3C;ejb-reference-description>
    &#x3C;ejb-ref-name>ejb/HelloWorldEJB&#x3C;/ejb-ref-name>
     &#x3C;jndi-name>HelloWorldEJB&#x3C;/jndi-name>
   &#x3C;/ejb-reference-description>
  &#x3C;/reference-descriptor>
&#x3C;/weblogic-web-app>
 
</code></pre><h3>2.4 Acceso remoto y local a los beans</h3><p>Al diseñar aplicaciones J2EE, una de las primeras decisiones que hay que tomar es el tipo de acceso que van a utilizar en los beans: remoto o local.</p><h4>2.4.1. Acceso remoto</h4><p>Un cliente remoto de un enterprise bean tiene las siguientes características</p><ul><li>Puede correr en una máquina física distinta o en una máquina virtual Java (JVM) distinta de aquella en la que se encuentra el bean al que está accediendo.</li><li>Puede ser un componente Web, una aplicación cliente J2EE o también otro enterprise bean.<br></li></ul><p>Para crear un enterprise bean con un acceso remoto es necesario codificar una interfaz remota y una interfaz home. La <em>interfaz remota</em> define los métodos de negocio que podrán ser respondidos por las instancias del bean. Por ejemplo, la interfaz remota de un bean llamado CuentaBancariaEJB podría tener métodos de negocio como transferir o credito. La <em>interfaz home</em> proporciona los métodos necesarios para gestionar el ciclo de vida de las instancias del bean, como create y remove. Para los beans de entidad, la interfaz home también define métodos de búsqueda y métodos home (equivalentes a los métodos de clase en Java). Los métodos de búsqueda se usan para localizar instancias de beans de entidad a partir de su clave primaria. Los métodos home son métodos de negocio cuya invocación afecta a todas las instancias de un bean.</p><h4>2.4.2 Acceso local</h4><p>Un cliente local tiene estas características:<br></p><ul><li>Debe correr en la misma JVM que el bean al que está accediendo.</li><li>Puede ser un componente Web o también otro enterprise bean.</li><li>Para el cliente local, la localización del enterprise bean al que está accediendo no es transparente.</li><li>A menudo el cliente local es otro bean de entidad que tienen una relación gestionada por el contenedor con otro bean de entidad.<br></li></ul><p>Al igual que en el acceso remoto, para construir un enterprise bean que permita acceso local se debe codificar la interfaz local y la interfaz home local. La interfaz local define los métodos de negocio del bean y la interfaz home local los métodos que gestionan el ciclo de vida de las instancias del bean.</p><h4>2.4.3. Interfaces locales y relaciones gestionadas por el contenedor</h4><p>Si un bean de entidad es el objetivo de una relación gestionada por el contenedor, entonces debe tener una interfaz local. La dirección de la relación determina si un bean es un objetivo o no lo es. En la figura 2.1, por ejemplo, <code>ProductoEJB</code> es el objetivo de una relación unidireccional con <code>LineaPedidoEJB</code>. Debido a que <code>LineaPedidoEJB</code> accede a <code>ProductoEJB</code> localmente, <code>ProductoEJB</code> debe tener una interfaz local. El bean <code>LineaPedidoEJB</code> también necesita una interfaz local ya que es el objetivo de una relación con <code>PedidoEJB</code>. Y como la relación entre <code>LineaPedidoEJB</code> y <code>PedidoEJB</code> es bidireccional ambos beans deben tener interfaces locales.</p><p>Todos los beans que participan en un grupo de relaciones manejadas por el contenedor deben residir en el mismo fichero JAR, ya que todos requieren interfaces locales.</p><p>El beneficio principal de las interfaces locales es una mejora en la eficiencia de las invocaciones entre beans, debido a que los parámetros no tienen que serializarse.</p><p> Ejercicios sesión 2</p><h3>Ejercicio 1: Compilación, despliegue y prueba de una aplicación web que usa un bean de sesión sin estado</h3><h4>Pasos previos</h4><p>Antes de realizar el ejercicio, vamos a asegurarnos de que todo está configurado correctamente:</p><ul><li>El dominio <code>moduloejb</code> debe estar creado. Compruébalo mirando si existe un directorio con ese nombre en el directorio <code>bea/user_projects</code>.</li><li><p>Actualiza la variable <code>CLASSPATH</code>:</p><pre><code>% export PATH=$PATH:/home/j2ee/bea/weblogic700/server/bin
% . setWLSEnv.sh
% export CLASSPATH=$CLASSPATH:.
</code></pre></li><li>Descarga el fichero ZIP con el código fuente del ejercicio (<code>ejercicio2.zip</code>) en el directorio de trabajo <code>/home/j2ee/ejb</code></li></ul><h4>Compilación y creación del fichero JAR con el bean</h4><p>Al descomprimir el fichero ZIP debes tener la siguiente estructura de ficheros:</p><pre><code>HelloWorldWeb/jsp/CommonFunctions.jsp
HelloWorldWeb/jsp/HelloWorld.jsp

HelloWorldWeb/src/HelloWorldServlet.java
HelloWorldWeb/src/HelloWorldSLBean/HelloWorld.java 
HelloWorldWeb/src/HelloWorldSLBean/HelloWorldBean.java 
HelloWorldWeb/src/HelloWorldSLBean/HelloWorldHome.java 

HelloWorldWeb/xml/application.xml
HelloWorldWeb/xml/ejb-jar.xml 
HelloWorldWeb/xml/web.xml
HelloWorldWeb/xml/weblogic-application.xml
HelloWorldWeb/xml/weblogic-ejb-jar.xml 
HelloWorldWeb/xml/weblogic.xml 
</code></pre><p>1. Compila los ficheros del bean:</p><pre><code>% cd HelloWorldWeb/src
% javac HelloWorldSLBean/*.java
</code></pre><p>2. Crea el fichero EJB JAR</p><pre><code>% cd ..
% mkdir jar-ejb
% cd jar-ejb
% mkdir META-INF
% cp ../xml/ejb-jar.xml META-INF
% cp ../xml/weblogic-ejb-jar.xml META-INF
% mkdir HelloWorldSLBean
% cp ../src/HelloWorldSLBean/*.class HelloWorldSLBean 
% jar cvf helloworld-ejb.jar *
manifest agregado
agregando: META-INF/ejb-jar.xml
agregando: META-INF/weblogic-ejb-jar.xml
agregando: HelloWorldSLBean/HelloWorld.class
agregando: HelloWorldSLBean/HelloWorldBean.class
agregando: HelloWorldSLBean/HelloWorldHome.class
</code></pre><p>3. Compila el servlet</p><pre><code>% cd ../src
% javac HelloWorldServlet.java
</code></pre><p>4. Crea el fichero WAR JAR con la aplicación web</p><pre><code>% cd ..
% mkdir jar-war
% cd jar-war
% mkdir WEB-INF
% cp ../xml/web.xml WEB-INF
% cp ../xml/weblogic.xml WEB-INF
% cp ../jsp/* .
% mkdir WEB-INF/classes
% mkdir WEB-INF/classes/HelloWorldSLBean
% cp ../src/HelloWorldSLBean/HelloWorld.class WEB-INF/classes/HelloWorldSLBean/
% cp ../src/HelloWorldSLBean/HelloWorldHome.class WEB-INF/classes/HelloWorldSLBean/
% cp ../src/HelloWorldServlet.class WEB-INF/classes
% jar cvf helloworld.war *
manifest agregado
agregando: CommonFunctions.jsp
agregando: HelloWorld.jsp
agregando: WEB-INF/
agregando: WEB-INF/classes/
agregando: WEB-INF/classes/HelloWorldServlet.class
agregando: WEB-INF/classes/HelloWorldSLBean/
agregando: WEB-INF/classes/HelloWorldSLBean/HelloWorld.class
agregando: WEB-INF/classes/HelloWorldSLBean/HelloWorldHome.class
agregando: WEB-INF/web.xml
agregando: WEB-INF/weblogic.xml
</code></pre><p>5. Por último, vamos a crear el fichero JAR con la aplicación (fichero EAR):</p><pre><code>% cd ..
% mkdir jar-ear
% cd jar-ear
% mkdir META-INF
% cp ../xml/application.xml META-INF
% cp ../xml/weblogic-application.xml META-INF
% cp ../jar-ejb/helloworld-ejb.jar .
% cp ../jar-war/helloworld.war .
% jar cvf helloworld.ear *
manifest agregado
agregando: META-INF/
agregando: META-INF/application.xml
agregando: META-INF/weblogic-application.xml
agregando: helloworld-ejb.jar
agregando: helloworld.war
</code></pre><h4>Desplegar la aplicación</h4><p>1. Arranca el servidor de aplicaciones instalado en el ejercicio 1 de la sesión anterior</p><p>2. Usando la consola de administración, elimina el EJB HelloWorld existente (si es que hubiera alguno).</p><p>3. Despliega la aplicación. Importante: hazlo sin subir el fichero al servidor de aplicaciones, porque ya lo tienes allí:</p><ul><li>Selecciona la opción <em>Applications > Configure new a new Application</em>.</li><li>Muévete por el árbol de directorios y selecciona el fichero helloworld.ear</li></ul><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/ejercicio12.png" alt="" data-size="original"></p><p><strong>Probar la aplicación</strong></p><p>1. Prueba el servlet y la página JSP</p><pre><code>http://localhost:7001/HelloWorld/HolaMundo
http://localhost:7001/HelloWorld/HolaMundo.jsp
</code></pre><p>2. Compila el cliente y pruébalo.</p><pre><code>% cd src
% javac HelloWorldClient.java
% java HelloWorldClient
</code></pre><h3>Ejercicio 2: cambiar algunos descriptores del despliegue</h3><h4>URLs de la aplicación</h4><p>1. Las URL públicas de la aplicación se encuentran definidas en los elementos <code>url-pattern</code> del fichero de despliegue de la aplicación web (<code>web.xml</code>). El directorio raíz de la aplicación se encuentra definido en el elemento <code>context-root</code> del fichero de descripción del despliegue <code>application.xml</code>.</p><p>2. Cambia el nombre de estos elementos para que el acceso al servlet y a la página JSP se a las siguientes direcciones</p><pre><code>http://localhost:7001/hw/hw
http://localhost:7001/hw/hw.jsp
</code></pre><p>3. Reconstruye los ficheros <code>helloworld.war</code> y <code>helloworld.ear</code> y redespliega la aplicación. Pruébala para asegurarte que funciona correctamente.</p><h4>Referencias a beans en la aplicación web</h4><p>1. En la aplicación web se accede al bean HelloWorld de forma indirecta, usando la dirección <code>java:comp/env/ejb/HelloWorldEJB</code> del espacio local de nombres JNDI ENC. Esto permite definir de forma declarativa el enlace entre la aplicación y el bean hasta el momento del despliegue y cambiar el mismo sin tener que recompilar el EJB.</p><ul><li>La definición de qué EJB concreto se liga a la dirección <code>ejb/HelloWorldEJB</code> se realiza en el fichero <code>weblogic.xml</code>, asociando un nombre JNDI concreto a esa dirección.</li><li>La definición del nombre JNDI del bean HelloWorld se realiza en el fichero <code>weblogic-ejb-jar.xml</code>.</li></ul><p>2. Cambia el nombre JNDI del bean y llámalo <code>HW</code>, ahora usando la consola de administración (seleccionando el bean <em>HelloWorld</em> y pulsando en la opción <em>Edit EJB Descriptor</em>). En el árbol con los elementos XML de la ventana del navegador que se acaba de abrir despliega la opción <em>WebLogic EJB JAR</em> y luego <em>Weblogic Enterprise Beans</em>. Pincha en el bean y cambia su nombre JNDI. Pincha en el padre de todo el árbol de elementos XML (con el nombre <em>helloworld-ejb.jar</em>) y pulsa la opción <em>Persist</em>. De esta forma se habrá guardado en el fichero de descripción del despliegue el nuevo nombre JNDI del bean. Puedes cerrar la ventana del navegador.</p><p>3. Redespliega la aplicación. En la ventana principal de la consola de administración pulsa la opción Applications y selecciona la aplicación <em>HelloWorld</em>. Pulsa la opción <em>Deploy Application</em> para volver a desplegar la aplicación.</p><p><img src="https://expertojavaua.github.io/www.jtech.ua.es/j2ee/2002-2003/modulos/ejb/apuntes/imagenes/ejercicio11.png" alt="" data-size="original"></p><p>4. Prueba ahora cualquiera de las URLs y verás que aparece un error.</p><p>5. Modifica el código fuente de la aplicación cliente para que se conecte al bean con el nuevo nombre JNDI. Recompila y comprueba que ahora sí funciona.</p><p>6. Modifica el nombre JNDI de la referencia <code>ejb/HelloWorldEJB</code> usando también la consola de administración. Graba el cambio con la opción <em>Persist</em> y redespliega la aplicación. Prueba ahora las URLs.</p><p></p><div data-gb-custom-block data-tag="file" data-src="/broken/files/eF2NOu7WSO4Qsdryc9TK"></div><p></p><p>Tema 3. Un ejemplo completo de EJB de sesión con estado</p><blockquote><p>3.1 La clase SessionBean<br>3.2 La interfaz Home<br>3.3 La interfaz Remote<br>3.4 El fichero descriptor del despliegue<br>3.5 Clases de apoyo<br>3.6 El fichero EJB JAR<br>3.7 La aplicación cliente<br>3.8 Otras características de los EJBs</p></blockquote><h2>Tema 3: Un ejemplo completo de bean de sesión con estado</h2><p>Vamos a construir en esta sesión un ejemplo completo de bean de sesión. En concreto, vamos a implementar un bean de sesión con estado que define un carrito de la compra de una librería.</p><p>El bean de sesión <code>CartEJB</code> representa un carrito de la compra de una librería on line. El cliente del bean podrá añadir un libro al carrito, eliminar un libro o consultar el contenido del carrito. Tal y como adelantamos en el tema 2, para construir el enterprise bean <code>CartEJB</code>, se necesitan los siguientes ficheros:<br></p><ul><li>Clase de implementación bean (<code>CartBean</code>)<br></li><li>Interface home (<code>CartHome</code>)<br></li><li>Interface remota (<code>Cart</code>)<br></li></ul><p>El estado del bean va a estar definido por sus variables de instancias. Estas variables de instancia deben declararse en la clase <code>CartBean</code> que implementa la lógica de negocio, y serán actualizadas por los métodos del bean, como consencuencia de la invocación remota del cliente.</p><p>Además de estas clases, vamos a necesitar dos clases de apoyo, la clase <code>BookException</code> y <code>IdVerifier</code>.</p><p>La siguiente tabla muestra cómo están relacionados los métodos en la interface home, la interfaz remota y la implementación.</p><p></p><p>    </p><p></p><p>El código fuente de este ejemplo está en el fichero <code>ejercicio3.zip</code> en la página web del módulo de EJB.</p><h3>3.1 La clase bean de sesión (<code>SessionBean</code>)</h3><p>Siguiendo las indicaciones de nomenclatura que comentamos en la sesión pasada, la clase bean se llama <code>CartBean</code>. Esta clase implementa la lógica de negocio del bean, y debe cumplir los siguientes requisitos:</p><ul><li>Implementa la interfaz <code>SessionBean</code>.<br></li><li>La clase se define como <code>public</code>.<br></li><li>La clase no puede definirse como <code>abstract</code> ni <code>final</code>.<br></li><li>Implementa uno o más métodos <code>ejbCreate</code>.<br></li><li>Implementa los métodos remotos definidos en la interfaz remota del bean.<br></li><li>Contiene un constructor <code>public</code> sin parámetros.<br></li><li>No debe definir el método <code>finalize</code>.<br></li></ul><p>El código fuente sigue a continuación:</p><pre><code>import java.util.*;
import javax.ejb.*;

public class CartBean implements SessionBean {

   String customerName;
   String customerId;
   Vector contents;


   public void ejbCreate(String person) 
      throws CreateException {

      if (person == null) {
         throw new CreateException("Null person not allowed.");
      }
      else {
         customerName = person;
      }

      customerId = "0";
      contents = new Vector();
   }

   public void ejbCreate(String person, String id) 
      throws CreateException {

      if (person == null) {
         throw new CreateException("Null person not allowed.");
      }
      else {
         customerName = person;
      }

      IdVerifier idChecker = new IdVerifier();
      if (idChecker.validate(id)) {
         customerId = id;
      }
      else {
         throw new CreateException("Invalid id: "+ id);
      }

      contents = new Vector();
   }

   public void addBook(String title) {
      contents.addElement(title);
   }

   public void removeBook(String title) throws BookException {

      boolean result = contents.removeElement(title);
      if (result == false) {
         throw new BookException(title + "not in cart.");
      }
   }

   public Vector getContents() {
      return contents;
   }

   public CartBean() {}
   public void ejbRemove() {}
   public void ejbActivate() {}
   public void ejbPassivate() {}
   public void setSessionContext(SessionContext sc) {}

} 
</code></pre><h4>3.1.1 Las variables de instancia</h4><p>Las variables de instancia definen el estado de una instancia de enterprise bean. En este caso se trata de <code>customerName</code>, <code>customerId</code> y <code>contents</code>. Las variables de instancia se inicializan al crearse una instancia del bean, copiándose en ellas los argumentos del método <code>ejbCreate</code>. Después son modificadas por las llamadas de los clientes a los métodos de negocio <code>addBook()</code> y <code>removeBook()</code>.</p><h4>3.1.2 La interfaz <code>SessionBean</code></h4><p>La interfaz <code>SessionBean</code> extiende la interfaz <code>EnterpriseBean</code>, que a su vez extiende el interfaz <code>Serializable</code>. La interfaz <code>SessionBean</code> declare los métodos <code>ejbRemove</code>, <code>ejbActivate</code>, <code>ejbPassivate</code>, y <code>setSessionContext</code>. Estos métodos se llaman desde el contenedor EJB cuando el bean va pasando de un estado a otro en su ciclo de vida. La clase <code>CartBean</code> no usa estos métodos, pero debe implementarlos porque están declarados en la interfaz <code>SessionBean</code>.<br></p><h4>3.1.3 Los métodos <code>ejbCreate</code></h4><p>Un cliente no puede instanciar directamente un bean, ya que éste reside en el contenedor EJB. Sólo el contenedor EJB puede realizar la instanciación. En el ejemplo del carrito de la compra esto sucede de la siguiente forma:<br></p><p>1. El cliente invoca un método <code>create</code> en el objeto <code>home</code>:<br></p><pre><code>Cart shoppingCart = home.create("Duke DeEarl","123");
</code></pre><p>2. El contenedor EJB instancia el enterprise bean.<br>3. El contenedor EJB invoca el método <code>ejbCreate</code> apropiado en <code>CartBean</code>:</p><pre><code>    public void ejbCreate(String person, String id) 
      throws CreateException {

      if (person == null) {
         throw new CreateException("Null person not allowed.");
      }
      else {
         customerName = person;
      }

      IdVerifier idChecker = new IdVerifier();
      if (idChecker.validate(id)) {
         customerId = id;
      }
      else {
         throw new CreateException("Invalid id: "+ id);
      }

      contents = new Vector();
   }
</code></pre><p>Al tratarse de un bean de sesión con estado, el método <code>ejbCreate</code> inicializa este estado. El método <code>ejbCreate</code> anterior, por ejemplo, inicializa las variables <code>customerName</code> y <code>customerId</code> con los argumentos pasados por el método <code>create</code>.</p><p>Un enterprise bean debe tener uno o más métodos <code>ejbCreate</code>. Las signaturas de estos métodos deben cumplir los siguientes requisitos:</p><ul><li>El modificador de control de acceso debe ser <code>public</code>.<br></li><li>El tipo de retorno debe ser <code>void</code>.<br></li><li>Si el bean permite un acceso remoto, los argumentos deben ser tipos legales de RMI.<br></li><li>El modificador no puede ser <code>static</code> ni final.</li></ul><p>La clásula throws puede incluir la excepción <code>javax.ejb.CreateException</code> y cualquier otra excepción específica de la aplicación. El método <code>ejbCreate</code> arroja normalmente una excepción <code>CreateException</code> si un parámetro de entrada no es válido.</p><h4>3.1.4 Métodos de negocio</h4><p>El propósito fundamental de un bean de sesión es ejecutar tareas de negocio a petición de aplicaciones cliente. El cliente invoca métodos de negocio en la referencia remota del objeto que es devuelta por el método <code>create</code>. Desde la perspectiva del cliente, los métodos de negocio parecen ejecutarse de forma local, pero realmente lo que se ejecuta es un método del stub que envía al skeleton (recordatorio de RMI!!) la petición de invocación remota, junto con todo el <em>marshaling</em> de parámetros.</p><p>Un ejemplo del punto de vista del cliente:</p><pre><code>Cart shoppingCart = home.create("Duke DeEarl", "123");
...
shoppingCart.addBook("The Martian Chronicles"); 
shoppingCart.removeBook("Alice In Wonderland");
bookList = shoppingCart.getContents();
</code></pre><p>La clase <code>CartBean</code> implementa los métodos de negocio en el siguiente código:</p><pre><code>public void addBook(String title) {
   contents.addElement(new String(title));
}

public void removeBook(String title) throws BookException {
   boolean result = contents.removeElement(title);
   if (result == false) {
      throw new BookException(title + "not in cart.");
   }
}

public Vector getContents() {
   return contents;
}
</code></pre><p>La signatura de un método de negocio debe cumplir los siguientes requisitos:</p><ul><li>El nombre del método no debe entrar en conflicto con ningún otro definido por la arquitectura EJB. Por ejemplo, un método de negocio no se puede llamar <code>ejbCreate</code> o <code>ejbActivate</code>.<br></li><li>El modificador de control de acceso debe ser <code>public</code>.<br></li><li>Si el bean permite acceso remoto, los argumentos y los tipos devueltos deben ser tipos legales de RMI.<br></li><li>El modificador no puede ser <code>static</code> ni <code>final</code>.<br></li></ul><p>La cláusula <code>throws</code> puede incluir excepciones que se definen en la aplicación. Por ejemplo, el método <code>removeBook</code> arroja la excepción <code>BookException</code> si el libro no está en el carrito.</p><p>Para indicar un problema de nivel de sistema, como la imposibilidad de conectar con una base de datos, un método de negocio debería arrojar una excepción <code>javax.ejb.EJBException</code>. Cuando un método de negocio arroja una excepción <code>EJBException</code>, el contenedor EJB la envuelve en una <code>RemoteException</code>, que es capturada por el cliente. El contenedor no envuelve excepciones de aplicación como <code>BookException</code>. Debido a que <code>EJBException</code> es una subclase de <code>RuntimeException</code>, no es necesario incluirla en la cláusula <code>throws</code> del método de negocio.</p><h3>3.2 La interfaz home<br></h3><p>La interfaz home extiende la interfaz <code>javax.ejb.EJBHome</code>. Para un bean de sesion, el propósito de la interfaz home es definir los métodos <code>create()</code> (puede haber más de uno, dependiendo de los argumentos) que el cliente remoto puede invocar para crear instancias del bean. El cliente <code>CartCliente</code>, por ejemplo, invoca este método <code>create</code></p><pre><code>(Cart shoppingCart = home.create("Duke DeEarl", "123");
</code></pre><p>Por cada método create en la interfaz home debe existir un método <code>ejbCreate</code> correspondiente en la clase de implementación del bean (clase <code>CartBean</code>). En nuestro ejemplo, definíamos dos signaturas de métodos <code>ejbCreate</code>:</p><pre><code>public void ejbCreate(String person) throws CreateException   
... 
public void ejbCreate(String person, String id) 
   throws CreateException 
</code></pre><p>Y el código correspondiente en el fichero <code>CartHome.java</code> es el siguiente:</p><pre><code>import java.io.Serializable;
import java.rmi.RemoteException;
import javax.ejb.CreateException;
import javax.ejb.EJBHome;

public interface CartHome extends EJBHome {
   Cart create(String person) throws 
                  RemoteException, CreateException;
   Cart create(String person, String id) throws 
                  RemoteException, CreateException; 
}
</code></pre><p>Las signaturas de ambos conjuntos de métodos son similares, pero difieren en aspectos importantes. Un resumen de las reglas que debemos aplicar al crear ambas signaturas es el siguiente:</p><ul><li>El número y tipos de argumentos en el método create debe corresponderse con los definidos en el método <code>ejbCreate</code> asociado.<br></li><li>Los tipos de los argumentos y valores devueltos deben ser tipos válidos RMI.<br></li><li>Cuando usemos llamadas remotas, los métodos create de la interfaz home siempre debe devolver el tipo de la interfaz remota del bean. Cuando un cliente invoque este método se le devolverá una referencia remota del bean recién creado. El método <code>ejbCreate</code>, sin embargo, debe devolver <code>void</code>. Es el contenedor EJB el que se encarga de crear el bean, llamar al método <code>ejbCreate</code> y devolver la referencia remota.<br></li><li>La cláusula <code>throws</code> del método <code>create</code> debe incluir las excepciones <code>java.rmi.RemoteException</code> y <code>java.ejb.CreateException</code>.</li></ul><h3>3.3 Interfaz Remote</h3><p>La interfaz remota siempre debe extender la interfaz <code>javax.ejb.EJBObject</code>. Esta interfaz define los métodos de negocio que el cliente remoto puede invocar. A continuación se muestra el código fuente del fichero <code>Cart.java</code>:</p><pre><code>import java.util.*;
import javax.ejb.EJBObject;
import java.rmi.RemoteException;

public interface Cart extends EJBObject {
 
   public void addBook(String title) throws RemoteException;
   public void removeBook(String title) throws 
                     BookException, RemoteException;
   public Vector getContents() throws RemoteException;
}
</code></pre><p>La definición de los métodos en la interfaz remota debe seguir estas reglas:</p><ul><li>Cada método en la interfaz remota debe corresponderse con un método equivalente en la clase del enterprise bean. Las signaturas de ambos deben ser iguales.<br></li><li>Los tipos de los argumentos y valores devueltos deben ser tipos válidos RMI.<br></li><li>La cláusula <code>throws</code> debe incluir la excepción <code>java.rmi.RemoteException</code>.<br></li></ul><h3>3.4 El fichero descriptor del despliegue</h3><p>El fichero <code>ejb-jar.xml</code> se muestra a continuación</p><pre><code>&#x3C;ejb-jar>
  &#x3C;display-name>CartJAR&#x3C;/display-name>
  &#x3C;enterprise-beans>
    &#x3C;session>
      &#x3C;display-name>CartEJB&#x3C;/display-name>
      &#x3C;ejb-name>CartEJB&#x3C;/ejb-name>
      &#x3C;home>CartHome&#x3C;/home>
      &#x3C;remote>Cart&#x3C;/remote>
      &#x3C;ejb-class>CartBean&#x3C;/ejb-class>
      &#x3C;session-type>Stateful&#x3C;/session-type>
      &#x3C;transaction-type>Container&#x3C;/transaction-type>
      &#x3C;security-identity>
        &#x3C;use-caller-identity/>
      &#x3C;/security-identity>
    &#x3C;/session>
  &#x3C;/enterprise-beans>
    ...
&#x3C;/ejb-jar>
</code></pre><p>Y el fichero <code>weblogic-ejb-jar.xml</code> es el siguiente. Los únicos datos que se definen son el nombre del EJB y el nombre JNDI del bean.</p><pre><code>  &#x3C;weblogic-ejb-jar>
     &#x3C;weblogic-enterprise-bean>
        &#x3C;ejb-name>CartEJB&#x3C;/ejb-name>
        &#x3C;stateful-session-descriptor>&#x3C;stateful-session-cache>
        &#x3C;/stateful-session-cache>&#x3C;stateful-session-clustering>
        &#x3C;/stateful-session-clustering>&#x3C;/stateful-session-descriptor>
        &#x3C;transaction-descriptor>&#x3C;/transaction-descriptor>
        &#x3C;jndi-name>CartEJB&#x3C;/jndi-name>
     &#x3C;/weblogic-enterprise-bean>
  &#x3C;/weblogic-ejb-jar>
</code></pre><h3>3.5 Clases de apoyo</h3><p>El bean de sesión CartEJB tiene dos clases de apoyo: <code>BookException</code> y <code>IdVerifier</code>. La excepción <code>BookException</code> es arrojada por el método <code>removeBook</code> y el <code>IdVerifier</code> valida el clienteId en uno de los métodos <code>ejbCreate</code>. Ambas clases deben residir en el mismo fichero JAR en el que se empaqueta todo el enterprise bean.</p><p>A continuación se muestran los códigos de ambas clases:</p><pre><code>public class BookException extends Exception {

    public BookException() {
    }

    public BookException(String msg) {
        super(msg);
    }
}


public class IdVerifier {

    public IdVerifier() {
    }

    public boolean validate(String id) {

       boolean result = true;
       for (int i = 0; i &#x3C; id.length(); i++) {
         if (Character.isDigit(id.charAt(i)) == false)
            result = false;
       }
       return result;
    }
}
</code></pre><h3>3.6 El fichero EJB JAR</h3><p>El fichero EJB JAR tiene la siguiente estructura, sencilla al no usar paquetes en la definición de las clases</p><pre><code>extracted: META-INF/MANIFEST.MF
extracted: BookException.class
extracted: Cart.class
extracted: CartBean.class
extracted: CartHome.class
extracted: IdVerifier.class
  created: META-INF/
extracted: META-INF/ejb-jar.xml
extracted: META-INF/weblogic-ejb-jar.xml
</code></pre><h3>3.7 La aplicación cliente</h3><p>La aplicación cliente compra algunos libros y después elimina algún libro no existente en el carrito, lo que genera un error.</p><pre><code>import java.util.*;
import javax.naming.Context;
import javax.naming.InitialContext;
import javax.rmi.PortableRemoteObject;

public class CartClient {

   public static void main(String[] args) {
       try {
           Context jndiContext = getInitialContext();
           Object objref = jndiContext.lookup("CartEJB");

           CartHome home = 
               (CartHome)PortableRemoteObject.narrow(objref, 
                                            CartHome.class);

           Cart shoppingCart = home.create("Duke DeEarl","123");

           shoppingCart.addBook("The Martian Chronicles");
           shoppingCart.addBook("2001 A Space Odyssey");
           shoppingCart.addBook("The Left Hand of Darkness");
           
           Vector bookList = new Vector();
           bookList = shoppingCart.getContents();

           Enumeration enumer = bookList.elements();
           while (enumer.hasMoreElements()) {
              String title = (String) enumer.nextElement();
              System.out.println(title);
           }

           shoppingCart.removeBook("Alice in Wonderland");
           shoppingCart.remove();

           System.exit(0);

       } catch (BookException ex) {
           System.err.println("Caught a BookException: " + ex.getMessage());
           System.exit(0);
       } catch (Exception ex) {
           System.err.println("Caught an unexpected exception!");
           ex.printStackTrace();
           System.exit(1);
       }
   } 

    public static Context getInitialContext() 
        throws javax.naming.NamingException {
           Properties p = new Properties();
	   p.put(Context.INITIAL_CONTEXT_FACTORY, "weblogic.jndi.WLInitialContextFactory");  
	   p.put(Context.PROVIDER_URL, "t3://localhost:7001");
           return new javax.naming.InitialContext(p);
    }
} 
</code></pre><h3>3.8 Otras características de los enterprise beans</h3><p>Los aspectos que siguen se aplican tanto a beans de sesión como a beans de entidad. Veremos en primer lugar cómo leer desde los beans entradas del entorno que se especifican de forma declarativa en la descripción de despliegue del bean. A continuación revisaremos cómo comparar enterprise beans. Terminaremos comentando cómo pasar al cliente referencias remotas de beans.<br></p><h4>3.8.1 Cómo acceder a entradas del entorno</h4><p>Una <em>entrada del entorno</em> (<em>environment entry</em>) es una pareja nombre-valor que se almacena en el fichero de descripción del despliegue y que permite modificar la lógica de negocio del bean sin cambiar su código fuente ni recompilarlo. El formato con el que se almacena en el fichero <code>ejb-jar.xml</code> es el siguiente</p><pre><code>&#x3C;env-entry>
    &#x3C;description>Discount Level&#x3C;/description>
    &#x3C;env-entry-name>DiscountLevel&#x3C;/env-entry-name>
    &#x3C;env-entry-type>java.lang.Double&#x3C;/env-entry-type>
    &#x3C;env-entry-value>300.0&#x3C;/env-entry-value>
&#x3C;/env-entry>
&#x3C;env-entry>
    &#x3C;description>Discount Percent&#x3C;/description>
    &#x3C;env-entry-name>Discount Percent&#x3C;/env-entry-name>
    &#x3C;env-entry-type>java.lang.Double&#x3C;/env-entry-type>
    &#x3C;env-entry-value>0.15&#x3C;/env-entry-value>
&#x3C;/env-entry>
</code></pre><p>En el ejemplo se han definido las entradas del entorno <code>DiscountLevel</code> y <code>DiscountPercent</code>.</p><p>Una vez desplegado el enterprise bean en el contenedor EJB, estas entradas se almancenan como objetos JNDI en el contexto <code>java:comp/env</code>. Para usar estas entradas en los métodos de negocio del enterprise bean hay que usar JNDI y obtener el contexto de nombres del entorno invocando a <code>lookup</code> del contexto inicial con el parámetro <code>java:comp/env</code>. Luego ya se puede invocar a loockup del contexto de nombres pasándole como parámetro el string que define el nombre de la entrada del entorno.</p><p>El siguiente código proporciona un ejemplo práctico, el método de negocio applyDiscount:</p><pre><code>public double applyDiscount(double amount) {

   try {

      double discount;

      Context initial = new InitialContext();
         Context environment = 
            (Context)initial.lookup("java:comp/env");

      Double discountLevel = 
         (Double)environment.lookup("DiscountLevel");
            Double discountPercent = 
               (Double)environment.lookup("DiscountPercent");

      if (amount >= discountLevel.doubleValue()) {
         discount = discountPercent.doubleValue();
      }
      else {
         discount = 0.00;
      }

      return amount * (1.00 - discount);

   } catch (NamingException ex) {
      throw new EJBException("NamingException: "+
         ex.getMessage());
   }
}
</code></pre><h4>3.8.2 Cómo comparar enterprise beans</h4><p>Un cliente puede determinar si un bean de sesión con estado ya ha sido definido y está residiendo en el contenedor de aplicaciones usando el método <code>isIdentical</code>:</p><pre><code>bookCart = home.create("Bill Shakespeare"); 
videoCart = home.create("Lefty Lee");
...
if (bookCart.isIdentical(bookCart)) { 
   // true ... }
if (bookCart.isIdentical(videoCart)) { 
   // false ... }
</code></pre><p>Debido a que los beans de sesión sin estado siempre tienen la misma identidad como objetos, el método <code>isIdentical</code> siempore devolverá true cuando se comparan.</p><p>Para determinar si dos beans de entidiad son identicos, el cliente puede usar el método isIdentical o puede obtener y comparar las claves primarias de los beans:</p><pre><code>String key1 = (String)accta.getPrimaryKey();
String key2 = (String)acctb.getPrimaryKey();

if (key1.compareTo(key2) == 0)
   System.out.println("equal");
</code></pre><h4>3.8.3 Cómo devolver una referencia a un enterprise bean</h4><p>Supongamos que queremos pasar la referencia de un mismo bean a otro bean, o al cliente que invoca un método de negocio del bean. No podemos usar <code>this</code>, por que apunta a la instancia del bean, que está corriendo en el contenedor EJB.</p><p>Se obtiene llamando al método <code>getEJBObject</code> de la interfaz <code>SessionContext</code>. Un bean de entidad llamaría al método <code>getEJBObject</code> de la interfaz <code>EntityContext</code>. Estas interfaces proporcionan a los beans la posibilidad de acceder a contextos de instancias mantenidos por el contenedor EJB. Normalmente, el bean graba los contextos en el método <code>setSessionContext</code>. El siguiente código muestra un ejemplo de cómo usar estos métodos:</p><pre><code>public class WagonBean implements SessionBean {
   
   SessionContext context;
   ...
   public void setSessionContext(SessionContext sc) { 
      this.context = sc; 
   }
   ...
   public void passItOn(Basket basket) {
   ...
      basket.copyItems(context.getEJBObject()); 
   } 
   ...
</code></pre><p> </p><p></p><p>Tema 4: Un ejemplo completo de EJB de entidad con persistencia gestionada por el bean</p><blockquote><p>4.1 La clase EntityBean<br>4.2 La interfaz Home<br>4.3 La interfaz Remote<br>4.4 El fichero descriptor del despliegue</p></blockquote><p>Tema 5: Beans de entidad con persistencia gestionada por el contenedor</p><blockquote><p>5.1 Introducción<br>5.2 Implementación completa de un EJB de entidad<br>5.3 Campos de persistencia</p></blockquote><p>Tema 6: Relaciones entre beans de entidad</p><blockquote><p>6.1 Definición del bean dependiente<br>6.2 Definiciones en el bean origen de la relación<br>6.3 Actualización de la relación desde los clientes<br>6.4 El modelo abstracto de programación<br>6.5 El esquema abstracto de persistencia<br>6.6 Modelado de la base de datos<br>6.7 Relación uno-a-uno unidireccional<br>6.8 Relación uno-a-uno bidireccional<br>6.9 Relación uno-a-muchos unidireccional</p></blockquote><p>Tema 7: Gestión de transacciones</p><blockquote><p>7.1 Introducción<br>7.2 Alcance de una transacción<br>7.3 Atributos de una transacción<br>7.4 Propagación de una transacción<br>7.5 Relaciones basadas en colecciones y transacciones</p></blockquote><p>Tema 8: Seguridad</p><blockquote><p>8.1 Introducción a la seguridad en los EJBs<br>8.2 Control de acceso basado en roles<br>8.3 Métodos no chequeados<br>8.4 La identidad de seguridad runAs</p></blockquote><p>Tema 9: Buenas prácticas con EJBs</p><blockquote><p>9.1 Buenas prácticas de diseño<br>9.2 Buenas prácticas de implementación<br>9.3 Buenas prácticas de despliegue y prueba</p></blockquote></td></tr></tbody></table>

<table><thead><tr><th width="68"></th><th width="137">Método de la interfaz home</th><th width="149">Método de la interfaz remota</th><th width="194">Método de la clase de implementación</th></tr></thead><tbody><tr><td>Creación</td><td><code>Cart create(args) throws CreateException, RemoteException;</code></td><td>No disponible</td><td><code>public void ejbCreate(args)</code></td></tr><tr><td>Uso</td><td>No disponible</td><td>Métodos de negocio (deben arojar la excepción RemoteException)</td><td>Métodos de negocio con la misma signatura (arrojar RemoteException es opcional)</td></tr><tr><td>Borrado</td><td><code>public void remove();</code></td><td><code>public void remove()</code></td><td><code>public void ejbRemove();</code></td></tr></tbody></table>

<table><thead><tr><th width="68"></th><th width="137">Método de la interfaz home</th><th width="149">Método de la interfaz remota</th><th width="194">Método de la clase de implementación</th></tr></thead><tbody><tr><td>Creación</td><td><code>Cart create(args) throws CreateException, RemoteException;</code></td><td>No disponible</td><td><code>public void ejbCreate(args)</code></td></tr><tr><td>Uso</td><td>No disponible</td><td>Métodos de negocio (deben arojar la excepción RemoteException)</td><td>Métodos de negocio con la misma signatura (arrojar RemoteException es opcional)</td></tr><tr><td>Borrado</td><td><code>public void remove();</code></td><td><code>public void remove()</code></td><td><code>public void ejbRemove();</code></td></tr></tbody></table>

| Espeficiación EJB | Fecha          | Principales novedades                                                                                                                                                                                                                         |
| ----------------- | -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| EJB 1.0           | Marzo 1998     | Propuesta inicial de la arquitectura EJB. Se introducen los beans de sesión y los de entidad (de implementación opcional). Persistencia manejada por el contendedor en los beans de entidad. Manejo de transacciones. Manejo de seguridad.    |
| EJB 1.1           | Diciembre 1999 | Implementación obligatoria de los beans de entidad. Acceso al entorno de los beans mediante JNDI.                                                                                                                                             |
| EJB 2.0           | Agosto 2001    | Manejo de mensajes con los beans dirigidos por mensajes. Relaciones entre beans manejadas por el contenedor. Uso de interfaces locales entre beans que se encuentran en el mismo servidor. Consultas de beans declarativas, usando el EJB QL. |
| EJB 2.1           | Agosto 2002    | Soporte para servicios web. Temporizador manejado por el contenedor de beans. Mejora en el EJB QL.                                                                                                                                            |
