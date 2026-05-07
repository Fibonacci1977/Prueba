# Conexión Base Datos WildFly

### Conexión Base Datos WildFly

### Fuente:

[http://wildfly.org/news/2014/02/06/GlassFish-to-WildFly-migration/](http://wildfly.org/news/2014/02/06/GlassFish-to-WildFly-migration/)

### Agregar Driver JDBC MySQL

Descargarlo desdehttp://dev.mysql.com/downloads/connector/j/\
\
En Runtime→Manage Deployments→presionar el botón Add

![a.png](https://lh3.googleusercontent.com/PBE3JI394yz7pDG46tCNbjMYi1BoUmVEjIgOuRSILg8puOgHeb6thgEAjRdTPg2LRwd5dhPW_OP0fIAMHbizSIi-2ZV0UBlyu8tQ_yae7tsXZifOXySTwW2L9gZrOQ)\
\
presionar el botón Seleccionar archivo\
![sd.png](https://lh6.googleusercontent.com/7wQWddogFt-AYdoBCeJpMnBHDEmKuKOiynJBu0zjJp0VS6CLQOVlUKod4mAmrOXIVhK-cKlWsPuSG-H-xYGaInKK-VoL_j05zADypl0_HbaN-oRrXMnoCkPJ8fYCxQ)\
\
\
\
\
\
\
\
\
\
\
seleccionar el driver jdbc mysql

![mysql.png](https://lh6.googleusercontent.com/nibOT5I1t1VeuiWjusTNynUMcSlpg7Vor8Ldsu1-deH0udSUOosQeegmrswpJdF_BYDssm5RySH1Rz79nbRCCEv12Jj1Le-9XoB8J_pcKSaF82ufh6uWrF6nEwdVTw)\
\
\
Presionar el botón Next

![n.png](https://lh6.googleusercontent.com/QMtAGm_GsbUtIUMOp2qfboGSQRS1sRzLYYUq62oIZxqScdCkpEqwLl2TprTHUpEQ77nTMUtClNnYnCMXjrjarMjvlpXEtdKJLoVWS68oEPrcwAlXOVUiqr5gUqZPGA)\
\
\
\
Presionar el botón Save

![sa.png](https://lh4.googleusercontent.com/fyOu08x8kfw4w1Wezaag7WQkMCwPyyTGaIIr_yy00RxHGO0jbhVEW3C3sk5NP8uBXZA1ziE95luFWWyIQ5m3ngPHetMHcFN_yx1ikgwWogfE4coi2dN9-JYeRNhbfw)\
\
\
Se muestra el driver agregado,Dar clic en En/Disable

![s.png](https://lh3.googleusercontent.com/2wodqT-6xHCB1I15B4Wj62v2lUCkPzjt4uGt5e-JcK-paI_sSr2E2hwZHLpesl1aW12DLMF9MIK5UIzOhXjZpcqSK3LROB0UA9wsFtj3MiQpIhZNLBg8t8rUVIezIg)\
\
\
\
\
Confirmar la solicitud\
![r56.png](https://lh4.googleusercontent.com/Je-U_M1KVG2or9XToX91cxw6v_EQSiPxR5qeJ3-eWY__rNufnZEyQJG1f_ihMFApg719Yc_-nEhH3UngRSClgAxfU8Y_YVn7e2RMlijFeOiSXgPfuKxBK-OSAOX8gg)\
Se muestra el conector habilitado\
![ens.png](https://lh6.googleusercontent.com/qJ8tXthaN0vdTwsOCWP9Qykf9rMqiSQ8jT-ge0HCUDb3kzDsaf4gwVGE15MZxk0UBphWb3xYlqQmZwhdjllaU6v3pLEmRh9M6JSWJFdN_DxQZBd0w-_0xHmDm4J65Q)<br>

### Crear un modulo

Pasos:

1. Entrar al directorio /modules/system/layers/base/com dentro de wildFly
2. crear el directorio mysql/main
3. Copiar el jdbc driver a ese directorio
4. Crear el archivo module.xml

\
\
\
Entrar el directoriocd wildfly-8.0.0.Final/modules/system/layers/base/com\
\
Crear el directorio mysqlmkdir mysql\
\
Crear el directorio maincd mysqlmkdir main\
\
Copiar el driver jdbc mysql al directorio main recién creado

![s.png](https://lh4.googleusercontent.com/sjYilp7ILVNbZ2gmhHUVHPL8yegoX0s7fArYc50v6b6VAXFsXBnO77RSBjPaYdFgipyJ4OlF7180GfaQyxCWNKa2OJKwllefZxywm2S8glImLVyHGJoFvbDjYTQ_7Q)\
\
Crear el archivo module.xmlgedit module.xml\
\
\<?xml version="1.0" encoding="UTF-8"?>       \<module xmlns="urn:jboss:module:1.1" name="com.mysql">           \<resources>               \<resource-root path="mysql-connector-java-5.1.29-bin.jar"/>           \</resources>           \<dependencies>               \<module name="javax.api"/>               \<module name="javax.transaction.api"/>           \</dependencies>       \</module>\
\
Agregar la configuraciónPodemos hacerlo desde la línea de comandos o editar directamente el archivo standalone.xmlEditaremos el archivo standalone.xmltgedit  wildfly-8.0.0.Final/standalone/configuration/standalone.xmlLocalizamos \<datasources>, agregamos el driver\
![d.png](https://lh5.googleusercontent.com/xJ48VxPSTEShU8Yln6SOLtyu-DkOtbLCPub06DxXc2z2B8IGuJMpUbJr83yaam8ngA4RjGqVIOqt_sz4f8k1kBWD8UKHC9e6ni-EZxq5dRosEs81s6i6e3_XZ7n4CQ)\
\
Agregamos el driver\<driver name="mysql" module="com.mysql">     \<xa-datasource-class>       com.mysql.jdbc.jdbc2.optional.MysqlXADataSource     \</xa-datasource-class>   \</driver>\
\
![s.png](https://lh6.googleusercontent.com/u6crbuDnaMflYFOFW8IG_1l9pnA6YaFeL4Unkow26GBv0gzNoC1YgBiMcXDAScesKkQyTgtLBdqwf4b_OL6KW8qrBxJ-5OmtUTOMuRfkrAiWOBjSULkNEm-0sWH9nw)\
En Profile→ Connector→Datasources dar clic en Add\
![add.png](https://lh5.googleusercontent.com/hBIb4dqQwOsKfoFgB--SGzUpxMJxnm2rYcFWiL2oEZzeD9UV0aMSw2OYXEkt48dvz4CeEKQ-ZpoNcynHIDamzDU_wtRUsHngYEo0P91wRSYJFWj9VGxX_7KnIC6xqA)\
\
\
En Name colocamos el nombre rigemdby en JNDI Name a diferencia de GlassFish debemos incluir el prefijo java:/java:/jdbc/rigmendb\
![n.png](https://lh3.googleusercontent.com/42UzzOc51mMlvc5q-KwrOZs5a1H_6zCgr6uscZPt6ALLHqD5L_EN_AmIu7HCjeOsEI0WWezUa9LKqPIfRvtEofGT1nAZWyiYzDq8yVZM1ig7zPEtWO0Q0iteJzDZjg)\
\
\
\
\
En la siguiente ventana como detecto el driver mysql dar clic en Next![d.png](https://lh4.googleusercontent.com/luGqyn_95-eZa0joCWoW_FK1nhCXp4p6qjNxJdBvNvhqO4aAr9hKygURQvCFC0TpmJ0RslvFZZDcal1XfGYqxMiMcOxlE0vP0mQZxgKD_piT1x0hnS_hzeFG8QOKuw)\
\
\
\
Especificar\
<br>

* Connection URL: jdbc:mysql://localhost:3306/rigemdb
* Username: root
* Password: secret

\
![d.png](https://lh3.googleusercontent.com/og7Cuu-a-eJYmG1uutx2v4oN4MnWRhfjaWgxesWZpsws8mymtbMGWpRnwVesqWowkQg9R98S94bCbxUq_uF4UYp2AdDYlLBctodw7TuPCaO5pTr-3PTVA_TYa2Iryg)\
\
\
\
\
\
\
\
Se muestra, el datasources

![a.png](https://lh3.googleusercontent.com/v_pdvfjlMmx6gQJac8l5TkpK8FA-EOgOQs0dV5dTk1KvHtNwRgfc3s97Y25lXjmXm8FO7cOeLlbPS-d8IJKO9rbNvHdAr4sIs3rfytkjtr1PRyYlCrYoFLBb13bu0A)\
\
\
presionar el botón Enable

,![d.png](https://lh4.googleusercontent.com/sYtvdVycRk-W1XvvmuTpMWVDgnu97izyGFwznZbC0ss-vaJUfoxP0Jtl86y0x-Uku7P6iJH3rgtCCCL_Hth-McxIKbvj7PBLIKyqZEIfPlHCHHDGAHM-oUrcL4MGuQ)

presionar el botón Confirm , para confirmar la solicitudQueda habilitado

![a.png](https://lh3.googleusercontent.com/Uyzj41tfznFlzlx0DAaD_7bVDuGmTFwTDdskKi1FB6qXs_XF79Muj_PkQ67j6mwXmCr4hT7lLKWzooj8NvzDlutK7zzu2A-Fj8gk4WNEusHT4xwgxzN-mMDhjisGJA)\
\
Seleccione la pestaña Pool y presione el botón Edit

![4.png](https://lh6.googleusercontent.com/n8XqqaojTfUCNdJ9RaK_nyuX1ruR_AoEsR5l5awYHnhCmpkIXFvg6d5IuDdKa3HdBUaGxwvGjGQMMyIbrbZsiuOf4tjLthQP4G_Ll-LPwyba6ElfMjhZp_aqGopGFg)\
\
\
y cambie los valores Min Pool Size a 5 y Max Pool Size a 15 y presione el botón Save\
![a.png](https://lh4.googleusercontent.com/6PTJnzDlSZq-oievvUExLqI3qmCReAUdV8QrrqFxtTdFE-b9Li0uf_Q4sr0_ebVoGBtdpWr63wxeDt3AVaF2UxKi4cmGAoJ91dOhAlMd-vavg6bJE6pcTadvg8oPwA)\
\
\
\
\
\
\
\
\
\
\
\
\
\
En la pestaña Connection dar clic en el botón Test Connection\
![t.png](https://lh4.googleusercontent.com/c3IZJrVUz4ZOCfHdEFPGIlLKZqkGlIJGJf9_3WxWzr2Vr7Bk8qwDQ67bDk9XiySK8VcKda0Z1U2h-q9T21gXtRWGSHAZNul0_bSLO0Otvi1vUeTTGh_vwiMm2xJgMQ)\
\
Nos envía el mensaje de conexión exitosa

![d.png](https://lh3.googleusercontent.com/-Kq6CvuOUjprPjD-F-iEtEu0qQJzCOwSunQEwiyL5eJC4gt1FNElewccEwS7ECEJb8CVALiq8xEr8__Ct217cOC8DT42Xht126FkH1pnNraiojEP5idarvCJI-aCLg)
