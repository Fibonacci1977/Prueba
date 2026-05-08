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

***

## Como Crear Un Formulario de Login en Java

[![Como Crear Un Formulario de Login en Java](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjfGuq6YSHRxAw_1KYHIMvkvlKgRd-ZEAbElWD9g7apzIn8KZBLhnqS0DJnesjzUfArh7s4T_8UWhCbkxWWV0t1KRMvyMtscPn_jdGf_jxxTSES_0F-o2BKTqaKmTpvuvlWN_nRw18CjT5W/s1600/Como+Crear+Un+Formulario+de+Login+en+Java.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjfGuq6YSHRxAw_1KYHIMvkvlKgRd-ZEAbElWD9g7apzIn8KZBLhnqS0DJnesjzUfArh7s4T_8UWhCbkxWWV0t1KRMvyMtscPn_jdGf_jxxTSES_0F-o2BKTqaKmTpvuvlWN_nRw18CjT5W/s1600/Como+Crear+Un+Formulario+de+Login+en+Java.jpg)

En esta ocasión traigo un tutorial sobre como crear un formulario de acceso en Java, ya que estos son muy útiles en el desarrollo de aplicaciones al ser un mecanismo de seguridad en las mismas.\
Muchas aplicaciones empresariales requieren de unos datos de validación antes de acceder a ellas y aunque estos sistemas requieren de seguridad adicional como encriptación de contraseñas, entre otros, en este artículo nos centraremos en ver como es el funcionamiento básico de un formulario de Login en Java.\
Por el momento, utilizaremos datos de acceso sumnistrados por nosotros mismos y que estarán almacenados en la aplicación, y en otro tutorial veremos como podemos hacerlo con datos recogidos de una base de datos.\
¿Qué Usaremos Para Este Tutorial?\
\- NetBeans v7.4\
\- Java 1.7\
\
Nivel: Intermedio\
\
Tiempo: 15 minutos\
\
1\. Creamos un proyecto en NetBeans con la siguiente estructura:\
\
[![Estructura Proyecto Como Crear Un Formulario de Login en Java](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhS5kp-h0i9Yz8zuB4ioww9iCeir2F7GQp-41TcDWLV0B_paI0Nt7ijwQdoYzHKysNpN5Sj-r2LHFpbOGZd6qIdsvwq7IqlE1ePoaCQ48nPZcvrKXLFozzbDHAKhy5_LPq5HMgsWOCIs8lN/s1600/Estructura+Proyecto+Como+Crear+Un+Formulario+de+Login+en+Java.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhS5kp-h0i9Yz8zuB4ioww9iCeir2F7GQp-41TcDWLV0B_paI0Nt7ijwQdoYzHKysNpN5Sj-r2LHFpbOGZd6qIdsvwq7IqlE1ePoaCQ48nPZcvrKXLFozzbDHAKhy5_LPq5HMgsWOCIs8lN/s1600/Estructura+Proyecto+Como+Crear+Un+Formulario+de+Login+en+Java.jpg)\
2\. Creamos las interfaces de usuario necesarias para este proyecto, las cuales corresponden a 2 JFrames. El primero lo hemos llamado Acceso y comprende el formulario de Login donde insertaremos dos JLabels, un JTextField, un JPasswordField y un JButton. El segundo JFrame lo nombramos Bienvenido y contiene solamente un JLabel con un mensaje de bienvenida.\
[![Formulario Login - Como Crear Un Formulario de Login en Java](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh1ek1Fc3Z6oFsj-tM7HdEmV0GfruDpvkJLR4EUs4fe2SSiUYhyphenhyphenDFKIlaQdrUpvqkz9Uzb7ACpCjSCMfKhLfNi4tJsLWduZY1nW3q-TWbEbC1e26KH1APq1mTG2pxnovHmuDqXfIeUsWWx1/s1600/Formulario+Login+-+Como+Crear+Un+Formulario+de+Login+en+Java.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh1ek1Fc3Z6oFsj-tM7HdEmV0GfruDpvkJLR4EUs4fe2SSiUYhyphenhyphenDFKIlaQdrUpvqkz9Uzb7ACpCjSCMfKhLfNi4tJsLWduZY1nW3q-TWbEbC1e26KH1APq1mTG2pxnovHmuDqXfIeUsWWx1/s1600/Formulario+Login+-+Como+Crear+Un+Formulario+de+Login+en+Java.jpg)\
[![Panel Bienvenida - Como Crear Un Formulario de Login en Java](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiWOA7092agGafSpsxTX3tyad6TuUlshAxleWcZRktvJ2aCYQkiT10vscjHWx-wemLvjwoO2Tu6pXeaGZwM7xmVbIjeqmSeapkzmCwrpnz2NuRSrd5AnAtf2BIGkJ_f4WrHX_TY75_2fjvh/s1600/Panel+Bienvenida+-+Como+Crear+Un+Formulario+de+Login+en+Java.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiWOA7092agGafSpsxTX3tyad6TuUlshAxleWcZRktvJ2aCYQkiT10vscjHWx-wemLvjwoO2Tu6pXeaGZwM7xmVbIjeqmSeapkzmCwrpnz2NuRSrd5AnAtf2BIGkJ_f4WrHX_TY75_2fjvh/s1600/Panel+Bienvenida+-+Como+Crear+Un+Formulario+de+Login+en+Java.jpg)\
3\. Creamos una variable de la clase Bienvenido antes del Constructor\
<br>

```
private Bienvenido b;
```

\
4\. En el código del ActionPerformed del JButton, colocaremos el siguiente código:\
<br>

```
String user, pass;
        
user = jTFuser.getText();
pass = jPFpass.getText();
      
if (user.equals("") || pass.equals("")) {
    /**
     * Mostramos este mensaje en caso de que alguno de los campos quede vacío
     */
    JOptionPane.showMessageDialog(this, "Debe Ingresar todos los campos", "Mensaje de Error", JOptionPane.ERROR_MESSAGE);
} else if(user.equals("usuario") || pass.equals("user123")) {
    /**
     * Mostramos este mensaje cuando los datos son correctos.
     * Además inicializamos la clase Bienvenido, ocultamos el formulario de login
     * y mostramos la ventana de bienvenida
     */
    JOptionPane.showMessageDialog(this, "Acceso Concedido");
    b = new Bienvenido();
    this.setVisible(false);
    b.setVisible(true);
} else {
    /**
     * Mostramos este mensaje en caso de que los datos de acceso no coincidan
     */
    JOptionPane.showMessageDialog(this, "Los datos no coinciden", "Mensaje de Error", JOptionPane.ERROR_MESSAGE);
}
```

\
El código quedaría más o menos así (omitiendo el código por defecto que crea NetBeans):\
<br>

```
private Bienvenido b;
    
public Acceso() {
    initComponents();
}                       

private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
    String user, pass;
       
    user = jTFuser.getText();
    pass = jPFpass.getText();
        
    if (user.equals("") || pass.equals("")) {
        JOptionPane.showMessageDialog(this, "Debe Ingresar todos los campos", "Mensaje de Error", JOptionPane.ERROR_MESSAGE);
    } else if(user.equals("usuario") || pass.equals("user123")) {
        JOptionPane.showMessageDialog(this, "Acceso Concedido");
        b = new Bienvenido();
        this.setVisible(false);
        b.setVisible(true);
    } else {
        JOptionPane.showMessageDialog(this, "Los datos no coinciden", "Mensaje de Error", JOptionPane.ERROR_MESSAGE);
    }
}
```

\
5\. Ejecutamos y listo.\
\
Si lo deseas, puedes ver un vídeo tuorial donde realizo este proyecto y explico a detalle cada paso para realizar un formulario de login en java:

{% embed url="https://youtu.be/UGv9boto8e4?si=0RoIIbwjDyhbqbjw" %}

***

## Cómo crear un Login? (Con conexión a base de datos MVC)

[11:15 a.m.](https://uh-tis.blogspot.com/2018/09/curso-de-java-como-crear-un-login-con-conexion-a-base-de-datos-mvc.html)  [APLICACIONES](https://uh-tis.blogspot.com/search/label/APLICACIONES?\&max-results=8), [BASES DE DATOS](https://uh-tis.blogspot.com/search/label/BASES%20DE%20DATOS?\&max-results=8), [CÓDIGO](https://uh-tis.blogspot.com/search/label/C%C3%93DIGO?\&max-results=8), [CURSO DE JAVA](https://uh-tis.blogspot.com/search/label/CURSO%20DE%20JAVA?\&max-results=8), [CURSOS](https://uh-tis.blogspot.com/search/label/CURSOS?\&max-results=8), [DESARROLLO DE SOFTWARE](https://uh-tis.blogspot.com/search/label/DESARROLLO%20DE%20SOFTWARE?\&max-results=8), [DESCARGAR](https://uh-tis.blogspot.com/search/label/DESCARGAR?\&max-results=8), [FORMULARIO](https://uh-tis.blogspot.com/search/label/FORMULARIO?\&max-results=8), [JAVA](https://uh-tis.blogspot.com/search/label/JAVA?\&max-results=8), [JFRAME](https://uh-tis.blogspot.com/search/label/JFRAME?\&max-results=8), [LOGIN](https://uh-tis.blogspot.com/search/label/LOGIN?\&max-results=8), [modelo vista controlador](https://uh-tis.blogspot.com/search/label/modelo%20vista%20controlador?\&max-results=8), [MVC](https://uh-tis.blogspot.com/search/label/MVC?\&max-results=8), [MYSQL](https://uh-tis.blogspot.com/search/label/MYSQL?\&max-results=8), [NETBEANS IDE](https://uh-tis.blogspot.com/search/label/NETBEANS%20IDE?\&max-results=8), [poo](https://uh-tis.blogspot.com/search/label/poo?\&max-results=8), [PROGRAMACIÓN](https://uh-tis.blogspot.com/search/label/PROGRAMACI%C3%93N?\&max-results=8), [TUTORIALES](https://uh-tis.blogspot.com/search/label/TUTORIALES?\&max-results=8)\
\
\
\
\
En este nuevo capítulo nos adentraremos a una parte esencial de este curso, cuando se trata de desarrollar una aplicación surge la necesidad de validar el ingreso a nuestro sistema, esto lo hacemos a través de una validación de usuario. Donde el administrador del sistema ingresa digitando un usuario y una contraseña en la cual los datos de acceso se encuentran previamente almacenados en una base de datos, lo que nosotros hacemos simplemente es validar la información ingresada con la información o datos de acceso que ya tenemos en nuestra base de datos.\
Para el desarrollo de este ejemplo aplicaremos el patrón de diseño Modelo Vista Controlador (MVC), aplicando este patrón de diseño básicamente lo que haremos es separar la parte lógica de nuestra aplicación con la parte gráfica, este concepto  será ampliado en el transcurso de este tutorial.\
Te recomiendo los siguientes POST para ampliar conceptos que estaremos tratando en el desarrollo de este ejemplo.\
[Cómo hacer un Pool de Conexiones?](https://uh-tis.blogspot.com/2014/05/curso-de-java-como-conectar-nuestra-aplicacion-con-una-base-de-datos-forma-optima.html)\
[Cómo hacer un proyecto, un paquete y un formulario?](https://uh-tis.blogspot.com/2012/07/curso-de-java-como-hacer-un-proyecto-un.html)\
\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjj6amzppxrGcbaWVKcREnshGDyeaUcwgME1a-XAEAqVwEXZI278DU9uvX95YSAtSwnn6ohYzW6gXqcvsXezwAVMn1KJ6y6qe445SR1DWK6xAbUGLbPACR1fPfGmwP7O4BKjlyXbv8-HH8/s640/Login_MVC_en_java_INICIO%5B1%5D.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjj6amzppxrGcbaWVKcREnshGDyeaUcwgME1a-XAEAqVwEXZI278DU9uvX95YSAtSwnn6ohYzW6gXqcvsXezwAVMn1KJ6y6qe445SR1DWK6xAbUGLbPACR1fPfGmwP7O4BKjlyXbv8-HH8/s1600/Login_MVC_en_java_INICIO%5B1%5D.jpg)\
\
\
\
Explicación por Videotutorial:\
Parte 1 Modelo<br>



{% embed url="https://youtu.be/K9hBs7fxGpE?si=6oN61aJ7_s_DZ9Bn" %}

Parte 2 Controlador

{% embed url="https://youtu.be/liZ6BeAPRcQ?si=TpoJRtsA5e2C4eB4" %}

Parte 3 Vista

{% embed url="https://youtu.be/r7l5LR0QqyQ?si=M1XbNcUcWPYnRU5c" %}

\
\
\
Explicación por Foto-Tutorial: \
\
Antes de adentrarnos en el desarrollo de nuestro  ejemplo, explicare el concepto del patrón de diseño modelo-vista-controlador (MVC). Este será la base de nuestra aplicación.\
\
Según Wikipedia el MVC se define como: \
\
"Un patrón de arquitectura de software, que separa los datos y la lógica de negocio de una aplicación de su representación y el módulo encargado de gestionar los eventos y las comunicaciones. Para ello MVC propone la construcción de tres componentes distintos que son el modelo, la vista y el controlador, es decir, por un lado define componentes para la representación de la información, y por otro lado para la interacción del usuario."\
\
En resumidas cuentas lo que logramos bajo esta arquitectura es dividir nuestro código de aplicación en tres capas la parte de la vista podemos definirla como la sección de nuestra aplicación donde están todos lo componentes gráficos de esta, la cual podrá interactuar con el administrador o usuario que maneje el sistema.\
La sección del modelo se encuentra  toda la parte lógica de nuestra aplicación, para el ejemplo que desarrollaremos en la sección del modelo, irán los métodos y clases que nos permitirán acceder a la base de datos.\
La sección del controlador será él puente de comunicación entre la vista y el modelo en esta se identificaran los eventos que accione el administrador del sistema, aplicado a nuestro ejemplo; cuando el administrador del sistema ingrese los datos de acceso y este oprima el botón de inicio de sesión, se activara un evento en la clase controlador, la cual se comunicara con el la clase modelo que realizara la consulta a la base de datos y esta arrojara los resultados, donde validaremos si el usuario y contraseña coinciden con los almacenados en la base de datos. <br>

> &#x20;NOTA: Si tienes dificultad o quieres reforzar conceptos de base de datos te invito a que visites nuestro [curso de MySQL](https://uh-tis.blogspot.com/search/label/CURSO%20DE%20MYSQL?\&max-results=8)

\
1\.  Trabajaremos con una base de datos a la cual hemos llamado "ejemplousuarios", la cual contara con una tabla que lleva la siguiente estructura:\
<br>

| [![Base de datos perteneciente a los usuarios](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg0LFtpjMapW_dqK1nC-hidukE_gVGP0WceYThKUWXwMNwdv19c-3SDtOM7ZKEgqXeDcCd-uAPTxWv6abFVbgkXjs7s5ahPv5hEzz8n0l4x7zXE6YT4hDzh6Bp8azmMLqXB_28IqzaD_oY/s400/base-de-datos-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg0LFtpjMapW_dqK1nC-hidukE_gVGP0WceYThKUWXwMNwdv19c-3SDtOM7ZKEgqXeDcCd-uAPTxWv6abFVbgkXjs7s5ahPv5hEzz8n0l4x7zXE6YT4hDzh6Bp8azmMLqXB_28IqzaD_oY/s1600/base-de-datos-java.png) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Base de datos "ejemplousuarios"                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

| [![tabla la cual almacenara los datos de acceso de los usuarios](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgo1ItpmaagIimw2ziCI_9IyCi_SLZSC-17Gbfbkf5nUEXGeOhUngrRelHGITquVqat4B5f73yKhpamWVChS7C3vMX8CoeSMap5N4ZHS3umZ8u1PyLFAjojxIRGY7BBraov_o1599JLvMo/s320/tabla-base-de-datos.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgo1ItpmaagIimw2ziCI_9IyCi_SLZSC-17Gbfbkf5nUEXGeOhUngrRelHGITquVqat4B5f73yKhpamWVChS7C3vMX8CoeSMap5N4ZHS3umZ8u1PyLFAjojxIRGY7BBraov_o1599JLvMo/s1600/tabla-base-de-datos.png) |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p><br></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

Una vez creada la base de datos creamos una tabla la cual contiene 3 campos, el primer campo (id) es de tipo entero esta será la Primary key o Llave primaria de la tabla. El segundo campo (User) tipo VARCHAR en el cual guardaremos los respectivos nombres de usuarios, por ultimo tenemos el campo Pass es un campo de tipo LONGBLOB, en el cual almacenaremos las respectivas contraseñas.<br>

> &#x20;NOTA: Es recomendable trabajar con campos tipo BLOB (\
> LONGBLOB), cuando de almacenar contraseñas se trate para tener mayor seguridad en estas.\
> Estos temas pueden interesarte.\
> [Cómo crear una Base de datos con phpMyAdmin y MySQL Workbench?](https://uh-tis.blogspot.com/2014/01/Curso-de-MySQL-Como-crear-una-Base-de-datos-en-MySQL-con-phpMyAdmin-y-MySQL-Workbench.html)\
> [Cómo crear una tabla con phpMyAdmin y Workbench? ](https://uh-tis.blogspot.com/2014/04/curso-de-mysql-como-crear-una-tabla-en-mysql-con-phpmyadmin-y-workbench.html)

\
2\.  La estructura de nuestro proyecto en java, constara de cuatro paquetes, estos serán: \
paquete controlador; el cual contendrá la clase controlador.java. \
paquete imagenes; agregaremos los archivos externos(imágenes) que utilizara nuestra aplicación. \
paquete loginmvc; contendrá tres clases (Inicio.java, LoginMVC.java y login.java) aquí agregaremos nuestra clase principal y la interfaz gráfica que estaremos manejando.\
paquete modelo;  contendrá tres clases(User.java, modelUser.java, pool.java) esta clases nos permitirán establecer la conexión con la base de datos e igualmente la validación de los datos de inicio de sesión de usuario.\
Por ultimo agregaremos las librerías requeridas a nuestro proyecto, con el fin de poder usar los métodos y clases de estas.\
<br>

> &#x20;NOTA: Las librerías utilizadas en este proyecto junto con el código fuente, puedes acceder a estos en la [zona de descargas.](https://uh-tis.blogspot.com/p/blog-page.html)

| [![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjxpz9Dd0I0uqlJQ7V1Oyz07pS8fe1xsYQb52X0D4-A54rblJ1k4teLV5lH1FRDI1DAkHbYOkEsf0nPYYxjFbTD4KF0pGI7afKHDA6NPsidbxrQkKUCTdd32UO1oZEi-L_crSrkTqw20fM/s640/estructura-proyecto-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjxpz9Dd0I0uqlJQ7V1Oyz07pS8fe1xsYQb52X0D4-A54rblJ1k4teLV5lH1FRDI1DAkHbYOkEsf0nPYYxjFbTD4KF0pGI7afKHDA6NPsidbxrQkKUCTdd32UO1oZEi-L_crSrkTqw20fM/s1600/estructura-proyecto-java.png) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Estructura Proyecto java                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

\
\
3\.  Iniciamos creando las clases del paquete modelo, la primera que crearemos  será la clase pool.java, la cual nos permitirá realizar las configuraciones requeridas para poder conectarnos con la base de datos (ejemplousuarios).\
Entre las llaves {} de apertura y cierre de nuestra clase, creamos una serie de objetos y variables en los cuales almacenaremos los datos de conexión a la base de datos, por ejemplo:\
En la variable db la cual será tipo String agregaremos el nombre de la base de datos.\
En la variable url escribimos la dirección en la cual se encuentra la base de datos, nosotros la trabajaremos de manera local. \
En la variable user guardamos el usuario que tiene acceso a dicha base de datos, trabajaremos con el que viene por defecto (root).\
\
\
Clase pool.java<br>

```
```

```
package modelo;

import javax.sql.DataSource;
import org.apache.commons.dbcp.BasicDataSource;

/**
 *
 * @author jorgeluis
 */

public class pool {
    
    public DataSource dataSource;
    public String db = "ejemplousuarios";
    public String url = "jdbc:mysql://localhost/"+db";    public String user = "root";    public String pass = "";
    public pool(){

        inicializaDataSource();

    }

    private void inicializaDataSource(){


        BasicDataSource basicDataSource = new BasicDataSource();

        basicDataSource.setDriverClassName("com.mysql.jdbc.Driver");
        basicDataSource.setUsername(user);
        basicDataSource.setPassword(pass);
        basicDataSource.setUrl(url);
        basicDataSource.setMaxActive(50);

        dataSource = basicDataSource;

    }

    

    
}
```

```
```

```
```

> &#x20;NOTA: Te recomiendo el siguiente POST en el cual aprenderás a detalle [Cómo hacer un Pool de Conexiones?](https://uh-tis.blogspot.com/2014/05/curso-de-java-como-conectar-nuestra-aplicacion-con-una-base-de-datos-forma-optima.html)

\
4\.  El siguiente paso será crear la clase Usuario.java, esta clase tendrá unos componentes precisos, ya que a través de esta clase podemos asignar o mostrar los valores obtenidos de la base de datos.\
Para esto debemos crear una serie de variables que harán referencia a los campos que contiene la tabla en nuestra base de datos. Por ejemplo:\
Nuestra tabla usuarios, tiene un campo id, User y Pass, esto quiere decir que las variables que necesitaremos crear en nuestra clase serán dos, una hará referencia a User y otra a Pass.\
\
Dentro de las llaves {} de apertura y cierre, creamos dos variables tipo String, la cual llamaremos User y Pass respectivamente, el modificador de acceso de estas variables será de tipo private. \
Seguido a esto creamos el método constructor e inicializamos las variables creadas con anterioridad (User y Pass).\
Creamos los métodos get y set de las variables esto con el fin de obtener los valores de dichas variables, desde otra clase.\
\
Clase Usuario.java<br>

```
```

package modelo;\
/\*\* \* \* @author Software Galaxia \*/\
public class Usuario {\
\
private String User;\
private String Pass;\
\
public Usuario(){\
User="";\
Pass="";\
}\
\
public String getUser() {\
return User;\
}\
\
public void setUser(String User) {\
this.User = User;\
}\
\
public String getPass() {\
return Pass;\
}\
\
public void setPass(String Pass) {\
this.Pass = Pass;\
}\
\
}<br>

```
```

```
```

\
5\.  El siguiente paso será crear la clase metodosUsuario.java, esta clase tendrá los métodos que nos permitirán realizar la validación con los datos almacenados; en el cual verificaremos si lo datos ingresados por el usuario o administrador del sistema son válidos.\
\
\*Iniciamos importando las respectivas librerías que utilizaremos, para el correcto funcionamiento de nuestro código.\
\
<br>

| [![clase metodosUsuario.java](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj4V6x2Ga4TtMB12cupeqUpa1kSJs5OTuUUsnnCM5i3r-6ulcfiz_vlnj5VQUVeTpSQE67t-FqmBvsyQRuqxQ2O3sLEK8bh7bT8sd94On-l6eKKsprdMQrvfePRsJr3cDsM67YkbVNKx4Q/s640/modelo-imports.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj4V6x2Ga4TtMB12cupeqUpa1kSJs5OTuUUsnnCM5i3r-6ulcfiz_vlnj5VQUVeTpSQE67t-FqmBvsyQRuqxQ2O3sLEK8bh7bT8sd94On-l6eKKsprdMQrvfePRsJr3cDsM67YkbVNKx4Q/s1600/modelo-imports.png) |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| importamos las librerías requeridas                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

\
\*Una vez importadas las librerías, dentro de las llaves {} de apertura y cierre de nuestra clase, creamos un objeto de tipo pool  llamado conexion, seguido a esto inicializamos nuestro objeto desde el método constructor de la clase.\
Recordemos que la clase pool contiene los datos de acceso a la base de datos\
<br>

| [![clase modelUser.java](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgzPtypNpnlZgb1XaOiWzJeESSHuG0o7Mq355bR62R-rfRqq2Qi6RmqoV7fj_qYvfDTBMhqTkVlOIfGOZsl8u-kA5eSDBSL4yM_Nu9wo0WyMas97DOsnnKdbZGAX02o6iFHsUBDqlGsPAs/s640/modelUser-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgzPtypNpnlZgb1XaOiWzJeESSHuG0o7Mq355bR62R-rfRqq2Qi6RmqoV7fj_qYvfDTBMhqTkVlOIfGOZsl8u-kA5eSDBSL4yM_Nu9wo0WyMas97DOsnnKdbZGAX02o6iFHsUBDqlGsPAs/s1600/modelUser-java.png) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Clase modelUser.java                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

\
\*Lo que haremos será crear una función, que nos devolverá un elemento de tipo ArrayList  nuestro ArrayList sera de tipo Usuario (clase), recordemos que esta es la clase que creamos en el paso anterior (paso 4), la estructura de nuestra función será de acceso public (public ArrayList\<Usuario>) llevara dos parámetros tipo String que harán referencia al usuario y contraseña.(public ArrayList\<Usuario> login(String user, String clave){}).\
\* Debemos crear 5 objetos de suma importancia para este método:\
&#x20;  1- objeto tipo Conection (conectar) el cual nos permitirá administrar la             conexión obtenida con la base de datos.\
&#x20;  2- objeto tipo PreparedStatement (pst) el cual principalmente nos                   permitirá cargar y ejecutar la sentencia sql que estaremos creando.\
&#x20; 3-  objeto tipo ResultSet (rs) el cual nos permitirá obtener los resultados             que arroje la consulta sql que estaremos realizando.\
&#x20; 4- objeto tipo Usuario (cuenta), este objeto almacenara los resultados              obtenidos de la base de datos, posteriormente serán asignados a un              ArrayList.\
&#x20;  5- objeto tipo ArrayList (list) agregaremos cada elemento obtenido de               manera ordenada. \
\
<br>

| [![método login](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgtpwZS9GrXrvfqRZ6Icm_73Qg1IusM33PEA2ExkP-pZjLmFJ9ulzPLPWvCPDN9WiLFTcXsGo39cpFZk65fBHXWwELWsqzxbD3wROXhSBg2Lu4b38uAgf3M_lA0_7_nenfJ6pu0b_QVCYY/s640/metodo-login-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgtpwZS9GrXrvfqRZ6Icm_73Qg1IusM33PEA2ExkP-pZjLmFJ9ulzPLPWvCPDN9WiLFTcXsGo39cpFZk65fBHXWwELWsqzxbD3wROXhSBg2Lu4b38uAgf3M_lA0_7_nenfJ6pu0b_QVCYY/s1600/metodo-login-java.png) |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| método login                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

\*  Creamos un bloque de tipo try-catch-finally, en la sección del try iniciamos obteniendo la conexión con la base de datos, el resultado obtenido lo asignaremos al objeto conectar (tipo Connection). Seguido a esto verificamos si conectar es diferente de null.\
<br>

| [![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiOMAfNuw9WWX-Rqd51U-pgXzQd0vsAmldPM4xBxEL10LnswSewXpk4sbf1VxhdLlXpRhSpqT9S5lju2hywazRX5XT4_X5nTaM2rLKM21nQvE-H_TQdpwywrWjLBHwsJCEfACU1-u4iZT0/s640/try-catch-finally-modelo.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiOMAfNuw9WWX-Rqd51U-pgXzQd0vsAmldPM4xBxEL10LnswSewXpk4sbf1VxhdLlXpRhSpqT9S5lju2hywazRX5XT4_X5nTaM2rLKM21nQvE-H_TQdpwywrWjLBHwsJCEfACU1-u4iZT0/s1600/try-catch-finally-modelo.png) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| establecer conexión con la base de datos                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

\
\*  Nos posicionamos en la sección donde realizamos la consulta a la base de datos, la cual consta de la siguiente estructura.\
\
Select User, Pass From usuarios\
\
En la primera sección de la sentencia, iniciamos con la palabra clave Select la cual es utilizada cuando queremos obtener información de la base de datos, seguido  a esto seleccionamos los campos a los cuales deseamos acceder, en este caso será: el campo User y Pass, igualmente seleccionamos la tabla a la cual deseamos acceder en este caso es la tabla usuarios.\
\
WHERE User=? AND Pass=AES\_ENCRYPT(?, 'key')\
\
La segunda sección de nuestra sentencia es la parte de las condiciones requeridas para la búsqueda, hacemos uso de la palabra clave WHERE, en la cual necesitaremos verificar si el usuario y contraseña coinciden con la información almacenada en la base de datos, debemos hacer uso de una función propia de MySQL, la cual es AES\_ENCRYPT, la cual nos permitirá encriptar la contraseña ingresada y así compararla con el campo de la base de datos.\
Consta de dos parámetros (?, 'key'), el primero hará referencia a la contraseña ingresada para este ejemplo es "1234", el segundo parámetro será la llave que nos permitirá acceder a esta, nuestra llave será 'key'.\
\
<br>

| [![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj5aBFunhnrEHXxH6a3EF3PcNBT_myKXSxON5d6Y8Y3JvMd2Csu-BRpoupYireNA59D4Qf7St7S-MCIJ27hlultgJ9Pq1OlQRAWLJz2M2Dm-Z7CUe5WbdwkYEE4jxTmggfXnFPnehF15Ro/s640/sentencia-SQL.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj5aBFunhnrEHXxH6a3EF3PcNBT_myKXSxON5d6Y8Y3JvMd2Csu-BRpoupYireNA59D4Qf7St7S-MCIJ27hlultgJ9Pq1OlQRAWLJz2M2Dm-Z7CUe5WbdwkYEE4jxTmggfXnFPnehF15Ro/s1600/sentencia-SQL.png) |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| sentencia SQL y parametros                                                                                                                                                                                                                                                                                                                                                                                                                                               |

\
\* Una vez pasado los respectivos parámetros de consulta y una vez ejecutada la misma, debemos obtener dicho resultados esto lo haremos con las siguientes líneas de código:\
&#x20;                <br>

| [![metodosUsuario.java](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEimZHDGyHK7C_4rkIlH2W47YByx5LexP42hDS51xwKlIFDVLZfRnY-hRhgmxIFsBgm_5p2JT6WYXGxrlmqC-C1qjonimwqgMX-u1cTu0xObvmRgaic8_JgILmEK6OdQ9sER34sko56ud5g/s640/condicional-modelo-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEimZHDGyHK7C_4rkIlH2W47YByx5LexP42hDS51xwKlIFDVLZfRnY-hRhgmxIFsBgm_5p2JT6WYXGxrlmqC-C1qjonimwqgMX-u1cTu0xObvmRgaic8_JgILmEK6OdQ9sER34sko56ud5g/s1600/condicional-modelo-java.png) |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Verificamos Resultados de consulta SQL                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |

\
\
\
\
\
\
\
Clase metodosUsuario.java<br>

```
```

package modelo;\
\
import java.sql.Connection;\
import java.sql.PreparedStatement;\
import java.sql.ResultSet;\
import java.sql.SQLException;\
import java.util.ArrayList;\
import javax.swing.JOptionPane;<br>

```
```

\
public class metodosUsuario {\
&#x20;   \
\
&#x20; private final pool conexion;\
&#x20;   \
&#x20; public metodosUsuario(){\
&#x20;   conexion=new pool();\
\
\
&#x20; }\
\
&#x20;   public ArrayList\<Usuario> login(String user, String clave){\
&#x20;    \
&#x20;          Connection conectar=null;\
&#x20;          PreparedStatement pst;\
&#x20;          ResultSet rs ;\
&#x20;          Usuario cuenta ;\
&#x20;          ArrayList list = new ArrayList();\
&#x20;      \
&#x20;         try{\
&#x20;              // obtenemos la conexion con la base de datos\
&#x20;              conectar = conexion.dataSource.getConnection(); \
&#x20;          \
&#x20;              if(conectar != null){\
\
&#x20;                  String sql ="SELECT User, Pass FROM usuarios WHERE User =? AND Pass=AES\_ENCRYPT(?, 'key')";\
&#x20;                  pst = conectar.prepareStatement(sql);\
&#x20;                  pst.setString(1, user);\
&#x20;                  pst.setString(2, clave);\
&#x20;                  rs = pst.executeQuery();\
&#x20;              \
&#x20;                  if(rs.next()){\
&#x20;                  \
&#x20;                       cuenta = new Usuario();\
&#x20;                       cuenta.setUser(rs.getString("User"));\
&#x20;                       cuenta.setPass(rs.getString("Pass"));                                       \
&#x20;                       list.add(cuenta);\
&#x20;                 }\
&#x20;          \
&#x20;            }else{\
&#x20;            \
&#x20;                JOptionPane.showMessageDialog(null, "Hubo un error al realizar la operación, intente mas tarde","ERROR",JOptionPane.ERROR\_MESSAGE);\
&#x20;            }\
&#x20;      \
&#x20;        }catch(SQLException e){\
&#x20;    \
&#x20;            JOptionPane.showMessageDialog(null, e , " .::Error En la Operacion::.", JOptionPane.ERROR\_MESSAGE);\
&#x20;      \
&#x20;       }finally{\
&#x20;           try{\
&#x20;             conectar.close();\
&#x20;           }catch(SQLException ex){\
&#x20;              System.out.println("error "+ex);\
&#x20;           }\
&#x20;        }\
&#x20;\
&#x20;   return list;\
&#x20;   }\
\
}   \
\
\
\
<br>

```
```

\
6\.  Una vez creada las clases del paquete modelo, procedemos a crear la clase controlador.java; la cual tendrá la siguiente estructura.\
<br>

| [![controlador.java imports](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi6CgnuJCMszEnatp5uZUkcZ-1OImSneHK42iMHvajhTR9oQla5b-XD8ZelcDXHdhKwrPm1mqfdsvd_NVEJ6BqG-_bvxzI2go2UB13YCZ5G79Fyw6zfdFpeSar39tB-NR7O79z9NRQcHrI/s640/controlador1-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi6CgnuJCMszEnatp5uZUkcZ-1OImSneHK42iMHvajhTR9oQla5b-XD8ZelcDXHdhKwrPm1mqfdsvd_NVEJ6BqG-_bvxzI2go2UB13YCZ5G79Fyw6zfdFpeSar39tB-NR7O79z9NRQcHrI/s1600/controlador1-java.png) |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Imports Clase controlador.java                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

\
\*Iniciamos realizando las respectivas importaciones de librerías y clases con las cuales vamos a trabajar.\
\
\
<br>

| [![controlador.java](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh0-EPgpUaClesG4Fn1msVfFVSKMd3xwbXvJ8jnJBHTOA16sZaHJxWcg7f_WtaE5rCq41Oox3315vgfTRPULgMglySfd_GmKEDCqGcIPP2uaAy8n7FmPB6LgSFJn2pkWQxjzB2lG65zG5U/s640/Clase-controlador-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh0-EPgpUaClesG4Fn1msVfFVSKMd3xwbXvJ8jnJBHTOA16sZaHJxWcg7f_WtaE5rCq41Oox3315vgfTRPULgMglySfd_GmKEDCqGcIPP2uaAy8n7FmPB6LgSFJn2pkWQxjzB2lG65zG5U/s1600/Clase-controlador-java.png) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Linea inicial controlador.java                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

\
\*Creamos nuestra clase la cual llamaremos controlador.java, hacemos uso de la palabra clave implements, y de estas manera llamar la interfaz ActionListener, la cual la utilizaremos para accionar los eventos que vamos a trabajar en este ejemplo, estos eventos se ejecutaran cuando presionemos el botón de inicio de sesión o el botón salir.\
<br>

| [![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg9X-2uOSpfpsPQlEyq-NSkPN56zQ4Y5g7CVE2pdJOOJLuD1Pv1P9p5O2nZ3uZPnvuxR6RasjFehcSidh2jI_7_mcs7APeQQt8Zbk_lqaDSw44ttxvrnJYJA387sGoSjr1AlqiJHkerzR4/s640/Objetos-controlador-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg9X-2uOSpfpsPQlEyq-NSkPN56zQ4Y5g7CVE2pdJOOJLuD1Pv1P9p5O2nZ3uZPnvuxR6RasjFehcSidh2jI_7_mcs7APeQQt8Zbk_lqaDSw44ttxvrnJYJA387sGoSjr1AlqiJHkerzR4/s1600/Objetos-controlador-java.png) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Objetos pertenecientes a la vista y modelo                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

\
\*Lo siguiente que haremos será crear tres objetos, recordemos que esta clase es la que comunicara las clases de la vista y el modelo; por lo tanto creamos un objeto tipo login la cual contiene los elementos de la interfaz gráfica(vista). Creamos un objeto tipo metodosUsuarios, recordemos que esta clase contiene el método que nos permitirá validar la información ingresada con la que tenemos almacenada en base de datos.\
Creamos un objeto tipo inicio, el cual contiene una vista de inicio que mostraremos si el usuario y contraseña son correctos.\
\
<br>

| [![clase controlador.java](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiNEUH2VhW7hpXdDcWw5k4-q-MVKl6Gf2pZ5h4z3Lt6ApyNnLsmM_BTgKQq4aPxIdx-gMCP3f1kWssQX23_wWEifNlR_K8n9RavIcKiPjdj9ZzlKs4v9TWoUw-AokQybt5sbc-m5CP0WNo/s640/eventos-controlador-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiNEUH2VhW7hpXdDcWw5k4-q-MVKl6Gf2pZ5h4z3Lt6ApyNnLsmM_BTgKQq4aPxIdx-gMCP3f1kWssQX23_wWEifNlR_K8n9RavIcKiPjdj9ZzlKs4v9TWoUw-AokQybt5sbc-m5CP0WNo/s1600/eventos-controlador-java.png) |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Agregamos los eventos al controlador                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

\
\* Creamos un método (eventos), en el cual asignaremos eventos a los respectivos componentes de la vista, recordemos que; para acceder a los componentes de otra clase, debemos hacer uso de un objeto (view) de esta, seguido del nombre del componente y por ultimo llamamos el método addActionListener.\
\
<br>

| [![metodo contructor controlador.java](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiaNmy5EhyphenhyphenPNk6y6ghplIGXd8EdEH2n07B7T_cDQRD_vu1K3F_XK3UYAu428tMAE7AFwOSvzNEvE_K1SFRzuLCpOLvDGCeiaAi-VvJhhmSUjD1oKbsN4d2POrDQQaKK4o9NYBgmreDCxJw/s640/metodo-constructor-controlador-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiaNmy5EhyphenhyphenPNk6y6ghplIGXd8EdEH2n07B7T_cDQRD_vu1K3F_XK3UYAu428tMAE7AFwOSvzNEvE_K1SFRzuLCpOLvDGCeiaAi-VvJhhmSUjD1oKbsN4d2POrDQQaKK4o9NYBgmreDCxJw/s1600/metodo-constructor-controlador-java.png) |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| método constructor                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

\
\* Lo siguiente que haremos será crear el método constructor de la clase, \
el cual llevará un parámetro de tipo login(vista), inicializamos el objeto view que creamos( this.view=vista;) e igualmente agregamos el método eventos, de esta manera pasaremos a la sección mas importante de nuestro código que es el control de los eventos.\
\
<br>

| [![eventos controlador.java](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhVgWQtcxu9LDtEN8ypOZPCjvlYTVXvvcHhb1KKUA4dVoUKr66cM1wvRVRXV8Kaiylf5NHtDUKCGct3ZY2ozmCTbqcvj3NsUp7YFl_MrMyZlF5gFL3KiAKX5gBEu7yW6UxBxo-HVwRFaxU/s640/metodo-actionperformed-controlador-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhVgWQtcxu9LDtEN8ypOZPCjvlYTVXvvcHhb1KKUA4dVoUKr66cM1wvRVRXV8Kaiylf5NHtDUKCGct3ZY2ozmCTbqcvj3NsUp7YFl_MrMyZlF5gFL3KiAKX5gBEu7yW6UxBxo-HVwRFaxU/s1600/metodo-actionperformed-controlador-java.png) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| método actionPerformed                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

\
\*Al utilizar la palabra clave implements seguido de actionListener al inicio de nuestra clase, esto nos permitirá acceder a su método actionPerformed, dentro de este método irán todas las acciones que deseamos que se ejecuten, la cual debemos controlar a través de condicionales.\
\
La variable la cual controlara los eventos que se accionen será evt, en el primer condicional verificamos si se ha oprimido el botón de inicio de sesión(if(evt.equals(view.btn\_enter))), seguido a esto debemos verificar si el campo usuario(txt\_user) y el campo contraseña(txt\_pass) tienen información valida.\
\
\* De esta manera nace nuestro primer condicional, en el cual verificamos si el campo txt\_user o el campo txt\_pass están vació; si la condición se cumple, imprimimos un mensaje de advertencia. <br>

| [![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhH_s8yj2MBILs1DpuxntLES4MIgvJSHqH2fJFhrOK7LRLy6xXffARFCFWe8wGJaZGyec9CKNHfFkz6yaQA3c7zZaBpulXNLFrTmLXg0-V7sgq5vGE9hNlzu5MlycTtUWBPsJWqqitZ2Cc/s640/condicional-login-controlador-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhH_s8yj2MBILs1DpuxntLES4MIgvJSHqH2fJFhrOK7LRLy6xXffARFCFWe8wGJaZGyec9CKNHfFkz6yaQA3c7zZaBpulXNLFrTmLXg0-V7sgq5vGE9hNlzu5MlycTtUWBPsJWqqitZ2Cc/s1600/condicional-login-controlador-java.png) |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Condicional                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

\* En la sección del sino (else{}) iniciamos creando una variable tipo String, la cual le asignaremos la información contenida en el campo txt\_user haciendo uso del método getText(). Seguido a esto creamos un objeto tipo ArrayList y este sera de tipo Usuario (ArrayList\<Usuario> list), recordemos que la función que se encuentra en la clase metodosUsuario devuelve un valor de este tipo. Por ultimo llamamos la función login haciendo uso del objeto modelo el resultado que obtengamos lo asignaremos al ArrayList(list) llevara dos parámetros los cuales serán los valores ingresados en los campos de texto(user, pass).\
\
<br>

| [![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj4ZFuwp2u-8wjd4ZprVRGlWAEWlKX2iCUMQcNd5C_fQbU8GS5GHETW3giLFQs677W0MskMMucun8ezx7cCcWxr4h1CvSdXBYqvr6RBSp_e4HytzkwOIZczmhK-vNst3o_EFsK3lXN-PVk/s640/sino-controlador-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj4ZFuwp2u-8wjd4ZprVRGlWAEWlKX2iCUMQcNd5C_fQbU8GS5GHETW3giLFQs677W0MskMMucun8ezx7cCcWxr4h1CvSdXBYqvr6RBSp_e4HytzkwOIZczmhK-vNst3o_EFsK3lXN-PVk/s1600/sino-controlador-java.png) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| clase controlador.java                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

\
\* El siguiente paso es verificar si se obtuvo resultado de dicha consulta, verificamos si la longitud del ArrayList es mayor que cero, haciendo uso del método size ().\
\
Si es mayor que cero mostraremos un mensaje de bienvenida; cerraremos la ventana actual, haciendo uso del método dispose () y haremos visible la nueva ventana haciendo uso del método setVisible el cual le pasamos como parámetro true.\
\
Sino mostraremos un mensaje y denegamos el acceso a nuestro sistema.\
&#x20;       <br>

| [![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhavx9ha3Fm1d5oB_Z0_CzX1rrRlALQGIuqZSNImD6eGrZs_HDLVidpYpOit3k7dIigYZyCwDvcsIj4EPtDClwl62cfvkPG2d9MaaqAwMj07MfWudK_Uee3NVR7hQ_p18lg_BOZoPhg-Rg/s640/controlador2-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhavx9ha3Fm1d5oB_Z0_CzX1rrRlALQGIuqZSNImD6eGrZs_HDLVidpYpOit3k7dIigYZyCwDvcsIj4EPtDClwl62cfvkPG2d9MaaqAwMj07MfWudK_Uee3NVR7hQ_p18lg_BOZoPhg-Rg/s1600/controlador2-java.png) |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| clase controlador.java                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

\
\* Trabajaremos los eventos restantes los cuales se activaran cuando se presione el botón salir(btn\_exit) y cuando activemos el checkbox que nos permitirán desenmascara y enmascarar la contraseña\
\
<br>

| [![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhtPVSimRyAqEBc9girYQ_ts_UHiXyerYKiD7imHu5yG0314kNQL1mjFtRXZQt49lT_LRmo7tAxgNKOjOMeJy2-cQTr1raDkD4g8oCFZhorp4GhB5Zj6NszYP-xNYLLt9KTAjY1MMDmHHI/s640/eventos-controlado2-java.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhtPVSimRyAqEBc9girYQ_ts_UHiXyerYKiD7imHu5yG0314kNQL1mjFtRXZQt49lT_LRmo7tAxgNKOjOMeJy2-cQTr1raDkD4g8oCFZhorp4GhB5Zj6NszYP-xNYLLt9KTAjY1MMDmHHI/s1600/eventos-controlado2-java.png) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Eventos Controlador.java                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

\
Clase Controlador.java             <br>

```
```

\
package controlador;\
\
import iniciosesionmvc.Inicio;\
import iniciosesionmvc.login;\
import java.awt.event.ActionEvent;\
import java.awt.event.ActionListener;\
import java.util.ArrayList;\
import javax.swing.JOptionPane;\
import modelo.Usuario;\
import modelo.metodosUsuario;\
\
public class controlador implements ActionListener{\
&#x20;   \
&#x20;   private login view;\
&#x20;   private metodosUsuario modelo = new metodosUsuario();\
&#x20;   Inicio inicio = new Inicio();\
&#x20;   \
&#x20;   public void eventos(){\
&#x20;       view.btn\_enter.addActionListener(this);\
&#x20;       view.btn\_exit.addActionListener(this);\
&#x20;       view.checkviewpass.addActionListener(this);\
&#x20;   }\
&#x20;   \
&#x20;   public controlador(login vista){\
&#x20;       this.view=vista;\
&#x20;       eventos();\
&#x20;   }\
\
&#x20;   @Override\
&#x20;   public void actionPerformed(ActionEvent e) {\
\
&#x20;       Object evt = e.getSource();\
&#x20;       \
&#x20;       if(evt.equals(view.btn\_enter)){\
&#x20;           \
&#x20;           char p \[] =view.txt\_pass.getPassword();\
&#x20;           String pass = new String(p);\
&#x20;           \
&#x20;           if(view.txt\_user.getText().isEmpty() || pass.isEmpty()){\
&#x20;               \
&#x20;               JOptionPane.showMessageDialog(null, "Debe digitar un Usuario y una Contraseña", "Error en la Operación", JOptionPane.ERROR\_MESSAGE);                \
&#x20;               \
&#x20;           }else{\
&#x20;               \
&#x20;               String user=view.txt\_user.getText();\
&#x20;               ArrayList\<Usuario> list;\
&#x20;               list = modelo.login(user, pass);\
&#x20;               \
&#x20;               if(list.size()>0){\
&#x20;                   \
&#x20;                   JOptionPane.showMessageDialog(null, "Bienvenido al sistema");\
&#x20;                   view.dispose();\
&#x20;                   inicio.setVisible(true);\
&#x20;                   \
&#x20;               }else{\
&#x20;                   JOptionPane.showMessageDialog(null, "Acceso Denegado", "Error", JOptionPane.ERROR\_MESSAGE);\
&#x20;               }\
&#x20;               \
&#x20;               \
&#x20;               \
&#x20;           }\
&#x20;           \
&#x20;       }else if(evt.equals(view.btn\_exit)){\
&#x20;           \
&#x20;           int confirmar = JOptionPane.showConfirmDialog(null, "Esta seguro que desea salir del sistema?");\
&#x20;           \
&#x20;           if(confirmar==JOptionPane.YES\_OPTION){\
&#x20;               System.exit(0);\
&#x20;           }\
&#x20;           \
&#x20;       }else if(evt.equals(view.checkviewpass)){\
&#x20;           if(view.checkviewpass.isSelected()){\
&#x20;               view.txt\_pass.setEchoChar((char) 0);\
&#x20;           }else{\
&#x20;               view.txt\_pass.setEchoChar('\*'); \
&#x20;           }\
&#x20;       }\
&#x20;       \
&#x20;   }\
&#x20;   \
}\
<br>

```
```

\
7\.  Una vez terminada la creación de la clase controlador.java nos posicionaremos en el paquete de la  vista(loginmvc) y crearemos la clase login.java, debemos conectar la vista con el controlador para esto creamos un objeto de la clase controlador.java en el método constructor inicializamos el objeto creado al cual le pasaremos el parámetro de nuestra vista(controlador=new controlador(this)), una vez hecho esto tendremos nuestro proyecto debidamente conectado.\
\
\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg1hcBuztxZS3XQg7SyZ3sF-5xxXGgfjCt5H0SkeG7Vu6XflhCl-AsfH4fairaopYeLBuP1atqeEuRY5YAtYCztxqDOUpWx6RDe0inldJoBoy9EmeRqfYoIX_ewKozVwA03pvUIx4g4fjs/s640/clase-loginMVC.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg1hcBuztxZS3XQg7SyZ3sF-5xxXGgfjCt5H0SkeG7Vu6XflhCl-AsfH4fairaopYeLBuP1atqeEuRY5YAtYCztxqDOUpWx6RDe0inldJoBoy9EmeRqfYoIX_ewKozVwA03pvUIx4g4fjs/s1600/clase-loginMVC.png)\
8\.  Vista inicial interfaz gráfica login.\
\
<br>

| [![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEinzu5LVkRZng2RSqjkYeybJQ_1fui0lA_M4yZxY3QLkj77cojeYwcFW8mTTyjxw4Sl6435WDR-0Ko4mR8QPtocp2zBvd7F4DMcHqdot5cYRULthLaG63AJibW3jmRioPzbnvwSgV1sOiI/s640/interfaz-login.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEinzu5LVkRZng2RSqjkYeybJQ_1fui0lA_M4yZxY3QLkj77cojeYwcFW8mTTyjxw4Sl6435WDR-0Ko4mR8QPtocp2zBvd7F4DMcHqdot5cYRULthLaG63AJibW3jmRioPzbnvwSgV1sOiI/s1600/interfaz-login.png) |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Inicio de sesión login                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

| [![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEimSJtlCASuhnn7u3LzagM6eoebUaYOaiWnN9Rs5Lg5JvIzUwHU7HGQ6fpX9-EpIF51ZIgY6S73BcXCYnpa3XPbpPo-wvOf8wMCUdzhQepvaw_9Y1erg-POg5UBem_U0if64KoABhDPVt8/s640/interfaz-login1.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEimSJtlCASuhnn7u3LzagM6eoebUaYOaiWnN9Rs5Lg5JvIzUwHU7HGQ6fpX9-EpIF51ZIgY6S73BcXCYnpa3XPbpPo-wvOf8wMCUdzhQepvaw_9Y1erg-POg5UBem_U0if64KoABhDPVt8/s1600/interfaz-login1.png) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| datos de inicio sesión incorrectos                                                                                                                                                                                                                                                                                                                                                                                                                                           |

\
<br>

| [![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjRjFJIoaJWChIOBzj7soH4ygr2oR-erFfC64Qzpv0ToJ2zTej4_Jrm1Gyo5QOZGXOLTgd26Y5L6_J8If1_cgIDkQn41F_fv95q2OUILzWu3HR-Rm3vnK_1vJRdLRzHgFgNE0Fl5FqeqcA/s640/interfaz-login2.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjRjFJIoaJWChIOBzj7soH4ygr2oR-erFfC64Qzpv0ToJ2zTej4_Jrm1Gyo5QOZGXOLTgd26Y5L6_J8If1_cgIDkQn41F_fv95q2OUILzWu3HR-Rm3vnK_1vJRdLRzHgFgNE0Fl5FqeqcA/s1600/interfaz-login2.png) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Activar evento desenmascarar contraseña                                                                                                                                                                                                                                                                                                                                                                                                                                      |

| [![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgNYpWSa_wTUg5xAT-tvyPJpc6I1WqrJJeJk-WsYEPC1nnMxKqxOsGxJxgwiulFO9GAmZJxmGBWDJ-zhHTJDXkq9xOU4lZJ9BVRrB0S-Qbaw8EGiMhyphenhyphenIZ5pXh66zILMblTcYndqHahHxPs/s640/interfaz-login3.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgNYpWSa_wTUg5xAT-tvyPJpc6I1WqrJJeJk-WsYEPC1nnMxKqxOsGxJxgwiulFO9GAmZJxmGBWDJ-zhHTJDXkq9xOU4lZJ9BVRrB0S-Qbaw8EGiMhyphenhyphenIZ5pXh66zILMblTcYndqHahHxPs/s1600/interfaz-login3.png) |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Acceso concedido segunda vista                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

\
\
\
\
Con esto hemos concluido con el desarrollo de nuestro proyecto, es recomendable tener conocimientos previos relacionado a los temas de base de datos y programación orientada objetos.\
Espero este corto tutorial te haya sido de gran ayuda y pronto estaremos tratando otros temas interesantes relacionados
