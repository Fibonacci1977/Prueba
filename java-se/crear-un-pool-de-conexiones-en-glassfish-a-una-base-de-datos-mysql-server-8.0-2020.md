# Crear un Pool de conexiones en GlassFish a una base de datos MySQL Server 8.0 (2020)

Glassfish tiene una manera peculiar de tratar los recursos JDBC: Tiene un pool de conexiones, y después un JDBC Resources. Supongo que es porque un pool de conexiones puede tener varios JDBC Resource. Los demás Servidores de Aplicaciones que he visto usan unicamente un JDBC Resource, y en ese mismo se configura la configuración del pool.

En este post aprenderemos a crear un Pool de Conexion + JDBC Resource en GlassFish Server. Primero lo haremos directamente desde el mismo servidor GlassFish y después desde la misma IDE de  NetBeans.

Herramientas

* NetBeans IDE 8.0.2
* GlassFish Server 4.1
* MySQL Server 8.0.

Desde GlassFish

Pasos

0\. Antes que nada, debemos agregar el jar de conexión MySQL al domino de GlassFish, en mi caso debo copiar el jar en la siguiente ruta:&#x20;

_C:\Users\XxkokoxXT\AppData\Roaming\NetBeans\8.0.2\config\GF\_4.1\domain1\lib_

Si no saben como encontrar la ruta en su máquina, deben ir a la pestaña Tools / Server de su NetBeans.&#x20;

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjrwQG1REx34lwUKlCpJzyyVIepfmZORmGdy3z7aouUL09w_Ns2fMe07zWqowX55erq9apG0CorXaajuzjaWRuPFBFI5LB0mvKuHZSCvj1NvSSAoG_TuGxGD6teXbfNKndr-nE9lDIhZZs/w625-h416/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjrwQG1REx34lwUKlCpJzyyVIepfmZORmGdy3z7aouUL09w_Ns2fMe07zWqowX55erq9apG0CorXaajuzjaWRuPFBFI5LB0mvKuHZSCvj1NvSSAoG_TuGxGD6teXbfNKndr-nE9lDIhZZs/s768/image.png)

<br>

1\. El servidor GlassFish debe estar levantado

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi4lcJQ7PiT94YBSErjQwMqD5P_cvtWOU8YlO8YZvseyczAAFWBZd_qDzYPNpqW7OtahWMZgQXH_po1SutwalEEItbYpvD5VW0UWa34YZ8k4OFjfGghSnN2LE_45naRWbEAnbUnDYdbftU/w371-h313/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi4lcJQ7PiT94YBSErjQwMqD5P_cvtWOU8YlO8YZvseyczAAFWBZd_qDzYPNpqW7OtahWMZgQXH_po1SutwalEEItbYpvD5VW0UWa34YZ8k4OFjfGghSnN2LE_45naRWbEAnbUnDYdbftU/s371/image.png)\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgdxCjB89-wmzP_Ffa6UwPKMPMPR3BcR7ebWz8VKSn93QNVU4uiDl-ki7cQuxEx56JiLVvIidW8tNulbTE5YSTpSg-fUf2D7IbMrYUlN7MBErUaNTJisl0MmOqQZxAE960QnZqsp-fyBbY/w319-h269/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgdxCjB89-wmzP_Ffa6UwPKMPMPR3BcR7ebWz8VKSn93QNVU4uiDl-ki7cQuxEx56JiLVvIidW8tNulbTE5YSTpSg-fUf2D7IbMrYUlN7MBErUaNTJisl0MmOqQZxAE960QnZqsp-fyBbY/s255/image.png)<br>

2\. Accedemos al administrador de consola

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhRL_MxFDtrLEYH3Bmzg4E2qTpH9ektsF9skOANK9Ils-zCLRpnBKBF5CzttPRQave_2G1YQ7BypmDOfAdoH8kxSvKhADYiNQ-1JoMs4eC9fPp7ORr79h4ICX3T4ReS4f1UC_RUWjXmyhM/s0/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhRL_MxFDtrLEYH3Bmzg4E2qTpH9ektsF9skOANK9Ils-zCLRpnBKBF5CzttPRQave_2G1YQ7BypmDOfAdoH8kxSvKhADYiNQ-1JoMs4eC9fPp7ORr79h4ICX3T4ReS4f1UC_RUWjXmyhM/s442/image.png)

