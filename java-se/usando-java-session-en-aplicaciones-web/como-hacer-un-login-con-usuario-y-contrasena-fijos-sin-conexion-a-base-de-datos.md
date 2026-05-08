# Cómo hacer un Login, con usuario y contraseña fijos (sin conexión a Base de datos)?

Al realizar una aplicación, en especial una que maneja información importante para el usuario y/o empresa que adquiere dicho programa, se hace necesario crear esquemas de seguridad como lo son en primera instancia el acceso al sistema mediante un usuario y contraseña.\
<br>



{% embed url="https://youtu.be/o16JF-LuHK4?si=YbALxT9bXeBEYLhM" %}

\
\
Luego de haber aprendido en el capítulo anterior a [agregar datos de un formulario a una tabla, y eliminarlos de la misma](http://uh-tis.blogspot.com/2013/11/Curso-de-JAVA-como-agregar-datos-de-un-formulario-a-una-tabla-y-eliminarlos-de-la-misma.html), en esta parte del curso aprenderemos a desarrollar un sencillo formulario de acceso o Login, el cual consta de un usuario y contraseña fijos; es decir, establecidos por el desarrollador en el código del software, lo que los hace inmodificables una vez se haya compilado el programa.\
Explicación por VideoTutorial:\
\
\
\
\
\
Explicación por Foto-Tutorial:\
\
Procederemos a crear un nuevo formulario el cual llamaremos Login (te podría interesar [ver cómo crear un proyecto, un paquete y un formulario](http://uh-tis.blogspot.com/2012/07/curso-de-java-como-hacer-un-proyecto-un.html)), y a este le\
agregaremos 2 JLabel (a uno le asignamos el texto “USUARIO”, y al otro el texto “CLAVE”), 1 JTextField (donde se digitará el usuario para ingresar al sistema), 1 JPasswordField (donde se digitará la contraseña para ingresar al sistema), y por último colocamos 1 JButton (a este le asignamos el texto “INGRESAR”):\
[![Login, Formulario de acceso, Usuario, Contraseña, JAVA, Seguridad, Ingresar al sistema, Password](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj6kGnXBB89m0uCsSyDHN4EG-E72SDdSPIIZrVOYX7JqLoZahAh_yVplBsTAMO5jlO_Imsp8pQdPXTh4-3UCMfMLBKv-p1NxBtiqoGld6tRJkC0RQn2vk7bYYWihA8SGLrrJvCsMCuVUic0/s400/formulario-login-java.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj6kGnXBB89m0uCsSyDHN4EG-E72SDdSPIIZrVOYX7JqLoZahAh_yVplBsTAMO5jlO_Imsp8pQdPXTh4-3UCMfMLBKv-p1NxBtiqoGld6tRJkC0RQn2vk7bYYWihA8SGLrrJvCsMCuVUic0/s1600/formulario-login-java.jpg)\
[![Login, Formulario de acceso, Usuario, Contraseña, JAVA, Seguridad, Ingresar al sistema, Password](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjQ0B4a0pUqoO8LXEMgjG_QCi0H7iCs1reG5xj7c7-U675Zfc_Lb3gF4t4RAOyJV-BARHKL_6YIS5wgpRTpCHuducwZyA3qeyT7I6IER18c_91ME6OwLlQoArr2rBopm_jZwUoJ7aeL5kH_/s400/jpasswordfield-clave-java.jpg) ](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjQ0B4a0pUqoO8LXEMgjG_QCi0H7iCs1reG5xj7c7-U675Zfc_Lb3gF4t4RAOyJV-BARHKL_6YIS5wgpRTpCHuducwZyA3qeyT7I6IER18c_91ME6OwLlQoArr2rBopm_jZwUoJ7aeL5kH_/s1600/jpasswordfield-clave-java.jpg)\
[![Login, Formulario de acceso, Usuario, Contraseña, JAVA, Seguridad, Ingresar al sistema, Password](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjv3Yg-l7JP9_CsI0azpTUXHOqwIggQpiPcC288iXvHWG9-ED4CevXjLCXMPS1AkMdTWYB9n4ZjlGJfcLfRGqRGrPowlF443i3N272iRb-jCsRM28dUauSwmNm1pIIqIeDlBKI-8UgWX4xi/s400/formulario-ingreso-sistema.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjv3Yg-l7JP9_CsI0azpTUXHOqwIggQpiPcC288iXvHWG9-ED4CevXjLCXMPS1AkMdTWYB9n4ZjlGJfcLfRGqRGrPowlF443i3N272iRb-jCsRM28dUauSwmNm1pIIqIeDlBKI-8UgWX4xi/s1600/formulario-ingreso-sistema.jpg)\
Después lo que haremos será darle un nombre a cada componente, ej. :\
Campo de texto usuario= txtUsuario\
Campo de texto de la clave= jpassClave\
Botón de ingreso= btnIngresar\
\
[![Login, Formulario de acceso, Usuario, Contraseña, JAVA, Seguridad, Ingresar al sistema, Password](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhe4aft0nLxzZuqKaqiqZk-65efI44tWdbRhbLe52M0Aj4EVGajKKmv5JFTZrlOY_hdln7ZLqzGNaZzomSNFavvD-U3XkOiNrTubixPynkwKPkShRlVkkkT9PoGlqbMqYtEPzvwKBsEge4G/s400/renombrar-caja-texto.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhe4aft0nLxzZuqKaqiqZk-65efI44tWdbRhbLe52M0Aj4EVGajKKmv5JFTZrlOY_hdln7ZLqzGNaZzomSNFavvD-U3XkOiNrTubixPynkwKPkShRlVkkkT9PoGlqbMqYtEPzvwKBsEge4G/s1600/renombrar-caja-texto.jpg)\
Luego damos doble clic sobre el botón “INGRESAR”, y borramos el comentario que trae por defecto:\
[![Login, Formulario de acceso, Usuario, Contraseña, JAVA, Seguridad, Ingresar al sistema, Password](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhPsNAzswOQPUsOxIW-oWjagij-WK_hfbdBydSCNqUZ8QpzqrV-_dqL9WxS6U4casl-9wLFQ8rm_uxC6nJEDH7ldLKynmT8HDalQyKKwiR9aZ20qNoSezVLuzn-LG_Tp5oU1nSrudfABhQO/s400/boton-ingresar-java.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhPsNAzswOQPUsOxIW-oWjagij-WK_hfbdBydSCNqUZ8QpzqrV-_dqL9WxS6U4casl-9wLFQ8rm_uxC6nJEDH7ldLKynmT8HDalQyKKwiR9aZ20qNoSezVLuzn-LG_Tp5oU1nSrudfABhQO/s1600/boton-ingresar-java.jpg)\
[![Login, Formulario de acceso, Usuario, Contraseña, JAVA, Seguridad, Ingresar al sistema, Password](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhUS87-eOFZL26nZaSalSIQu3yVwmI6ThNRgwBk154_6jVx5JV2tW2V6sp3Gy0wSNBIVhm5oo0K39NkLbJDvNcFP1o0fW26I6c3R-CHLjUfZopc6ajHv4TIi14IcyHDr5T3JSYsmAE9ILs0/s400/comentario-boton-java.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhUS87-eOFZL26nZaSalSIQu3yVwmI6ThNRgwBk154_6jVx5JV2tW2V6sp3Gy0wSNBIVhm5oo0K39NkLbJDvNcFP1o0fW26I6c3R-CHLjUfZopc6ajHv4TIi14IcyHDr5T3JSYsmAE9ILs0/s1600/comentario-boton-java.jpg)\
Pegamos el siguiente código dentro del método del botón “INGRESAR”:\
\
char clave\[]=jpassClave.getPassword();\
String clavedef=new String(clave);\
\
if (txtUsuario.getText().equals("Administrador") && clavedef.equals("12345")){\
\
&#x20;                   this.dispose();\
\
&#x20;                   JOptionPane.showMessageDialog(null, "Bienvenido\n"                    + "Has ingresado satisfactoriamente al sistema",   "Mensaje de bienvenida",                    JOptionPane.INFORMATION\_MESSAGE);\
\
&#x20;                   Formulario1 formformulario1 = new Formulario1();\
&#x20;                   formformulario1.setVisible(true);\
\
&#x20;           }else {\
\
&#x20;                   JOptionPane.showMessageDialog(null, "Acceso denegado:\n"                    + "Por favor ingrese un usuario y/o contraseña correctos", "Acceso denegado",                    JOptionPane.ERROR\_MESSAGE);           \
&#x20;           }\
\
\
\
\
\
\
NOTA: Si deseas una explicación más detallada acerca de cada sección del código anterior puedes visitar el siguiente artículo: [Código JAVA: Login, con usuario y contraseña fijos (sin conexión a Base de datos)](http://codigosparadesarrolladores.blogspot.com/2014/01/Codigo-JAVA-Login-con-usuario-y-contrasena-fijos-sin-conexion-a-Base-de-datos.html)\
\
Lo que hacemos en el código es guardar el contenido del JPasswordField en un array tipo char, y luego convertimos ese array en un String. Seguidamente realizamos un condicional donde compararemos el contenido de lo que se haya digitado en la caja de texto de usuario y la clave que hemos convertido a String con anterioridad; esta comparación se hace con datos fijos (inmodificables por el usuario); en el caso dado que ambos datos sean correctos, se procederá a cerrar el formulario de acceso y seguidamente se mostrará un cuadro de diálogo dando la bienvenida al sistema y abriendo el formulario principal del programa:\
[![Login, Formulario de acceso, Usuario, Contraseña, JAVA, Seguridad, Ingresar al sistema, Password](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgYBuLncwk2L43gSAlhWvfGi3sXFk6Y6J_EvjVrOh9B0h56gm_wULqljrGa5gv5PEmlbRtXL5XFy7NCAPeIZtfMEOe_laBitYTQKTEKmdQKGD8hU3798Z2zQ2ZbokptfbnqQMFo-HaQDNvt/s320/login-sistema-java.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgYBuLncwk2L43gSAlhWvfGi3sXFk6Y6J_EvjVrOh9B0h56gm_wULqljrGa5gv5PEmlbRtXL5XFy7NCAPeIZtfMEOe_laBitYTQKTEKmdQKGD8hU3798Z2zQ2ZbokptfbnqQMFo-HaQDNvt/s1600/login-sistema-java.jpg)\
\
[![Login, Formulario de acceso, Usuario, Contraseña, JAVA, Seguridad, Ingresar al sistema, Password](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhGkQV7PD4yfrIg7p09wmTXxyhArlU6QKJMMSGxpz0Z4mRtpSt-ZX0Cd-T6rWBntcn2oIp3XYmTqcT3bDWQLK2-JQF0sqs3TDDNGp9O5SpQOJWdc3D-DqW_Bsd1F5Al5b5Dga03T31AtVRo/s1600/joptionpane-java-dialogo.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhGkQV7PD4yfrIg7p09wmTXxyhArlU6QKJMMSGxpz0Z4mRtpSt-ZX0Cd-T6rWBntcn2oIp3XYmTqcT3bDWQLK2-JQF0sqs3TDDNGp9O5SpQOJWdc3D-DqW_Bsd1F5Al5b5Dga03T31AtVRo/s1600/joptionpane-java-dialogo.jpg)\
[![Login, Formulario de acceso, Usuario, Contraseña, JAVA, Seguridad, Ingresar al sistema, Password](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgo7688to4q4W3TDtCCBuiZIUIWCjaoqZUKR-8kWho5JmnvwCRpMqdiKZD4YCfNGZK1jM1mU4RaECgamQYRwGEH-akoSD4evrKXbDVKpu3bDcXyRosjwaW7MYZtHFXgxAX5wcQDiY2LMRZb/s320/formulario-principal-java.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgo7688to4q4W3TDtCCBuiZIUIWCjaoqZUKR-8kWho5JmnvwCRpMqdiKZD4YCfNGZK1jM1mU4RaECgamQYRwGEH-akoSD4evrKXbDVKpu3bDcXyRosjwaW7MYZtHFXgxAX5wcQDiY2LMRZb/s1600/formulario-principal-java.jpg)\
\
Si por el contrario digitamos mal los datos de ingreso, nos aparecerá un cuadro de diálogo, advirtiéndonos dicha situación:\
[![Login, Formulario de acceso, Usuario, Contraseña, JAVA, Seguridad, Ingresar al sistema, Password](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiHwZaGsa3FynQcOimKwVNxaRDeXFiqdDnKyUnzRHUoVjDeE8f5eK-9oKK6_Smyys-O3iixR1Es2Q9clNCREV1-iyHwZVSfh_rsDooFL_GtYj8KyKaX-Zmc0QqXpntaPSSa38ia21L-pOGH/s400/acceso-denegado-java.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiHwZaGsa3FynQcOimKwVNxaRDeXFiqdDnKyUnzRHUoVjDeE8f5eK-9oKK6_Smyys-O3iixR1Es2Q9clNCREV1-iyHwZVSfh_rsDooFL_GtYj8KyKaX-Zmc0QqXpntaPSSa38ia21L-pOGH/s1600/acceso-denegado-java.jpg)<br>

Si lo que estás necesitando es crear un formulario de acceso un poco más avanzado, te interesará ver nuestro post donde explicamos [cómo crear un login con conexión a una base de datos.](http://uh-tis.blogspot.com/2014/09/curso-de-java-como-crear-un-login-con-conexion-a-base-de-datos.html)\
Cómo crear un Login? (Con conexión a base de datos)

\
\
\
Cómo crear un Login? (Con conexión a base de datos)\
\
Luego de haber aprendido a [crear formularios](http://uh-tis.blogspot.com/2012/07/curso-de-java-como-hacer-un-proyecto-un.html) y a conectar nuestras aplicaciones hechas en Java con una base de datos, tanto de una [forma básica](http://uh-tis.blogspot.com/2014/04/curso-de-java-como-conectar-java-con-una-base-de-datos-forma-basica.html) o ya sea realizando un [Pool de conexiones](http://uh-tis.blogspot.com/2014/05/curso-de-java-como-conectar-nuestra-aplicacion-con-una-base-de-datos-forma-optima.html); ahora podremos fusionar ambas partes y/o conocimientos, para llevar a cabo la construcción de módulos en nuestro software, con una mayor funcionalidad y usabilidad.\
<br>

\
En un capítulo anterior, pudimos observar e ilustrar como [desarrollar un sencillo y/o básico formulario de acceso o Login](http://uh-tis.blogspot.com/2014/01/Curso-de-JAVA-Como-hacer-un-Login-con-usuario-y-clave-fijos-sin-conexion-a-Base-de-datos.html) en nuestro programa; el cual nos iba a permitir controlar el acceso al sistema a los usuarios previamente dictaminados y/o configurados en nuestro código, haciendo muy limitado el uso del mismo. Por ello, en esta ocasión llevaremos a cabo la construcción de un Login que se comunicará con una base de datos para llevar a cabo la verificación de los datos de acceso al programa como el usuario y la contraseña, que han sido asignados a las personas autorizadas para hacer uso del mismo. Este tipo de formulario de acceso, nos dará la posibilidad de ampliar el uso de un determinado software a más usuarios que se vayan registrando en dicho programa, por parte del administrador de este, el cual podrá darle las autorizaciones y/o permisos respectivos para el uso de algunas o todas las funcionalidades que ofrece el sistema de información.\
Explicación por Videotutorial:<br>



{% embed url="https://youtu.be/xHWGMOWQ3F8?si=5Geu7BbC1t8Pmi68" %}

\
\
\
Explicación por Foto-Tutorial: \
\
\*Deberemos previamente [crear una base de datos](http://uh-tis.blogspot.com/2014/01/Curso-de-MySQL-Como-crear-una-Base-de-datos-en-MySQL-con-phpMyAdmin-y-MySQL-Workbench.html) y luego [crear una tabla](http://uh-tis.blogspot.com/2014/04/curso-de-mysql-como-crear-una-tabla-en-mysql-con-phpmyadmin-y-workbench.html) que en este caso hemos llamado “usuarios”:\
[![Tabla Usuarios creada en nuestra base de datos](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi6bsQmFpNCHSQmLemdToSDUiRrhZMd0THPBHHapDn57MyxZ1QwT02zb5eOzw_0OTnr-xpMJbnm6jHXwwz1nvDrEFqyBWV9dH6M42x7G6MQ8aDgjaVt7pm6bHX6y4TLwcU9lTC2MzWvEcfz/s1600/tabla-mysql-usuarios.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi6bsQmFpNCHSQmLemdToSDUiRrhZMd0THPBHHapDn57MyxZ1QwT02zb5eOzw_0OTnr-xpMJbnm6jHXwwz1nvDrEFqyBWV9dH6M42x7G6MQ8aDgjaVt7pm6bHX6y4TLwcU9lTC2MzWvEcfz/s1600/tabla-mysql-usuarios.png)\
Esta tabla consta de tres campos principales:\
-id\_usuario: Este será la llave primaria de nuestra tabla, el tipo de datos es entero (INT), con una longitud de 11, auto increment y NOT NULL.\
\
-usuario: Tipo de datos VARCHAR, con una longitud de 15 y NOT NULL.\
\
-clave: Tipo de datos BLOB y NOT NULL. En este campo como su nombre lo indica será donde guardaremos la contraseña de cada usuario, por ello usamos el tipo de datos BLOB ya que nos permitirá guardar cadenas de caracteres binarias (bytes) permitiéndonos aumentar la seguridad de las claves.\
\
\*Nos dirigiremos a nuestro proyecto en NetBeans IDE, seleccionamos nuestro paquete “Metodos” y damos clic derecho sobre el mismo; nos ubicamos en la opción “New” (Nuevo) y seguido damos clic sobre “Java Class…” (Clase Java):\
[![Crear una nueva Clase Java en nuestro proyecto](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhRuCw8bD7HBUx4_01GKiU17mWE1VigdF7yWb8LaBDJ5ITCCjlE-k6Qh68QWCvFIZ1ckCluLUFyikK1wEGNsBUWA_fPw8oU-Bc8ONqvlVFDejijy4PTAnXk22qyM4N5uG6Owo328uhfeiXb/s1600/new-java-class.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhRuCw8bD7HBUx4_01GKiU17mWE1VigdF7yWb8LaBDJ5ITCCjlE-k6Qh68QWCvFIZ1ckCluLUFyikK1wEGNsBUWA_fPw8oU-Bc8ONqvlVFDejijy4PTAnXk22qyM4N5uG6Owo328uhfeiXb/s1600/new-java-class.png) \
\*Nos saldrá una ventana “New Java Class” (Nueva Clase Java), en la cual nos ubicaremos en el campo “Class Name” (Nombre de la Clase) allí como su nombre lo indica digitaremos un nombre para nuestra Clase que en esta oportunidad llamaremos “MetodosLogin”; por último, damos clic en el botón “Finish” (Finalizar), y de esta manera nuestra Clase se habrá creado:\
[![Asignando un nombre a nuestra Clase Java](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjlSUfPNEC2MEUOGIjAFr5-zah9t8eJHxPfdDekqlLduNTnI9ytbZXfIB2S0TvdCc0tJlYAwyqvExR49Z_PkFsX4th4A9eBoEryWMSjzuQzhm9ajPYmiJlELYIhZfe0EER3bF3hYVb1MD5F/s1600/nueva-clase-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjlSUfPNEC2MEUOGIjAFr5-zah9t8eJHxPfdDekqlLduNTnI9ytbZXfIB2S0TvdCc0tJlYAwyqvExR49Z_PkFsX4th4A9eBoEryWMSjzuQzhm9ajPYmiJlELYIhZfe0EER3bF3hYVb1MD5F/s1600/nueva-clase-java.png)[![Clase Java creada en nuestro proyecto](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgZJGXf92VNsJxF-xyCX5RsPHCnjjPhMEt91oH9WLy8YJb1u3XtIs7kPKciGFhChZelbeHBgv08Nn3LSGtigaaiP-2xcCdN81j6knSsyC5X0K5h7TeV7jgk6UKwHr3_2Yay_baJxjLuEzHG/s1600/clase-java-metodoslogin.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgZJGXf92VNsJxF-xyCX5RsPHCnjjPhMEt91oH9WLy8YJb1u3XtIs7kPKciGFhChZelbeHBgv08Nn3LSGtigaaiP-2xcCdN81j6knSsyC5X0K5h7TeV7jgk6UKwHr3_2Yay_baJxjLuEzHG/s1600/clase-java-metodoslogin.png)\
\
\*Antes de seguir con nuestra Clase, nos dirigiremos al [formulario de acceso que creamos en un capítulo anterior](http://uh-tis.blogspot.com/2014/01/Curso-de-JAVA-Como-hacer-un-Login-con-usuario-y-clave-fijos-sin-conexion-a-Base-de-datos.html) de [este curso](http://uh-tis.blogspot.com/search/label/CURSO%20DE%20JAVA?\&max-results=8), allí seleccionaremos el campo de texto donde se digitará el nombre de usuario; luego, damos clic derecho y escogemos la opción “Customize Code” (Personalizar el Código):\
\
[![Seleccionamos el JTextField donde se digitará el nombre de usuario](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiw_3DzruEmhDCm_OGMhwMlzpKoSZY9yUQndN4ct4tUs1H-uuzgA3i1DI9bBRxjpWd-aoLcU90MsDDwtz5udRB80LktTprz2Z5n-afP83CALYlwSNdprO0vfABPMeZa-9j-DRpUd5S9DG_i/s1600/jtextfield-login-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiw_3DzruEmhDCm_OGMhwMlzpKoSZY9yUQndN4ct4tUs1H-uuzgA3i1DI9bBRxjpWd-aoLcU90MsDDwtz5udRB80LktTprz2Z5n-afP83CALYlwSNdprO0vfABPMeZa-9j-DRpUd5S9DG_i/s1600/jtextfield-login-java.png) \*Nos aparecerá una nueva ventana en la cual nos desplazaremos hacia la parte inferior, ubicándonos en la lista desplegable “Access”, donde deberemos seleccionar la opción “public” y seguidamente deberemos activar la casilla “static”; luego, damos clic en el botón “OK”, y clic en el botón “Save all files” (guardar todos los archivos) de la ventana principal de NetBeans IDE:\
\
[![Configurando las propiedades de acceso al componente JTextField](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi9RCXcDIZZXIp_mjao4P-ZQJH1K3Po2jnJhWvx8Wx3Pm4w85BFFjuJQfH0PSP_Wy5SFkHV3tTTosJiqwLNYFSJbw7-4deu4-Dlh1ktAb0NYxDyjrvSA55KdQJxRp7Cj7s8-DTL6SEZkUzs/s1600/access-public-static.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi9RCXcDIZZXIp_mjao4P-ZQJH1K3Po2jnJhWvx8Wx3Pm4w85BFFjuJQfH0PSP_Wy5SFkHV3tTTosJiqwLNYFSJbw7-4deu4-Dlh1ktAb0NYxDyjrvSA55KdQJxRp7Cj7s8-DTL6SEZkUzs/s1600/access-public-static.png)[![Clic en el botón guardar de la ventana principal de Netbeans IDE](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgvim78SRo39VECQXmC9Ksje7UWSwPNd0Cj-Xy3sQ0pv7oJgDTvLIZpriz6Sf8rpcY8sxgzlD26tFzT4kWKw6AQs-XsGycqgIqBJjWXFusjX25KZgtl9GVz8Gl5k21saPy579z1avQsCsW7/s1600/guardar-cambios-proyecto.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgvim78SRo39VECQXmC9Ksje7UWSwPNd0Cj-Xy3sQ0pv7oJgDTvLIZpriz6Sf8rpcY8sxgzlD26tFzT4kWKw6AQs-XsGycqgIqBJjWXFusjX25KZgtl9GVz8Gl5k21saPy579z1avQsCsW7/s1600/guardar-cambios-proyecto.png)\
El procedimiento anterior deberemos realizarlo igualmente con el campo de contraseña (JPassswordField).\
&#x20;\*Ahora, en la Clase “MetodosLogin” crearemos un método especial que nos permitirá llevar a cabo la verificación de los datos de ingreso al sistema; tales como, el usuario y la clave; para ello procedemos a realizar una consulta en la tabla "usuarios" de nuestra base de datos.Nuestra Clase quedará de la siguiente forma:\
\
\
\
\
<br>

```
package Metodos;

import Formularios.Login;
import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import javax.swing.JOptionPane;


public class MetodosLogin {

Pool metodospool = new Pool();

public int validar_ingreso(){

    String usuario = Login.txtUsuario.getText();
    String clave = String.valueOf(Login.jpassClave.getPassword());

    int resultado=0;
    
    String SSQL="SELECT * FROM usuarios WHERE usuario='"+usuario+"' AND clave=sha1('"+clave+"')";

    Connection conect = null;

    try {

        conect = metodospool.dataSource.getConnection();
        Statement st = conect.createStatement();
        ResultSet rs = st.executeQuery(SSQL);

        if(rs.next()){

            resultado=1;

        }

    } catch (SQLException ex) {

        JOptionPane.showMessageDialog(null, ex, "Error de conexión", JOptionPane.ERROR_MESSAGE);

    }finally{


        try {

            conect.close();

        } catch (SQLException ex) {

            JOptionPane.showMessageDialog(null, ex, "Error de desconexión", JOptionPane.ERROR_MESSAGE);

        }

    }

return resultado;

}

}
```

\
Si quieres una explicación más detallada sobre cada línea del código anterior, no dudes en visitar la siguiente entrada: ["Código JAVA: Login con conexión a Base de datos."](http://codigosparadesarrolladores.blogspot.com/2014/09/codigo-java-login-con-conexion-a-base-de-datos.html)\
\*Una vez que tengamos lista nuestra Clase, procederemos a dar doble clic sobre el botón “Ingresar” de nuestro formulario Login:\
\
\
[![Doble clic en el botón ingresar de nuestro formulario Login](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgs6LW4az26PBryygey_gEU3N6lNW1v6_VkcNl0hSBlig4fNrE90yLe_cUAdnXlEqRw7xTv7w479RzadN-SYoTphTxeMtH_sKYk7az1bLOxrOGj6fDcyJc8neGkAzRa89eBDqiKdJr2-R63/s1600/formulario-login-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgs6LW4az26PBryygey_gEU3N6lNW1v6_VkcNl0hSBlig4fNrE90yLe_cUAdnXlEqRw7xTv7w479RzadN-SYoTphTxeMtH_sKYk7az1bLOxrOGj6fDcyJc8neGkAzRa89eBDqiKdJr2-R63/s1600/formulario-login-java.png)\
\*Cuando entremos al método de dicho botón, borraremos el comentario que está por defecto y pegaremos el siguiente código:\
<br>

```
MetodosLogin metodoslogin = new MetodosLogin();

if(metodoslogin.validar_ingreso()==1){
                 
        this.dispose();

        JOptionPane.showMessageDialog(null, "Bienvenido\n Has ingresado "
        + "satisfactoriamente al sistema", "Mensaje de bienvenida",
        JOptionPane.INFORMATION_MESSAGE);

        Formulario1 formformulario1 = new Formulario1();          
        formformulario1.setVisible(true);

}else {
                    
        JOptionPane.showMessageDialog(null, "Acceso denegado:\n"
        + "Por favor ingrese un usuario y/o contraseña correctos", "Acceso denegado",
        JOptionPane.ERROR_MESSAGE);
            
}
```

\
\*En este código, lo que hacemos es llamar al método que creamos con anterioridad y luego validar a través de un condicional "if" que se cumpla un requisito (que el método nos devuelva un valor igual a 1) y proceder a ejecutar lo que allí definimos, en caso contrario se llevará a cabo lo que planteamos en la parte del "else".\
Si quieres una explicación más detallada sobre cada línea del código anterior, no dudes en visitar el siguiente artículo: ["Código JAVA: Login con conexión a Base de datos."](http://codigosparadesarrolladores.blogspot.com/2014/09/codigo-java-login-con-conexion-a-base-de-datos.html)\
\
\*Seleccionaremos ahora el archivo Login.java; es decir, el formulario Login de nuestro proyecto, damos clic derecho sobre el mismo y escogemos la opción “Run File” (ejecutar archivo):\
[![Procedemos a ejecutar el archivo .java del formulario Login de nuestro proyecto](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiLJOQPrD5Fig-f_gJofh0mGaOukWZM4PqQKENSZ0xgycJHhF_VBIHH_I42gIgBLc2cSqnqBRkAPLULy3jzlYpo0hUGFQMLN_gOJJoMzpoure8G8Z-HJOqT34UJ_CSEtZeIN-W6WTIONtGu/s1600/ejecutar-archivo-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiLJOQPrD5Fig-f_gJofh0mGaOukWZM4PqQKENSZ0xgycJHhF_VBIHH_I42gIgBLc2cSqnqBRkAPLULy3jzlYpo0hUGFQMLN_gOJJoMzpoure8G8Z-HJOqT34UJ_CSEtZeIN-W6WTIONtGu/s1600/ejecutar-archivo-java.png)\
\*Si ejecutamos nuestro formulario de acceso, podremos verificar que si digitamos datos incorrectos, no podremos ingresar al sistema:\
[![JOptionPane informándonos que los datos de ingreso al sistema están errados](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjpZMgpuppyI2QixU5TQS2k5O2JOYTyrnwTrFEJwa9-sb8V9q19op-6NPROVTvQfxSjZi04ofZeo5QsZKccHi8Aq4R2Z7sY9cm6HieE9jYxpSm_A6a6yweU-o5SfmGm6pwgtJ2IUnM9dD0B/s1600/ventana-acceso-denegado.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjpZMgpuppyI2QixU5TQS2k5O2JOYTyrnwTrFEJwa9-sb8V9q19op-6NPROVTvQfxSjZi04ofZeo5QsZKccHi8Aq4R2Z7sY9cm6HieE9jYxpSm_A6a6yweU-o5SfmGm6pwgtJ2IUnM9dD0B/s1600/ventana-acceso-denegado.png)\
\*En caso contrario:\
[![JOptionPane dándonos la bienvenida al sistema, luego de ingresar el usuario y clave correctos](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiC28KQiFWvw2DkkZySCXq9wnX87zrTycX2xTtjPWL0spUvUcPbEzic1gzxpCfXuM8rooEAROvgWmwpdpqnzlHkKoTyyN8F86j9_FmZEcRbc5l5flwq5ba1PLy1TJKtTjzy8VEGWYqv4C-G/s1600/joptionpane-de-bienvenida.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiC28KQiFWvw2DkkZySCXq9wnX87zrTycX2xTtjPWL0spUvUcPbEzic1gzxpCfXuM8rooEAROvgWmwpdpqnzlHkKoTyyN8F86j9_FmZEcRbc5l5flwq5ba1PLy1TJKtTjzy8VEGWYqv4C-G/s1600/joptionpane-de-bienvenida.png)\
[![Formulario principal de nuestro sistema de información](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEihbsO-Mi7nikwv8qsWuEJKlniUSvoipqNYs_qFc_-ciWPW9JtWdM44ULwWZH-g1e1pdm2FQatENKx9_olliZRBiJNWpmO161WpM1KWyBsQmHBBriWUrUGxsaoqRuPEZ0ziXV8wld33c856/s1600/formulario-principal-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEihbsO-Mi7nikwv8qsWuEJKlniUSvoipqNYs_qFc_-ciWPW9JtWdM44ULwWZH-g1e1pdm2FQatENKx9_olliZRBiJNWpmO161WpM1KWyBsQmHBBriWUrUGxsaoqRuPEZ0ziXV8wld33c856/s1600/formulario-principal-java.png)\
Ahora tenemos la posibilidad de integrar este módulo a nuestras aplicaciones, brindando así a nuestros usuarios y/o clientes; mayor seguridad y privacidad de la información de su empresa.<br>
