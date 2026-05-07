# Como crear un Connection Pool en WebLogic

&#x20;([Como crear un Data Source en WebLogic](http://javamex.wordpress.com/2014/07/21/como-crear-un-datasource-en-weblogic/)) los cuales serán necesarios para la configuración de un Connection Pool.  Estos ayudan enormemente al performance de la aplicación permitiendo tener a la mano un conjunto de conexiones listas para ser utilizadas.

Las pasos requeridos para su creación en Weblogic son los siguientes:

### **Crear el Connection Pool**

1. Entramos a la consola de Weblogic que se encuentra en la URL **http:/ \<localhost> : \<puerto> /console**. Si tenemos la instalación en el localhost tendríamos por default la siguiente URL http://localhost:7001/console.
2. Presionamos en la opción **Deployments**
3. [![Connection Pool](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step11.png)](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step11.png)
4. En **Deployments** buscamos la opción de **DBAdapter** y damos click sobre ella.[![Connection Pool](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step21.png)](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step21.png)
5. En la siguiente pantalla presionamos sobre las pestañas superiores de esta forma **Configuration/Outbound Connection Pools** y presionamos en el botón **New** como se muestra en la imagen siguiente:
6. [![Connection Pool](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step31.png)](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step31.png)
7. En la pantalla siguiente seleccionamos el ConnectionFactory al que queremos asociar al Connection Pool y presionamos siguiente.
8. [![Connection Pool](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step41.png)](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step41.png)
9. En la siguiente pantalla tendremos que ponerle un nombre JNDI por el cual haremos referencia al Connection Pool para utilizarlo
10. .[![Connection Pool](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step51.png)](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step51.png)
11. En la siguiente pantalla solo continuamos para finalizar.
12. [![Connection Pool](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step61.png)](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step61.png)
13. Con esto hemos finalizado la primera parte que es la crear el Connection Pool sin embargo falta configurarlo para asociarlo a un Data Source para extraer las conexiones.
14. **Configurar el Connection Pool**
    1. Nos dirigimos a la pantalla del paso D del y en vez de seleccionar New expandimos el **ConnectionFactory** con el símbolo de + para visualizar los ConnectionPool que están creados y ubicamos el connection pool que creamos en los pasos anteriores y damos clic sobre el.
    2. [![Connection Pool](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step71.png)](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step71.png)
    3. En la siguiente pantalla seleccionamos la pestaña de properties y en la tabla configuración ubicamos la propiedad **xaDataSource** (En caso de que nuestro DataSource sea XA) o **dataSourceName**(En caso de que nuestro DataSource no sea XA) y pones el nombre JNDI del DataSource.
    4. [![Connection Pool](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step81.png)](http://www.oscarblancarteblog.com/wp-content/uploads/2014/07/step81.png)
    5. Finalmente guardamos los cambios y nuestro Connection Pool estará listo para utilizarse.

&#x20;

Si sigues los pasos al pie de la letra no deberías tener ningún problema para crear un Connection Pool.