<br>

3\. En la interfaz que se abre en el navegador seleccionamos la opción JDBC / JDBC Connection Pools

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjAcOeY0-fUvf6nb6Oq3vazMfpoeO9DMryBMxYyMDV_0c1zpMHklZRerM3Piy24AshwOrgHz-giRSvLqMfVbV2NjkBIZaLrkZQQBkwvjf-hbIDQ1lG2iTvteeGYiPYiMyY_gV33DW2U7YY/s640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjAcOeY0-fUvf6nb6Oq3vazMfpoeO9DMryBMxYyMDV_0c1zpMHklZRerM3Piy24AshwOrgHz-giRSvLqMfVbV2NjkBIZaLrkZQQBkwvjf-hbIDQ1lG2iTvteeGYiPYiMyY_gV33DW2U7YY/s856/image.png)<br>

4\. Clic en el botón New y completamos los siguientes campos.

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiHMdSlnZl2l3k4jFg2Aii3a3Mhrw3NVf9GAL-VK4KhoWBI4dXXX1uQzJCB2I2OTrwPJQhO8V5liE5i3R5VErm5rSBKTuANyK6uAzgTPsKGlaq6JVKchQD4AlvjENiH1iXQHc2Pl2Z-lQM/s640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiHMdSlnZl2l3k4jFg2Aii3a3Mhrw3NVf9GAL-VK4KhoWBI4dXXX1uQzJCB2I2OTrwPJQhO8V5liE5i3R5VErm5rSBKTuANyK6uAzgTPsKGlaq6JVKchQD4AlvjENiH1iXQHc2Pl2Z-lQM/s726/image.png)

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgUx7mzouQB4ky4-4D_Z3II7Nn9VD2x2tBPgNFKnV68vrfMCsZCYwWhwWVAFe4eCE1iDcsmKCv1aHh08E8n9Z_SJq-g09hPVc8g9p9jeXSbUpgO1iUxmAAGMGKrtTXucaeuey6QIIHEN7g/s640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgUx7mzouQB4ky4-4D_Z3II7Nn9VD2x2tBPgNFKnV68vrfMCsZCYwWhwWVAFe4eCE1iDcsmKCv1aHh08E8n9Z_SJq-g09hPVc8g9p9jeXSbUpgO1iUxmAAGMGKrtTXucaeuey6QIIHEN7g/s703/image.png)

<br>

5\. Clic en _Next_ y en la siguiente ventana debemos agregar las siguientes propiedades. Para no confundirnos con la lista de propiedades que aparece por defecto, eliminamos todas las propiedades y volvemos a agregar las propiedades que vamos a necesitar,&#x20;

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgqv7oYAL2Qc65aCCY_UBYg5_ms_wBu9kXbDU6RBOwDrvPKaCPsYVe1dQWsG_Ysfz9mtWCsJPs9Yz7XCC7LZUQIj-cYBjCO39EyXcaFBU47KS7TQSBLAJJ_qxqax691i6oedeUZxkyD7OY/s640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgqv7oYAL2Qc65aCCY_UBYg5_ms_wBu9kXbDU6RBOwDrvPKaCPsYVe1dQWsG_Ysfz9mtWCsJPs9Yz7XCC7LZUQIj-cYBjCO39EyXcaFBU47KS7TQSBLAJJ_qxqax691i6oedeUZxkyD7OY/s1065/image.png)<br>

Propiedades básicas

\<property name="serverName" value="localhost"/>

\<property name="portNumber" value="3306"/>

\<property name="Port" value="3306"/>

\<property name="databaseName" value="java19materias"/>

\<property name="User" value="root"/>

\<property name="Password" value="root"/>

