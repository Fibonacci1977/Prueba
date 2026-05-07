# Conectar JAVA con base de datos ACCESS

[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhA1a0svKK2OLbLnnH2yVB5EsXr06-bFAq_A6ecPIFXpoWCAMl9DDAsCs6fAHIT5PGHUvZK73_f8KZJgum-48Ryn1W0vl0yiXnpbm7S-6MkT-VHaz4rjh1Y8brJ5rsjTSWnqqNKS3leHKU/s320/java-oracle-juuchini.jpg)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhA1a0svKK2OLbLnnH2yVB5EsXr06-bFAq_A6ecPIFXpoWCAMl9DDAsCs6fAHIT5PGHUvZK73_f8KZJgum-48Ryn1W0vl0yiXnpbm7S-6MkT-VHaz4rjh1Y8brJ5rsjTSWnqqNKS3leHKU/s1600/java-oracle-juuchini.jpg)\
\
\
Lo primero que necesitamos es descargar el driver llamado ucanaccess-3.0.2. Usaremos la versión (3.0.2) esta la pueden descargar desde el siguiente enlace:\
&#x20;[https://mega.nz/#F!So8GGTpT!u2jgrB0YKiG6rIxgRNX0Hg](https://mega.nz/#F!So8GGTpT!u2jgrB0YKiG6rIxgRNX0Hg)\
\
Después de la descarga nos quedaran los siguientes archivos:\
\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEikksJR9IaWf5yl4rEYrZqs96COfsILhTk0-5Tx7yKY9_US36QrXm_Ljuyw48UHWIshJDVeU6ZLJ98PJDeyF2wgQwVxREJmqkEsnVoKbAEaIwVAC83OS_VOARiMe5zCm6chkNSCP_EduK0/s1600/BaseAccess.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEikksJR9IaWf5yl4rEYrZqs96COfsILhTk0-5Tx7yKY9_US36QrXm_Ljuyw48UHWIshJDVeU6ZLJ98PJDeyF2wgQwVxREJmqkEsnVoKbAEaIwVAC83OS_VOARiMe5zCm6chkNSCP_EduK0/s1600/BaseAccess.png)\
Bien ahora nos vamos a NetBeans para importar las librerías en el proyecto que deseen.\
Damos clic izquierdo en la carpeta de librerías y damos clic en Add JAR/FOLDER: \
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjRMS6X8UIGQKB3ELsuAAGSs_riYlS8Cj5qLJ0v4rke63lT2TSht6txo1-Uu9ixFNaVdXtm4uIk3srt8rf1hffPdzxyVMAcDFYcd2y6J7C7YT1ZFP13iOyXnyucQleoNC88reyirMxEdYc/s1600/BaseAccess.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjRMS6X8UIGQKB3ELsuAAGSs_riYlS8Cj5qLJ0v4rke63lT2TSht6txo1-Uu9ixFNaVdXtm4uIk3srt8rf1hffPdzxyVMAcDFYcd2y6J7C7YT1ZFP13iOyXnyucQleoNC88reyirMxEdYc/s1600/BaseAccess.png)\
Ahora seleccionaremos todas las librerías manteniendo presionada la tecla de control y damos clic en abrir.[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh8td64_BTwVmR1afqu2d7tYQRhxoAQ3nrtbT10Zofo2uq3ltQ8wgrkWmWRCyZgY277LcL0H5YILg2Wy-RaQa4EcaSfZQ5JC7XgCnKz3pExLWoOAvHJ5sUDtNfWsXWINx8AC_pgnqMDVYA/s400/BaseAccess.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh8td64_BTwVmR1afqu2d7tYQRhxoAQ3nrtbT10Zofo2uq3ltQ8wgrkWmWRCyZgY277LcL0H5YILg2Wy-RaQa4EcaSfZQ5JC7XgCnKz3pExLWoOAvHJ5sUDtNfWsXWINx8AC_pgnqMDVYA/s1600/BaseAccess.png)\
\
\
Nos quedara de la siguiente forma:\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgpgo2w_LmLtuFtXRZWXL4kyN8QT042OaCFm39Ix9LaVF2WvUbcIiEIlxH025lR-NdN2LuTJpLAdiXmxbxUQc4Lhd1c_4mb0kEKrfHSnsq3xBgqZMz9zZpIssr8OeXJz-APepqQBxTjc9U/s320/BaseAccess.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgpgo2w_LmLtuFtXRZWXL4kyN8QT042OaCFm39Ix9LaVF2WvUbcIiEIlxH025lR-NdN2LuTJpLAdiXmxbxUQc4Lhd1c_4mb0kEKrfHSnsq3xBgqZMz9zZpIssr8OeXJz-APepqQBxTjc9U/s1600/BaseAccess.png)\
Ahora importamos las siguientes librerías:\
import java.sql.Connection;import java.sql.DriverManager;import java.sql.SQLException;import java.sql.Statement;\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhrs8g94dk7m0yY9a27iYK-BuQHjCyGXLt9bsJP_LNFe6X_63S1mAmzwIRUkpfWN2cKbMwP2L3QUd6J4uZkiArYVaEQ8d8paxUy1ekCGbyfSPCGVPb5f1kME2016EpafYz5myXI4Qrqb-o/s640/BaseAccess.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhrs8g94dk7m0yY9a27iYK-BuQHjCyGXLt9bsJP_LNFe6X_63S1mAmzwIRUkpfWN2cKbMwP2L3QUd6J4uZkiArYVaEQ8d8paxUy1ekCGbyfSPCGVPb5f1kME2016EpafYz5myXI4Qrqb-o/s1600/BaseAccess.png)\
Ahora crearemos las siguientes variables que son conexion y sentencia de manera global de esta forma nos permitirá utilizarlas en todo el proyecto:\
Connection conexion;Statement sentencia;\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjhsNrg6pRY38LUNtncUkkMEVOCJmyfVx9W4kgWhvgU8vZwP0xKGhlJ4j9evH2RvRBMz0ytYnV1hhNvdWRg98x8UffmwVwRePQxLSKv0uPYVbtxoizLpeJgm24_2CiqvjVj7D_P5ZO_CFY/s400/BaseAccess.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjhsNrg6pRY38LUNtncUkkMEVOCJmyfVx9W4kgWhvgU8vZwP0xKGhlJ4j9evH2RvRBMz0ytYnV1hhNvdWRg98x8UffmwVwRePQxLSKv0uPYVbtxoizLpeJgm24_2CiqvjVj7D_P5ZO_CFY/s1600/BaseAccess.png)\
\
El siguiente paso es crear un método llamado conectatarBaseDatos(), para crear la conexión.\
\
public void conectatarBaseDatos() {\
&#x20;       try {\
&#x20;           Class.forName("net.ucanaccess.jdbc.UcanaccessDriver"); //Linea que carga el driver\
&#x20;       } catch (ClassNotFoundException e) {\
&#x20;           JOptionPane.showMessageDialog(null, "Error al cargar Dirver");\
&#x20;       }\
&#x20;       try {\
&#x20; conexion = DriverManager.getConnection("jdbc:ucanaccess://src\\\BaseDatos\\\Proyecto.accdb");\
//En esta parte tenemos que cambiar la ruta en la que se encuentra nuestra base de datos \
//Ejemplo "jdbc:ucanaccess://C:\\\Proyecto.accdb" hace referencia que esta en el disco local C\
&#x20;       } catch (SQLException e) {\
&#x20;           JOptionPane.showMessageDialog(null, "Error en la dirección de la base de datos");\
&#x20;       }\
&#x20;       try {\
&#x20;           sentencia = conexion.createStatement();\
&#x20;       } catch (SQLException e) {\
&#x20;           JOptionPane.showMessageDialog(null, "Error al crear la conexión con la base de datos");\
&#x20;       }\
&#x20;   }\
\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiKxHb8tbfDeIM7LQNqFRElDfTVzffcx8jALTQN47yQfe3KM9wlLxMAebvcyq7StAlSHNPoAxFUcRmxKQdXBr4Z1NeRGH76ah3FmaGb1-cPlhsmT4uAyiGW0dxnLN6H30o5-I3FtCyJG2E/s640/BaseAccess.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiKxHb8tbfDeIM7LQNqFRElDfTVzffcx8jALTQN47yQfe3KM9wlLxMAebvcyq7StAlSHNPoAxFUcRmxKQdXBr4Z1NeRGH76ah3FmaGb1-cPlhsmT4uAyiGW0dxnLN6H30o5-I3FtCyJG2E/s1600/BaseAccess.png)\
\
Después de haber creado el método nos falta llamarlo, esto lo haremos desde el constructor:\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjxf9rQK7tbhtm3TshtjAGNxLE55hOfANwMjMicAdm_zYJSvtwrOqdO0Gg6CmoNZyv_MEwO18-T2sp7YLLoAuRq9oZ6u0cg56-flQzianZRRDdR8fkCfB1aoasDPOn5vECQREffa_9pERw/s640/BaseAccess.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjxf9rQK7tbhtm3TshtjAGNxLE55hOfANwMjMicAdm_zYJSvtwrOqdO0Gg6CmoNZyv_MEwO18-T2sp7YLLoAuRq9oZ6u0cg56-flQzianZRRDdR8fkCfB1aoasDPOn5vECQREffa_9pERw/s1600/BaseAccess.png)\
Lo ultimo que nos falta seria cerrar la base de datos cuando cerremos el proyecto esto se hace de la siguiente manera:\
Nos dirigimos al diseño de nuestro proyecto y damos clic derecho en frame: \
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEid1jTtp9LojWONB1AQk_XAow9B7jZWmOZruRLodJnxB-OkrJJOpP-oyi-6LrfY5EkOzqt6o0jtP76gkG_y1YWBaKxOX-iTtrjfatdbfqrBNBeokTpCUNV2rQERXL8jwXXf2Ytp3hL2a3c/s1600/BaseAccess.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEid1jTtp9LojWONB1AQk_XAow9B7jZWmOZruRLodJnxB-OkrJJOpP-oyi-6LrfY5EkOzqt6o0jtP76gkG_y1YWBaKxOX-iTtrjfatdbfqrBNBeokTpCUNV2rQERXL8jwXXf2Ytp3hL2a3c/s1600/BaseAccess.png)\
\
Nos mostrara las siguientes opciones en la cual crearemos un evento llamado windowsClosing:\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjSigtGFkf9_VXdY1FfK04TWECA6EvdVWOcoo9Y57O62XTC98MIpN9-aVTzUGAoQ1Vr6F6RndtG1oz1JTg_z_OmsrgmLP_JKsLqL57s2WNnb96I1DyRtUN4OcT8M07KrKRMP2D0kQ9tsJc/s400/BaseAccess.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjSigtGFkf9_VXdY1FfK04TWECA6EvdVWOcoo9Y57O62XTC98MIpN9-aVTzUGAoQ1Vr6F6RndtG1oz1JTg_z_OmsrgmLP_JKsLqL57s2WNnb96I1DyRtUN4OcT8M07KrKRMP2D0kQ9tsJc/s1600/BaseAccess.png)\
\
Bien ahora escribiremos el siguiente código que sirve para cerrar la conexión con la base de datos de ACCESS:\
&#x20;  try {            sentencia.close();        } catch (SQLException e) {            JOptionPane.showMessageDialog(null, "Error al cerrar la base de datos" + e);        }\
[![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhLp0UYsHTOQO5o0Unvy_lm9v2hv1DROsaT9iFayvBzAzq1_x2gqatbIy6zm5sk37r8DaQf7uomL5g8EgRrZj3y42AvZIZBCvGZ6sL6WdvcMWVG3-_SOvMGxFdehuL_iBj5SZ6neeJRlPk/s640/BaseAccess.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhLp0UYsHTOQO5o0Unvy_lm9v2hv1DROsaT9iFayvBzAzq1_x2gqatbIy6zm5sk37r8DaQf7uomL5g8EgRrZj3y42AvZIZBCvGZ6sL6WdvcMWVG3-_SOvMGxFdehuL_iBj5SZ6neeJRlPk/s1600/BaseAccess.png)\
Y listo ya tenemos conectado nuestro proyecto java con la base de datos ACCESS.
