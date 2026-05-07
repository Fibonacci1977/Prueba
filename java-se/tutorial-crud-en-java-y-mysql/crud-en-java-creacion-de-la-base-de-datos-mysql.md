# CRUD en Java Creación de la base de datos MySQL

![Logo Java](https://byspel.com/wp-content/uploads/2018/05/Java-Logo.jpg)

En los próximos artículos de la sección de Java, estaremos desarrollando las funcionalidades básicas de un  [**Software** ](https://www.youtube.com/c/byspel)con conexión a bases de datos (**CRUD**: _Create, Read, Update, Delete_); estas funcionalidades permitirán abarcar cualquier tipo de proyecto de Software que requiera la gestión de una base de datos. Empezaremos con la creación de la base de datos. sin más veamos un caso estudio sobre el cual construiremos nuestro Software, sigue paso a paso las instrucciones y podrás construir un proyecto CRUD en [**Java**](https://byspel.com/category/java/).

> **Nota:** Es importante resaltar que estos tutoriales han sido descritos minuciosamente; sin embargo algunas instrucciones requieren ciertos conocimientos básicos.

#### **CRUD en Java Creación de la base de datos (Tutorial 1)**

**Caso estudio:** Usted ha sido contratado para desarrollar un Software para gestionar el ingreso de personas a un establecimiento comercial. Dicho Software estará en capacidad de realizar las acciones básicas para la manipulación de la base de datos (CRUD) de cada persona que ingrese al establecimiento se deberá recolectar:

* Tipo Documento
* Identificación.
* Nombres
* Apellidos
* Teléfono.
* Dirección.
* Correo Electrónico.
* Motivo.
* Fecha de Ingreso.
* Hora de Ingreso.

**Las acciones que deberá realizar el Software serán las siguientes:**

* Registrar en la base de datos todas las personas que ingresen al establecimiento.
* Mostrar el listado de todas las personas que ingresaron.
* Posibilidad de actualizar los datos en caso de errores al momento del registro.
* Posibilidad de eliminar registros de personas registradas.

**CRUD en Java Creación de la base de datos**

Teniendo presente el caso estudio anterior procedemos al análisis de nuestra base de datos, por lo cual a continuación detallaremos la entidad sobre la cual almacenaremos los datos de las personas.

> #### [**Código fuente: Proyecto CRUD en Java MVC – con base de datos MySQ**L](https://byspel.com/proyecto-agenda-telefonica-en-java-mvc-con-base-de-datos-mysql/)

Base de datos: **Registro**

Tabla: **Personas**

**Descripción de los campos**

<table><thead><tr><th width="228">Campo</th><th width="92">Tipo</th><th width="100">Longitud</th><th width="224">Descripción</th></tr></thead><tbody><tr><td>Id</td><td>Int</td><td>10</td><td>Primary Key, auto_increment.</td></tr><tr><td>Td</td><td>Char</td><td>2</td><td>Tipo de documento, puede ser: CC, CE, TI.</td></tr><tr><td>Identificación</td><td>Int</td><td>10</td><td>Datos personales de cada una de las personas que ingresan al establecimiento.</td></tr><tr><td>Nombres</td><td>Varchar</td><td>100</td><td></td></tr><tr><td>Apellidos</td><td>Varchar</td><td>100</td><td></td></tr><tr><td>Teléfono</td><td>Int</td><td>10</td><td></td></tr><tr><td>Dirección</td><td>varchar</td><td>200</td><td></td></tr><tr><td>Fecha_Ingreso</td><td>Date</td><td></td><td>Fecha de ingreso al establecimiento.</td></tr><tr><td>Hora_Ingreso</td><td>Time</td><td></td><td>Hora de ingreso al establecimiento.</td></tr><tr><td>Motivo</td><td>text</td><td></td><td>Descripción de ingreso al establecimiento.</td></tr></tbody></table>

**Escribiendo las instrucciones necesarias en la consola de MySQL.**

Luego de iniciar sesión en el servidor MySQL, crea la base de datos:

![CRUD en Java Creación de la base de datos](https://1.bp.blogspot.com/-szz_5mhPtpI/XBlQF3sBqZI/AAAAAAAACkY/w31WT9YsxiE1cXRTFO5Rhkt4r2LAFk-EwCLcBGAs/s1600/CRUD%2Ben%2BJava%2B1.jpg)

Ver másprogramaciónProgramaciónAprendizaje automático e inteligencia artificial

Indica al **servidor MySQ**L que trabajarás sobre la base de datos “Registro”.

![CRUD en Java Creación de la base de datos](https://4.bp.blogspot.com/-b9BFCsKQOA0/XBlQX3K50BI/AAAAAAAACkg/UlZnguoHMbk_amkbMJu6l4N-G6raA5uvgCLcBGAs/s1600/CRUD%2Ben%2BJava%2B2.jpg)

Ya con la base de datos seleccionada procedemos a crear la tabla “Personas”, con los datos descritos en la tabla anterior.

![CRUD en Java Creación de la base de datos](https://3.bp.blogspot.com/-UxH1_8oWa9c/XBlQwxVVCHI/AAAAAAAACko/ivxeahtAh8gaLYlWKxY6uHlhXrYDo0QRQCLcBGAs/s1600/CRUD%2Ben%2BJava%2B3.jpg)

**Insertando datos de ejemplo**

A continuación ingresamos desde la consola varios registros de ejemplo:

![CRUD en Java Creación de la base de datos](https://2.bp.blogspot.com/-HT1h3kFxTNs/XBlRPP418rI/AAAAAAAACkw/YTpuEuhFiSsP8p1EibMb1MC5FzD0-t19gCLcBGAs/s1600/CRUD%2Ben%2BJava%2B4.jpg)

De esta manera logramos crear la base de datos con la tabla necesaria para guardar los registros necesarios, ahora procederemos a la configuración del proyecto.

## [CRUD en Java Configuración del proyecto en NetBeans (Tutorial 2)](https://byspel.com/crud-en-java-configuracion-del-proyecto-en-netbeans-tutorial-2/)

![Logo Java](https://byspel.com/wp-content/uploads/2018/05/Java-Logo.jpg)

Luego de [construir la base de datos](https://byspel.com/crud-en-java-creacion-de-la-base-de-datos-mysql-tutorial-1/) sobre la cual almacenaremos los registros desde la aplicación; seguimos con la configuración del proyecto en [Java](https://byspel.com/category/java/) para la construcción del **CRUD**, así que sin más abrimos [NetBeans](https://www.youtube.com/c/byspel) y procedemos a realizar las **instrucciones** indicadas a continuación:

#### **CRUD en Java Configuración del proyecto en NetBeans**

Crea un nuevo proyecto con el nombre: **CRUD\_Registro,** con la siguiente estructura:

![CRUD en Java Configuración del proyecto](https://2.bp.blogspot.com/-rc5z1zs1HkM/XBlWIkE2KII/AAAAAAAACk8/TwTv9sNglPAg5GWjZ4LA4LWOMlcNEF4UQCLcBGAs/s1600/CRUD%2Ben%2BJava%2B1.jpg)

**Librerías necesarias y clase para conectar**

Para realizar una conexión entre la base de datos MySQL y nuestro Software, debemos utilizar la librería: mysql-connector-java-5.1.18-bin.jar, esta contiene todas las clases, métodos y funciones necesarias para enviar peticiones al servidor MySQL (Consultas).

> [**🌟 ¡Visita Nuestra Tienda para Programadores! 🌟**](https://shop.byspel.com/)
>
> Descubre [Códigos Fuente](https://shop.byspel.com/), [Cursos](https://shop.byspel.com/), Software, Computadoras, Accesorios y Regalos Exclusivos. ¡Todo lo que necesitas para llevar tu programación al siguiente nivel!

> #### [**Código fuente: Proyecto CRUD en Java MVC – con base de datos MySQ**L](https://byspel.com/proyecto-agenda-telefonica-en-java-mvc-con-base-de-datos-mysql/)

**Descarga la librería de conexión**

Puedes proceder a la descarga de la librería desde el siguiente link:

[https://goo.gl/whUC3f](https://goo.gl/whUC3f)

**Al descargar la librería sigue los siguientes pasos:**

**1.** Crea una carpeta dentro de la carpeta de tu proyecto “**CRUD\_Registro**”, que está ubicada en **NetBeansProyects**, asigna como nombre “**Librerías**”.

![CRUD en Java Configuración del proyecto](https://4.bp.blogspot.com/-EX5QRqophFU/XBlWnXGt7xI/AAAAAAAAClE/BFI3nIZdBqEttvxRjXx7YNXX2-O9ZO8JwCLcBGAs/s1600/CRUD%2Ben%2BJava%2B2.jpg)

Ver másprogramaciónProgramaciónAprendizaje automático e inteligencia artificial

**2.** Pega dentro de la carpeta “Librerías”, el archivo: **mysql-connector-java-5.1.18-bin.jar**

![CRUD en Java Configuración del proyecto](https://3.bp.blogspot.com/-OT2Uoaq2vF4/XBlW82Uk-bI/AAAAAAAAClM/4CglwjSxegUj2ktem4i5d5pYUo-47h6UQCLcBGAs/s1600/CRUD%2Ben%2BJava%2B3.jpg)

> **Nota:** Es importante ubicar las librerías que se utilizarán en una carpeta dentro del mismo proyecto por facilidad, debido a que si deseamos mover el proyecto para trabajarlo desde otro computador. Ya tendremos todas las librerías configuradas, de lo contrario se deberán importar nuevamente.

**Importar la librería**

Importar una librería es asignarla a nuestro proyecto, con el fin de poder utilizar todas sus funcionalidades, realiza los siguientes pasos:

**1. Clic derecho** sobre el **paquete bibliotecas** en el “Explorador de proyectos de NetBeans”.

![CRUD en Java Configuración del proyecto](https://1.bp.blogspot.com/-NuC8B-U9eds/XBlXTnhBvuI/AAAAAAAAClU/oZk-1-TirMYLEmV03g9ZSE-sBSGOhkSoACLcBGAs/s1600/CRUD%2Ben%2BJava%2B4.jpg)

Selecciona “**Agregar archivo JAR/Carpeta..**.”, a continuación selecciona en el cuadro de dialogo la librería descargada y ubicada en la carpeta “Librerías” de tu proyecto.

![CRUD en Java Configuración del proyecto](https://1.bp.blogspot.com/-TKKwLfek1-8/XBlXjg5fY_I/AAAAAAAAClg/N4d-XBrXgCcEqJK04VlnQGdk2GImWQV6wCLcBGAs/s1600/CRUD%2Ben%2BJava%2B5.jpg)

Al seleccionar la librería verás cómo se carga en el explorador de proyectos de NetBeans, indicando que está lista para ser usada.

![CRUD en Java Configuración del proyecto](https://2.bp.blogspot.com/-fvay_3rQRHg/XBlX2X5LruI/AAAAAAAAClo/95pLHgxcNUUy8ddJ_feb94oftp_42Sv_gCLcBGAs/s1600/CRUD%2Ben%2BJava%2B6.jpg)

**Creando la clase conexión**

En esta case se detallan todos los métodos para poder conectarnos a la base de datos y hacer todas las consultas necesarias, así como también desconectarnos de la misma.

**1.** Crea una clase java en el paquete “Clases” y asigna como nombre “**ConexiónBD**”.

## [CRUD en Java Crear la interfaz del Software (Tutorial 3)](https://byspel.com/crud-en-java-crear-la-interfaz-software-tutorial/)

![Logo Java](https://byspel.com/wp-content/uploads/2018/05/Java-Logo.jpg)

**CRUD en Java Crear la interfaz:** Luego de la configuración del proyecto, [Artículo que puedes ver haciendo clic aquí](https://byspel.com/crud-en-java-configuracion-del-proyecto-en-netbeans-tutorial-2/); procedemos a construir las interfaces que el [Software](https://www.youtube.com/c/byspel) llevará, recordando que la interfaz construida deberá permitir realizar las acciones solicitadas (**CRUD**), para crear la interfaz del Software debemos ser cuidadosos sobre que paquetes estamos utilizando para almacenar las interfaces del CRUD, así que empecemos.

> **Nota:** Es importante asignar los nombres tal como están en el tutorial; de lo contrario obtendrás errores en tu código. Ahora bien, si deseas manejar otros nombres no olvides hacer la asociación correcta en tu código con los nombres utilizados.

#### **CRUD en Java Crear la interfaz del Software**

Realiza las siguientes instrucciones paso a paso para construir la interfaz del Software:

**1.** Crear un formulario de tipo (**JFrame**) en el paquete “**Formularios**”, asigna el nombre “_Principal_”.

![CRUD en Java Crear la interfaz del Software](https://4.bp.blogspot.com/-s__Gkn2Ll8Q/XBpjs8pyCTI/AAAAAAAACmI/VSQWRZZp4dIP_Sok0yU-_UId4d-sv7lzgCLcBGAs/s1600/CRUD%2Ben%2BJava%2B1.jpg)

> [**🌟 ¡Visita Nuestra Tienda para Programadores! 🌟**](https://shop.byspel.com/)
>
> Descubre [Códigos Fuente](https://shop.byspel.com/), [Cursos](https://shop.byspel.com/), Software, Computadoras, Accesorios y Regalos Exclusivos. ¡Todo lo que necesitas para llevar tu programación al siguiente nivel!

**2.** Diseñe el **JFrame** “**Principal**” con la siguiente estructura:

![CRUD en Java Crear la interfaz del Software](https://3.bp.blogspot.com/-dnAUhwEQe5g/XBpkSPVnnnI/AAAAAAAACmQ/M1tqc1wp08wxesKzqe8fJYHEzwbOSu2jwCLcBGAs/s1600/CRUD%2Ben%2BJava%2B2.jpg)

**Especificación de los controles del formulario:**

> #### [**Código fuente: Proyecto CRUD en Java MVC – con base de datos MySQ**L](https://byspel.com/proyecto-agenda-telefonica-en-java-mvc-con-base-de-datos-mysql/)

| **Nombre del control** | **Tipo**   | **Observación**                                                                       |
| ---------------------- | ---------- | ------------------------------------------------------------------------------------- |
| **cbTD**               | jComboBox  | Opciones posibles: TI, CC, CE.                                                        |
| **txtDocumento**       | JTextField |                                                                                       |
| **txtNombres**         | JTextField |                                                                                       |
| **txtApellidos**       | JTextField |                                                                                       |
| **txtTelefono**        | JTextField |                                                                                       |
| **txtDireccion**       | JTextField |                                                                                       |
| **txtFechaI**          | JTextField |                                                                                       |
| **txtHoraI**           | JTextField |                                                                                       |
| **txtMotivo**          | JTexArea   |                                                                                       |
| **Tabla\_Registros**   | JTable     | Aquí se mostrarán los registros guardados en la base de datos.                        |
| **btnGuardar**         | JButton    | Al pulsarlo deberá guardar los datos del formulario en la tabla de la base de datos.  |
| **btnLimpiar**         | JButton    | Al pulsarlo deberá vaciar o limpiar los controles del formulario.                     |
| **btnConsultar**       | JButton    | Al pulsarlo deberá mostrar todos los registros de la tabla de MySQL.                  |
| **btnActualizar**      | JButton    | Al pulsarlo deberá abrir otra ventana en la cual actualizar el registro seleccionado. |
| **btnEliminar**        | JButton    | Al pulsarlo deberá eliminar de la tabla de MySQL el registro seleccionado.            |

**Código de “CRUD\_Registro.java”**

Esta es nuestra clase principal, por ende aquí debemos indicar las instrucciones del inicio del Software; estas instrucciones deben ser escritas dentro del método “main”.

Ver másProgramaciónprogramaciónAprendizaje automático e inteligencia artificial

¿_Qué instrucciones debemos colocar_?, pues bien. Al inicial el Software debemos mostrar el formulario “Principal”, por lo tanto codificamos:\
![CRUD en Java Crear la interfaz del Software](https://1.bp.blogspot.com/--yXh_lLZBkM/XBplO8iDSuI/AAAAAAAACmc/1LtVfWCuD1oUgEsgfU1HIVHkTSPGtEq9wCLcBGAs/s1600/CRUD%2Ben%2BJava%2B3.jpg)

![CRUD en Java Crear la interfaz del Software](https://1.bp.blogspot.com/-OZJ8a0_qi2s/XBplicHzd4I/AAAAAAAACmk/hFApjh58V3UKXb_Zeu2sCkh-W2d4gQ6kACLcBGAs/s1600/CRUD%2Ben%2BJava%2B4.jpg)

Finalmente si al ejecutar el proyecto se muestra el formulario “_Principal_”, [sigue con la siguiente parte de este tutorial para la creación de un **CRUD en Java**](https://byspel.com/crud-en-java-insertar-registros-en-mysql-tutorial-4/).

## [CRUD en Java Insertar registros en MySQL (Tutorial 4)](https://byspel.com/crud-en-java-insertar-registros-en-mysql-tutorial-4/)

![Logo Java](https://byspel.com/wp-content/uploads/2018/05/Java-Logo.jpg)

En esta parte de la creación del [**CRUD** ](https://www.youtube.com/c/byspel)en Java veremos como insertar registros en [**MySQL**](https://byspel.com/category/mysql), realizando la primera conexión con la [base de datos](https://byspel.com/category/mysql) para guardar los registros que ingresa el usuario final. Esto se realiza cuando hacemos clic en el botón “_Guardar_”, veamos:

#### **CRUD en Java Insertar registros en MySQL**

**1.** Presiona doble clic sobre el botón “**Guardar**”, para configurar el evento: **ActionPerformed**.

**2.** Codifica las siguientes instrucciones:

**Recomendación:** Es importante escribir las instrucciones tal como están a continuación, de lo contrario tendrás errores.



> #### [**Código fuente: Proyecto CRUD en Java MVC – con base de datos MySQ**L](https://byspel.com/proyecto-agenda-telefonica-en-java-mvc-con-base-de-datos-mysql/)

#### ![CRUD en Java insertar registros](https://3.bp.blogspot.com/-1LviyIjSa6w/XBvG7-sobtI/AAAAAAAACmw/MJK_lPa6aLYJrqiukT6Qi7ZSIDthIl_bgCLcBGAs/s1600/CRUD%2Ben%2BJava%2B1.jpg)

> **Nota:** Configura el Zoom para visualizar bien el código.

**3.** Ejecuta el Software e ingresa datos para verificar el funcionamiento:

Ver másProgramaciónprogramaciónAprendizaje automático e inteligencia artificial

![CRUD en Java insertar registros](https://3.bp.blogspot.com/-Hqq8nLqmuu8/XBvHehLu_7I/AAAAAAAACm4/_5WZtFuhVo0P6Ch4esqYWwObkQFQsrtbQCLcBGAs/s1600/CRUD%2Ben%2BJava%2B2.jpg)

**4.** Si recibiste el mensaje que indica que los datos se guardaron con éxito verifica en la base de datos que el registro se halla creado correctamente en los campos deseados:

![CRUD en Java insertar registros](https://4.bp.blogspot.com/-wnOFG5QVp8Y/XBvH2mdAlXI/AAAAAAAACnA/fofGzCvJur4K72a9uc9GOtdN3ekBygkrwCLcBGAs/s1600/CRUD%2Ben%2BJava%2B3.jpg)

Ver másProgramaciónAprendizaje automático e inteligencia artificialprogramación

Al consultar los datos en MySQL y estos se encuentran registrados de forma correcta, damos por terminada nuestra primera conexión a la base de datos en la cual añadimos o guardamos registros; es importante que si obtienes errores verificar el código SQL escrito, los nombres de las columnas de la tabla de MySQL deben estar escritos de forma correcta, de lo contrario obtendrás errores.

**Errores comunes**

* Condicionales: Es muy común los errores en los condicionales. Confundir variables, llaves, mucho ojo con el «else», donde abre y donde cierra un paréntesis.
* Los nombres de las columnas de la tabla en MySQL: estos deben ser referenciados desde el código Java con el mismo nombre como fueron creados en MySQL.
* Número de parámetros: Si en la cláusula Insert definiste 4 valores, deberás enviar 4 valores dentro de «values». Si envías más o menos valores obtendrás errores.
* Escritura: Deberás mantener los ojos bien abiertos sobre las instrucciones escritas, si algo sale mal lo único que indica es que lo más probable es que esté mal escrito.

Si llegaste a esta parte del tutorial sin problemas puedes acceder a la siguiente [desde aquí](https://byspel.com/crud-en-java-consultar-registros-en-mysql-tutorial-5/); en la cual consultaremos los datos almacenados en MySQL desde el Software.