\<property name="URL" value="jdbc:mysql://localhost:3306/java19materias"/>

\<property name="driverClass" value="com.mysql.jdbc.Driver"/>

\-----------------------

Para los que tienen problemas de zona horaria deben agregar las siguientes propiedades a la URL, de lo contrario obtendrán el siguiente error: _Cannot establish a connection to jdbc:mysql://localhost:3306/java19materias using com.mysql.jdbc.Driver (The server time zone value 'Hora est. Pacífico, Sudaméric' is unrecognized or represents more than one time zone. You must configure either the server or JDBC driver (via the serverTimezone configuration property) to use a more specifc time zone value if you want to utilize time zone support.)_

\<property name="URL" value="jdbc:mysql://localhost:3306/java19materias?useTimezone=true\&serverTimezone=UTC"/>

<br>

Para conectarnos a MySQL 8.0 debemos agregar la conexión de la siguiente manera, de lo contrario nos saldrá el siguiente error: _Loading class \`com.mysql.jdbc.Driver'. This is deprecated. The new driver class is \`com.mysql.cj.jdbc.Driver'._

\<property name="driverClass" value="com.mysql.cj.jdbc.Driver"/>

Si al hacer ping para testear el pool de conexiones  nos sale el siguiente el error:  _Unable to load authentication plugin 'caching\_sha2\_password_'. Debemos agregar la siguiente propiedad.

\<property name="UseSSL" value="true"/>

Si al hacer ping para testear el pool de conexiones no sale el siguiente error: _Ping Connection Pool failed for connectionPool2020. Connection could not be allocated because: Cannot open file:C:\Users\XxkokoxXT\AppData\Roaming\NetBeans\8.0.2\config\GF\_4.1\domain1/config/keystore.jks \[Keystore was tampered with, or password was incorrect] Please check the server.log for more details._ Debemos agregarle la siguiente propiedad.

\<property name="UseSSL" value="false"/>

<br>

En mi caso solo necesito definir las siguientes propiedades:

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgG9Jm40D6S5JhzakXeq4aoQbZOmdxCSkcIFSqs88LHtAflwb8RWQj1Ilzd4W7RcCJUqmnQ003tUclbYw_W9HlFQ0wKcCDmeXuN9tNLZ5TSRezUoeBWH9Ooe0RwDQjsWIVk3jFstrdfUfE/w625-h295/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgG9Jm40D6S5JhzakXeq4aoQbZOmdxCSkcIFSqs88LHtAflwb8RWQj1Ilzd4W7RcCJUqmnQ003tUclbYw_W9HlFQ0wKcCDmeXuN9tNLZ5TSRezUoeBWH9Ooe0RwDQjsWIVk3jFstrdfUfE/s876/image.png)\
En la pentaña _General_ debemos actualizar el campo DataSource Classname de com.mysql.jdbc.jdbc2.optional.MysqlDataSource  acom.mysql.cj.jdbc.MysqlDataSource\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgEh5p-Dn9UrJcTNvOa864pyZ5o5qDgytyJl1LKD3KUhF2iWJanX7I4YRTdClUqsnM_uauAdgDfoHpgnCs7kh7Ihqa0Zi3Eu-PWkq2Ub2i3CKOTUwa5QgznGFRx9j3-RqsY_T3-D4Ytj_M/w625-h356/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgEh5p-Dn9UrJcTNvOa864pyZ5o5qDgytyJl1LKD3KUhF2iWJanX7I4YRTdClUqsnM_uauAdgDfoHpgnCs7kh7Ihqa0Zi3Eu-PWkq2Ub2i3CKOTUwa5QgznGFRx9j3-RqsY_T3-D4Ytj_M/s791/image.png)\
\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgL8lGM33Idx79aLiom7q34mj5Ge2BeVhvxBq9oxChG5WTDylF59NUu1WADcqp-Sfe9gfDgSqpyTmFOACcqAOcX62c9VnLj-HQMrV0FFi8NJxJaMQ-YEBrxMTPvkJ6mpZrYaiYfqrcQuI4/w625-h338/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgL8lGM33Idx79aLiom7q34mj5Ge2BeVhvxBq9oxChG5WTDylF59NUu1WADcqp-Sfe9gfDgSqpyTmFOACcqAOcX62c9VnLj-HQMrV0FFi8NJxJaMQ-YEBrxMTPvkJ6mpZrYaiYfqrcQuI4/s766/image.png)\
[Ver otros cambios en el _Connector/J API_](https://dev.mysql.com/doc/connector-j/8.0/en/connector-j-api-changes.html)<br>

Si queremos probar el pool que creamos debemos ir a la pestaña _General_ y hacer clic en el botón _Ping_.

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhluID-v9dXOO_SIO0zQN_3VWgmBuEA1uBR6OnEYWm-l3XsW2zq8FKtHQmtutIh1_fboh-0amRtFLNp4m9pmqy_BuEqHRMcrafuc5ynEWmXSlSTuIgwgCVcvzLgCDReCXpSSYEetXwJ6Pk/w625-h301/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhluID-v9dXOO_SIO0zQN_3VWgmBuEA1uBR6OnEYWm-l3XsW2zq8FKtHQmtutIh1_fboh-0amRtFLNp4m9pmqy_BuEqHRMcrafuc5ynEWmXSlSTuIgwgCVcvzLgCDReCXpSSYEetXwJ6Pk/s986/image.png)<br>

6\. Clic en _Finish_

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh_jsFWcj4751DrhJIXhDn14LtxXu4-PfuFEq_Jb6zJOp6aPYhjPDVmot9YMGL1TiWamiSXj7GWI97MCwFzBSwwPdQxNQ776rOlf_FTZbn5AEkLZ7vp67ExWGEwiEoHXx9Y8CKkpOERXPM/w640-h228/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh_jsFWcj4751DrhJIXhDn14LtxXu4-PfuFEq_Jb6zJOp6aPYhjPDVmot9YMGL1TiWamiSXj7GWI97MCwFzBSwwPdQxNQ776rOlf_FTZbn5AEkLZ7vp67ExWGEwiEoHXx9Y8CKkpOERXPM/s908/image.png)<br>

7\. Ahora debemos crear un Data Source, para ello, nos vamos a la opción JDBC / Data Resources y seleccionamos la opción New.

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi8wPu39fNYXOXigx07JeR8CuJ0z0NFmtSspG-R9Xiy_jrt96-JxTMhXBb0StIBNMJpkcLYqRqFh4nv_hrs4-rcQZeXM9m1ltMUKZI8hv0W9n-LYYcBCdxM62qMw-Wk7khLpBoP90z8tP8/s0/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi8wPu39fNYXOXigx07JeR8CuJ0z0NFmtSspG-R9Xiy_jrt96-JxTMhXBb0StIBNMJpkcLYqRqFh4nv_hrs4-rcQZeXM9m1ltMUKZI8hv0W9n-LYYcBCdxM62qMw-Wk7khLpBoP90z8tP8/s583/image.png)\
En Pool Name seleccionamos el pool de conexión que creamos\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjJ8GXLJSBQYI9JUdllOxLJrYfPH3H45E6pI2xnyrsBQpAeTtRthy7GVf1EY6svvdwxgnvJndZbIw33Tpg67qCbv9_tPMc9KzjRJKrKx9QRtA3d3MfzgkP0kFsFW8gdqQLrlGfZQSO8bfU/s0/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjJ8GXLJSBQYI9JUdllOxLJrYfPH3H45E6pI2xnyrsBQpAeTtRthy7GVf1EY6svvdwxgnvJndZbIw33Tpg67qCbv9_tPMc9KzjRJKrKx9QRtA3d3MfzgkP0kFsFW8gdqQLrlGfZQSO8bfU/s542/image.png)

<br>

8\. Clic en el botón _OK_ y ya tenemos listo nuestro pool de conexión + jdbc resources en GlassFish. Para probarla, solo debemos crear un proyecto y llamar al DataSource.&#x20;

<br>

Crear un Proyecto Java

Creamos un proyecto web, para ello vamos a la opción File / New / Java Web / Web Application.

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgutprqp7INmbLa6Yx5oguT_QDC5dUUEcy3-tnDO-9HXcFEyhRtB8b57_p0-S6Jt3Aeb2ZCCK7K8Z5xno2isSaJAWHbZiIfXequO5Cl7tcLT-z4ICJ62WtaQu_DpDBSoNFlhdoqesX147s/s640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgutprqp7INmbLa6Yx5oguT_QDC5dUUEcy3-tnDO-9HXcFEyhRtB8b57_p0-S6Jt3Aeb2ZCCK7K8Z5xno2isSaJAWHbZiIfXequO5Cl7tcLT-z4ICJ62WtaQu_DpDBSoNFlhdoqesX147s/s735/image.png)\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiq0hPY6AanzxTL40U_SVLmDzl6w-lGKLbe1B01m5JUqo0Nb9SWMchKqrgKt1nUTPoSLB4PVJ_uuY39h5wZGh8mJLgQHyj_njQpWP37Pij0EgL3ndlqAQPt_qzU3l0UM4eiOXKBmGnFpsY/s640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiq0hPY6AanzxTL40U_SVLmDzl6w-lGKLbe1B01m5JUqo0Nb9SWMchKqrgKt1nUTPoSLB4PVJ_uuY39h5wZGh8mJLgQHyj_njQpWP37Pij0EgL3ndlqAQPt_qzU3l0UM4eiOXKBmGnFpsY/s737/image.png)\
Seleccionamos el servidor GlassFish que es en donde tenemos creado el pool de conexión\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjQnY6wH0vyM6WEgRgxyzOl-t87ndp1nKi9fgggW6bnXRsviTPA2loQE7z-hNR1VzmcyEBcWgcr_SfbNIIIiWpeg94R4JwJsTOqGhroWRoHp0qly2JOAZuD5Vo-L7P1pJHU9Xl3IVb6i_g/s640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjQnY6wH0vyM6WEgRgxyzOl-t87ndp1nKi9fgggW6bnXRsviTPA2loQE7z-hNR1VzmcyEBcWgcr_SfbNIIIiWpeg94R4JwJsTOqGhroWRoHp0qly2JOAZuD5Vo-L7P1pJHU9Xl3IVb6i_g/s743/image.png)\
Agregamos algunos framaeworks ya que en un siguiente post crearemos un CRUD usando JPA, EJB,  JSF y Primefaces.\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjUFwAWVkv0VE3hDD2XOJkGKrbgGeGoobAHKrSiCePFVUdqp4_cQVMmswrxW1bxsEn7M9LiqoB7lkNfEYSOEmngdL3x3PfS4T1s-04yydtehmG0_tIcJg0ruWARSsQb5Ra6n4VrgfNKEPk/s640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjUFwAWVkv0VE3hDD2XOJkGKrbgGeGoobAHKrSiCePFVUdqp4_cQVMmswrxW1bxsEn7M9LiqoB7lkNfEYSOEmngdL3x3PfS4T1s-04yydtehmG0_tIcJg0ruWARSsQb5Ra6n4VrgfNKEPk/s737/image.png)\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhXDPOZFa5yAfS-wSv_OacEKQw1sZ1nf8clpgoJom0BzkYgQye9YyIsbSJqbQvt34MQ54y6eKf3x7eAEAabAUb8UizX3XJHqfcMaXnA6yCEttKQsDa48p62_rGPiZyto1blP2EwFg7fGSE/s640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhXDPOZFa5yAfS-wSv_OacEKQw1sZ1nf8clpgoJom0BzkYgQye9YyIsbSJqbQvt34MQ54y6eKf3x7eAEAabAUb8UizX3XJHqfcMaXnA6yCEttKQsDa48p62_rGPiZyto1blP2EwFg7fGSE/s743/image.png)<br>

Luego vamos a Source Package clic derecho / New / Other y creamos una clase Entidad a partir de una base de datos. De esa manera nos conectaremos al Data Source que creamos en el servidor GlassFish.

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhpKViNRYCl7bkgUiwWXXsh8WdTt7PJkNt-KlyvNtDi6c6ECuKv3_MNEeApiTSPLWSilYpXtbD2umykFND3Vbre_nK1q3ISaFLnaYO0cxRt9ttNxpeFts4bopmKQrTXe4BkwfUxREUxgEo/s0/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhpKViNRYCl7bkgUiwWXXsh8WdTt7PJkNt-KlyvNtDi6c6ECuKv3_MNEeApiTSPLWSilYpXtbD2umykFND3Vbre_nK1q3ISaFLnaYO0cxRt9ttNxpeFts4bopmKQrTXe4BkwfUxREUxgEo/s588/image.png)\
\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhAeaGV_4A0ATbIQ4wodzeUqlOtiXZ82VprwQqj6Mvs5uj6jIHv-mdp3HFcVDuG3TLegpyX2GBoh2zPfusrXV31wj97MWIrfso2uPoJGCOh-2Y2-GF3NUnMX2mDCxqyiAUooBaUJvSZpQk/s640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhAeaGV_4A0ATbIQ4wodzeUqlOtiXZ82VprwQqj6Mvs5uj6jIHv-mdp3HFcVDuG3TLegpyX2GBoh2zPfusrXV31wj97MWIrfso2uPoJGCOh-2Y2-GF3NUnMX2mDCxqyiAUooBaUJvSZpQk/s740/image.png)<br>

En el Data Source buscamos el Data Source que creamos en el administrador de consola de Glasfish. Al seleccionar nos mostrará las tabla de la base de datos.

<br>

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgJCIwkk1TqZuy380wx4xasyfctmvP_61_0nH9FvmjOO1zUG2OjEmkVvSZuTnhpL2fhd4lEgDjOisrGgF7A2NODU38B1Pij3FYeZ88_fxlUdNie78DEMBZw1A2rUah3f6676g87tS5ZJSU/s640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgJCIwkk1TqZuy380wx4xasyfctmvP_61_0nH9FvmjOO1zUG2OjEmkVvSZuTnhpL2fhd4lEgDjOisrGgF7A2NODU38B1Pij3FYeZ88_fxlUdNie78DEMBZw1A2rUah3f6676g87tS5ZJSU/s734/image.png)\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh4Fins-ujRSRKrvkPjiq8gH8GiY3c3k65yubi8V7tvk6ApfbkJNK4n0baDUL4uXwSWHS1ac7vlb0_SBpdoCba6gGd4ats8BuNKUZyLYmDbzqWYMi29qPDOd7B_OqibH5KYTfyIxfrYctE/s640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh4Fins-ujRSRKrvkPjiq8gH8GiY3c3k65yubi8V7tvk6ApfbkJNK4n0baDUL4uXwSWHS1ac7vlb0_SBpdoCba6gGd4ats8BuNKUZyLYmDbzqWYMi29qPDOd7B_OqibH5KYTfyIxfrYctE/s737/image.png)<br>

Listo, si deseas puedes continuar está guía viendo el post para crear un CRUD Java Web usando los frameworks de JPA, EJB, JSF y Primefaces

[Ver post](https://joseltoro.blogspot.com/2020/09/crear-un-proyecto-java-web-con-jpa-ejb.html)

<br>

Desde NetBeans

Pasos

1\. Para realizarlo desde NetBeans, necesitamos tener el proyecto que usará la base de datos abierto. Luego, presionamos _Ctrl+N_ o hacemos clic derecho al proyecto _File / New File / Other_

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjQhrEEjsEz3Nm4HcRl7n4aL2R2vNSSGC3qjoYvtE34JHuhxRJryZLOih_7-OEAPUlniWRZsStrkj_vu1yyPCwYtRke7OWbYLH6n5X-lJ0XQXXij3inw5t8OHQXYAtuD5aHaVrGbyFba_o/w640-h426/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjQhrEEjsEz3Nm4HcRl7n4aL2R2vNSSGC3qjoYvtE34JHuhxRJryZLOih_7-OEAPUlniWRZsStrkj_vu1yyPCwYtRke7OWbYLH6n5X-lJ0XQXXij3inw5t8OHQXYAtuD5aHaVrGbyFba_o/s648/image.png)

<br>

2\. Seleccionamos la categoría _GlassFish_ y el tipo de archivo _JDBC Connection Pool_

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiAGryfKXFJoAjYO3IwzBeECdhCs4FAOpw0k6bNsGUbCcEwhVXgw5vmDm1M0eo2FEA7Lk1crlXJKaTyagYVGhbD4YZJhwUl90QcR2PUB7Z7TJD4NmENf67bBCo1r_W_0eBvkiZULd7pfMo/w640-h442/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiAGryfKXFJoAjYO3IwzBeECdhCs4FAOpw0k6bNsGUbCcEwhVXgw5vmDm1M0eo2FEA7Lk1crlXJKaTyagYVGhbD4YZJhwUl90QcR2PUB7Z7TJD4NmENf67bBCo1r_W_0eBvkiZULd7pfMo/s739/image.png)

<br>

3\. Escribimos el nombre de nuestro pool de conexiones. Además, seleccionamos cual es la base de datos que usaremos. Como es una conexión nueva, seleccionamos New configuration using database, y en mi caso selecciono MySQL.

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh0-GUtoF3G4KOqfds7iz5W9PlaCjmmMZAED7rA4VMen7ZCp_YeqlNDSaK5ng9tqMQrdXaTmru12RNZAGUVh1O_ozrPa-5mAziK0fLpkHxi02Fw_b-jnWsdXw5bMyaAWkT447HBi1nkBXo/w640-h394/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh0-GUtoF3G4KOqfds7iz5W9PlaCjmmMZAED7rA4VMen7ZCp_YeqlNDSaK5ng9tqMQrdXaTmru12RNZAGUVh1O_ozrPa-5mAziK0fLpkHxi02Fw_b-jnWsdXw5bMyaAWkT447HBi1nkBXo/s836/image.png)

4\. Clic en _Next_ y en la ventana que aparece seleccionamos el tipo de recurso (por omisión es java.sql.DataSource, escribimos el URL de nuestra conexión JDBC, el usuario y la contraseña.

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEisT0lmD-WeSqAGuMhy0nDF_GbfTGpi_tJ4YQF_gSxu3FuZgOERO9msbGCzSS9YLb5bT495Kf5Vd8Z9dM_wzpPPtwy5XoXJer6OD46JVnIrqCcX6Bz2Oc7S7AyFZOFQAruFLvIyPNCH4Ew/w640-h394/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEisT0lmD-WeSqAGuMhy0nDF_GbfTGpi_tJ4YQF_gSxu3FuZgOERO9msbGCzSS9YLb5bT495Kf5Vd8Z9dM_wzpPPtwy5XoXJer6OD46JVnIrqCcX6Bz2Oc7S7AyFZOFQAruFLvIyPNCH4Ew/s839/image.png)

Clic en Finish y ya tenemos nuestro pool de conexiones creado para nuestro proyecto desde NetBeans

<br>

5\. Ahora debemos crear un Data Source, para ello, presionamos _Ctrl+N_ o hacemos clic derecho al proyecto _File / New File / Other._ Seleccionamos la categoría _GlassFish_ y el tipo de archivo _JDBC Connection Pool_

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjxrYJBBoToDGkzxprSn31OKj1zDsgWLhq-Ab1EswdcrKjZ2QjEwxrrGbWUm7sBw3jUIB8u-BMZ5sHoBv0UKEvbMm0M5eizRSgHPjd_LbZW5Sgv30ic_C2Ae5WdNDnExLvwj0rHMkJbw2o/w640-h442/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjxrYJBBoToDGkzxprSn31OKj1zDsgWLhq-Ab1EswdcrKjZ2QjEwxrrGbWUm7sBw3jUIB8u-BMZ5sHoBv0UKEvbMm0M5eizRSgHPjd_LbZW5Sgv30ic_C2Ae5WdNDnExLvwj0rHMkJbw2o/s736/image.png)

6\. Clic en _Next_ y en la ventana que sigue seleccionamos el pool de conexiones que estará asociado a nuestro recurso JDBC. En mi caso es ConnectionPool, y escribo el nombre en formato JNDI

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhE6AXXkFoU7X7Oisg6hw-G9ujfveFuOyccnti5iDPEf4O0oHhL7FhnaMjmL36bGcNcOo9q4RKhYxPS7OuUC57HG6Q0M3TtkSP3vcaaFfldvJ4XJrsUKfIBLmh_MwuKmmpgCOO6n8pUXG0/w640-h538/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhE6AXXkFoU7X7Oisg6hw-G9ujfveFuOyccnti5iDPEf4O0oHhL7FhnaMjmL36bGcNcOo9q4RKhYxPS7OuUC57HG6Q0M3TtkSP3vcaaFfldvJ4XJrsUKfIBLmh_MwuKmmpgCOO6n8pUXG0/s735/image.png)

Clic en Finish y ya tenemos nuestro recurso JDBC.

<br>

El recurso JDBC y el pool de conexiones creados desde NetBeans se crearán en el glassfish unicamente cuando se despliegue el proyecto.

<br>

<br>

¿Cuál es la diferencia en hacer desde Glassfish o desde NetBeans?

Cuando se hace desde NetBeans, es solo para fines de desarrollo. Notemos que se ha creado el archivo _sun-resources.xml_ en nuestro proyecto.

Dentro tiene toda la configuración que NetBeans usará para crear los recursos JDBC para que nuestra aplicación funcione en nuestro GlassFish de desarrollo. Para nada más.

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiW9cbCfILaF81Wav6OQyMlQMsa6YrduD4LY3eLEHP6_smBvwcgNbFvZNVrq2UhADkS8zxT9GgrMyzoSvO1NRzPO1dd-Tooxp51gweRoKC53YmKE6bU7dJp2cxbO6YnH1_IuVA7sxtT03Q/w640-h204/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiW9cbCfILaF81Wav6OQyMlQMsa6YrduD4LY3eLEHP6_smBvwcgNbFvZNVrq2UhADkS8zxT9GgrMyzoSvO1NRzPO1dd-Tooxp51gweRoKC53YmKE6bU7dJp2cxbO6YnH1_IuVA7sxtT03Q/s1432/image.png)

<br>

Cuando se crea el archivo _.war_ para desplegar nuestra aplicación en un GlassFish de producción, el archivo _sun-resources.xml_ no existe dentro del paquete de instalación. Simplemente no hay.&#x20;

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi7FVjb26tUhL95tbQvejH1PR0Czu9Ve_jC0GcwF2c7pHFA_jBpP0rkXUdQycX0I3CgApi9r-g474KtRJ8NQQ7o74kbQTmnWgYg8av8q4hZaecRvPbf1X_iqCKZwd9RP-Mm-UEB5wz3qoI/w262-h640/image.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi7FVjb26tUhL95tbQvejH1PR0Czu9Ve_jC0GcwF2c7pHFA_jBpP0rkXUdQycX0I3CgApi9r-g474KtRJ8NQQ7o74kbQTmnWgYg8av8q4hZaecRvPbf1X_iqCKZwd9RP-Mm-UEB5wz3qoI/s603/image.png)<br>

Entonces ¿cómo nuestra aplicación puede conectarse a la base de datos estando en el GlassFish de producción? Pues bien, en este GlassFish de producción, creamos el JDBC resource directamente en el mismo GlassFish.

Esto es bueno, porque cuando desarrollamos usamos una base de datos que es solo para desarrollo. Mientras que para poner en producción, usaremos otra conexión, otra base de datos que será para producción.
