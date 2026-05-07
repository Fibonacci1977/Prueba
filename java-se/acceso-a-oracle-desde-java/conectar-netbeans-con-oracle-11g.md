# Conectar NetBeans con Oracle 11g

Hola, por un proyecto en el cual me encuentro trabajando tuve la necesidad de acceder a una base de datos Oracle (oracle 11g).

Bueno ahí les dejo los tips.

Antes de iniciar el proyecto asegúrense de tener instalado el Oracle 11g express y el archivo ojdbc6.jar ([http://www.oracle.com/technetwork/apps-tech/jdbc-112010-090769.html](http://www.oracle.com/technetwork/apps-tech/jdbc-112010-090769.html)), el cual debe copiarlo en la carpeta domain1 de su glassfish (algo así como copiaron el .jar para SQL.).

**Crear el proyecto**

Crean un proyecto Enterprise Application al cual llamaremos WebHROracle![screenshot\_1](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_1.png?w=1000)

![screenshot\_2](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_2.png?w=1000)

![screenshot\_3](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_3.png?w=1000)

Hasta aquí lo único relacionado con Oracle es el nombre del proyecto.

![screenshot\_4](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_4.png?w=1000)

**Configuración de Framework**

En este caso como en todos lo ejemplos vamos a utlizar el framework «JavaServer Faces», así que seleccionamos el proyecto WebHROracle-war (**OJO SELECCIONAR EL WAR**), presionamos con el click derecho y seleccionamos Properties (Propiedades).

Seleccionamos la categoria FRAMEWORKS y pulsamo el boton «Add…», el cual mostrara una ventana con la lista del los frameworks disponibles, nosotros elegiremos JavaServer Faces y presionamos OK.

![screenshot\_5](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_5.png?w=1000)

Una vez hecho esto en la parte inferior de la ventana de propiedades debemos selecionar la pestaña Components, marcamos con check PrimeFaces y presionamos el boton «More…»

Esto abrirá otra ventana en la que elegiremos PrimeFaces 5.0 (en Primefaces Library) si no aparece PrimeFaces 5.0 esperamos un momento hasta que aparece damos OK.

![screenshot\_6](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_6.png?w=1000)

**Unidad de Persistencia**&#x20;

Seleccionar el proyecto EJB, click derecho, opción nuevo, opcion Otros…

![screenshot\_7](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_7.png?w=1000)

en filter digitamos persistence, seleccionamos el tipo de Archivo «Persistence Unit» y presionomas Next.

![screenshot\_8](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_8.png?w=1000)

y Finish.

Hasta aquí no seleccionaremos DataSource porque aun no ha sido creado.

**Estos se realizara en la consola de administración de GlassFish.**

![screenshot\_9](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_9.png?w=1000)

**Creación del Pool de Conexiones**

Desde NetBeans seleccionamos Servers / GlassFish Server, ahí presionamos click derecho y elegimos la opción View Domain Admin Console.

![screenshot\_10](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_10.png?w=1000)

En la consola de Glassfish, ingresamos a Resource \ JDBC \ JDBC Connection Pools, y en el lado derecho se mostrar la lista de todas las conexiones creadas.

Presionamos el boton New…

![screenshot\_11](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_11.png?w=1000)

Digitamos lo siguiente:

Pool Name: pool\_oracle

Resource Type: javax.sql.DataSource

Database Driver Vendor : Oracle

y presionamos Next.

![screenshot\_40](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_40.png?w=1000)

En la siguiente pantalla, nos dirigimos hasta la parte inferior donde se encuentras las propiedades adicionales para la conexión.

![screenshot\_13](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_13.png?w=1000)

Estas propiedades básicas se requieren para lograr la conexión.

![screenshot\_41](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_41.png?w=1000)

Luego nos dirigimos a la opción JDBC Resource y presionamos el boton New…

![screenshot\_15](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_15.png?w=1000)

Y digitamos lo siguiente:

JNDI Name : jdbc/oracle

Pool Name: pool\_oracle (que es el nombre de nuestro pool de conexiones)

Presionamos Ok.

![screenshot\_42](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_421.png?w=1000)

**Configurando archivo de Persistencia**

Regresamos al proyecto EJB y abrimos el archuvo persistence.xml ubicado en la carpeta Configuration Files.

al abrir el arhcivo seleccionamos la opcion Data Source y de la lista desplegable selecciomos el JDBC Resource que creamos en el GlassFish,

seleccionamos jdbc/oracle y grabamos.

![screenshot\_17](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_17.png?w=1000)

**Creación de la entidad**

Lo que viene a continuación es la creación de la entidad, para el ejemplo solo crearemos la entidad JOBS del Schema HR.

Nos ubicamos en el proyecto EJB en la carpeta Source Package y con click derecho seleccionamos New / ENTITY CLASES FROM DATABASES

![screenshot\_18](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_18.png?w=1000)

Aqui lo mejor sera crear un data source nuevo y no usar el jdbc/oracle creado previamente, esto con la finalidad de mostrar las tablas del schema.

![screenshot\_19](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_19.png?w=1000)

![screenshot\_20](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_20.png?w=1000)

Una vez creada se mostraran las tablas del sistema, seleccionamos JOBS y presionamos ADD![screenshot\_21](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_21.png?w=1000)

seleccionamos la tabla y presionamos Next

![screenshot\_22](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_22.png?w=1000)

antes de grabar indicamos el nombre del paquete en el que se grabara la entidad

por ej. com.oracle.entidad y presionamos next

.![screenshot\_23](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_23.png?w=1000)

aquí no modificamos nada y presionamos finish.

![screenshot\_24](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_24.png?w=1000)

**Creación del Session Bean de la entidad**

Nuevamente nos ubicamos en el proyecto EJB y con el click derecho seleccionamos New , SESSION BEANS FOR ENTITY CLASSES.

![screenshot\_25](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_25.png?w=1000)

seleccionamos la entidad JOBS creada previamente, presionamos el boton ADD y Next.

![screenshot\_26](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_26.png?w=1000)

En la sección de Package indicamos el nombre del paquete para nuestros controladores

Ej. com.oracle.controlador

Damos check en la opción LOCAL y Finish.

![screenshot\_27](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_27.png?w=1000)

Creación de JSF Bean.

Ahora nos ubicamos en el proyecto WAR y con el boton derecho seleccionamos la opcion NEW, JSF MANAGED BEAN.

![screenshot\_28](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_28.png?w=1000)

indicamos un  nombre para nuestra clase bean y el paquete, el alance (scope) que elegiremos sera SESSION y presionamos FINISH.

![screenshot\_29](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_29.png?w=1000)

Hasta aquí hemos creado la conexión y estructura de nuestro proyecto, solo queda por hacer el codigo.

**El código**

En el proyecto EJB, abrimos el package entidad y abrimos Jobs.java.

aquí realizaremos un ligero cambio.

en la sección @Tablename donde dice «JOBS» debe decir «HR.JOBS» y grabamos.

![screenshot\_30](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_30.png?w=1000)

No ubicamos en el proyecto WAR y dentro del package bean abrimos el archivo JobsBean.java y tratamos de digitar este código.

Mas facil…

solo crea las lineas 16/17/18/20/22/23/24 y agrega el getter y setter del objecto listaJobs.

![screenshot\_31](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_31.png?w=1000)

En el mismo proyecto WAR, abrimos el archivo XHTML (welcomePrimefaces.xhtml)

Y en la seccion \<p:layaoutUnit…., digitamos el codigo correspondiente al form y datatable, es decir todo lo que esta en el marco rojo.

![screenshot\_32](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_32.png?w=1000)

Si todo lo realizado hasta ahora esta bien y no nos falle algo que paso desapercibido, nos vamos al proyecto principal y le damos Clean and Build / Luego Deploy / y por ultimo RUN.![screenshot\_33](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_33.png?w=1000)![screenshot\_34](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_34.png?w=1000)![screenshot\_35](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_35.png?w=1000)

El resultado debe ser esta pagina index con un enlace, demos click a ese enlace.

![screenshot\_36](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_36.png?w=1000)

Este es el resultado.![screenshot\_37](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_37.png?w=1000)

Siempre no esta demas revisar el Log del proyecto y GlassFish Server.

![screenshot\_38](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_38.png?w=1000)

Y siempre que deseen agregar un comando print para mostrar que va ejecutando nuestro programa.

![screenshot\_39](https://javaconelchuz.wordpress.com/wp-content/uploads/2016/11/screenshot_39.png?w=1000)
