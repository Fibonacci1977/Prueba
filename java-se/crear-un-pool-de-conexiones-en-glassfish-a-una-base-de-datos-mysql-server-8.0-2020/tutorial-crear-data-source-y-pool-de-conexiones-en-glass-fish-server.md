# Tutorial: Crear Data Source y Pool de conexiones en Glass Fish Server

\
Hola, para este tutorial configuraremos un datasource y un pool de conexiones en GlassFish.\
\
El tiempo estimado de este tutorial es 5 a 10 minutos.\
\
Lo único que usaremos para esto es NetBeans y un explorador.\
\
1\. Abrimos el netbeans y en el explorador de servicios, en la opción servers veremos el GlassFish Server. damos clic derecho y si no esta iniciado lo iniciamos con la opción Start\
\
[![GlassFish](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjSpFKxkYofX4sAiPiJVd0yV3AMIW0D4UKkbjilzBEe0mIirSUrFyAZjnglQWHlfzMJFQfR0FLOsYiNHsaAlqLKtXL7BQEx3deRhV9SM3Wc6SKOHRg4kdAGSZAVULS0d1BvCMBVbn7fA-Rl/s1600/glassfish.PNG)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjSpFKxkYofX4sAiPiJVd0yV3AMIW0D4UKkbjilzBEe0mIirSUrFyAZjnglQWHlfzMJFQfR0FLOsYiNHsaAlqLKtXL7BQEx3deRhV9SM3Wc6SKOHRg4kdAGSZAVULS0d1BvCMBVbn7fA-Rl/s1600/glassfish.PNG)\
2\. Luego una vez iniciado, damos clic derecho  y seleccionamos la opción View Admin Console, inmediatamente se nos abrirá una ventana en el explorador con algo como lo siguiente\
\
[![GalssFish Console](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEigLN5MW1nj7WNoLV3YX6XLtSX08lJ1rWLGBJCQQuTnXjhnBrQD_Sox9JOCU-LpuZ6kJmnAqWfFcuyd45funr4dflSYKlFKAQvX0MjlJGOIpf7cg_O1zdi3Byf96WI7-czdjaQBCsjYOO-o/s1600/glassfisnh+princ.PNG)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEigLN5MW1nj7WNoLV3YX6XLtSX08lJ1rWLGBJCQQuTnXjhnBrQD_Sox9JOCU-LpuZ6kJmnAqWfFcuyd45funr4dflSYKlFKAQvX0MjlJGOIpf7cg_O1zdi3Byf96WI7-czdjaQBCsjYOO-o/s1600/glassfisnh+princ.PNG)\
3\. Vamos a la parte de recursos y seleccionamos la opción Crear Nuevo Pool de conexiones JDBC. Saldrá un listado de los pools creados, damos clic en el botón Nuevo de la parte superior de la lista.\
4\. Para crearlo necesitaremos llenar los siguientes campos:

* &#x20;Nombre de Pool: Nombre referencial, en nuestro caso le hemos puesto PoolPrueba
* Tipo de Recurso: Tienes algunas opciones para escoger de acuerdo a tus necesidades, para este ejemplo escogeré java.sql. Driver
* Proveedor de Controladores de BD: En mi caso me conectare a una base Postgresql, así que lo seleccionare de la lista.

\
Luego damos clic en el botón Siguiente

.[![Pool de conexiones](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjxyu7jRvbcyImS2Sm2wDhrxrdv4ki9L_HZZUx0ohIcD5brpJewtjudgEdnYxwikZ7CUH8UC9krF_5W12yszfOwARHtmsnw2gbhDwYOVs-_UW0w_lYySzf-X45iJH1BltME1KTggFw_G8Ue/s1600/glassfish1.PNG)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjxyu7jRvbcyImS2Sm2wDhrxrdv4ki9L_HZZUx0ohIcD5brpJewtjudgEdnYxwikZ7CUH8UC9krF_5W12yszfOwARHtmsnw2gbhDwYOVs-_UW0w_lYySzf-X45iJH1BltME1KTggFw_G8Ue/s1600/glassfish1.PNG)\
5\. En el paso 2, tenemos la configuración del Pool, podemos dejarlo con sus propiedades por default, y actualizar solamente las opciones de conexiónURL: La url de conexión a la base de datos user y password de conexión a la base Damos clic en el botón Finalizar.\
[![Conexion](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEimgpF1hkX4pIyymmk3E-h3yEli8-jeVW5IL5gkiJYuI5He16YqLNWs0oEUwIu-AjVXBFW_5HSjeys_X5QFfsN9uV0RLNdaj4YADD2KH6JdDHwpM85dENVcqaFHLQRaiPhVFVc82jp6StHs/s1600/glassfisnh+2.PNG)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEimgpF1hkX4pIyymmk3E-h3yEli8-jeVW5IL5gkiJYuI5He16YqLNWs0oEUwIu-AjVXBFW_5HSjeys_X5QFfsN9uV0RLNdaj4YADD2KH6JdDHwpM85dENVcqaFHLQRaiPhVFVc82jp6StHs/s1600/glassfisnh+2.PNG)\
6\.  Luego de creado el pool puedes probarlo, haciendo clic en el pool y presionando el botón Ping\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgHmMOfrfUloYc8t3TIZjrCj6C4DEs0pWEaAvdxMQTOTJAHtPFwNjctL3Z_VVVT7CX1k7thyphenhyphen9k5bGimqiqBzcW_Dr-tZ0IBnYn2cEctDaQ_qDMDYqQgdLbPTjuFqGz166v05LIpUvQfZT1X/s1600/ping.PNG)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgHmMOfrfUloYc8t3TIZjrCj6C4DEs0pWEaAvdxMQTOTJAHtPFwNjctL3Z_VVVT7CX1k7thyphenhyphen9k5bGimqiqBzcW_Dr-tZ0IBnYn2cEctDaQ_qDMDYqQgdLbPTjuFqGz166v05LIpUvQfZT1X/s1600/ping.PNG)\
7\. Terminado el pool, vamos a la opción de Recurso de JDBC, nos aparecerá una lista de los JDBC creados, damos clic en el botón Nuevo\
8.- Llenamos los campos, solicitados. En JNDI, pondrás un nombre único y si estas trabajando con JPA, es el nombre que usaras para hacer la conexión en tu unidad de persistencia. Luego seleccionas el pool de conexiones que configuraste previamente y das clic en aceptar\
[![Propiedaes Pools](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEivGQfLJ2kqgwLmLFVEQk0wv1DFLiwEXb1SGLtgZZs4vpnSO7OEKuac9Me9aBZ1Wz3MvCkJDBjhOmTW7nYwco3QPvUlP49FLVbm_OdwUz0vN7HV05E6YXpdSvJfhICIQZCfUXMKCm2HLkYR/s1600/JDBC1.PNG)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEivGQfLJ2kqgwLmLFVEQk0wv1DFLiwEXb1SGLtgZZs4vpnSO7OEKuac9Me9aBZ1Wz3MvCkJDBjhOmTW7nYwco3QPvUlP49FLVbm_OdwUz0vN7HV05E6YXpdSvJfhICIQZCfUXMKCm2HLkYR/s1600/JDBC1.PNG)\
\
Y con eso esta listo!&#x20;
