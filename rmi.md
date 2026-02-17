# RMI

### &#x20;RMI (Remote Method Ivocation)

RMI (Remote Method Invocation) es un mecanismo de comunicación entre procesos. Es parte del JDK standard. La idea consiste en ejecutar métodos remotos de un proceso ha otro, independiente si estos se encuentran alojados en diferentes instancias de JVM.

![rmi-2](https://daylersalazar.wordpress.com/wp-content/uploads/2017/01/rmi-2.png?w=484\&h=158)

En ese artículo vamos ha implementar un ejemplo Cliente Servidor con RMI.

![rmi-1](https://daylersalazar.wordpress.com/wp-content/uploads/2017/01/rmi-11.png?w=490\&h=255)

## Requerimientos

* JDK 8 standard. No requiere dependencias de librerías externas.
* Los Objetos ha ser transportados tienen que ser Serializables.

## Implementación

Será necesario la implementación tanto de una aplicación cliente que consuma el servicio y de una aplicación servidor que implemente el servicio, adicionalmente será necesario iniciar el programa «rmiregistry» que funciona como broker entre la aplicación cliente y la aplicación servidor.

### Servidor

Los pasos para implementar el servidor son los siguientes:

#### 1. Definir la interface remota.

* Debe extender de **java.rmi.Remote**.
* Todos sus métodos lanzan la excepción **java.rmi.RemoteException**.
* Debe ser común tanto para la aplicación servidor como para la aplicación cliente.

```java
import java.rmi.Remote;
import java.rmi.RemoteException; 
public interface MathService extends Remote { 
MathResult add(int a, int b) throws RemoteException; 
MathResult sub(int a, int b) throws RemoteException;}
```

#### 2. Implementación de la interface remota

La interface remota tiene que implementarse en el lado del aplicación servidor, la aplicación cliente no necesita conocer esta implementación. Esto significa que en classpath de la aplicación cliente no es necesaria una referencia ha esta implementación.

* Declarar la implementación de la interface remota, en este caso «MathService».
* Todos sus constructores tienen  que lanzar **java.rmi.RemoteException**.
* Tanto los parámetros de estrada a sus constructores y/o métodos, así como sus valores de retorno deben serializables, esto significa que:
  * Debe tener un constructor por defecto (constructor que no recibe parámetros).
  * Todos los objetos que recibe como parámetros de sus métodos o retorna como resultado de la llamada a sus métodos deben implementar **java.io.Serializable**.



```java
import java.rmi.RemoteException;
 
public class MathServiceImpl implements MathService {
 
public MathServiceImpl() throws RemoteException {
// No op
}
 
@Override
public MathResult add(int a, int b) throws RemoteException {
return new MathResult(a + b);
}
 
@Override
public MathResult sub(int a, int b) throws RemoteException {
return new MathResult(a - b);
}
}
```

Ambos métodos retornan un objeto del tipo «MathResult» que contiene el resultado de la operación, este objeto debe ser serializable. Es necesario hacer notar que ni los métodos de esta clase ni sus constructores lanzan la excepción **java.rmi.RemoteException.**

```java
import java.io.Serializable;
 
public class MathResult implements Serializable {
 
private static final long serialVersionUID = 20160106L;
 
private int value;
 
public MathResult() {
// No op
}
 
public MathResult(int value) {
this.value = value;
}
 
public int getValue() {
return value;
}
}
```

#### 3. Implementación de la Aplicación Servidor.

Esta es la clase principal de la aplicación.

* Crear una instancia de la implementación del servicio remoto.
* Crear un Stub de la instancia remota. Esto no es mas que un wrapper de la interface remota del tipo UnicastRemoteObject. También podemos hacer que la implementación de nuestra interface remota herede de UnicastRemoteObject y así obviar este paso, cosa que no estamos realizado en este ejemplo.
* Registrar el servicio (Registry).

Cabe aclarar que antes de iniciar nuestra aplicación servidor, es necesario iniciar el programa «rmiregistry», vamos ha detallar este tema mas adelante.

```java
import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry;
import java.rmi.server.UnicastRemoteObject;
 
public class RmiServer
{
 
public static void main( String[] args )
{
// export object
try {
// get an instance of the service implementation.
MathServiceImpl service = new MathServiceImpl();
MathService stub = (MathService) UnicastRemoteObject.exportObject(service, 0);
Registry registry = LocateRegistry.getRegistry();
// publish the service. Assign name.
registry.rebind("rmi-mathService", stub);
System.out.println("Published rmi-mathService");
} catch (Exception ex) {
ex.printStackTrace();
}
}
}Cliente
```

Para implementar la aplicación cliente, necesitaremos acceso a la definición de la interface remota, esto significa que esta definición debe ser accesible desde nuestro classpath. Sucede lo contrario con respecto ha la implementación de la interface remota, no es necesario que está última este presente en nuestro classpath, es mas no se usará en ningún punto del código del cliente.

### 1. Definir client.policy

Define las políticas de seguridad en el cliente, debe estar presente como un archivo de recursos del programa bajo el nombre de «client.policy», para este ejemplo estamos otorgando a nuestro cliente permisos absolutos. No vamos ha entrar en detalle acerca de como usar estas políticas de seguridad en este artículo.

```java
grant {
permission java.security.AllPermission;
};
```

### 2. Implementación programa cliente

Para este ejemplo el programa cliente no es mas de una aplicación main que suma dos números usando nuestro servicio remoto y despliega el resultado en consola.

* Define el security manager. En este caso usamos la implementación por defecto del JDK estándar.
* Obtenemos una referencia al servicio remoto desde «registry». Cabe aclarar que para esto funcione primero se debe iniciar la aplicación «rmiregistry» (veremos como hacerlo mas adelante) ademas de la aplicación servidor.

```java
import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry;
 
public class RmiClient {
public static void main( String[] args ) {
if (args.length &amp;amp;amp;amp;lt; 2) {
System.out.println("use: java RmiClient a b");
return;
}
// set up security manager
if (System.getSecurityManager() == null) {
System.setSecurityManager(new SecurityManager());
}
//
try {
// get registry instance
Registry registry = LocateRegistry.getRegistry("10.40.0.19"); // host in which is running the app server.
// lookup service
MathService service = (MathService) registry.lookup("rmi-mathService");
Integer a = Integer.valueOf(args[0]);
Integer b = Integer.valueOf(args[1]);
System.out.println("add " + a + "+" + b + "=" + service.add(a, b).getValue());
} catch (Exception ex) {
// TODO Auto-generated catch block
ex.printStackTrace();
}
}
}
```

## rmiregistry

Sus bianrios se encuentran en $JAVA\_HOME/bin bajo el mismo nombre. Se trata de un broker entre nuestra aplicación servidor y nuestra aplicación cliente. Nos permite identificar y localizar la instancia remota, esto significa que el cliente va ha preguntar ha este programa donde se encuentra el servicio remoto que queremos resolver, también implica que para que un servicio sea remoto este tiene que registrarse ha una instacia de «rmiregistry».

## Ejecutando los programas ejemplo

### 1. Iniciar el programa «rmiregistry»

Si el «rmiregistry» no ha sido inicializado, ni el cliente ni el servidor pueden inicializarse. Para arrancar el programa ejecutar el comando de abajo:

```java
$ rmiregistry -J-Djava.rmi.server.useCodebaseOnly=false &

```

El comando de arriba no debería producir ninguna salida. Para verificar que se inicio el programa podemos valernos de: **$ ls -fea | grep rmiregistry** que nos imprime en pantalla el proceso correspondiente al «rmiregistry».

### 2. Iniciar la Aplicación Servidor

Previamente es necesario que «rmiregistry» esté inicializado. Ejecutamos nuestra aplicación servidor de la misma forma que ejecutamos cualquier programa Java, con la salvedad de que añadiremos algunas propiedades de sistema propias de RMI.

```java
$ java -Djava.rmi.server.useCodebaseOnly=false -Djava.rmi.server.codebase=file:/full/path/to/rmi-example-core-1.0.jar -cp /path/to/rmi-example-server-1.0.jar:/path/to/rmi-example-core-1.0.jar com.dayler.rmi.RmiServer

```

Donde:

* -Djava.rmi.server.codebase: Debe contener el path absoluto hacia los binarios que contienen las definiciones remotas.
* rmi-example-core-1.0.jar: Contiene la definición de las interfaces remotas.
* rmi-example-server-1.0.jar: Contiene la aplicación servidor y a demás la implementación de las interfaces remotas.
* -cp: Añade los binarios al classpath, esta por demás decir que debe contener una referencia a las definiciones de las interfaces remotas.

Al ejecutarlo deberíamos tener la siguiente salida por consola:

```java
$ Published rmi-mathService
```

### 3. Iniciar la Aplicación Cliente

Requiere que las aplicaciones «rmiregistry» y «RmiServer» estén iniciadas. Ejecutamos nuestra aplicación cliente de la misma forma que ejecutamos cualquier programa Java, como en el caso anterior se añade propiedades del sistema propias de RMI.

```java
	
$ java -Djava.rmi.server.useCodebaseOnly=false -Djava.rmi.server.codebase=file:/full/path/to/rmi-example-core-1.0.jar -Djava.security.policy=/path/to/client.policy -cp /path/to/rmi-example-client-1.0.jar:/path/to/rmi-example-core-1.0.jar com.dayler.rmi.RmiClient 10 5

```

Donde:

* -Djava.rmi.server.codebase: Debe contener el path absoluto hacia los binarios que contienen las definiciones remotas.
* rmi-example-core-1.0.jar: Contiene la definición de las interfaces remotas.
* rmi-example-client-1.0.jar: Contiene la implementación del cliente.
* -Djava.security.policy: Debe contener el path ha «client.policy».

Cabe hacer notar que no existe ninguna referencia a la implementación de las ineterfaces remotas.

La aplicación cliente recibe dos números enteros y los suma. Al ejecutarlo deberíamos obtener la siguiente salida por consola:

```java
$ add 10+5=15
```

## Código fuente

Se puede obtener el código fuente del ejemplo desde:

* [https://github.com/dayler/rmi-example.git](https://github.com/dayler/rmi-example.git)

## Referencias

* Getting Started Using Java RMI – [http://docs.oracle.com/javase/8/docs/technotes/guides/rmi/hello/hello-world.html](http://docs.oracle.com/javase/8/docs/technotes/guides/rmi/hello/hello-world.html)
* Running the Example Programs – [https://docs.oracle.com/javase/tutorial/rmi/running.html](https://docs.oracle.com/javase/tutorial/rmi/running.html)
* java.rmi Properties – [http://docs.oracle.com/javase/7/docs/technotes/guides/rmi/javarmiproperties.html](http://docs.oracle.com/javase/7/docs/technotes/guides/rmi/javarmiproperties.html)
* Java-RMI-Example – [https://github.com/rm5248/Java-RMI-Example](https://github.com/rm5248/Java-RMI-Example)

{% file src=".gitbook/assets/Tema2_2aParte.pdf" %}

{% file src=".gitbook/assets/Lec03.ps.pdf" %}

{% file src=".gitbook/assets/Lec06.ps.pdf" %}

{% file src=".gitbook/assets/rpcgen1.pdf" %}
