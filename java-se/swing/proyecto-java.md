# Proyecto Java

## Proyecto Frontend en Java Swing.

Este Proyecto Frontend es el resultado que da seguimiento al curso Interfaz Gráfica en Java proporcionado por el grupo Semana de Ingenio y Diseño de la universidad Distrital de Colombia donde se usan una serie de técnicas para realizar GUI modernas y profesionales.

Algunas partes del código están inspiradas en otros proyectos, a continuación se deja enlaces de estos:

* [https://github.com/akashyap2013/Advanced-Login-UI](https://github.com/akashyap2013/Advanced-Login-UI)
* [https://ed.team/cursos](https://ed.team/cursos)

Dentro del proyecto Java que aplican una serie de técnicas y se da seguimiento a varios temas que ayudan a la creación de interfaces gráficas profesionales, mantenibles y con código basado en las buenas practicas. El curso puede ser encontrado en una seríe de repositorios donde se explican cada una de las técnicas y temas utilizados en el proyecto.

* **Clase 1:** [Estructura básica de una clase UI](https://github.com/CrissUD/InterfazGraficaJavaClase1)[.](proyecto-java.md#interfaz-grafica-en-java)
* **Clase 2:** Objetos Gráficos Básicos.
* **Clase 3:** [Objetos Decoradores](https://github.com/CrissUD/InterfazGraficaJavaClase3).
* **Clase 4:** [Modularización y optimización de código y recursos gráficos](https://github.com/CrissUD/InterfazGraficaJavaClase4).
* **Clase 5:** [Componentes Gráficos y eventos de acción](https://github.com/CrissUD/InterfazGraficaJavaClase5).
* **Clase 6:** [Componentes gráficos en una SPA y Routing](https://github.com/CrissUD/InterfazGraficaJavaClase6).
* **Clase 7:** [Reutilización de Componentes gráficos](https://github.com/CrissUD/InterfazGraficaJavaClase7).
* **Clase 8:** [Introducción eventos del mouse](https://github.com/CrissUD/InterfazGraficaJavaClase8).
* **Clase 9:** [Implementación eventos del mouse](https://github.com/CrissUD/InterfazGraficaJavaClase9).
* **Clase 10:** [Implementación de servicios Lógicos](https://github.com/CrissUD/InterfazGraficaJavaClase10).
* **Clase 11:** [Uso de Tablas gráficas](https://github.com/CrissUD/InterfazGraficaJavaClase11).
* **Clase 12:** [Implementación de animaciones](https://github.com/CrissUD/InterfazGraficaJavaClase12).
* **Clase 13:** [Uso de Graphics y Canvas](https://github.com/CrissUD/InterfazGraficaJavaClase13).
* **Clase 14:** [Personalización Avanzada de objetos gráficos](https://github.com/CrissUD/InterfazGraficaJavaClase14).
* **Clase 15:** [Uso de LayoutManager](https://github.com/CrissUD/InterfazGraficaJavaClase15).

### Descripción

En el ejemplo se presenta:

* Interfaz de usuario desde código Java (sin utilizar asistentes de GUI).
* Enfoque de **ComponentesGráficos** para modularización de responsabilidades.
* **Modularización de código** separando la creación de objetos gráficos.
* Optimizacion de recursos para aplicaciones a traves de **servicios**.
* Optimización de código a traces de **servicios**.
* Personalización avanzada a traves de **servicio**.
* Uso de **Servicios Lógicos** para obtención (Simulada) de información externa.
* Representación única de objetos de una misma clase (Singleton) para control de **Servicios**.
* Uso de eventos a traves de **ActionListener, MouseListener, FocusListener**.
* Discriminación por clases para control de eventos.
* Uso de **Tablas** y control de información a traves de ellas.
* Uso de ScrollPane para navegación de interfaz.
* Uso de **Graphics y Graphics2D** para pintar en pantalla.
* Animaciones de movimiento con uso de **Timer**.
* Uso de **LayoutManager** para posicionamiento automático de objetos gráficos.

### Demostración

Usted puede ver la aplicación corriendo a través de [Este Link de Youtube](https://youtu.be/_MbVCOJ1BUE).

A continuación se presentan algunas capturas.

<figure><img src="https://camo.githubusercontent.com/be737e9ebb385771894dfda2f42845c6ab8969b6bc739b470557363bdd9291b5/68747470733a2f2f692e696d6775722e636f6d2f333547623172612e706e67" alt=""><figcaption></figcaption></figure>

Login de usuarios.

<figure><img src="https://camo.githubusercontent.com/fbff53fddfdaec5d62ac55f063713aaa9489dfa64180bf8162e20e9984ed3009/68747470733a2f2f692e696d6775722e636f6d2f433332334847312e706e67" alt=""><figcaption></figcaption></figure>

Inicio de aplicación.

<figure><img src="https://camo.githubusercontent.com/1cfb3ba6299f26c18cf8d7e8b11a8e2ea4cdde6fca3572dff2c483c61c1a089d/68747470733a2f2f692e696d6775722e636f6d2f694c416e714e452e706e67" alt=""><figcaption></figcaption></figure>

Listado de productos.

## Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 1

### Objetivos

#### Objetivos Principales

* Explicar los temas principales y alcances del curso dejando claro que se quiere obtener al finalizar este.
* Revisar el concepto de Objetos y aterrizarlo con el concepto de Objetos gráficos para el contexto de un proyecto de Java UI.
* Identificar la estructura básica de una clase UI en Java y algunas normas que se tendrán en cuenta para su construcción.

#### Objetivos Secundarios

* Mostrar proyectos destacados realizados por estudiantes que han pasado anteriormente por el curso para aterrizar el alcance que busca este curso.
* Postular propuestas de trabajo para escoger el proyecto del curso que se realizará a lo largo del curso.
* Repasar conceptos básicos que serán pilares para la construcción de interfaces gráficas.

## Introducción y Alcance de Curso

### Temáticas

A continuación se muestran las temáticas que se dictarán en el curso.

<figure><img src="https://camo.githubusercontent.com/32ab9c38a2176e756cd98bbb869d089fcbe869f237dcc83bf7907b1a2d6ecc92/68747470733a2f2f692e696d6775722e636f6d2f6a71785761504a2e706e67" alt=""><figcaption></figcaption></figure>

Aunque las temáticas anteriores son importantes y fundamentales, algo **más importante que se quiere enseñar, es la perspectiva de arquitectura para la construcción de aplicaciones gráficas**.

<figure><img src="https://camo.githubusercontent.com/69ac9fe806d1310ad0d21066a0079b2dd85d723c55ee08c7f8a008466b53bbd2/68747470733a2f2f692e696d6775722e636f6d2f4474684e6b41632e706e67" alt=""><figcaption></figcaption></figure>

El anterior esquema esta basado en Frameworks y Librerías muy usados en el entorno del desarrollo Frontend y su enfoque da una visión organizada y estandarizada de como trabajar con proyectos Frontend. Este curso busca aterrizar esos conceptos utilizando el lenguaje Java para aplicaciones de escritorio, esto ademas de permitir la creación de un software organizado y estandarizado, ayudará al entendimiento principal de las metodologías que estas propuestas realizan y asi a la hora de trasladarse a estas tecnologías sea de una manera mas fácil.

Para los estudiantes que quieren obtener el grupo de trabajo como requisito de la carrera de Ingeniería de Sistemas a continuación se muestra los porcentajes de notas que se realizaran:

<figure><img src="https://camo.githubusercontent.com/a3162f0e84587979cb1c0b3c0b000fabfb3f98368be4da266cf7ad3839d8fc3e/68747470733a2f2f692e696d6775722e636f6d2f58714c4a4532712e706e67" alt=""><figcaption></figcaption></figure>

### Alcances

A continuación se muestra algunos proyectos realizados por estudiantes que pasaron por el curso anteriormente:

<figure><img src="https://camo.githubusercontent.com/2443a7162ea5285822a37404b41e86ae141d91c0faf8e70ac50842d343d5f0f0/68747470733a2f2f692e696d6775722e636f6d2f595662327474662e706e67" alt=""><figcaption></figcaption></figure>

## Definición de Objeto y Objetos Gráficos en Java

Para empezar se hablará de la evolución de los datos en la programación para explicar como se forma el concepto de Objetos. Si ya tiene conocimientos de POO se puede saltar esta explicación y pasar a la sección de **Definición de clase UI**

### Datos Primitivos

Primero se tienen los datos Primitivos, estos datos son la parte mas pequeña en cuanto a variables se refiere. Estos son tipos de datos que se encuentran en cualquier lenguaje de programación en la actualidad, en la siguiente imágen se ven alguno de estos, ademas de la forma de declarar (en Java) y su respectiva Notación.

<figure><img src="https://camo.githubusercontent.com/0c9ff763b35507bc475dfe768413ffd635233a1655c6ad8bdaf40fa351b45a9a/68747470733a2f2f692e696d6775722e636f6d2f7a4e306d5a54362e706e67" alt=""><figcaption></figcaption></figure>

Puede notarse que la declaración consta de varias partes:

* **Tipo Acceso:** este se refiere a la forma en que los datos pueden obtenerse a traves de otros archivos (clases). Esta propiedad esta enfocada en el paradigma orientado a objetos e indica como las otras clases pueden acceder o no a ciertos atributos o métodos de la clase. Estos pueden ser:
  * **Publico:** Se puede acceder al atributo desde cualquier otra Clase.
  * **Privado:** Unicamente se puede acceder al atributo por medio de la misma Clase.
  * **Protegido:** Solo la clase y las hijas podrán acceder al atributo.
  * **Default:** Las clases del paquete pueden tener acceso a estas.
* **Tipo de Dato Primitivo:** Simplemente el tipo de dato de toda la vida, puede ser int, String, float, char etc.
* **Variable:** Es el nombre con el que se maneja el tipo de dato, puede tener el nombre que uno decida darle, salvo algunas excepciones como iniciar con numero, caracteres especiales, etc.
* **Valor inicial:** Es el valor que puede tomar una variable una vez se declare, no es necesario que este valor se incluya directamente en la declaración.

### Arreglos

Los datos evolucionan a un concepto mas grande, estos son los arreglos. Los arreglos son colecciones de datos con las siguientes características:

* **Datos homogéneos:** Un arreglo es un conjunto finito de n datos y solo puede manejar un único tipo de dato. Esto quiere decir que en dado caso de crear un arreglo de números enteros, por ningún motivo en ninguna posición de dicho arreglo, este puede contener números decimales o caracteres. O por ejemplo un arreglo de Strings no puede contener datos tipo numéricos etc.
* **Tamaño estático:** Estos tienen un tamaño inicial y no es posible cambiar el tamaño de este, si un arreglo de enteros inicia con un espacio de 30 tendrá esa capacidad y no se puede cambiar en tiempo de ejecución.
* **Posicionamiento:** Cuando se quiere acceder a un dato especifico dentro del arreglo se debe tener en cuenta su posición dentro del mismo. Mientras un arreglo contenga datos el primer elemento, segundo, tercero,…, enésimo de éste, puede ser identificado a través de un numero ordenado que empieza en 0 y termina en (n-1) (el tamaño del arreglo - 1) y se conoce como **indice de posición**.
* **Dimensiones:** Estos pueden tener varias dimensiones que se deben indicar cuando se declara el arreglo y esta dimension tampoco podrá ser cambiada.
  * **1 dimension:** Los arreglos de una dimension son conocidos como **Vectores**.
  * **2 dimensiones** Los arreglos de 2 dimensiones son conocidos como **Matrices**.
  * **n dimensiones** Los arreglos pueden tener n dimensiones estos arreglos normalmente se entienden como una matriz que contiene otras matrices o vectores dentro y asi sucesivamente.

<figure><img src="https://camo.githubusercontent.com/1c63872e71ec006162138e069111dd07197d1fa0ae5268679b6f7f4e7a7210b8/68747470733a2f2f692e696d6775722e636f6d2f4748427567426a2e706e67" alt=""><figcaption></figcaption></figure>

Se puede notar que existen varias partes importantes a la hora de declarar un arreglo:

* **Dimension de arreglo:** Se debe denotar la dimension del arreglo con paréntesis cuadrados \[ ].
* **Inicialización de Arreglo:** Esta puede ser de varias formas y tampoco es obligatorio realizar en la declaración sin embargo es importante denotar que una vez se inicializa un arreglo se debe indicar el tamaño que tendrá o en su defecto el contenido del mismo.

### Estructuras de datos

Una estructura de datos es un tipo de dato que tiene la capacidad de contener otros datos, pero a diferencia de un arreglo, esta puede contener datos de diferentes tipos y ademas no existe un limite de cuantos datos podría contener. Otro punto de diferencia es que ya no obtiene sus valores a través de posiciones, sino que lo hace mediante un sistema conocido como **clave/valor**, donde cada valor es obtenido a través del nombre de la variable que se indicó dentro de la estructura. Incluso el concepto es tan amplio que tiene la capacidad de contener Strings, enteros, flotantes, arreglos e incluso otras estructuras de datos. Este ultimo aspecto es muy importante y da lugar a la creación de estructuras algo mas complejas como listas, pilas, colas, arboles, grafos que se estudian normalmente en cursos relacionados a la algoritmia y la ciencia de datos.

Nótese que en la declaración ha cambiado algo importante:

<figure><img src="https://camo.githubusercontent.com/b1f7a3e2e260ea507e378b55de535e20f73e02295c5a047909809850d6a86a28/68747470733a2f2f692e696d6775722e636f6d2f4b4c7756504d732e706e67" alt=""><figcaption></figcaption></figure>

* **Tipo de dato abstracto:** El tipo de dato ya no es convencional, no es una palabra clave del lenguaje (int, String, float etc.) sino que es un tipo de dato que tendrá el nombre de la estructura creada, esto quiere decir que al crear una estructura de datos se esta creando también un tipo de dato y se puede manipular mediante una variable. Este concepto se suele llamar como **tipo de dato abstracto**.
* **Inicializar estructura:** En Java el concepto de estructuras esta implementado con el concepto de objetos asi que no es posible dejar un ejemplo claro, sin embargo en lenguajes como C o C++ se puede inicializar como se ve en la imágen.

### Objetos

Los objetos son tomados del concepto de las estructuras de datos, sin embargo estos tienen unas características que lo diferencian de estas:

* **Comportamiento:** A diferencia de las estructuras de datos un objeto tiene una serie de **métodos** (funciones) que le proporcionan comportamiento a este. Tal concepto es importante y por lo general son los métodos el medio por el cual un objeto interactúa con otro.

<figure><img src="https://camo.githubusercontent.com/31e0756fc915d17ce692293ad03abbaff425b7be2c2903365cb2bbc5f7f8ab35/68747470733a2f2f692e696d6775722e636f6d2f53446a504638592e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo de métodos encargados de obtener y configurar un atributo nombre

* **Clases:** La clase es la representación en código de un objeto, esta representa el molde donde se definen sus atributos, comportamientos, entornos y accesibilidad. El objeto es entonces la ejemplificación de una clase.
* **Nuevos términos:** Cuando una variable es global para la clase (existe para todo el entorno) normalmente se suele referir a esta como **atributo**, si una variable por ejemplo es creada dentro de un método se le sigue considerando variable unicamente. Las funciones que hacen parte de la clase ahora se conocen como **métodos**.
* **Entornos (Scope):** Un entorno (Scope) es un contexto que esta aislado del resto, un método es un ejemplo de entorno, si una variable es creada dentro de él sera conocida solo para ese entorno, si otro método trata de manipular esa variable no existirá. Una clase también es un entorno que a su vez contiene otros entornos (métodos). Esto quiere decir que sus atributos y métodos solo existen en dicha clase, si se quiere acceder desde otra clase a alguna funcionalidad o atributo de este se debe tener en cuenta el tipo de acceso explicado previamente en este documento.
* **Constructor:** Entre sus métodos una clase tiene por defecto un Constructor. Este método es la función por la cual otra clase podrá realizar una ejemplificación del objeto. El constructor habitualmente tiene el mismo nombre que la clase y siempre es el primero en ejecutarse.

<figure><img src="https://camo.githubusercontent.com/6945c35ca2e402d9b5c2b41739b1985146c3272bcad551197bd3cbbd50db9669/68747470733a2f2f692e696d6775722e636f6d2f4231456e4542782e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo de una clase que representa los atributos y comportamiento de un objeto Casa con sus respectivas partes explicadas

A continuación se ve el ejemplo de una clase y como crear el objeto.

<figure><img src="https://camo.githubusercontent.com/89688391b3f8f0fc59262fbfaa62ad53d7423741bc3af5d4cdb6fafb61ac97c6/68747470733a2f2f692e696d6775722e636f6d2f39364d346443782e706e67" alt=""><figcaption></figcaption></figure>

Se puede ver que en la declaración de un objeto ocurren dos cosas interesantes:

* **Tipo de dato:** Al igual que una estructura de datos el tipo de dato ahora es abstracto y es igual al nombre que se deje en la clase.
* **Variable (Objeto):** El nombre de la variable que se coloca cuando se esta declarando es el objeto en si. Esta variable es entonces el medio para acceder a los atributos y funcionalidades creadas en la clase.
* **Ejemplificación:** Para poder interactuar con el objeto es necesario inicializar esta variable, una palabra apropiada para esta acción es ejemplificación (algunas veces mal llamada instanciación). Lo que se hace realmente, es llamar a su método **constructor** y de esta forma queda listo el objeto para ser usado.

Una cosa a resaltar es el acceso a los atributos y métodos, puede notarse que al intentar acceder a la variable **numero** de la clase no es posible acceder. Esto debido a que este atributo es de acceso **privado**.

Otro aspecto importante a mencionar son los **métodos** que contiene cada clase, estos tienen varias partes:

<figure><img src="https://camo.githubusercontent.com/2bdaa0bc13924940df858dad475f6a1a9faae4936e09f9ff19577d5ea03e8329/68747470733a2f2f692e696d6775722e636f6d2f667856467762352e706e67" alt=""><figcaption></figcaption></figure>

Partes de un método y como llamarlo

Se puede observar que un método cuenta con:

* **Tipo de acceso**: Puede ser publico, privado o protegido, sin embargo la mayoría de las veces se va a encontrar como publico.
* **Tipo de retorno**: Es el tipo de dato que el método puede retornar, si no retorna nada generalmente se pone la palabra clave **void**, un método puede retornar cualquier tipo de dato desde un dato primitivo hasta objetos, arreglos, colecciónes (Lista de objetos) etc.
* **Nombre del método**: Es arbitrario y generalmente se inicia con minúscula.
* **Parámetros**: Un método puede recibir por parámetros cualquier cantidad de datos y de cualquier tipo, estos se ponen dentro del paréntesis y se debe denotar siempre el **tipo de dato** seguido del **nombre de la variable**, si un método no recibe nada por parámetro se pone los paréntesis vacíos "**( )**".
* **Contenido**: Es el código escrito dentro del método, una cosa importante a aclarar es que si el método retorna algún tipo de dato obligatoriamente dentro del contenido debe estar la palabra clave **return** seguido de la variable que va a retornar y esta debe coincidir con el tipo de dato que se explicito que iba a retornar.
* **Argumentos**: Cuando un método se llama desde otra parte del código y el método exige el recibimiento de datos por parámetros, se debe enviar una serie de valores cuando se llama al método dentro del paréntesis y estas se conocerán como argumentos. Note que en el caso de envío no es necesario denotar el tipo de dato que es la variable, con solo esta ultima basta, sin embargo Java internamente comprueba que la variable enviada corresponda al tipo de dato que se pide.
  * **Envió --> Argumentos**
  * **Recibido --> Parámetros**

<figure><img src="https://camo.githubusercontent.com/d5427ec1bcdabbb15a4e9ea4a1b1c9d039aaaf0187e7f8a753ea070d9832b540/68747470733a2f2f692e696d6775722e636f6d2f35343274494d4c2e706e67" alt=""><figcaption></figcaption></figure>

Para explicar mejor el concepto de objetos podemos ver en la anterior imágen dos clases, algo a resaltar es que todos los atributos son privados y los métodos son públicos en ambas clases, esto generalmente debe realizarse por principios del paradigma orientado a objetos y se conoce como encapsulamiento.

Dentro de la clase carro entre uno de sus atributos esta el objeto Motor. Tenemos que ejemplificar el objeto antes de acceder a sus métodos y este se hace dentro del constructor para este caso (la ejemplificación del objeto se puede realizar en cualquier parte del código). Una vez el objeto este listo se pueden acceder a sus funcionalidades como por ejemplo **encender()**. Mas adelante en otra parte del código de la clase **Carro** por ejemplo en el método **arrancar()** se necesita obtener la información del cilindraje del motor, puede notarse que el atributo **cilindraje** de la clase **Motor** es privada pero por medio de su método **devolverCilindraje()** este devolverá el valor y se igualaría a la variable creada para el propósito del método arrancar.

<figure><img src="https://camo.githubusercontent.com/ae478dd5469868c304b98809e757e526c6e7ced0e2bcd7278efa279c693094de/68747470733a2f2f692e696d6775722e636f6d2f4b5346444438702e706e67" alt=""><figcaption></figcaption></figure>

Un objeto gráfico UI no es mas que clases creadas por los desarrolladores de Java contenidas en una serie de librerías como **AWT o Swing**, con los que se podrá interactuar a traves de la ejemplificación de su objeto, se puede notar que al igual que una clase común este tiene atributos y métodos por los cuales se puede acceder, con estas funcionalidades es posible mostrar una interfaz de usuario.

## Definición de Clase para UI

En Java existen muchas formas de crear Interfaces gráficas y no existe en realidad un estándar para la creación de estas, en este curso se pretende trabajar de una manera estandarizada que no solo ayudara con la organización y buenas practicas del código, también se encarga de escribir un código entendible y mantenible para todos los demás y en especial los que somos parte del curso. Esta metodología no es la verdad absoluta y tampoco pretende ser rígida ya que se pueden tener ligeras variaciones.

* El proyecto inicia con un paquete por defecto **DefaultPackage** sin embargo es bueno crear una carpeta raíz, en este caso se creara el paquete **app**.
* Es bueno separar las vistas o ventanas en paquetes únicos, es por esto que dentro del paquete **app** se crea un paquete llamado **VistaPrincipal** y dentro se crea la primera clase UI.
* Al crear una clase UI lo primero que se realiza es definir el nombre de la clase, por motivos de estándar se colocara el nombre de la clase (es arbitrario) seguido de la palabra **Template**. Así por ejemplo si quiero crear una clase llamada _VistaPrincipal_ esta quedara entonces con el nombre **VistaPrincipalTemplate**, esto tiene su razón y mas adelante en el curso esta razón sera explicada.

<figure><img src="https://camo.githubusercontent.com/0b8278819834ea03f637274429a40d3e5934dcf5f3e2a93c0b6f22af7a6a29ff/68747470733a2f2f692e696d6775722e636f6d2f79555a704478762e706e67" alt=""><figcaption></figcaption></figure>

Estructura básica de un proyecto GUI.

### EDT (Hilo despachador de eventos de Swing).

Se puede notar que en el paquete raíz **app**, existe otra clase **App.java**, esta clase contiene el método que ejecuta la aplicación (**método main**) y desde aquí debemos indicarle a la aplicación que se llamará a la ventana. Sin embargo, a diferencia de una aplicación que corre a través de la terminal, donde se llama a la clase o función que queremos ejecutar directamente desde el método **main**, cuando creamos aplicaciónes **Java Swing** debemos tener cuidado de la manera en que ejecutaremos la interfaz gráfica.

Esto se debe a que cuando ejecutemos una aplicación con interfaz gráfica, Java por debajo va a habilitar 3 hilos:

* **Hilo principal de java**: Este corre y administra toda operación que se llame a través del método main.
* **Hilo escuchador de eventos:** Es un hilo encargado de recibir cualquier evento que el usuario pueda dar en la aplicación ya sea escribiendo algo por teclado, dando click, arrastrando el mouse etc.
* **Hilo despachador de eventos (EDT):** Este hilo es creado por Swing y es el encargado de cualquier operación que afecte a la interfaz gráfica ya sea con un cambio de color, mostrar una ventana, dar click a un botón, escribir sobre un JTextField etc.

El problema esta en que el módelo de hilos de **Swing** se basa en el uso de un solo hilo para todas sus operaciones, en este caso el **EDT**. Pero si llamamos directamente a la clase UI que representa a la ventana y la ejemplificamos, está va a correr a traves del **Hilo principal de Java** y no del **EDT**.

<figure><img src="https://camo.githubusercontent.com/aa6e119b2062d59df942c37c8bfe2c69af02cc83fd2070b77ad2ffc98974e727/68747470733a2f2f692e696d6775722e636f6d2f504e695a49766d2e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo Creación y ejemplificación del objeto VistaPrincipal desde la Clase Main Directamente.

Esto a grandes rasgos no traerá muchos problemas, probablemente tu has ejecutado aplicaciones Swing de esta forma y no notaste ningún problema, pero si en algún momento se necesita realizar operaciones asíncronas para traer información de algún servidor externo, base de datos o realizar operaciones concurrentes el entrelazado de hilos seguramente va a provocar **deadlocks** en la aplicación haciendo que la interfaz gráfica se quede bloqueada y sin funcionar.

Para evitar estos escenarios y como buena practica se llamará a la clase UI a traves del hilo **EDT**, el siguiente código muestra la forma correcta de hacerlo:

```
public static void main(String[] args) {
    Runnable runApplication = new Runnable () {
        public void run(){
            VistaPrincipalTemplate vista = new VistaPrincipalTemplate();
        }
    };
    SwingUtilities.invokeLater(runApplication);
}
```

El anterior código asegura una ejecución de la interfaz gráfica a través del **EDT** y esto grácias al método **invokeLater** de SwingUtilities. No te preocupes si no entiendes algo en las lineas de código plasmadas, lo importante es el propósito que estas tienen y para tu tranquilidad es la única vez en el curso que tocaremos el tema de operaciones con hilos.

### Características de la clase UI

La Clase Template tiene ciertas características que a continuación serán explicadas:

* Una clase **Tempate** que se encarga unicamente de la muestra por pantalla de los objetos gráficos y con los que interactuará el usuario. También mostrará los valores obtenidos de la lógica realizada por otras clases.
* **No** se encarga del manejo de eventos ni llamada de servicios ni operaciones lógicas, su responsabilidad se reduce a la muestra de interfaces Gráficas y muestra y recolección de información que el usuario necesite ver o que este recopile.
* Hereda de una clase **JFrame** esto le dará a la clase que creemos, propiedades gráficas para ser mostrada al usuario.

<figure><img src="https://camo.githubusercontent.com/f5ae9714c6bc70f35f4d5f186e63e61c6aa54a91a3f08430cd8c565f05394c5d/68747470733a2f2f692e696d6775722e636f6d2f55374a795434572e706e67" alt=""><figcaption></figcaption></figure>

* Importara las librerías necesarias para configurar objetos gráficos en pantalla.
* Como propuesta inicial y para propósitos de explicación de otros temas dentro del curso, la configuración de objetos gráficos se realizará dentro del método **Constructor** sin embargo si se quiere configurar estos objetos en métodos separados desde el inicio no hay problema (mas adelante se tomará este segundo enfoque y se explicara el por que un enfoque es mejor que el otro).

<figure><img src="https://camo.githubusercontent.com/2b2a2da1620fd647fc00fdde1144d68776987da86342d8306cdf3a1c06343049/68747470733a2f2f692e696d6775722e636f6d2f4f42644c7169552e706e67" alt=""><figcaption></figcaption></figure>

En la imágen anterior se puede ver una serie de configuraciones, estas le dan características a la ventana y esto es posible gracias a la herencia a la clase **JFrame**. Cada configuración tiene su propósito:

* **super:** Recibe por parámetro un String y le da el titulo a la ventana que se verá reflejada en la barra superior de la interfaz. Es importante recalcar que este método debe colocarse como primera linea de código dentro del constructor, de lo contrario no tendrá efecto en la vista. Otra forma de hacer esto mismo es mediante el método **setTitle**.
* **setDefaultCloseOperation:** Recibe por parámetro configuraciones Java. Le indica al compilador que una vez la ventana sea cerrada el programa dejara de correr, esto lo hace gracias al parámetro recibido **EXIT\_ON\_CLOSE**. Si no hacemos esta configuración la ventana cerrara pero el programa seguirá corriendo en el compilador de Java.
* **setSize:** Recibe como parámetros un par de enteros. Le da propiedades de ancho y alto a la ventana, en este caso la interfaz gráfica ocupara 1200 pixeles de ancho y 700 pixeles de alto.
* **setLocationRelativeTo:** Recibe como parámetro la ventana o el componente con el que se quiere posiciónar relativo a este. le indica al sistema que la ventana se posicione en el centro del componente que le pasemos como parámetro. Esto ya que por defecto la ventana se posicionará en el punto (0,0) del monitor. Como generalmente en pantalla solo tendremos una sola ventana de la aplicación mostrándose, el parámetro **this** le indicará a la ventana que se va a posicionar en el centro de la pantalla, por otro lado si le pasamos el parámetro **null** se posicionará igualmente en el centro al no haber mas ventanas. _Es importante que este método se llame después de asignar el tamaño a la ventana o el compilador se confundirá y no la posicionará donde se quiere._
* **setLayout** Recibe por parámetro el LayoutManager que quiera ser utilizado para la gestión de posicionamiento. Java maneja el posicionamiento de sus objetos gráficos por medio de **LayoutManager**, este posicionamiento es algo confuso de entender cuando se esta empezando por lo que por ahora es mejor dejarlo **null** y ser nosotros mismos los que nos encarguemos del posicionamiento de los objetos gráficos.
* **setVisible** Recibe por parámetro un booleano y por defecto esta en false, debemos cambiarlo a true. Esta configuración le indica al sistema que muestre la ventana en pantalla. Nótese que se deja de ultimas ya que primero se deben configurar la ventana y los objetos gráficos y finalmente mostrar en pantalla. Si no se deja de ultimas probablemente existan conflictos al mostrar componentes gráficos en la ventana.

Existen otros métodos de configuración en ventanas que podrían ser de utilidad como por ejemplo.

* **setUndecorated** Recibe por parámetro un booleano y si se entrega como **true** este quitara la barra que por defecto crea Java, sin embargo esto quitara los botones encargados de cerrar, minimizar o expandir la ventana, también quitara la propiedad de arrastre por lo que nosotros mismos tendremos que crear esas funcionalidades en el futuro.
* **getContentPane().setBackground** recibe por parámetro un objeto de tipo Color y le da el color de fondo a la ventana, se debe llamar al panel contenedor para poder ver reflejado el color de fondo, esto pasa unicamente con las clases **JFrame**

Cuando se quiera crear atributos estos deben ir al comienzo de la clase y generalmente serán privados como se hablo anteriormente. Es común que los atributos para una clase UI sean objetos gráficos por lo que muchas veces sera necesaria la importación de librerías que soporten la creación de estos objetos. Normalmente cuando se declaran estos objetos el editor de texto ayuda con la importación automática de estas librerías y se colocarán antes de iniciar la clase.

<figure><img src="https://camo.githubusercontent.com/22c364971c1260aa5a65778cfc8d544fbc2b39a62937a769518e0a7336baace5/68747470733a2f2f692e696d6775722e636f6d2f697149304a30512e706e67" alt=""><figcaption></figcaption></figure>

Clase VistaPrincipalTemplate con la declaración de objetos gráficos y la importación de sus respectivas librerías

Se creará un método solo para simular como es tener un método dentro de la clase sin embargo, este no tiene ningún propósito:

```
public void saludar(){
    String mensaje = "Hola Mundo";
    System.out.println(mensaje);
}
```

Se puede notar que el método tiene una variable llamada **mensaje** de tipo String, y es una variable por que solo será conocido por el scope de este método. La clase se vera así finalmente con sus respectivas partes.

<figure><img src="https://camo.githubusercontent.com/7a9a4b1a63cea1bd18785fc3c1c3f968168d91e01e46bd2427e414c6b874c7be/68747470733a2f2f692e696d6775722e636f6d2f324853307334492e706e67" alt=""><figcaption></figcaption></figure>

Clase VistaPrincipalTemplate final

## Resultado

El resultado obtenido hasta ahora después de la configuración inicial de la clase UI es la siguiente:

<figure><img src="https://camo.githubusercontent.com/2270329dbb9bea5ba709259212fbaa01358ee1b6540818ea6c1aef6312dd7356/68747470733a2f2f692e696d6775722e636f6d2f4d54514a47544f2e706e67" alt=""><figcaption></figcaption></figure>

## Actividades

* Enviá un correo a [cfpatinoc@correo.udistrital.edu.co](mailto:cfpatinoc@correo.udistrital.edu.co) con el motivo de que deseas tomar el curso, luego te enviare un formulario Diagnostico de Google para saber como te sientes de conocimientos antes de comenzar el curso.
* Realizar la elección de proyecto de curso y enviarla por medio del formulario de Google que será enviado a traves de correo electrónico.
* Realizar un ejemplo de una clase UI con explicación de cada parte.

## Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 2

### Objetivos

* Identificar las 4 etapas involucradas en la creación de objetos gráficos básicos para ser mostrados en pantalla en una vista.
* Reconocer los métodos principales para configurar propiedades de los objetos gráficos y así ser mostrados en la pantalla.
* Explorar el enfoque de posicionamiento por medio de pixeles sin el uso de manager de Layout.
* Comprender la forma de adición de objetos gráficos en distintos objetos contenedores como pueden ser Frames (Ventanas) o Paneles.

## Creación de objetos gráficos

En esta sesión se verán conceptos relacionados con la creación de objetos gráficos y para esto se proporciona los siguientes items principales:

* **Etapas de Creación de un Objeto Gráfico**.
* **Creación de objetos gráficos básicos**.

## Etapas de Creación de un Objeto Gráfico

Las etapas de la creación de objetos gráficos son 3 principales, sin embargo la segunda se compone a su vez de dos etapas:

* **Declaración**
* **Construcción**
  * **Ejemplificación**
  * **Configuración**
* **Adición / Agregación**

### **Declaración**

La declaración de un objeto gráfico consiste en indicarle al sistema que la clase donde se esta trabajando tendrá un atributo de algún tipo de estos objetos. Esta declaración se suele ubicar al inicio de la clase y tiene 3 partes, estas son:

* **Tipo Acceso:** El tipo de acceso a menudo será privado ya que son atributos de la clase y se debe respetar el principio de encapsulamiento como se discutió en la anterior clase.
* **Tipo de Objeto Gráfico:** Se refiere a la clase del objeto que vamos a crear (JButton, JTextField, JLabel, JPanel son algunos ejemplos) y la generación de estas clases casi siempre van a necesitar la importación de la librería que soporte la creación del objeto, estas por lo general se importan automáticamente gracias al IDE o editor de código.
* **Variable:** El nombre que el programador elija darle y sera esta el objeto por el cual se podrá acceder a sus métodos.

<figure><img src="https://camo.githubusercontent.com/bb9d8c7560c59c5378751639e2d9bdcc22c3cd70571785a9a695ead6eeb389d3/68747470733a2f2f692e696d6775722e636f6d2f6a415330367a672e706e67" alt=""><figcaption></figcaption></figure>

Declaración de dos objetos gráficos tipo JPanel con sus 3 partes

### **Ejemplificación**

La ejemplificación del objeto Gráfico hace parte de la etapa de construcción y consiste en darle un valor inicial al objeto y para esto es necesario llamar al constructor de la clase, **este paso es importante y sin él no es posible realizar la configuración**. Para esta sesión las etapas de ejemplificación, configuración y adición se realizarán dentro del **constructor** de la clase.

<figure><img src="https://camo.githubusercontent.com/977e6e48b3e656fd5979397226ac50a17f58e40c2d8568c44e00afd5e438f39a/68747470733a2f2f692e696d6775722e636f6d2f5a5a6b4e6532342e706e67" alt=""><figcaption></figcaption></figure>

Ejemplificación de dos objetos gráficos tipo JPanel

### **Configuración**

La configuración también hace parte de la etapa de construcción y es la etapa donde se llaman a los métodos proporcionados por la clase del objeto gráfico para darle propiedades gráficas y estas puedan verse en la pantalla. Por ahora solo se mostrara un ejemplo, sin embargo, mas adelante en esta sesión se explicará la función de cada uno de los métodos de configuración usados.

<figure><img src="https://camo.githubusercontent.com/c0d8525546674d0ed17b6bc59384db29b57b7affe28ca7a63131e8d572b2c318/68747470733a2f2f692e696d6775722e636f6d2f366446554964572e706e67" alt=""><figcaption></figcaption></figure>

Configuración de dos objetos gráficos justo después de haberse ejemplificado

### **Adición**

Para este tramo el objeto gráfico esta listo para ser mostrado, sin embargo, aun no se ha creado la solicitud para que este sea agregado en la ventana, para esto es necesario adicionarlo a su objeto padre o también llamado objeto contenedor, un objeto contenedor puede ser una ventana, un panel, canvas etc. En este ejemplo el objeto padre es la ventana. Con el método **add()** se puede añadir el objeto gráfico.

<figure><img src="https://camo.githubusercontent.com/c4b8d9b2d88526395bc71a280d5b8b2993d4f9942d75ea6e3e0d7f63af5cc755/68747470733a2f2f692e696d6775722e636f6d2f534764355664662e706e67" alt=""><figcaption></figcaption></figure>

Adición de dos objetos gráficos una vez se hayan declarado, ejemplificado y configurado.

Puede verse en la anterior imagen que la forma de añadir elementos gráficos en la ventana consiste en llamar **this.add()** ya que la clase extiende de un JFrame. La palabra clave **this** hace referencia a que se esta llamando a la misma clase donde se esta codificando. Sin embargo pueden existir algunos objetos gráficos que no queremos añadir directamente en la ventana, se podrían añadir en un panel por ejemplo. A continuación se muestra como se podría hacer esto.

<figure><img src="https://camo.githubusercontent.com/671964009def5ecb024016553c40f7b5fe9fb45d1ca55bb92fe48ed5f20381cb/68747470733a2f2f692e696d6775722e636f6d2f4c5646624e59582e706e67" alt=""><figcaption></figcaption></figure>

Adición de objetos gráficos dentro de Paneles

## Creación de objetos gráficos básicos.

En esta sección se verá la forma de crear objetos gráficos para ser mostrados en pantalla, basado en los 4 pasos que se acabaron de explicar. Los objetos explicados a continuación serán:

* **JPanel**
* **JLabel**
* **JTextField**
* **JPasswordField**
* **JComboBox**
* **JButton**
* **JCheckBox**
* **ButtonGroup**
* **JRadioButton** (Se explicara brevemente su creación ya que es similar a la de checkBox)
* **JTextArea** (Se explicara brevemente su creación ya que es similar a la de un TextField)

### Antes de comenzar

Recordando la sesión 1, se crea una nueva clase llamada **LoginTemplate** y se configura la ventana.

<figure><img src="https://camo.githubusercontent.com/5ca81fbb5136f04cbd4ed6822b94f4b974cb24195aae6dcd36e7e52882449081/68747470733a2f2f692e696d6775722e636f6d2f4e4b69737050582e706e67" alt=""><figcaption></figcaption></figure>

Clase de login de usuario

Por otro lado en la clase principal se va a llamar a esta clase dentro del hilo EDT:

```
public static void main(String[] args) {
  Runnable runApplication = new Runnable() {
    public void run(){
      LoginTemplate login = new LoginTemplate();
      login.getClass();
    }
  };
  SwingUtilities.invokeLater(runApplication);
}
```

### JPanel

Los Paneles son la mejor forma de identificar partes de una ventana y modularizar diferentes secciones de esta y agrupando varios objetos gráficos que comparten un contexto.

Para el ejemplo de esta sesión se van a crear 2 paneles (los mismos que se han creado para el ejemplo de las etapas de la creación de objetos gráficos). Un punto importante a resaltar y que se toma como un estándar del curso es que en la declaración de los paneles las variables (objetos) empiezan con una p minúscula seguido del nombre arbitrario de la variable, ahora se explicarán los métodos de configuración.

```
pIzquierda.setSize(600, 500);
pIzquierda.setLocation(0, 0);
pIzquierda.setBackground(Color.BLUE);
```

* **setSize:** Recibe por parámetros un par de enteros y definen el tamaño del panel, siendo el ancho el primer parámetro y el alto el segundo.
* **setLocation:** Recibe por parámetros un par de enteros y definen la posición del panel, la posición en el eje x es el primer parámetro y la posición en el eje y el segundo.
* **setBackground:** Recibe por parámetro un _objeto decorador_ de tipo Color y define el color de fondo del panel.

Los métodos **setSize** y **setLocation** pueden ser reemplazados por el método:

* **setBounds:** Recibe por parámetros 4 números enteros de los cuales los dos primeros representan la posición y los dos últimos el tamaño **(x, y, ancho, alto)**

Hasta el momento la ventana se ve así:

<figure><img src="https://camo.githubusercontent.com/f24aab36c7c970338146e99a34fd456896d8ecff8b71c7b05ec1f6678aed20ee/68747470733a2f2f692e696d6775722e636f6d2f38714e6c77464a2e706e67" alt=""><figcaption></figcaption></figure>

Interfaz login de usuario con 2 paneles

Por ahora todo luce bien, sin embargo hay una propiedad crucial que no se explico a propósito, más adelante se va a recalcar. Los colores se configuraron para verificar la existencia de los paneles en la ventana, por ahora cambiará el color de fondo del panel **pDerecha** por un color blanco.

```
pDerecha.setBackground(Color.WHITE);
```

El código se ve asi:

<figure><img src="https://camo.githubusercontent.com/5cae1295fe0f7211b599ec5e964bfe5f520ddb8516f3a94845995b9250da96d8/68747470733a2f2f692e696d6775722e636f6d2f687235624944782e706e67" alt=""><figcaption></figcaption></figure>

Clase de login de usuario

Cabe resaltar que la configuración de la ventana se suele colocar de ultimas, si se deja en otros lados probablemente el programa tendrá problemas en mostrar la interfaz. Sobretodo la ultima linea de código **setVisible** debe ser la ultima en llamarse, ya que primero se deben agregan todos los elementos en la ventana para luego ser mostrada.

### JLabel

Los label en las interfaces gráficas representan textos o imágenes que se quieren mostrar en pantalla y que el usuario no podrá cambiar, normalmente son usados para dar indicaciones, títulos, subtítulos, iconos, logos etc.

Se puede empezar colocando un título en la interfaz, para esto se crea un JLabel (Realizando los 4 pasos anteriores)Ñ

* **Declaración**

```
// Al inicio de la clase
private JLabel lTituloApp;
```

La variable (objeto) que se coloca para los label empezarán con l minúscula seguido del nombre de la variable.

* **Ejemplificación**

```
// Dentro del constructor
lTituloApp = new JLabel("Login de Usuario");
```

Se puede notar que cuando se ejemplifica el objeto de tipo JLabel este puede recibir por parámetro en el constructor un String que representa el texto que se mostrará en pantalla, esto no es obligatorio, se puede crear con parámetros vacíos y mas adelante llamar al método **setText()** que también recibe un String y cumple la misma función, pero esta es una buena forma de ahorrar código.

* **Configuración**

```
// Dentro del constructor
lTituloApp.setBounds(100, 20, 220, 30);
lTituloApp.setForeground(Color.WHITE);
```

Puede notarse que en esta ocasión se utiliza el método **setBounds** en lugar de **setSize y setLocation** por separado, en realidad las dos formas son correctas y habrán casos donde se necesita hacer de una forma u otra. A parte tenemos otro método:

* **setForeground:** Recibe por parámetro un _objeto decorador_ de tipo Color y representa el color de la fuente del JLabel.
* **Adición**

```
// Dentro del constructor
pIzquierda.add(lTituloApp);
```

Puede observarse que este objeto se añadirá al panel de la izquierda y no en la ventana directamente. Ahora bien si se ejecuta la aplicación para ver el label es posible notar que este no se posiciono exactamente donde se configuro, ¿no se ve muy claro? ahora se hará un pequeño cambio. Posicionando el objeto 100 pixeles más hacia abajo.

```
lTituloApp.setBounds(100, 120, 200, 30);
```

Una vez la aplicación se ejecuta de nuevo el Label esta en la misma posición que antes.

**¿Por que esta pasando esto?**

Esto se debe al manager de posicionamiento de Java que por defecto maneja un Layout predeterminado, el cual tratará de dejar los objetos en la parte superior central de la ventana, cuando esta tiene dos o mas objetos tratará de dividir el panel de forma equitativa para posicionar los objetos de forma centrada. En muchas ocasiones esto no es lo que se busca. Para esto se debe configurar la ventana y los paneles para que deje nula esa propiedad y **sea el desarrollador quien posicione los objetos mediante el enfoque de posicionamiento en pixeles.**

```
// Se coloca en su respectiva configuración
pDerecha.setLayout(null);
pIzquierda.setLayout(null);
setLayout(null); // configuración de la ventana
```

Una vez corre la aplicación se observa como el Label esta en los pixeles indicados. Los 100 pixeles de mas en el eje Y se colocaron como prueba, se dejará la posición como se dejo originalmente.

```
lTituloApp.setBounds(100, 20, 200, 30);
```

También se va a añadir 3 label mas:

* **Declaración:**

```
// Al inicio de la clase
private JLabel lTituloApp, lEslogan, lTituloLogin, lNotificaciones;
```

* **Ejemplificación, configuración y adición**

```
// Dentro del constructor
lEslogan = new JLabel("Te ayudamos en todo");
lEslogan.setSize(130, 20);
lEslogan.setLocation((pDerecha.getWidth() - lEslogan.getWidth()) / 2, 40);
lEslogan.setForeground(Color.DARK_GRAY);
lEslogan.setHorizontalAlignment(SwingConstants.CENTER);
pDerecha.add(lEslogan);

lTituloLogin = new JLabel("Registra tus Datos");
lTituloLogin.setSize(150, 30);
lTituloLogin.setLocation((pDerecha.getWidth() - lTituloLogin.getWidth()) / 2, 60);
lTituloLogin.setForeground(Color.DARK_GRAY);
lTituloLogin.setHorizontalAlignment(SwingConstants.CENTER);
pDerecha.add(lTituloLogin);

lNotificaciones = new JLabel("¿Recibir Notificaciones?");
lNotificaciones.setSize(140, 20);
lNotificaciones.setLocation((pDerecha.getWidth() - lNotificaciones.getWidth()) / 2, 370);
lNotificaciones.setForeground(Color.DARK_GRAY);
lNotificaciones.setHorizontalAlignment(SwingConstants.CENTER);
pDerecha.add(lNotificaciones);
```

En el anterior código se resalta la importancia de cuando usar el enfoque de tamaño y posicionamiento por separado. Por ejemplo cuando un elemento se quiere colocar en el centro con respecto ya sea a su panel padre o a la ventana. Para esto se debe hacer un calculo que es:

* **(Ancho de panel - Ancho Objeto)/ 2**

El ancho de un objeto gráfico puede conocerse grácias al método **getWidth**. Sin embargo, para conocer el ancho del objeto es necesario proporcionarle la propiedad de tamaño previamente usando **setSize**. Si se usa **setBounds** al pedir los 4 datos al tiempo este no tendrá aun un ancho definido aun y no podrá calcularse la anterior operación.

Por otro lado los Label por defecto centran el texto en el eje vertical, pero en el eje horizontal el texto esta colocado por defecto en la parte izquierda o inicial del label, en este caso se quiere que el texto de forma interna este centrado con respecto al tamaño del label, para esto se usa el método:

* **setHorizontalAlignment:** Recibe por parámetro un objeto tipo **SwingConstants** y le da la dirección de la posición horizontal del texto. Si no se llama por defecto el texto estará posicionado en la parte izquierda, sus otras opciones principales son **CENTER** y **RIGHT**. Aunque existen más opciones, estas configuran la posición con respecto al eje Y, y no son necesarias en este método.

La ventana se esta viendo así:

<figure><img src="https://camo.githubusercontent.com/66b7759a1f82e04dd5f0ad962820d9c8b33ce32e0104913a321f41e4141dbf88/68747470733a2f2f692e696d6775722e636f6d2f576539643331662e706e67" alt=""><figcaption></figcaption></figure>

Interfaz login de usuario con paneles y labels

### JTextField

Los TextField son cajas de texto donde el usuario va poder ingresar información importante que la aplicación necesita de él. Muchas veces estará dentro de formularios donde se pide información, otras veces servirán como medio para realizar una consulta especifica, para modificar información etc.

Para este caso se usará un JTextField para que el cliente pueda escribir el nombre de su usuario.

* **Declaración**

```
// Al inicio de la clase
private JTextField tNombreUsuario;
```

La variable (objeto) que se coloca para los textField empezará con t minúscula seguido del nombre de la variable.

* **Ejemplificación**

```
// Dentro del constructor
tNombreUsuario = new JTextField("Nombre Usuario");
```

Al igual que con los Label estos pueden recibir un String por parámetro desde el constructor, este funciona como **placeholder** pero necesita de una configuración adicional que en esta clase no se verá. De nuevo no es obligatorio colocar el String inicial.

* **Configuración**

```
// Dentro del constructor
tNombreUsuario.setSize(260, 40);
tNombreUsuario.setLocation((pDerecha.getWidth() - tNombreUsuario.getWidth()) / 2, 120);
tNombreUsuario.setForeground(Color.DARK_GRAY);
tNombreUsuario.setBackground(Color.WHITE);
tNombreUsuario.setCaretColor(Color.BLUE);
tNombreUsuario.setHorizontalAlignment(SwingConstants.CENTER);
```

Como los anteriores objetos gráficos, este tiene algunas configuraciones ya vistas, mas una nueva propiedad:

* **setCaretColor:** recibe por parámetro un **objeto decorador** de tipo Color y representa el color del Caret (la linea que parpadea indicando la posición de texto para escribir).
* **setHorizontalAlignment:** Por defecto los TextField van a ubicar el texto en la parte izquierda pero en caso de que se quiera colocar el texto a en el centro o a la derecha se puede utilizar este método.
* **Adición**

```
// Dentro del constructor
pDerecha.add(tNombreUsuario);
```

### JPasswordField

Los JPasswordField son campos de texto donde el usuario va a escribir información confidencial, esto implica que por cuestiones de seguridad, la información proporcionada por el cliente no debe ser mostrada en pantalla. Como su nombre lo indica este objeto gráfico muchas veces se utiliza para el ingreso de contraseñas.

* **Declaración**

```
// Al inicio de la clase
private JPasswordField tClaveUsuario;
```

La variable (objeto) que se coloca para los JPasswordField empezará con t minúscula seguido del nombre de la variable.

* **Ejemplificación**

```
// Dentro del constructor
tClaveUsuario = new JPasswordField("Clave Usuario");
```

* **Configuración**

```
// Dentro del constructor
tClaveUsuario.setSize(260, 40);
tClaveUsuario.setLocation((pDerecha.getWidth() - tClaveUsuario.getWidth()) / 2, 240);
tClaveUsuario.setForeground(Color.DARK_GRAY);
tClaveUsuario.setCaretColor(Color.BLUE);
tClaveUsuario.setHorizontalAlignment(SwingConstants.CENTER);
```

* **Adición**

```
// Dentro del constructor
pDerecha.add(tClaveUsuario);
```

Se puede notar que una vez se ejecuta la aplicación en el campo de la clave del usuario este saldrá en forma de puntos escondiendo la información que el usuario coloque allí.

### JComboBox

Muchas veces el usuario tendrá que escoger entre varias opciones fijas que la aplicación le da a seleccionar, normalmente vista en forma de listas. Para eso es posible usar un JComboBox donde el usuario puede elegir opciones predeterminadas.

En este caso se usará un ComboBox para escoger el tipo de usuario:

* **Declaración**

```
// Al inicio de la clase
private JComboBox cbTipoUsuario;
```

La variable (objeto) que se coloca para los JComboBox empezará con cb minúscula seguido del nombre de la variable.

* **Ejemplificación**

```
// Dentro del constructor
cbTipoUsuario = new JComboBox();
```

* **Configuración**

```
// Dentro del constructor
cbTipoUsuario.addItem("Cliente");
cbTipoUsuario.addItem("Cajero");
cbTipoUsuario.addItem("Administrador");
cbTipoUsuario.setSize(220, 30);
cbTipoUsuario.setLocation((pDerecha.getWidth() - cbTipoUsuario.getWidth()) / 2, 185);
cbTipoUsuario.setForeground(Color.DARK_GRAY);
cbTipoUsuario.setBackground(Color.WHITE);
((JLabel) cbTipoUsuario.getRenderer()).setHorizontalAlignment(SwingConstants.CENTER);
```

A parte de las configuraciones que ya se vieron antes, en este caso existen dos particularidades:

* **addItem:** recibe por parámetro un String y lo admite como opción a seleccionar por el usuario.
* **getRenderer, setHorizontalAlignment:** Si se quieren centrar los elementos dentro de un ComboBox, esto no se podrá de forma directa. Cada una de las opciones dentro del ComboBox son tratados como Labels y para obtener su valor es necesario pedirle al ComboBox los elementos con el método **getRenderer**. Una vez obtenemos los elementos (JLabels) es necesario hacer un **Cast** de objeto para asi obtener las configuraciones propias de un JLabel **((JLabel) cbTipoUsuario.getRenderer())** de lo contrario al poner . (punto) para escribir los métodos de configuración no se vera la opción **setHorizontalAlignment**.
* **Adición**

```
// Dentro del constructor
pDerecha.add(cbTipoUsuario);
```

### JButton

Los botones son la forma mas común en la que un usuario podrá interactuar con las interfaces gráficas. Estos botones generan acciones que el usuario puede activar al dar Click sobre estos, entre algunas opciones, puede estar: el envío de información, traer información, abrir otras secciones, cerrar la aplicación etc.

* **Declaración**

```
// Al inicio de la clase
private JButton bEntrar;
```

La variable (objeto) que se coloca para los JButton empezará con b minúscula seguido del nombre de la variable.

* **Ejemplificación**

```
// Dentro del constructor
bEntrar = new JButton("Entrar");
```

Un Botón puede recibir por parámetro en el constructor un String que representa el texto, de nuevo se puede realizar también mediante el método **setText**.

* **Configuración**

```
// Dentro del constructor
bEntrar.setSize(250, 45);
bEntrar.setLocation((pDerecha.getWidth() - bEntrar.getWidth()) / 2, 300);
bEntrar.setBackground(Color.BLUE);
bEntrar.setForeground(Color.WHITE);
bEntrar.setFocusable(false);
```

A parte de las configuraciones que ya se vieron antes, en este caso existen dos particularidades:

* **setHorizontalAlignment:** Por defecto los botones van a ubicar el texto centrado pero en caso de que se quiera colocar el texto a la izquierda o a la derecha se puede utilizar este método.
* **setFocusable:** Recibe por parámetro un booleano que por defecto esta en true, si se cambia la configuración a false, se va a quitar el cuadro por defecto que rodea al texto del botón una vez se oprima click.

<figure><img src="https://camo.githubusercontent.com/618e195d597ef20b8c94f5a0943af78a396c145f3c8b3db1dc45e71e2d517fba/68747470733a2f2f692e696d6775722e636f6d2f564762486a30492e706e67" alt=""><figcaption></figcaption></figure>

Botón con SetFocusable(True)

<figure><img src="https://camo.githubusercontent.com/2a5ffd93a5383c3196289dea01f33f0b3b11cd352ced6ab19a929c2f24b39916/68747470733a2f2f692e696d6775722e636f6d2f584f6b503156672e706e67" alt=""><figcaption></figcaption></figure>

Botón con SetFocusable(False)

* **Adición**

```
// Dentro del constructor
pDerecha.add(bEntrar);
```

Hasta el momento la interfaz se ve asi:

<figure><img src="https://camo.githubusercontent.com/22013e19dc7815d4bea69a22faaa9258b6ea395ef9d1f8e984a0e88316b71b08/68747470733a2f2f692e696d6775722e636f6d2f495772374d6f682e706e67" alt=""><figcaption></figcaption></figure>

Interfaz login de usuario con los nuevos objetos añadidos

Se van añadir 5 botones más, utilizando lo aprendido hasta el momento:

* **Declaración**

```
// Al inicio de la clase
private JButton bEntrar, bCerrar, bRegistrarse, bOpcion1, bOpcion2, bOpcion3;
```

* **Ejemplificación, configuración y adición**

```
// Dentro del constructor
bCerrar = new JButton("X");
bCerrar.setBounds(330, 10, 45, 30);
bCerrar.setFocusable(false);
bCerrar.setBackground(Color.BLUE);
bCerrar.setForeground(Color.WHITE);
pDerecha.add(bCerrar);

bRegistrarse = new JButton("Registrarse");
bRegistrarse.setBounds(230, 420, 145, 35);
bRegistrarse.setFocusable(false);
bRegistrarse.setBackground(Color.BLUE);
bRegistrarse.setForeground(Color.WHITE);
pDerecha.add(bRegistrarse);

bOpcion1 = new JButton();
bOpcion1.setBounds(10, 220, 30, 20);
pIzquierda.add(bOpcion1);

bOpcion2 = new JButton();
bOpcion2.setBounds(10, 250, 30, 20);
pIzquierda.add(bOpcion2);

bOpcion3 = new JButton();
bOpcion3.setBounds(10, 280, 30, 20);
pIzquierda.add(bOpcion3);
```

y la interfaz se ve ahora así:

<figure><img src="https://camo.githubusercontent.com/ceb080768b38050b931837c2336640042a884ab0029c37e326ff10d6ea211a26/68747470733a2f2f692e696d6775722e636f6d2f546b43483962452e706e67" alt=""><figcaption></figcaption></figure>

Interfaz login de usuario, con adición de mas botones

### JCheckButton

Los CheckButton normalmente son usados para cubrir estados de varias opciones, puede utilizar varios enfoques:

* Elección multiple de opciones
* Elección de una sola opción.
* **Declaración**

```
// Al inicio de la clase
private JCheckBox checkSi, checkNo;
```

La variable (objeto) que se coloca para los JCheckButton empezará con check en minúscula seguido del nombre de la variable.

* **Ejemplificación**

```
// Dentro del constructor
checkSi = new JCheckBox("Si");
checkNo = new JCheckBox("No");
```

* **Configuración**

```
// Dentro del constructor
checkSi.setSize(45, 25);
checkSi.setFocusable(false);
checkSi.setBackground(Color.WHITE);
checkSi.setLocation((pDerecha.getWidth() - checkSi.getWidth()) / 2 - 15, 345);

checkNo.setSize(45, 25);
checkNo.setFocusable(false);
checkNo.setBackground(Color.WHITE);
checkNo.setLocation((pDerecha.getWidth() + checkNo.getWidth()) / 2 - 15, 345);
```

* **Adición**

```
// Dentro del constructor
pDerecha.add(checkSi);
pDerecha.add(checkNo);
```

En la aplicación se quiere tomar el enfoque de única opción, sin embargo al correr el app, es posible notar que se pueden seleccionan las dos opciones al tiempo.

[![](https://camo.githubusercontent.com/5b634b923cefb491633ae97ab749bc6c8b8badcee86e74a758b3ea9053ab27e7/68747470733a2f2f692e696d6775722e636f6d2f574f556e7251732e706e67)](https://camo.githubusercontent.com/5b634b923cefb491633ae97ab749bc6c8b8badcee86e74a758b3ea9053ab27e7/68747470733a2f2f692e696d6775722e636f6d2f574f556e7251732e706e67)

CheckBox con múltiple opción

Para obtener el enfoque de única opción se debe utilizar el siguiente objeto.

### ButtonGroup

Este es un objeto gráfico auxiliar que nos ayuda a agrupar objetos en un contexto y realizar acciones con esta agrupación. Es usado en la mayoría de casos para realizar un enfoque de única respuestas con los objetos de CheckButton o RadioButton. Este al ser un objeto Auxiliar (no tiene representación gráfica) no será necesario adicionarlo en ningún componente.

* **Declaración**

```
// Al inicio de la clase
private ButtonGroup grupo;
```

La variable (objeto) que se coloca para los ButtonGroup empezará con grupo en minúscula seguido del nombre de la variable. En este caso al haber solo un ButtonGroup solo pondremos la palabra clave.

* **Ejemplificación**

```
// Dentro del constructor
grupo = new ButtonGroup();
```

* **Configuración**

```
// Dentro del constructor
grupo.add(checkSi);
grupo.add(checkNo);
```

En la configuración es donde se van añadir los botones que pertenecen a un mismo contexto para que se pueda seleccionar una única opción. Al correr la aplicación se puede comprobar lo anterior dicho.

### JRadioButton

Los RadioButton cumplen la misma función que los checkButton, es cuestión del desarrollador cual de los dos quiera usar. De nuevo, tienen los enfoques de múltiples opciones o única opción utilizando un buttonGroup.

En este caso la interfaz no tendrá RadioButtons pero a continuación se muestra un ejemplo para su creación.

* **Declaración**

```
// Al inicio de la clase
private JRadioButton rbOpcion1, rbOpcion2;
```

La variable (objeto) que se coloca para los JRadioButton empezará con rb en minúscula seguido del nombre de la variable.

* **Ejemplificación**

```
// Dentro del constructor
rbOpcion1 = new JRadioButton("opcion1");
rbOpcion2 = new JRadioButton("opcion2");
```

* **Configuración**

```
// Dentro del constructor
rbOpcion1.setBounds(50, 400, 120, 30);
rbOpcion2.setBounds(200, 400, 120, 30);
```

* **Adición**

```
// Dentro del constructor
pIzquierda.add(rbOpcion1);
pIzquierda.add(rbOpcion2);
```

### JTextArea

Un objeto gráfico textArea expande un poco el concepto de los textField ya que soporta una mayor cantidad de texto y esta diseñado para recibir grandes cantidades de texto. A continuación se muestra una breve explicación de su creación ya que esta tampoco hará parte de esta interfaz:

* **Declaración**

```
// Al inicio de la clase
private JTextArea taSugerencias;
```

La variable (objeto) que se coloca para los JTextArea empezará con ta en minúscula seguido del nombre de la variable.

* **Ejemplificación**

```
// Dentro del constructor
taSugerencias = new JTextArea("Escribe algo...");
```

* **Configuración**

```
// Dentro del constructor
taSugerencias.setBounds(185, 180, 230, 140);
```

* **Adición**

```
// Dentro del constructor
pIzquierda.add(taSugerencias);
```

Si se añaden estos componentes la interfaz se vería algo así:

<figure><img src="https://camo.githubusercontent.com/400d6105d5390b8331db609933e7cdc8c2900347b5820780f1ee26ff4d35b2b3/68747470733a2f2f692e696d6775722e636f6d2f6673317037494e2e706e67" alt=""><figcaption></figcaption></figure>

Interfaz login de usuario con adición de JTextArea y JRadioButton

Sin embargo como se dijo anteriormente estos dos objetos gráficos no harán parte de esta interfaz asi que por ahora se comentarán estas partes en el código.

## Resultado

<figure><img src="https://camo.githubusercontent.com/b1ca41be6c4c65edb8ee94903b677b4293ce7c56a589e58fd7a83071983bb0e5/68747470733a2f2f692e696d6775722e636f6d2f41786e714447322e706e67" alt=""><figcaption></figcaption></figure>

Interfaz login de usuario, resultado Final

Este es el resultado del Login de usuario, hasta el momento se aprendió la configuración de objetos básicos y como mostrarlos en pantalla. En la siguiente sesión se verá la creación de objetos decoradores para hacer que la interfaz se vea mucho mas agradable a la vista del usuario.

## Actividades

Realizar un Login diferente al propuesto en clase, el login de usuario que se vaya a realizar sera parte del proyecto final asi que puede ser buena idea pensar como sería el login de acuerdo a la aplicación escogida como proyecto.

## Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 3

### Objetivos

* Identificar las etapas involucradas en la creación de objetos decoradores y como incorporarlos en objetos gráficos para dar un mejor aspecto la interfaz Gráfica.
* Reconocer la importancia de los objetos decoradores y el papel que toman para que una interfaz gráfica sea más amigable con los usuarios.
* Explorar cada uno de los objetos decoradores que ofrece Java Swing y el rol de cada uno para una personalización de las Interfaces gráficas.

## Antes de comenzar

#### **Recordatorio**

Recordando la sesión anterior, se había creado una interfaz gráfica para un Login de usuario. El resultado fue el siguiente:

<figure><img src="https://camo.githubusercontent.com/44783559100fc0e3027b523c6789f527e504f2326bee1f2b1a35bcad919a1285/68747470733a2f2f692e696d6775722e636f6d2f457078647666772e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario creado en la sesión anterior

## Objetos Decoradores

En esta clase se va a explorar la forma de crear e incorporar objetos decoradores para que el login de usuario tenga un mejor aspecto. Para esto se van a ver estos items principales:

* **Etapas de creación de Objetos Decoradores**
* **Creación de Objetos Decoradores**

## Etapas de creación de Objetos Decoradores

Los objetos decoradores también tienen ciertas etapas en su creación, aunque estas pueden variar un poco dependiendo de los casos, las etapas más comunes son:

### Declaración

La declaración de un objeto decorador consiste en indicarle al sistema que la clase donde se esta trabajando tendrá un atributo de algún tipo de estos objetos. La declaración tiene 3 partes, estas son:

* **Tipo Acceso:** El tipo de acceso sera a menudo privado ya que son atributos de la clase y se debe respetar el principio de encapsulamiento como se discutió en la primera clase.
* **Tipo de Objeto Decorador:** Se refiere a la clase del objeto que se va a crear (Color, Font, ImageIcon, Cursor son algunos ejemplos) y la generación de estas clases casi siempre van a necesitar la importación de la librería que soporte la creación del objeto, estas importaciones a menudo se hacen automáticamente dependiendo del IDE o editor de código.
* **Variable:** El nombre que el programador elija darle y sera esta el objeto por el cual se podrá acceder a sus métodos.

<figure><img src="https://camo.githubusercontent.com/86108d8f1e20c7460dbcb84d112c71e03d86a2b0ad11c7f3479249d87eff36ff/68747470733a2f2f692e696d6775722e636f6d2f637950497578562e706e67" alt=""><figcaption></figcaption></figure>

Declaración de un objeto decorador

### Ejemplificación

La ejemplificación de un objeto decorador consiste en darle un valor inicial al objeto y para esto es necesario llamar al constructor de la clase, **Cuando se realiza la ejemplificación de un objeto decorador al mismo tiempo se realiza la configuración del objeto**. Esto quiere decir que la ejemplificación va a variar según el tipo de objeto decorador que se este creando. Para esta sesión la ejemplificación se realizará dentro del **constructor** de la clase y serán los primeros objetos solo por debajo del método **super** en caso de que exista.

<figure><img src="https://camo.githubusercontent.com/bddc82d0a81cec52b22f5f5e90fc213ab96cf6cdb4b6dc69f4b57aac9eec22a8/68747470733a2f2f692e696d6775722e636f6d2f527770506d53412e706e67" alt=""><figcaption></figcaption></figure>

Ejemplificación de un objeto decorador

### Incorporación

Un objeto decorador no puede ser agregado directamente a la interfaz Gráfica, necesita ser incorporado a un objeto gráfico para que sea visible. La incorporación se realiza en la etapa de **configuración** de un objeto gráfico cuando se llama algún método relacionado con el uso del objeto decorador en cuestión, esto puede ser por ejemplo para dar un color de fondo, color de letra, estilo de letra o borde a un objeto gráfico. Por esta razón en lugar de adicionarse mas bien se incorporan a un objeto gráfico.

<figure><img src="https://camo.githubusercontent.com/c0894af18c253a8f8ac56a82e58bac0959c3c30adb4b51d7103fbac03585b018/68747470733a2f2f692e696d6775722e636f6d2f675773447936492e706e67" alt=""><figcaption></figcaption></figure>

Incorporación de un objeto decorador

## Creación de Objetos Decoradores

En esta sección se verá la forma de crear objetos Decoradores para ser incorporados, basándose en las 3 etapas que se acabaron de explicar. Los objetos a explorar a continuación serán:

* **Color**
* **Font**
* **Cursor**
* **Border**
* **ImageIcon**

## Color

Estos objetos decoradores cumplen la función de proporcionar color a los objetos gráficos en pantalla.

Existen varias formas para crear colores en Java y a continuación se mencionan las mas importantes:

### Colores por defecto en Java

Java trae por defecto una paleta de colores y para poder ser usados solo basta con llamar la clase **Color** y al digitar . (punto) se desplegará una variedad de colores. Es importante que la librería que soporta la creación de los colores sea importada, esto se hace por defecto dependiendo del editor que se maneje. Cuando se usan los colores por defecto de Java **no es necesario realizar la declaración ni la ejemplificación del objeto**.

<figure><img src="https://camo.githubusercontent.com/6f6c1a7ab5d2fe435804ff98a36aea3044d56c8087513a1696ed5b88b3efca72/68747470733a2f2f692e696d6775722e636f6d2f66316c3964644d2e706e67" alt=""><figcaption></figcaption></figure>

Paleta de colores por defecto de Java

### Colores Personalizados

Muchas veces se quieren colores personalizados que Java no trae por defecto y para esto es necesario realizar la creación del objeto decorador de tipo Color:

* **Declaración**

```
// Al inicio de la clase
private Color colorPrincipal, colorGrisOscuro;
```

La variable (objeto) que se coloca para los objetos Color empezará con color en minúscula seguido del nombre de la variable. También es recomendable no llamar a los colores con el color a representar a menos de que sea un color demasiado especifico, de esta forma si existe un color que esta en muchas partes del proyecto y cambia por algún motivo, el nombre **colorPrincipal** sigue teniendo valides. Algunas excepciones pueden ser colores en escala de grises o colores con un propósito muy especifico.

* **Ejemplificación**

```
// Dentro del constructor
colorPrincipal = new Color(60, 78, 120);
colorGrisOscuro = new Color(80, 80, 80);
```

Se puede observar que la notación para la configuración de un color esta basado en la creación de colores mediante el sistema RGB (Red, Green, Blue) proporcionando valores enteros que pueden ir desde 0 hasta 255. generando así la creación de una gran posibilidad de colores.

* **Incorporación**

```
// Dentro del constructor
tNombreUsuario.setForeground(colorPrincipal);
tNombreUsuario.setBackground(Color.WHITE);
tNombreUsuario.setCaretColor(colorGrisOscuro);
```

En el anterior código se ve reflejada la incorporación de varios objetos de tipo Color para un TextField, siendo algunos de estos creados por el desarrollador y otros que vienen por defecto en Java.

### Colores con Transparencia

Java también admite la creación de objetos RGBA los cuales agregan un nuevo canal (Alfa) para configurar la transparencia del color con valores enteros que van desde 0 (siendo un color totalmente transparente) hasta 255 (siendo un color totalmente solido). Los pasos para la creación de ese tipo de colores es la misma que los colores personalizados que se acaban de crear.

<figure><img src="https://camo.githubusercontent.com/15f4bc9b6d9950127f86db73403346658b032edb25e141592cf41009c3da0ab8/68747470733a2f2f692e696d6775722e636f6d2f5150616f62674b2e706e67" alt=""><figcaption></figcaption></figure>

Color oscuro con transparencia casi total

### Incorporación de los colores personalizados.

A continuación se muestran las partes del código donde se incorporan los colores personalizados creados anteriormente a los objetos gráficos. Cabe destacar que aunque aquí se ven todas las incorporaciones juntas, en el código estas incorporaciones se hacen en orden en la respectiva configuración de su objeto gráfico.

```
// En la respectiva configuración del objeto gráfico
lEslogan.setForeground(colorGrisOscuro);

lTituloLogin.setForeground(colorGrisOscuro);

lNotificaciones.setForeground(colorGrisOscuro);

tNombreUsuario.setForeground(colorPrincipal);
tNombreUsuario.setCaretColor(colorGrisOscuro);

tClaveUsuario.setForeground(colorPrincipal);
tClaveUsuario.setCaretColor(colorGrisOscuro);

cbTipoUsuario.setForeground(colorPrincipal);

bEntrar.setBackground(colorPrincipal);
bEntrar.setForeground(Color.WHITE);

bRegistrarse.setBackground(colorPrincipal);
bRegistrarse.setForeground(Color.WHITE);
```

Hasta el momento la Interfaz Gráfica se ve asi:

<figure><img src="https://camo.githubusercontent.com/40ec205a2844ca81d01b5935a1ea861df5da03fff6d418f2f72971cc4173485e/68747470733a2f2f692e696d6775722e636f6d2f75796e743867562e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario con incorporación de colores

## Font

Un objeto decorador Font se encarga de darle características gráficas a los textos vistos en la interfaz gráfica, para agregar dichas características un objeto Font se encarga de proporcionar 3 elementos:

* **Tipografía:** Da un nuevo aspecto a la letra de acuerdo a la tipografía seleccionada, la tipografía por defecto depende del sistema operativo que corra la aplicación. Para que una tipografía diferente pueda verse reflejada en la interfaz debe estar instalada previamente en el sistema operativo, una solución a esto es registrar la fuente dentro del **GraphicsEnvironment** de Java (más adelante se habla de este punto).
* **Estilo letra:** Da un estilo a la letra de acuerdo a la configuración dada, esta podría ser por ejemplo **negrilla** _cursiva_ subrayado etc.
* **Tamaño de la fuente:** Le da el tamaño de la fuente dependiendo del numero entero que reciba como parámetro.

A continuación se crean los objetos Font que se utilizarán para el Login de usuario:

* **Declaración**

```
// al inicio de la clase
private Font fontTPrincipal, fontTitulo, fontSubtitulo;
```

La variable (objeto) que se coloca para los objetos Font empezará con font en minúscula seguido del nombre de la variable.

* **Ejemplificación**

```
fontTPrincipal = new Font("Rockwell Extra Bold", Font.PLAIN, 20);
fontTitulo = new Font("Calibri (Cuerpo)", Font.BOLD, 17);
fontSubtitulo = new Font("Forte", Font.PLAIN, 13);
```

Se puede observar que al momento de ejemplificar el objeto se realiza su respectiva configuración desde el constructor pasando los 3 parámetros ya mencionados con anterioridad. Algunos puntos a resaltar son:

* La tipografía dada debe estar en comillas.
* Los diferentes estilos se pueden observar llamando a la clase Font y poniendo un . (punto).
* El tamaño de la letra será siempre un numero entero.

<figure><img src="https://camo.githubusercontent.com/225b5f593181b7e93d296fcadf9d0d1ffc060303f119fe957204cd7e62221b08/68747470733a2f2f692e696d6775722e636f6d2f426d375a5750412e706e67" alt=""><figcaption></figcaption></figure>

Ejemplificación de objetos decoradores tipo Font

* **Incorporación** A continuación se muestran las partes del código donde se incorporan los objetos decoradores Font. Recordar que aquí se muestran seguidas, sin embargo en el código estas incorporaciones se hacen en orden en la respectiva configuración de su objeto gráfico.

```
// En la respectiva configuración del objeto gráfico
lTituloApp.setFont(fontTPrincipal);
lEslogan.setFont(fontSubtitulo);
lTituloLogin.setFont(fontTitulo);
lNotificaciones.setFont(fontSubtitulo);
```

Se puede observar que para realizar la incorporación de las fuentes se debe llamar el método:

* **setFont** que recibe por parámetro un objeto decorador tipo Font y refleja un estilo en la letra del objeto gráfico.

La aplicación luce asi:

<figure><img src="https://camo.githubusercontent.com/dc2086e85495a0f59470e9f7e86c1e38b4cd521b8eff68987f3d38f69a32f88b/68747470733a2f2f692e696d6775722e636f6d2f627a77436b62332e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario con incorporación de fuentes

### Registro de fuentes en el GraphicsEnvironment

Aunque al incorporar algunas fuentes en el proyecto UI estas se verán reflejadas sin problema en la maquina que se corre, es posible que en otros computadores, estas no se vean reflejadas ya que el sistema operativo no tiene instaladas dichas fuentes, por otra parte es molesto tener que instalar las fuentes que se utilicen en cada maquina nueva que se ejecute la aplicación.

Para esto es posible registrar la fuente en el **GraphicsEnvironment** de Java y de esta forma las fuentes estarán siempre incorporadas en la aplicación sin afectar en que sistema se corra.

Lo primero que se debe hacer es colocar los archivos de las fuentes a usar dentro del proyecto, para esto se crea un paquete llamado **resources** que estará en la raíz del proyecto junto a la carpeta **src** y dentro de este otro paquete llamado **fonts**.

<figure><img src="https://camo.githubusercontent.com/e0a7345e6991fc59e42f2c1da19ed924adcb2b8b76195550fdb2ac0def17ff38/68747470733a2f2f692e696d6775722e636f6d2f7554304177706a2e706e67" alt=""><figcaption></figcaption></figure>

Nuevo paquete para incorporar fuentes.

Allí se colocan los archivos de las fuentes que por lo general tienen una extensión **.TTF** para este ejemplo se guardara la fuente **LuzSans-Book** que se descargo desde internet.

<figure><img src="https://camo.githubusercontent.com/671fdc73e37361d3a33b6aad6f40109072c0f5d23603aaf9db8efdec1e3220a3/68747470733a2f2f692e696d6775722e636f6d2f3150374f4343372e706e67" alt=""><figcaption></figcaption></figure>

Archivo TTF dentro del paquete fonts

Ahora se crea un nuevo método en la clase **LoginTemplate** el cual se llamará **generarFuentes**:

```
private void generarFuentes() {
}
```

Dentro se va a ejemplificar un objeto tipo **GraphicsEnvironment** este objeto se encarga de guardar todas las configuraciones globales de nuestra aplicación, para ejemplificar este objeto se debe llamar al método **getLocalGraphicsEnvironment** y ademas se crea un Try/Catch para controlar un posible error al generar la fuente:

```
private void generarFuentes() {
  try {
    GraphicsEnvironment ge = GraphicsEnvironment.getLocalGraphicsEnvironment();

  } catch (IOException | FontFormatException e) {
    System.out.println(e);
  }
}
```

Ahora se debe indicar al objeto de entorno gráficos que se registrará una nueva fuente con el método **registerFont**:

```
private void generarFuentes() {
  try {
    GraphicsEnvironment ge = GraphicsEnvironment.getLocalGraphicsEnvironment();
    ge.registerFont();
  } catch (IOException | FontFormatException e) {
    System.out.println(e);
  }
}
```

Dentro del método se crea la nueva fuente a registrar con el método **createFont** del objeto Font, este método pedirá por parámetro:

* **Formato de la fuente**: El tipo de estilo de la fuente, normalmente se escoge la opción **TRUETYPE\_FONT** para no alterar la fuente.
* **Archivo de la fuente**: Es un objeto normalmente de tipo **File** que contiene el archivo de la fuente y se le debe pasar la dirección de donde se encuentra.

```
private void generarFuentes() {
  try {
    GraphicsEnvironment ge = GraphicsEnvironment.getLocalGraphicsEnvironment();
    ge.registerFont( Font.createFont(
        Font.TRUETYPE_FONT,
        new File("Clase3/resources/fonts/LUZRO.ttf")
    ));
  } catch (IOException | FontFormatException e) {
    System.out.println(e);
  }
}
```

Por cada fuente que se necesite registrar se debe llamar al método **registerFont** y hacer el mismo procedimiento. Algo a aclarar es que muchas fuentes por lo general tienen un nombre distinto al nombre del archivo, en este caso por ejemplo el archivo de la fuente es **LUZRO**, sin embargo el sistema reconocerá la fuente como **LuzSans-Book** asi que es recomendable leer la documentación de la fuente a descargar.

Ahora se debe llamar al método desde el constructor, y se debe llamar antes de la ejemplificación de los objetos decoradores, o de lo contrario al crear una fuente con esta tipografía pero aun sin ser registrada no se verá reflejada:

```
public LoginTemplate() {
  this.generarFuentes();

  ...
  ...
}
```

Para probar la nueva fuente registrada se va a crear una nueva fuente que se usará en el futuro para otras partes del proyecto. Aunque en el login no tendrá uso se utilizará momentáneamente en el label del titulo para verificar su correcta incorporación.

* **Declaración:**

```
// Al inicio de la clase
private Font fontMediana;
```

* **Ejemplificación**

```
fontMediana = new Font("LuzSans-Book", Font.PLAIN, 15);
```

* **Incorporación:**

```
tNombreUsuario.setFont(fontMediana);
```

<figure><img src="https://camo.githubusercontent.com/b2b89075ae62dcab0a86e074c21d1263d79b226e86e8451398676b8f9bc13880/68747470733a2f2f692e696d6775722e636f6d2f6d61637a3145692e706e67" alt=""><figcaption></figcaption></figure>

Registro de fuente exitosa.

Ahora no importa en que sistema se ejecute la aplicación, el programa siempre registrará la fuente y podrá usarla en cualquier entorno.

_**Nota:** Recordar dejar la fuente del titulo que tenia antes._

## Cursor

Los cursores son todas las formas que pueden tomar el puntero del Mouse mientras pasa por alguna zona de la ventana, por ejemplo es común ver un icono de una mano cuando se pasa por un botón, una cruz cuando se esta trabajando en un espacio de gráficos (Paint por dar un ejemplo) un icono de bloqueo cuando no se pueda dar click en una parte etc.

* **Declaración**

```
private Cursor cMano;
```

La variable (objeto) que se coloca para los objetos Cursor empezará con c en minúscula seguido del nombre de la variable.

* **Ejemplificación**

```
cMano = new Cursor(Cursor.HAND_CURSOR);
```

Java proporciona una totalidad de 15 opciones de cursores para incorporar en las Interfaces de usurario, a continuación se muestran algunos de los mas importantes.

| Cursor            | Descripción                                       | imágen                                                                                                                                                                               |
| ----------------- | ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| CROSSHAIR\_CURSOR | Cursor en forma de Cruz                           | [![](https://github.com/CrissUD/InterfazGraficaJavaClase3/raw/master/cursores/ccross.png)](https://github.com/CrissUD/InterfazGraficaJavaClase3/blob/master/cursores/ccross.png)     |
| DEFAULT\_CURSOR   | Puntero en forma de flecha que esta por defecto   | [![](https://github.com/CrissUD/InterfazGraficaJavaClase3/raw/master/cursores/cdefault.png)](https://github.com/CrissUD/InterfazGraficaJavaClase3/blob/master/cursores/cdefault.png) |
| E\_RESIZE\_CURSOR | Cursor con dos flechas unidas de forma horizontal | [![](https://github.com/CrissUD/InterfazGraficaJavaClase3/raw/master/cursores/ceresize.png)](https://github.com/CrissUD/InterfazGraficaJavaClase3/blob/master/cursores/ceresize.png) |
| N\_RESIZE\_CURSOR | Cursor con dos flechas unidas de forma Vertical   | [![](https://github.com/CrissUD/InterfazGraficaJavaClase3/raw/master/cursores/cnresize.png)](https://github.com/CrissUD/InterfazGraficaJavaClase3/blob/master/cursores/cnresize.png) |
| HAND\_CURSOR      | Cursor con una mano                               | [![](https://github.com/CrissUD/InterfazGraficaJavaClase3/raw/master/cursores/chand.png)](https://github.com/CrissUD/InterfazGraficaJavaClase3/blob/master/cursores/chand.png)       |
| MOVE\_CURSOR      | Cursor en forma de Cruz con punta de flechas      | [![](https://github.com/CrissUD/InterfazGraficaJavaClase3/raw/master/cursores/cmove.png)](https://github.com/CrissUD/InterfazGraficaJavaClase3/blob/master/cursores/cmove.png)       |
| TEXT\_CURSOR      | Cursor en forma de linea para texto               | [![](https://github.com/CrissUD/InterfazGraficaJavaClase3/raw/master/cursores/ctext.png)](https://github.com/CrissUD/InterfazGraficaJavaClase3/blob/master/cursores/ctext.png)       |
| WAIT\_CURSOR      | Cursor en forma circular para esperar             | [![](https://github.com/CrissUD/InterfazGraficaJavaClase3/raw/master/cursores/cwait.png)](https://github.com/CrissUD/InterfazGraficaJavaClase3/blob/master/cursores/cwait.png)       |

* **Incorporación**

A continuación se muestran las partes del código donde incorporamos los objetos decoradores Cursor. Recordar que aquí se muestra todo junto, sin embargo, en el código estas incorporaciones se hacen en orden en la respectiva configuración de su objeto gráfico.

```
// En la respectiva configuración del objeto gráfico
bEntrar.setCursor(cMano);
bCerrar.setCursor(cMano);
bRegistrarse.setCursor(cMano);
bOpcion1.setCursor(cMano);
bOpcion2.setCursor(cMano);
bOpcion3.setCursor(cMano);
checkSi.setCursor(cMano);
checkNo.setCursor(cMano);
```

Se puede observar que el método para incorporar este objeto decorador es:

* **setCursor:** Recibe por parámetro un objeto de tipo Cursor y se ve reflejado cuando el usuario pasa por encima del objeto gráfico con el Mouse cambiando el icono del puntero.

Ahora la interfaz gráfica tiene interactividad con el Mouse cada que el usuario pasa por los botones:

<figure><img src="https://camo.githubusercontent.com/3e6e2a61d954928a5658bb19196e458afe8b98fc1ea74c9072ca130adbe9f346/68747470733a2f2f692e696d6775722e636f6d2f4a4957796374712e676966" alt=""><figcaption></figcaption></figure>

Login de usuario con incorporación de Cursores

## Borders

Los borders son aquellos que resaltan los limites de espacio de los objetos gráficos y existen una gran variedad de bordes para ser incorporados. A continuación se muestran los bordes mas importantes y cabe resaltar que la declaración e incorporación son muy similares por lo que solo se explicará la ejemplificación de los diferentes bordes.

* **Declaración**

***

```
// Al inicio de la clase
private Border bInferiorAzul;
```

La variable (objeto) que se coloca para los objetos Border empezará con b en minúscula seguido del nombre de la variable.

**Nota:**

A veces por defecto el IDE o editor de código importa la librería:

```
import javafx.scene.layout.Border;
```

Pero esa librería no va a funcionar y nos va a traer problemas. La librería correcta es:

```
import javax.swing.border.Border;
```

* **Ejemplificación**

***

A continuación se muestran los diferentes bordes que pueden crearse usando un único objeto (border) para mostrar la variedad de estos, sin embargo para el login solo se utilizará un tipo de estos bordes.

### **BorderFactory**

Antes de mostrar los diferentes bordes se debe importar otra librería más, esta es la librería **borderFactory** de Swing que dará la posibilidad de crear los borders.

```
import javax.swing.BorderFactory;
```

### **LineBorder**

Dibuja en los limites del objeto gráfico un borde con una linea:

```
border = BorderFactory.createLineBorder(colorPrincipal, 2, true);
```

Se puede observar que para crear un borde se debe llamar primero a la clase **BorderFactory** y seleccionar el método **createLineBorder**.

Los parámetros que recibe son:

* **Color de linea:** Recibe un objeto decorador tipo Color y representa el color de la linea.
* **Grosor:** Recibe un numero entero que representa el grosor de la linea.
* **Bordes redondos:** Recibe un booleano para indicar si quiere que las esquinas del borde estén redondeadas o no. El cambio será muy mínimo, si coloca true y no ve el cambio no hay por que preocuparse.
* **Resultado:**

<figure><img src="https://camo.githubusercontent.com/4c03bed6aef8db7e8f6cce1048064319c641b723b543363584f08a12ed5038e7/68747470733a2f2f692e696d6775722e636f6d2f663747717752332e706e67" alt=""><figcaption></figcaption></figure>

LineBorder en un JTextField

### **LoweredBevelBorder**

Dibuja un borde basado en sombras para crear un efecto en el cual el objeto gráfico pareciera estar hundido con respecto a la ventana. Este efecto se consigue dibujando las sombras en la parte superior izquierda del objeto gráfico. Existen dos variaciones **LoweredBevelBorder** o **LoweredSoftBevelBorder**, según la propia Documentación de Java la variación con el **Soft** genera sombras mas suaves en las esquinas sin embargo es difícil notar la diferencia.

Una desventaja de este tipo de bordes es que solo se notara cuando la ventana o panel donde esta el objeto gráfico tiene el color por defecto (gris) de lo contrario solo se vera con dos lineas en la parte izquierda y superior.

```
border = BorderFactory.createLoweredBevelBorder();
```

Se observa que para crear el borde se debe llamar primero a la clase **BorderFactory** y se selecciona el método **createLoweredBevelBorder**.

* **Resultado:**

<figure><img src="https://camo.githubusercontent.com/f28ba2e6a43ad3529a60b453073fa92d84c03d3a20ad29ed3ac6006859abf164/68747470733a2f2f692e696d6775722e636f6d2f517436357551542e706e67" alt=""><figcaption></figcaption></figure>

LoweredBevelBorder en un JTextField

### **RaisedBevelBorder**

Dibuja un borde basado en sombras para crear un efecto en el cual el objeto gráfico pareciera estar por encima con respecto a la ventana. Este efecto se consigue dibujando las sombras en la parte inferior derecha del objeto gráfico. Existen dos variaciones **RaisedBevelBorder** o **RaisedSoftBevelBorder**, según la propia Documentación de Java la variación con el **Soft** genera sombras mas suaves en las esquinas sin embargo es difícil notar la diferencia.

De nuevo la desventaja de este tipo de bordes es que solo se notara cuando la ventana o panel donde esta el objeto gráfico tiene el color por defecto (gris) de lo contrario solo se vera con dos lineas en la parte derecha e inferior.

```
border = BorderFactory.createRaisedBevelBorder();
```

Se puede observar que para crear el borde se debe llamar primero a la clase **BorderFactory** y luego seleccionar el método **createRaisedBevelBorder**.

* **Resultado:**

<figure><img src="https://camo.githubusercontent.com/b971f6805782287c969bba11dcf1324bf8cdc5c0ad7147be0fdbdd128e8298db/68747470733a2f2f692e696d6775722e636f6d2f755061696166502e706e67" alt=""><figcaption></figcaption></figure>

RaisedBevelBorder en un JTextField

### **BevelBorder**

Una buena solución al las desventajas de los bordes anteriores puede ser este borde, que en realidad es una combinación y mejora de los dos anteriores, este borde recibe colores en su constructor lo que hace que pueda ser usado sobre cualquier color de fondo. Entonces un BevelBorder se caracteriza por dibujar 4 lineas:

* **Linea Externa Lower:** dibuja una linea en la parte superior y en la parte izquierda del objeto y estará en el la parte externa.
* **Linea Interna Lower:** dibuja una linea en la parte superior y en la parte izquierda del objeto y estará en el la parte interna.
* **Linea Externa Raise:** dibuja una linea en la parte inferior y en la parte derecha del objeto y estará en el la parte externa.
* **Linea Interna Raise:** dibuja una linea en la parte inferior y en la parte derecha del objeto y estará en el la parte interna.

De igual manera este tipo de borde tiene dos variaciones **BevelBorder** y **SoftBevelBorder** que como comentamos da un suavizado en las esquinas pero el cambio no es muy notorio.

```
border = BorderFactory.createBevelBorder(
  BevelBorder.RAISED,
  Color.LIGHT_GRAY,
  colorGrisOscuro,
  Color.LIGHT_GRAY,
  Color.WHITE
);
```

Se observa que para crear el borde se debe llamar primero a la clase **BorderFactory** y seleccionar el método **createBevelBorder**.

Este recibe por parámetros:

* **Tipo borde Bevel:** recibe un tipo de borde tipo Bevel (Lower o Raised) y en realidad lo que hace esta configuración es cambiar el orden de los colores que va a recibir por parámetro dependiendo de la elección.
* **Color Externo1:** Recibe un objeto decorador tipo Color y representa el color externo ya sea del Lower o el Raise
* **Color Interno1:** Recibe un objeto decorador tipo Color y representa el color interno que acompaña al color externo 1 ya sea del Lower o el Raise
* **Color Externo2:** Recibe un objeto decorador tipo Color y representa el color externo del contrario a la opción escogida.
* **Color Interno2:** Recibe un objeto decorador tipo Color y representa el color interno que acompaña al color externo 2.

Cabe destacar que con este borde se puede el efecto de **Hundido** o **Encima** o también es posible generar otros efectos con la combinación de varios colores.

* **Resultados:**

<figure><img src="https://camo.githubusercontent.com/13ccef9ce4c480ba4485a39b048456eeb71d862def4e8b64430ab6bdf86c5072/68747470733a2f2f692e696d6775722e636f6d2f325877547070632e706e67" alt=""><figcaption></figcaption></figure>

BevelBorder en un JTextField

<figure><img src="https://camo.githubusercontent.com/bd344b5411347722099e3c307f86b3c233fdf4a7b35232033b6b502b3bcee4b6/68747470733a2f2f692e696d6775722e636f6d2f7234554e7456352e706e67" alt=""><figcaption></figcaption></figure>

BevelBorder en un JTextField con colores

### **EtchedBorder**

Este tipo de borde dibuja 2 LineBorder en el objeto gráfico dejando así una linea interna y una linea externa que se intercalan entre si. Este tipo de bordes da un buen efecto de difuminado pequeño o de iluminado si se usan los colores correctos.

```
border = BorderFactory.createEtchedBorder(EtchedBorder.RAISED, Color.ORANGE, Color.YELLOW);
```

Se puede observar que para crear el borde se debe llamar primero a la clase **BorderFactory** y seleccionar el método **createEtchedBorder**.

Este recibe por parámetros:

* **Tipo borde Etched:** recibe un tipo de borde tipo Etched (Lower, Raised) y en realidad lo que hace esta configuración es cambiar el orden de los colores que va a recibir por parámetro dependiendo de la elección.
* **Color:** Recibe un objeto decorador tipo Color y representa el color de una de las lineas del borde que en una parte será externa pero en otra interna.
* **Color:** Recibe un objeto decorador tipo Color y representa el color de una de las lineas del borde que en una parte será externa pero en otra interna.
* **Resultado:**

<figure><img src="https://camo.githubusercontent.com/661aa22744b58f34cab994dc4bd837aedf7236451c858ca309cfdf97a1d5e5ce/68747470733a2f2f692e696d6775722e636f6d2f4a6455316b52482e706e67" alt=""><figcaption></figcaption></figure>

EtchedBorder en un JTextField

### **MatteBorder**

Este es uno de los bordes más usados y aunque su configuración es simple se puede sacar gran provecho de este. Dibuja una linea en los lados que se le indique, por ejemplo para un panel en la parte izquierda seria bueno un borde en la parte derecha nada mas indicando la separación y con este tipo de Border se puede lograr.

```
border = BorderFactory.createMatteBorder(0, 0, 3, 0, colorPrincipal);
```

Se puede observar que para crear el borde se debe llamar primero a la clase **BorderFactory** y seleccionar el método **createMatteBorder**.

Este recibe por parámetros:

* **Grosor en la linea superior:** Recibe un numero entero que indica el grosor en la linea superior.
* **Grosor en la linea izquierda:** Recibe un numero entero que indica el grosor en la linea izquierda.
* **Grosor en la linea inferior:** Recibe un numero entero que indica el grosor en la linea inferior.
* **Grosor en la linea derecha:** Recibe un numero entero que indica el grosor en la linea derecha.
* **Color del borde:** Recibe un objeto decorador tipo Color y representa el color de la linea del borde.
* **Ejemplo**

<figure><img src="https://camo.githubusercontent.com/600b1dff71d54bce4aecdc7e55c6819c405147587dbdd15716560f9f15ff62f3/68747470733a2f2f692e696d6775722e636f6d2f6a636c6c5132752e706e67" alt=""><figcaption></figcaption></figure>

MatteBorder en un JTextField

### **DashedBorder**

Dibuja un tipo de borde con una linea punteada o intermitente para limitar el objeto gráfico.

```
border = BorderFactory.createDashedBorder(colorPrincipal, 2, 3, 2, true);
```

Se observa que para crear el borde se debe llamar primero a la clase **BorderFactory** y seleccionar el método **createDashedBorder**.

Este recibe por parámetros:

* **Color del borde:** Recibe un objeto decorador tipo Color y representa el color de la linea del borde.
* **Grosor de la linea:** Recibe un numero entero que indica el grosor de la linea.
* **Largo de las lineas:** Recibe un numero entero que indica el largo de cada una de las lineas intermitentes.
* **Espacio entre lineas:** Recibe un numero entero que indica el espacio que hay entre las lineas.
* **Bordes redondeados:** Recibe un booleano que si se deja como True pondrá los bordes redondeados, sin embargo el efecto es poco notorio.
* **Resultado:**

<figure><img src="https://camo.githubusercontent.com/915e5ccff9330933d842b02407c58be5d13a1a4866ff34fb5a40cbc498d465f9/68747470733a2f2f692e696d6775722e636f6d2f6d6b38657768502e706e67" alt=""><figcaption></figcaption></figure>

DashedBorder en un JTextField

### **EmptyBorder**

Este borde crea un borde vació en los objetos gráficos y es muy util cuando se quiere generar un espacio entre los limites del objeto gráfico y el contenido de este, creando un **Padding** gracias a este borde, ya que cuando se crea un borde este, en lugar de ocupar mas espacio externamente en un objeto gráfico, en realidad ocupa espacio internamente.

```
border = new EmptyBorder(2, 20, 2, 2);
```

Se observa que para crear el borde no es necesario llamar al **BorderFactory** simplemente se crea bajo el objeto tipo **EmptyBorder**.

Este recibe por parámetros:

* **Grosor de borde superior:** Recibe un numero entero que indica el grosor del borde o espacio en la parte superior.
* **Grosor de borde izquierdo:** Recibe un numero entero que indica el grosor del borde o espacio en la parte izquierda.
* **Grosor de borde inferior:** Recibe un numero entero que indica el grosor del borde o espacio en la parte inferior.
* **Grosor de borde derecho:** Recibe un numero entero que indica el grosor del borde o espacio en la parte derecha.

### **CompoundBorder**

Es un Border compuesto que recibe como parámetro dos objetos Borders y los combina, dejando un borde interno y otro borde externo.

A continuación se muestra una implementación de este borde con la combinación de varios LineBorders para dar un efecto difuminado.

<figure><img src="https://camo.githubusercontent.com/16a7d44b9430b84015dda9b60b28ce503f0974966f3351e5db8209b5add89d11/68747470733a2f2f692e696d6775722e636f6d2f6d614f6f7572322e706e67" alt=""><figcaption></figcaption></figure>

Implementación de CompoundBorder

Se observa que para crear este tipo de borde se debe llamar primero a la clase **BorderFactory** y seleccionar el método **createCompoundBorder**.

Este recibe por parámetros:

* **Borde Interno:** Recibe un objeto tipo Border y representa el borde interno.
* **Borde Externo:** Recibe un objeto tipo Border y representa el borde Externo.
* **Resultado:**

<figure><img src="https://camo.githubusercontent.com/1b246efdae53ca712e1e2c40ce04e2e8f67bf603f26fb2bd933919ba0acedc68/68747470733a2f2f692e696d6775722e636f6d2f63534a534433352e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo de un CompoundBorder en un JPanel

* **Incorporación**

***

A continuación se muestra el borde que se usa para la ventana y las incorporaciones de este en el código. También mostraremos algunas correcciones en la posición de los objetos gráficos para que tengan un mejor aspecto con la incorporación del borde. Recordar que aquí se muestra todo junto, sin embargo en el código estas incorporaciones se hacen en orden en la respectiva configuración de su objeto gráfico.

```
bInferiorAzul = BorderFactory.createMatteBorder(0, 0, 2, 0, colorPrincipal);
```

```
tNombreUsuario.setBorder(bInferiorAzul);
tClaveUsuario.setBorder(bInferiorAzul);
cbTipoUsuario.setLocation((pDerecha.getWidth() - cbTipoUsuario.getWidth()) / 2, 195);
```

Hasta el momento la interfaz estará así:

<figure><img src="https://camo.githubusercontent.com/edbca775c5a5afa4231b2d63a32921af7a35be182b57bf1167b08e0da48e3d00/68747470733a2f2f692e696d6775722e636f6d2f6d4a437873676d2e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario con la incorporación de bordes

## ImagenIcon

Las imágenes en las ventanas son quizás el objeto decorador determinante para que una interfaz gráfica luzca mucho más amigable con los usuarios. A continuación se ve la creación de estos objetos decoradores y la incorporación en la interfaz de Login para resaltar su importancia.

### Antes de comenzar

Es importante tener todos los recursos dentro de un paquete en el proyecto. Para esto crearemos una carpeta llamada **images** que estará dentro del paquete **resources**, allí es donde se guardan las imágenes e iconos a usar.

[![](https://camo.githubusercontent.com/b985a1b73ebf66752abe10dda0457a04a71c02d81ab2f378dcfe6b80852eba18/68747470733a2f2f692e696d6775722e636f6d2f793272376338462e706e67)](https://camo.githubusercontent.com/b985a1b73ebf66752abe10dda0457a04a71c02d81ab2f378dcfe6b80852eba18/68747470733a2f2f692e696d6775722e636f6d2f793272376338462e706e67)

Carpeta resources dentro del proyecto

<figure><img src="https://camo.githubusercontent.com/f5f8fd9cb102fa422bac67d3f676f096c9b570069ed646d6cac42e7a44bebea9/68747470733a2f2f692e696d6775722e636f6d2f63485a5164794e2e706e67" alt=""><figcaption></figcaption></figure>

Carpeta images dentro de la carpeta resources

<figure><img src="https://camo.githubusercontent.com/439d0dfaeb6fac4452057c3a8e40a7d05138428ae0f9f06f08f34fe20010e4c0/68747470733a2f2f692e696d6775722e636f6d2f6c5835367634392e706e67" alt=""><figcaption></figcaption></figure>

imágenes que vamos a usar en la interfaz

**Nota**

Algunas de estas imágenes tienen un numero al final ya que más adelante en el curso se añadirán variaciones de estas mismas imágenes. Por otro lado estas imágenes pueden ser descargadas desde este mismo repositorio, entrando a la carpeta **Clase3** seguido de la carpeta a **resources/images** y ahi se prodran ver y descargar cada una de las imágenes.

<figure><img src="https://camo.githubusercontent.com/4deec1217f405a4d2ae24fd82257a9fa385066d96654def1aa8882d5220594be/68747470733a2f2f692e696d6775722e636f6d2f595067563054452e706e67" alt=""><figcaption></figcaption></figure>

Carpeta clase3 dentro del repositorio

<figure><img src="https://camo.githubusercontent.com/114dbf08a9ae769ae804e947e913ea401abe05516e716a3aa934c8ddda27b542/68747470733a2f2f692e696d6775722e636f6d2f415031386c71622e706e67" alt=""><figcaption></figcaption></figure>

Carpeta resources dentro del repositorio

<figure><img src="https://camo.githubusercontent.com/7d97261878c695637099430498b3604f65e78ddf2ef69560707d44302e22b861/68747470733a2f2f692e696d6775722e636f6d2f7a377975566f4c2e706e67" alt=""><figcaption></figcaption></figure>

Carpeta images dentro del repositorio

<figure><img src="https://camo.githubusercontent.com/347cc7cd2002d4129c43cb7883116713b664a8b462ba35f116993946c8f7913a/68747470733a2f2f692e696d6775722e636f6d2f486530366d7a742e706e67" alt=""><figcaption></figcaption></figure>

Lista de imágenes dentro del repositorio

<figure><img src="https://camo.githubusercontent.com/65ce17c62d9ae42cab353a2d83e2686e9a9785e2fbb4e54fe990445aafb2af5f/68747470733a2f2f692e696d6775722e636f6d2f397877377a72522e706e67" alt=""><figcaption></figcaption></figure>

Descarga de imágenes dentro del repositorio

* **Declaración**

```
private ImageIcon iFondo, iLogo, iCerrar;
private ImageIcon iSvg1, iUsuario2, iClave2, iPunto1, iFacebook1, iTwitter1, iYoutube1, iDimAux;
```

La variable (objeto) que se coloca para los objetos ImageIcon empezará con i en minúscula seguido del nombre de la variable. En este caso algunas variables se les añadió un número al final ya que mas adelante en el curso se usarán algunas variaciones de esas mismas imágenes.

* **Ejemplificación**

A continuación se muestra la ejemplificación y configuración de los objetos Decoradores tipo ImageIcon:

```
iFondo = new ImageIcon("Clase3/resources/img/fondo.png");
iLogo = new ImageIcon("Clase3/resources/img/logo.png");
iUsuario2 = new ImageIcon("Clase3/resources/img/usuario2.png");
iClave2 = new ImageIcon("Clase3/resources/img/clave2.png");
iPunto1 = new ImageIcon("Clase3/resources/img/punto1.png");
iFacebook1 = new ImageIcon("Clase3/resources/img/facebook1.png");
iTwitter1 = new ImageIcon("Clase3/resources/img/twitter1.png");
iYoutube1 = new ImageIcon("Clase3/resources/img/youtube1.png");
iSvg1 = new ImageIcon("Clase3/resources/img/imagen1.png");
iCerrar = new ImageIcon("Clase3/resources/img/cerrar.png");
```

Se puede observar que al momento de ejemplificar el objeto decorador ImageIcon, este recibe por parámetro un String que en realidad representa la dirección donde esta contenida la imágen. También es importante fijarse en la extensión de la imágen en este ejemplo todas son **.png** pero Java también soporta **.jpg**, **.gif** etc.

**Otro punto importante que hay que resaltar es que la dirección puede variar entre IDEs y editores de código, por ejemplo estas direcciónes funcionan en el editor de texto Visual Studio Code. Pero en NetBeans por ejemplo habría que quitar en la dirección la parte "Clase3/" y empezar por "resources/.."**

* **Incorporación**

Como un ImageIcon es un objeto decorador, este no se puede agregar directamente a la ventana, necesitamos un objeto gráfico como intermediario para ser mostrado. Una manera de realizar esto es mediante la creación de labels que contengan estas imágenes. Ya que los JLabel por defecto traen un fondo transparente y esto es de gran utilidad. Por lo que se van a crear los JLabel correspondientes:

### Declaración objetos JLabel

```
private JLabel lFondo, lSvg1, lLogo, lUsuario, lClave, lFacebook, lTwitter, lYoutube;
```

### Ejemplificación y Configuración y Adición objetos JLabel

Se va a ver primero el ejemplo con uno de los labels para explicar unos **aspectos importantes**.

Se va a añadir un fondo a la interfaz, lo primero que se hace es poner el color de fondo del panel pIzquierda a blanco:

```
pIzquierda.setBackground(Color.white);
```

Asi se ve la interfaz:

<figure><img src="https://camo.githubusercontent.com/ba114a3e118c39ab2ac21713e1e3332dc1e79d01bb58984dd1f40593a9f48589/68747470733a2f2f692e696d6775722e636f6d2f3454764b4d56542e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario cambiando el color de fondo al pIzquierda

Ahora se va a Ejemplificar y configurar el objeto JLabel.

Una pregunta valida en este punto puede ser: **¿Si se quiere una imágen de fondo, por que no incorporarla al JPanel directamente?**

Esto es debido a que los JPanel no tienen la propiedad de incorporar una imágen. Por eso se hace por medio de un JLabel.

```
// dentro del constructor
lFondo = new JLabel();
lFondo.setBounds(0, 0, 600, 600);
lFondo.setIcon(iFondo);
pIzquierda.add(lFondo);
```

Se puede observar que el método para incorporar un objeto decorador tipo ImageIcon es:

* **setIcon:** Recibe por parámetro un objeto decorador ImageIcon y representa la imágen que se añade a la ventana.

#### **Aspecto 1: Orden de objetos mostrados en pantalla**

Una pregunta realmente importante que hay que hacerse es **¿En que parte del constructor se debe colocar la creación del nuevo JLabel?** Y esta pregunta es valida por que si por ejemplo se pone este fragmento de código justo después de la creación de los JPanel ocurre lo siguiente:

<figure><img src="https://camo.githubusercontent.com/49c487b2a34db94695571f725ef920abd094de0a9fab5b2a2e0131a55eb449e5/68747470733a2f2f692e696d6775722e636f6d2f476c38714e77682e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario agregando imágen de fondo justo después de la creación de los paneles

Se puede observar que la imágen de fondo quedo encima del Label que daba el titulo a la aplicación y encima de los botones ubicados en la parte izquierda. Y es por que Java **pondrá los elementos uno detrás de otro en el eje Z a medida que se vayan añadiendo.** Por lo que si queremos que la imágen quede en el fondo tendremos que ponerla de ultimas justo después de los últimos botones que habíamos adicionado en el panel pIzquierda:

<figure><img src="https://camo.githubusercontent.com/791b16dd12bdcdc6f36b975166ae634f76388a9d5a501c5b507a84ae58139604/68747470733a2f2f692e696d6775722e636f6d2f3949574a5074322e706e67" alt=""><figcaption></figcaption></figure>

Orden en código de elementos en pIzquierda para que la imágen quede en el fondo de la ventana

De esta manera la interfaz quedara asi:

<figure><img src="https://camo.githubusercontent.com/d4b51f5b716bffb671ad02ccffd68836fe8f6672ecd5ad9be4b7fcdadc74348e/68747470733a2f2f692e696d6775722e636f6d2f74784e6d5a56692e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario agregando imágen de fondo justo después de la creación del ultimo objeto gráfico adicionado en pIzquierda

#### **Aspecto 2: Redimensión de las imágenes**

Se observa que en la interfaz la imágen de fondo quedo incorporada, sin embargo, no quedo como se esperaba. Esto es debido a que la imágen es de dimensiones mucho mas grandes que las de la ventana asi que será buena idea redimensionarla.

Una posible forma de redimensión sería de forma manual con algún programa como photoshop, sin embargo, esto no es nada optimo y menos si hay una gran cantidad de imágenes por redimensionar.

La mejor forma es hacerlo en el código y para esto necesitamos de un objeto auxiliar:

<figure><img src="https://camo.githubusercontent.com/ddf9b54e8b0780aa9266d46e25b77184a7b5f749da6eed9941478042e440e80c/68747470733a2f2f692e696d6775722e636f6d2f54516b697750682e706e67" alt=""><figcaption></figcaption></figure>

Objeto Auxiliar

Antes de poder realizar la redimensión necesitamos agregar una librería más en el código:

```
import java.awt.Image;
```

Para realizar esta redimension realizaremos este código justo encima de la creación del JLabel que contiene la imágen de fondo:

```
iDimAux = new ImageIcon(
  iFondo.getImage()
    .getScaledInstance(600, 600, Image.SCALE_AREA_AVERAGING)
);

lFondo = new JLabel();
...
...
```

Se puede observar que se esta realizando una ejemplificación de un objeto decorador ImageIcon, sin embargo no está recibiendo ninguna ruta, este esta recibiendo por parámetro otro objeto ImageIcon y se están llamando el siguiente método:

* **getImage:** que nos trae el Objeto **Image** del ImageIcon, esto se realiza para poder obtener las propiedades del objeto tipo **Image** como la **redimension** ya que el objeto ImageIcon no cuenta con esta propiedad dentro de su configuración.

Una vez con el objeto **Image** se procede a llamar el método:

* **getScaledInstance:** que se encarga de redimensionar la imágen al tamaño que se indique y recibe estos parámetros:
  * **ancho:** Un numero entero que representa el nuevo ancho de la imágen
  * **alto:** Un numero entero que representa el nuevo alto de la imágen
  * **sistema de escala:** Es un sistema interno de la clase **Image** que se encarga de re acomodar los pixeles. Existen varias opciones para escalar los pixes (**SCALE\_AREA\_AVERAGING, SCALE\_DEFAULT, SCALE\_REPLICATE** etc). sin embargo el que por experiencia da mejores resultados es el **SCALE\_AREA\_AVERAGING**

Si se ejecuta la aplicación es posible observar que la imágen sigue igual **¿por qué?**, ya que nos falto cambiar el ImageIcon en el label, ahora este debe incorporar el ImageIcon **iDimAux** quien es el que contiene la imágen redimensionada.

```
lFondo.setIcon(iDimAux);
```

Y ahora la interfaz se verá así:

<figure><img src="https://camo.githubusercontent.com/24d7f922c3e33928716abf46b95027e0d8a3f7f0eba7751c80e6f23b7f4289d2/68747470733a2f2f692e696d6775722e636f6d2f456570666452622e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario con imágen de fondo redimensionada

### Creando los otros label para mostrar en la Interfaz

A continuación se muestra la creación de los objetos JLabel que incorporan las imágenes repitiendo el proceso que vimos anteriormente. Recordar que aunque se muestre el código aquí todo junto en la aplicación se ponen en el orden de tal manera que tenemos presente la organización de objetos con respecto al eje Z.

```
iDimAux = new ImageIcon(
  iLogo.getImage()
    .getScaledInstance(40, 40, Image.SCALE_AREA_AVERAGING)
);

lLogo = new JLabel();
lLogo.setBounds(50, 20, 40, 40);
lLogo.setIcon(iDimAux);
pIzquierda.add(lLogo);
```

```
iDimAux = new ImageIcon(
  iSvg1.getImage()
    .getScaledInstance(500, 345, Image.SCALE_AREA_AVERAGING)
);

lSvg1 = new JLabel();
lSvg1.setBounds(100, 100, 500, 345);
lSvg1.setIcon(iDimAux);
pIzquierda.add(lSvg1);
```

```
iDimAux = new ImageIcon(
  iFacebook1.getImage()
    .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
);

lFacebook = new JLabel();
lFacebook.setBounds(20, 420, 30, 30);
lFacebook.setIcon(iDimAux);
lFacebook.setCursor(cMano);
pIzquierda.add(lFacebook);

iDimAux = new ImageIcon(
  iTwitter1.getImage()
    .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
);

lTwitter = new JLabel();
lTwitter.setBounds(60, 420, 30, 30);
lTwitter.setIcon(iDimAux);
lTwitter.setCursor(cMano);
pIzquierda.add(lTwitter);

iDimAux = new ImageIcon(
  iYoutube1.getImage()
    .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
);

lYoutube = new JLabel();
lYoutube.setBounds(100, 420, 30, 30);
lYoutube.setIcon(iDimAux);
lYoutube.setCursor(cMano);
pIzquierda.add(lYoutube);
```

```
iDimAux = new ImageIcon(
  iUsuario2.getImage()
    .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
);

lUsuario = new JLabel();
lUsuario.setBounds(40, 130, 30, 30);
lUsuario.setIcon(iDimAux);
pDerecha.add(lUsuario);

iDimAux = new ImageIcon(
  iClave2.getImage()
    .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
);

lClave = new JLabel();
lClave.setBounds(40, 250, 30, 30);
lClave.setIcon(iDimAux);
pDerecha.add(lClave);
```

Con estas adiciones en el código la interfaz gráfica queda asi:

<figure><img src="https://camo.githubusercontent.com/4d262d4f1c1c454180b193ad1faceddaf9f02ca9443b194702db0dd18926b7f4/68747470733a2f2f692e696d6775722e636f6d2f5a4f767163476b2e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario con incorporación de ImageIcon

### Agregando imágenes en botones

**!Ya falta poco!** Ahora hay dos imágenes que no se han incorporado aun, estas se van a incorporar en los botones, bCerrar y bOpcion1, bOpcion2, bOpcion3.

Se empieza por los botones opciones, la imágen que se quiere incorporar esta contenida en el objeto decorador iPunto.

Primero se redimensiona la imágen par a luego incorporarla en los botones:

```
iDimAux = new ImageIcon(
  iPunto1.getImage()
    .getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
);

bOpcion1.setIcon(iDimAux);
bOpcion2.setIcon(iDimAux);
bOpcion3.setIcon(iDimAux);
```

Los botones se verán asi:

[![](https://camo.githubusercontent.com/2967f60e24a4bfcca28a2d976fbe59d34026d6ce213c745544671250f951134e/68747470733a2f2f692e696d6775722e636f6d2f397079503377752e706e67)](https://camo.githubusercontent.com/2967f60e24a4bfcca28a2d976fbe59d34026d6ce213c745544671250f951134e/68747470733a2f2f692e696d6775722e636f6d2f397079503377752e706e67)

Botones con incorporación de ImageIcon

Sin embargo esto no es lo deseado, para empezar se quiere que los botones queden con un fondo transparente. Esto lo haremos con el siguiente método:

```
bOpcion1.setContentAreaFilled(false);
bOpcion2.setContentAreaFilled(false);
bOpcion3.setContentAreaFilled(false);
```

* **setContentAreaFilled:** Recibe por parámetro un booleano que por defecto esta en True, si se cambia a false este quitara ciertas propiedades de los botones que traen por defecto en Java como el color por defecto en gris y la iluminación cada vez que se pasa encima de el.

Los botones ahora están asi:

[![](https://camo.githubusercontent.com/1b5b380e0b2d4b682cbeeb1f12b1f634ebc18d6ef8704677849647de9f0ae750/68747470733a2f2f692e696d6775722e636f6d2f34776472576b372e706e67)](https://camo.githubusercontent.com/1b5b380e0b2d4b682cbeeb1f12b1f634ebc18d6ef8704677849647de9f0ae750/68747470733a2f2f692e696d6775722e636f6d2f34776472576b372e706e67)

Botones sin propiedades content Area

Sin embargo tienen unas lineas que rodean a la imágen que no se quieren ver, esto es por que por defecto los botones tienen un borde, se debe retirar y además no se le ha quitado la propiedad focusable:

```
bOpcion1.setFocusable(false);
bOpcion1.setBorder(null);

bOpcion2.setFocusable(false);
bOpcion2.setBorder(null);

bOpcion3.setFocusable(false);
bOpcion3.setBorder(null);
```

[![](https://camo.githubusercontent.com/1ebb7dc7684fe06e34dcdbb34d6b999c4aaf7b07eb9460041fc43e124164243e/68747470733a2f2f692e696d6775722e636f6d2f4f3031565569692e706e67)](https://camo.githubusercontent.com/1ebb7dc7684fe06e34dcdbb34d6b999c4aaf7b07eb9460041fc43e124164243e/68747470733a2f2f692e696d6775722e636f6d2f4f3031565569692e706e67)

Botones sin borde ni la propiedad focusable

Ya esta hecho ! ahora se repite el proceso para el botón bCerrar:

```
iDimAux = new ImageIcon(
  iCerrar.getImage()
    .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
);

bCerrar = new JButton(); // Se quita el texto que tenia al inicio
bCerrar.setIcon(iDimAux);
bCerrar.setContentAreaFilled(false);
bCerrar.setFocusable(false);
bCerrar.setBorder(null);
```

La Interfaz Luce asi:

<figure><img src="https://camo.githubusercontent.com/27b9bb289783752c33ac7ad0d10dea2c5206b5a7ef10c82c509b1fcee965b965/68747470733a2f2f692e696d6775722e636f6d2f4d4e47764868342e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario con incorporación de ImageIcon

## Decoraciones Adicionales

A continuación y para acabar se van a realizar unas pequeñas modificaciones y adiciones en el código para darle los toques finales.

### Quitar la barra por defecto en Java

En la primera clase se menciono este método pero es la hora de usarse, en la configuración de la ventana se añade el método:

```
setUndecorated(true);
```

Notamos como la interfaz ya no cuenta con la barra por defecto de Java, ahora podemos borrar la configuración **super**, ya que no sera necesaria.

Se pueden notar algunas cosas:

* **La aplicación ya no cierra** Este problema se solucionará en otra clase, por ahora podemos cerrarlo desde la barra de tareas.

<figure><img src="https://camo.githubusercontent.com/e292a77ea975f03b99945b0c3fddb7cbb20449dd1daae13b4892416bfce03a85/68747470733a2f2f692e696d6775722e636f6d2f784730707935772e706e67" alt=""><figcaption></figcaption></figure>

Cerrando desde la barra de tareas

* **La aplicación no se mueve** Este es otro problema que se tratará en futuras clases.
* **Ahora hay mas espacio** efectivamente ahora la aplicación tiene un poco más de espacio por lo que ahora se harán unas pequeñas correcciones de posición sobretodo en el eje Y para aprovechar este espacio. Recordar que aquí se muestra todo junto, sin embargo en el código estas modificaciones se hacen en orden en la respectiva configuración de su objeto gráfico.

```
lEslogan.setLocation((pDerecha.getWidth() - lEslogan.getWidth()) / 2, 60);
lTituloLogin.setLocation((pDerecha.getWidth() - lTituloLogin.getWidth()) / 2, 80);
lNotificaciones.setLocation((pDerecha.getWidth() - lNotificaciones.getWidth()) / 2, 400);
lUsuario.setBounds(40, 140, 30, 30);
lClave.setBounds(40, 270, 30, 30);
tNombreUsuario.setLocation((pDerecha.getWidth() - tNombreUsuario.getWidth()) / 2, 130);
tClaveUsuario.setLocation((pDerecha.getWidth() - tClaveUsuario.getWidth()) / 2, 260);
cbTipoUsuario.setLocation((pDerecha.getWidth() - cbTipoUsuario.getWidth()) / 2, 210);
bEntrar.setLocation((pDerecha.getWidth() - bEntrar.getWidth()) / 2, 330);
bCerrar.setBounds(350, 10, 45, 30);
bRegistrarse.setBounds(240, 460, 145, 35);
lFacebook.setBounds(20, 460, 30, 30);
lTwitter.setBounds(60, 460, 30, 30);
lYoutube.setBounds(100, 460, 30, 30);
checkSi.setLocation((pDerecha.getWidth() - checkSi.getWidth()) / 2 - 15, 375);
checkNo.setLocation((pDerecha.getWidth() + checkNo.getWidth()) / 2 - 15, 375);
```

## Resultado

Finalmente la interfaz de usuario con todos los Objetos Decoradores incorporados queda asi:

<figure><img src="https://camo.githubusercontent.com/9beb76115743e92d1a3506346305822296f09244050ca3d708c75d981b78c0a7/68747470733a2f2f692e696d6775722e636f6d2f436a76466151592e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario Finalizado

El Login anterior es una reconstrucción inspirada del proyecto web que puede ver en este [link de repositorio](https://github.com/akashyap2013/Advanced-Login-UI)

Si has llegado hasta aquí **!! felicitaciones !!**

Se ha creado la primera interfaz gráfica con una vista amigable con los usuarios, se aprendió como crear objetos gráficos y mostrarlos en pantalla ademas de como incorporar objetos decoradores para que las interfaces gráficas luzcan mucho mejor.

En la siguiente clase se hará una parada sobre las interfaces y se va a explorar un poco el código escrito ya que existen maneras de optimizar mucho más el código.

## Actividad

Utiliza los objetos decoradores en el login de usuario escogido para que luzca mucho más amigable a la vista de los usuarios. Sube a Github los resultados y envía el link al correo:

[cfpatinoc@correo.udistrital.edu.co](mailto:cfpatinoc@correo.udistrital.edu.co)

## Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 4

### Objetivos

* Reconocer la forma de añadir modularidad al código en las clases **Template** separando la creación de objetos gráficos.
* Optimizar el código con el uso de un servicio que encapsule el funcionamiento de la construcción de objetos gráficos.
* Optimizar los recursos de la aplicación con el uso de un servicio que administre los objetos que pueden ser utilizados en diferentes clases.

## Antes de comenzar

#### **Ajustes en el proyecto**

En las anteriores sesiones se han creado las clases **VistaPrincipalTemplate** y **LoginTemplate** cada una en su respectivo paquete como se puede ver a continuación:

<figure><img src="https://camo.githubusercontent.com/a8efdf827de7e6b9ee0fba6b04636dcf123d7e090a19d4b7a945a403de3b55bf/68747470733a2f2f692e696d6775722e636f6d2f31306d30625a612e706e67" alt=""><figcaption></figcaption></figure>

Clases UI en sus respectivos paquetes

Ahora por motivos de modularidad se crea un paquete llamado **client** y allí se dejan los paquetes de las clases UI que se han creado. El archivo de ejecución App.java sigue estando ubicado en el paquete principal **app**.

<figure><img src="https://camo.githubusercontent.com/31199a85e2adbfa63c4209fd91d751e8a93abb18cb776925edf6d6e7e36badff/68747470733a2f2f692e696d6775722e636f6d2f31546f566c586c2e706e67" alt=""><figcaption></figcaption></figure>

Creación de paquete client que contiene los paquetes creados previamente

#### **Recordatorio**

Recordando un poco el recorrido del curso, en la primera sesión se había creado la clase **VistaPrincipalTemplate** que hasta el momento esta vacía:

<figure><img src="https://camo.githubusercontent.com/97c71c4812963850985f65b6e53bf7c499c076bb329e0573b182035d64ee6e39/68747470733a2f2f692e696d6775722e636f6d2f367237616362562e706e67" alt=""><figcaption></figcaption></figure>

Vista principal creada en primera sesión.

También se creo la clase **LoginTemplate** y el resultado de la anterior sesión fue el siguiente:

<figure><img src="https://camo.githubusercontent.com/a6c657e3b37c33ab62016bef7aa1215c674c3f566e025a51e44b966fcf84fdbf/68747470733a2f2f692e696d6775722e636f6d2f464432776248772e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario resultado anterior sesión.

## Modularización y optimización

En esta lección se van a tratar 3 temas principales que serán de vital ayuda para que el código creado al construir interfaces gráficas de usuario sea ordenado, mantenible, entendible y sencillo. Los temas principales son:

* **Modularización de código**
* **Optimización de código**
* **Optimización de recursos**

## Modularización de código

Ya se ha creado el login de usuario usando objetos gráficos y objetos decoradores los cuales hacen que la interfaz de usuario se vea muy bien, sin embargo, si en algún momento se quiere cambiar alguna configuración en uno de los objetos gráficos creados, realmente va ser algo complicado encontrar dicho objeto dentro del constructor. Aunque el código tiene algo de organización con la separación de la creación de cada uno de los objetos gráficos, el constructor tiene una gran cantidad de lineas de código.

<figure><img src="https://camo.githubusercontent.com/bbc51a46fc2feffd5d20c58c724eb705342b754d3cd51f4ef47b2d9081da2c50/68747470733a2f2f692e696d6775722e636f6d2f6139394776736f2e706e67" alt=""><figcaption></figcaption></figure>

Separación de creación de objetos gráficos dentro del constructor.

Una buena idea para organizar el código es el uso de métodos que nos ayuden a separar la creación de objetos gráficos de acuerdo a varios criterios, algunos de ellos podrían ser por sus tipos, por contenido, por contexto etc. Por ejemplo en el login se puede realizar la creación de métodos que separe de acuerdo al tipo de objetos y con base a esto crear un método llamado **crearJPanels()** y se inserta la creación de todos los objetos tipo JPanel allí.

```
public void crearJPanels(){
  pIzquierda = new JPanel();
  pIzquierda.setSize(600, 500);
  pIzquierda.setLocation(0, 0);
  pIzquierda.setBackground(Color.white);
  pIzquierda.setLayout(null);
  this.add(pIzquierda);

  pDerecha = new JPanel();
  pDerecha.setSize(400, 500);
  pDerecha.setLocation(600, 0);
  pDerecha.setBackground(Color.white);
  pDerecha.setLayout(null);
  this.add(pDerecha);
}
```

Ahora se crea otro método llamado **crearJTextfields()** y se inserta la creación de los objetos gráficos tipo JTextField.

```
public void crearJTextFields(){
  tNombreUsuario = new JTextField("Nombre Usuario");
  tNombreUsuario.setSize(260, 40);
  tNombreUsuario.setLocation((pDerecha.getWidth() - tNombreUsuario.getWidth()) / 2, 130);
  tNombreUsuario.setForeground(colorPrincipal);
  tNombreUsuario.setBackground(Color.WHITE);
  tNombreUsuario.setCaretColor(colorGrisOscuro);
  tNombreUsuario.setBorder(bInferiorAzul);
  tNombreUsuario.setHorizontalAlignment(SwingConstants.CENTER);
  pDerecha.add(tNombreUsuario);
}
```

Otro método podría ser el de **crearObjetosDecoradores** donde se inserta la creación de todos los objetos de este tipo:

```
public void crearObjetosDecoradores(){
  colorPrincipal = new Color(60, 78, 120);
  colorGrisOscuro = new Color(80, 80, 80);
  fontTPrincipal = new Font("Rockwell Extra Bold", Font.PLAIN, 20);
  fontTitulo = new Font("Calibri (Cuerpo)", Font.BOLD, 17);
  fontSubtitulo = new Font("Forte", Font.PLAIN, 13);
  fontMediana = new Font("LuzSans-Book", Font.PLAIN, 15);
  cMano = new Cursor(Cursor.HAND_CURSOR);
  bInferiorAzul = BorderFactory.createMatteBorder(0, 0, 2, 0, colorPrincipal);
  iFondo = new ImageIcon("Clase4/resources/images/fondo.png");
  iLogo = new ImageIcon("Clase4/resources/images/logo.png");
  iUsuario2 = new ImageIcon("Clase4/resources/images/usuario2.png");
  iClave2 = new ImageIcon("Clase4/resources/images/clave2.png");
  iPunto1 = new ImageIcon("Clase4/resources/images/punto1.png");
  iFacebook1 = new ImageIcon("Clase4/resources/images/facebook1.png");
  iTwitter1 = new ImageIcon("Clase4/resources/images/twitter1.png");
  iYoutube1 = new ImageIcon("Clase4/resources/images/youtube1.png");
  iSvg1 = new ImageIcon("Clase4/resources/images/imagen1.png");
  iCerrar = new ImageIcon("Clase4/resources/images/cerrar.png");
}
```

otros métodos de creación necesarios para la clase son:

```
public void crearJButtons(){
    ...
}
```

```
public void crearJLabels(){
    ...
}
```

```
public void crearJPasswordFields(){
    ...
}
```

```
public void crearJComboBoxes(){
    ...
}
```

```
public void crearJCheckBoxes(){
    ... // También se crea el objeto ButtonGroup aquí al ser un objeto auxiliar 
}
```

Una vez realizada la modularización, vale la pena aclarar varias aspectos:

### Excepción

Existe una excepción para el objeto decorador **iDimAux** encargado de redimensionar las imágenes, este estará presente en los diferentes métodos de construcción respectiva al objeto gráfico al que se va a incorporar, ya que es un objeto auxiliar y es necesario dejarlo justo encima del objeto gráfico al que se incorpora, porque que esta variable estará cambiando constantemente con cada redimension nueva requerida.

<figure><img src="https://camo.githubusercontent.com/6839a2d49f26cd6923a20fabf9d6bb36c8c62492d6749865b7410e1502cef41a/68747470733a2f2f692e696d6775722e636f6d2f316c46383658412e706e67" alt=""><figcaption></figcaption></figure>

Excepción con el objeto auxiliar que estará presente en varios métodos de creación.

### ¿Por que es posible hacer esta modularización?

Como se vio en las anteriores lecciones, la declaración de los objetos gráficos y objetos decoradores se realiza de forma global en la clase ya que se ubica al inicio de la misma, haciendo de estos objetos atributos de la clase.

<figure><img src="https://camo.githubusercontent.com/0ac27ab22ea56300b029cae5644b0b0f1a1df7b460981875722afe1e15ef42ea/68747470733a2f2f692e696d6775722e636f6d2f336c54734257512e706e67" alt=""><figcaption></figcaption></figure>

Atributos de la clase LoginTemplate.

Esto permite que cualquier entorno interno (Método) dentro de la clase pueda conocer cada uno de estos objetos gráficos. Por ejemplo si en un caso hipotético se realizara la declaración de los paneles dentro del método **crearJPanels()** estos objetos gráficos solo existirían dentro de ese método y cuando se quiera agregar el JTextField creado en el método **crearJTextFields()** al panel **pDerecha** saltará un error porque para ese método el panel pDerecha no existe.

<figure><img src="https://camo.githubusercontent.com/371baa59fac4001726d87c3cbaeeb09bd3a2c1375a0a342437c15ab7467fc2b6/68747470733a2f2f692e696d6775722e636f6d2f7968544c424b732e706e67" alt=""><figcaption></figcaption></figure>

Error al declarar los paneles dentro de un solo entorno.

Es por esta razón que la declaración se hace de forma global y como atributos de la clase **separando la declaración de la ejemplificación**. La declaración ira siempre al empezar las clases, la ejemplificación ira dentro de cada uno de los métodos.

Aunque no todos los objetos gráficos o decoradores tienen que ser atributos, por ejemplo un **ButtonGroup** que solo afecta a los objetos **JCheckBox** se puede crear como variable en el método **crearJCheckBoxes()** y como probablemente este objeto no se necesite para nada más en el futuro se podría tratar como una variable dentro de este método. El programador debe elegir cual de los objetos gráficos y objetos Decoradores necesita declarar globalmente o como variable dentro de un entorno. Sin embargo nunca se sabe cuando se podría necesitar alguno de estos en otro contexto (otras clases) así que es preferible mantener todos los objetos gráficos y los objetos Decoradores como atributos de la clase.

### Ejecución de métodos de creación desde el constructor

Una vez pasados todos los objetos gráficos y objetos Decoradores a sus respectivos métodos, el constructor se verá así:

<figure><img src="https://camo.githubusercontent.com/ff9c8ac1dda96bd47c3439daa9f53f25f06f140ee5b6ef0646ce324999fb811d/68747470733a2f2f692e696d6775722e636f6d2f474275594168672e706e67" alt=""><figcaption></figcaption></figure>

Constructor después de hacer los métodos de creación.

Se puede notar que lo único que esta dentro del constructor es la configuración de la ventana. Si se ejecuta la aplicación se observa que no se verá nada.

<figure><img src="https://camo.githubusercontent.com/9444b6a27104b5bb484ecd123090d6d4d19b883185489727a9079a95097c9159/68747470733a2f2f692e696d6775722e636f6d2f70564f7668457a2e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario después de hacer los métodos de creación.

Esto es por que se debe que llamar desde el constructor a los métodos de creación. Por ejemplo al llamar estos 4 métodos de creación :

<figure><img src="https://camo.githubusercontent.com/67e40679db710c71baed6408a1c0a1039c69d595cd0b283957d8c5cb76ad5436/68747470733a2f2f692e696d6775722e636f6d2f49614c463541572e706e67" alt=""><figcaption></figcaption></figure>

Constructor después de hacer los métodos de creación.

La aplicación se vera así.

<figure><img src="https://camo.githubusercontent.com/d3a4b61e60b80325beaa3559d2c78c881bd6af4a25bb2c719e0f698d187dceed/68747470733a2f2f692e696d6775722e636f6d2f734542324244392e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario con la llamada de algunos métodos de creación.

Por lo que es necesario llamar a todos estos métodos de creación dentro del constructor.

### Organización en el eje Z y de métodos de creación

Se debe tener en cuenta la organización de los objetos con respecto al eje z como se discutió en la lección anterior. Eso quiere decir que hay que tener cuidado en el **orden en que se van a llamar los métodos**. Por ejemplo:

* Si llamamos el método **crearJTextFields()** antes del método **crearJPanels()** ocurrirá un error por que no es posible añadir un objeto gráfico a un panel que aun no se ha creado.

<figure><img src="https://camo.githubusercontent.com/26ec7137519b02b9079cfc9e3d80a3f240f8b7a14aa981aba41393dcd040ece8/68747470733a2f2f692e696d6775722e636f6d2f3061744a5033662e706e67" alt=""><figcaption></figcaption></figure>

Error por que no se ha creado los JPanel previamente.

* Si llamamos el método **crearObjetosDecoradores()** después de llamar cualquier otro método que crea objetos gráficos en los que se incorporan objetos decoradores ocurrirá un error.

<figure><img src="https://camo.githubusercontent.com/8e0a739d814cc234aeddc22a5b68051e6d6fd3293aaeb572ed2874368ad206c0/68747470733a2f2f692e696d6775722e636f6d2f753357477a73572e706e67" alt=""><figcaption></figcaption></figure>

Error por que no se ha creado los objetos decoradores previamente.

* Si llamamos el método **crearJLabels()** antes de llamar el método de **crearJButtons()** el fondo del login tapara los botones en el panel **pIzquierda**.

<figure><img src="https://camo.githubusercontent.com/37f054c20d9ca1e0a6c0aac1440a0cf956b3ac71b43404bca8a4743affec052e/68747470733a2f2f692e696d6775722e636f6d2f67506442617a562e706e67" alt=""><figcaption></figcaption></figure>

Los botones del panel pIzquierda no se ven por que están tapados por el fondo.

Entonces es necesario que el programador tenga en cuenta la organización en la llamada de los métodos de creación. Una organización apropiada para este caso puede ser:

<figure><img src="https://camo.githubusercontent.com/8d6356cf7eb58caef2e01b5a085283620d1ac838c98882b31a84f691e2928b45/68747470733a2f2f692e696d6775722e636f6d2f67637a627843652e706e67" alt=""><figcaption></figcaption></figure>

Organización correcta en la llamada de los métodos de creación.

### Ventajas de este enfoque

El código esta más organizado, cuando se quiera cambiar la configuración de algún botón ya no será una tarea tediosa el tener que encontrarlo dentro del constructor, ahora solo hay que enfocarse en el método encargado de la creación de botones y cambiar lo que sea necesario.

Ademas para poder concentrarse aun mejor en una parte del código, el editor de texto da la posibilidad de minimizar el código por métodos y así enfocarse en una sola parte de este.

<figure><img src="https://camo.githubusercontent.com/ad7b78142d4f002ad592f75e0bfa81d5101b7c626c6fe3383f91e17d4ff5bf95/68747470733a2f2f692e696d6775722e636f6d2f5150394275587a2e706e67" alt=""><figcaption></figcaption></figure>

Minimización de código por métodos.

## Optimización de código

Ya se vio la forma de como crear los objetos gráficos para ser mostrados en pantalla y como crear objetos decoradores para incorporarlos en los primeros. Sin embargo, son muchas las configuraciones que hay que aprender y es mucho el código que se extiende en las clases para la creación de estos objetos gráficos. Si la interfaz Gráfica de usuario tiene 20 botones por ejemplo se debe realizar el proceso de creación 20 veces y no solo gasta tiempo sino que requiere la memorización de muchas configuraciones y el código se hará más y más largo.

Una alternativa a esto es la creación de una clase que se encargue de proporcionar un servicio, este servicio será el de la construcción de los objetos gráficos de forma genérica de tal manera que para crear uno objeto gráfico solo se tenga que llamar al servicio, pasar los parámetros correspondientes y este retorne el objeto construido. A continuaron se va a explicar como realizar este servicio.

**Nota**: _A continuación se tratara con un tema relacionado a los servicios, esta sesión no tiene como finalidad explicar que son los servicios asi que solo se dará una breve explicación de ellos a medida que se avanza, sin embargo en clases posteriores se va a explicar su concepto y finalidad. Estos servicios tampoco están relacionados al concepto de servicios web._

Dentro del proyecto en el paquete **app** se crea un nuevo paquete llamado **services** y dentro se crea una clase llamada **ObjGraficosService**.

<figure><img src="https://camo.githubusercontent.com/2ef5b35222aad9869c52b75555ff6cca4c98c210490839816aa3a24a77d2a230/68747470733a2f2f692e696d6775722e636f6d2f7a454939726f532e706e67" alt=""><figcaption></figcaption></figure>

Creación de paquete services y servicio para la construcción de objetos gráficos.

Cabe resaltar que los servicios que se crean en el proyecto tendrán el nombre de la clase (arbitrario) seguido de la palabra **Service**.

La clase **ObjGraficosService** se encargará de la **construcción** de los objetos gráficos a traves de métodos que se podrán usar desde cualquier clase **Template** dentro del proyecto. Para garantizar lo anterior dicho, debemos crear un mecanismo para que cualquier clase dentro de la aplicación pueda llamar al objeto del servicio y pueda usar sus métodos pero a su vez **este objeto solo se cree una vez para todas las clases.**

#### **Paréntesis**

Antes se hablo de las 4 etapas de la creación de un objeto gráfico:

* **Declarar**
* **Ejemplificar**
* **Configurar**
* **Adicionar**

Note que se esta hablando del termino que es la **construcción** de un objeto, este termino hace referencia a la generalización de 2 de las 4 etapas que son la de **ejemplificar** **configurar** quedando:

* **Declarar**
* **Construir** **(Ejemplificar, Configurar)**
* **Adicionar**

Por lo que el servicio se va a encargar de realizar justamente la etapa de construcción de los objetos.

### Singleton

Es importante que este servicio se cree una sola vez en memoria. Esto por que va a ser un objeto usado en todas las clases **template** que se creen y si el proyecto tiene 30 clases por ejemplo y si cada una de estas crea un objeto de este servicio se están creando 29 objetos de más innecesarios que consumirán recursos.

Lo primero que se hará es crear su constructor pero su **tipo de acceso será privado**:

```
private ObjGraficosService(){ }
```

Esto garantiza que no se pueda ejemplificar el objeto desde ninguna otra clase (es decir no se puede hacer **.. = new ObjGraficosService()**).

Dentro de la misma clase **ObjGraficosService** se declarara un objeto **static** del tipo de la misma clase del servicio:

```
static private ObjGraficosService servicio;
```

Ahora se crea un método **static** que se encarga de la ejemplificación del objeto de este servicio y retornarlo a quien lo necesite.

```
public static ObjGraficosService getService(){
    if(servicio == null) servicio = new ObjGraficosService();
    return servicio;
}
```

Se pueden notar varias cosas del método anterior:

* La palabra clave **static** asegura que el método dentro de este servicio pueda ser llamado desde cualquier otra clase sin necesidad de ejemplificar el objeto anteriormente.
* En el atributo de la clase se pone el **static** también por que las variables que se trabajen dentro de un método **static** deben serlo también.
* El método retorna un objeto de la propia clase. Esto quiere decir que es la misma clase la única encargada de su propia ejemplificación.
* la condición **if** asegura la ejemplificación única del objeto del servicio, si este es nulo lo ejemplifica y lo retorna, cosa que ocurrirá la primera vez que se llame al método. Pero en las posteriores llamadas al método, como el objeto ya fue ejemplificado previamente ya no entrara al if y lo retornara simplemente.
* Este método que acabamos de realizar es conocido como **Patron Singleton** y hace parte de los patrones creacionales de diseño.

Ahora en la clase **LoginTemplate** podemos obtener el objeto del servicio llamando a este método de la siguiente manera:

* Primero se importa el servicio

```
import app.services.ObjGraficosService;
```

* Se declara el objeto:

```
// Al inicio de la clase
private ObjGraficosService sObjGraficos;
```

La declaración de los objetos de los servicios inician con una s en minúscula seguido de la variable (objeto) arbitraria.

* Se obtiene su ejemplificacíon dentro del constructor (Esta sera la primera linea de código en el constructor).

```
// Dentro del constructor
sObjGraficos = ObjGraficosService.getService();
```

Como esta es la primera clase que llama a este método el objeto del servicio se ejemplificará, pero mas adelante cuando otra clase **template** realice el mismo proceso obtendrá el objeto que ya se había ejemplificado previamente.

Ahora se verá un acercamiento de como serán los métodos de que encapsulan la construcción genérica de los objetos gráficos dentro del servicio:

### JPanel

Dentro del servicio se puede encapsular la construcción de paneles, para esto declaramos un objeto gráfico tipo JPanel y lo configuramos dentro de un método al cual llamaremos **construirJPanel**, este recibirá por parámetros las características necesarias para su correcta construcción.

```
private JPanel panel;
```

```
public JPanel construirJPanel(int x, int y, int ancho, int alto, Color colorFondo, Border borde){
  panel = new JPanel(); 
  panel.setSize(ancho, alto);
  panel.setLocation(x, y);
  panel.setLayout(null);
  panel.setBackground(colorFondo);
  panel.setBorder(borde);
  return panel;
}
```

Podemos observar que este método retorna un objeto tipo JPanel y recibe por parámetros:

* **Posición en x**: Recibe un entero (int).
* **Posición en y**: Recibe un entero (int).
* **Ancho**: Recibe un entero (int).
* **Alto**: Recibe un entero (int).
* **Color de Fondo**: Recibe un objeto decorador tipo Color.
* **Borde**: Recibe un objeto decorador tipo Border.

Adentro se encarga de la **ejemplificación y configuración del objeto gráfico para después retornarlo** por lo que realiza 2 de las 4 etapas de la creación de un objeto gráfico, recordar que estas dos etapas se generalizan en un termino que es la **construcción del objeto**, esta es la razón del nombre del método.

También se puede notar que hay configuraciones por defecto como la anulación del Layout Manager para ser posicionado por el desarrollador.

Ahora desde la clase **LoginTemplate** es posible llamar a este método buscando un panel dentro del método encargado de la creación de paneles:

```
pIzquierda = sObjGraficos.construirJPanel(0, 0, 600, 500, Color.WHITE, null);
this.add(pIzquierda);
```

**Note varias cosas importantes:**

* La creación de un JPanel se redujo de 6 lineas de código a solo 2.

<figure><img src="https://camo.githubusercontent.com/a02ff30aa3e14954d97cafa14952328898bc50b0597e963287cab2e3b48eaee6/68747470733a2f2f692e696d6775722e636f6d2f663131704268772e706e67" alt=""><figcaption></figcaption></figure>

Comparación de creación de un JPanel de forma habitual o con el servicio.

* Los nombres en los parámetros son muy intuitivos esto quiere decir que ya no se tiene que recordar el nombre exacto de cada método de configuración en el futuro si no que el método explica que se debe enviar.

<figure><img src="https://camo.githubusercontent.com/c032c0358834ab9ded64a674532410c5c85d5c2d108cbb795aa6481249faef61/68747470733a2f2f692e696d6775722e636f6d2f504c486b434c562e706e67" alt=""><figcaption></figcaption></figure>

Parámetros intuitivos en la creación de los objetos gráficos.

* Si un objeto gráfico no contiene alguna propiedad que se pide en el método como es el ejemplo de un borde para el panel simplemente se envía el argumento como **null**.

<figure><img src="https://camo.githubusercontent.com/8c4aa7abe945688509371f2486e103fc44394a9d3eec31f922d4966904a18555/68747470733a2f2f692e696d6775722e636f6d2f45793666436d472e706e67" alt=""><figcaption></figcaption></figure>

Argumento de borde enviado como null ya que no se requiere en el panel.

* Si el desarrollador considera que el código ocupa mucho espacio de forma horizontal puede acomodarlo a su preferencia:

<figure><img src="https://camo.githubusercontent.com/10ac8a087c917739ba5ea31cd07edc6f92a57de6d10ad185c5168fee8b50a1e9/68747470733a2f2f692e696d6775722e636f6d2f6d4b4151526d6d2e706e67" alt=""><figcaption></figcaption></figure>

Otras formas de identar del código.

Se realiza el mismo proceso con el otros paneles dentro del login, en este caso el panel **pDerecha**.

### JButton

Se va a mostrar como se realizaría el método para la construcción genérica de un botón. Y se explica este método en especifico por que es el método de construcción que necesita más parámetros para construir:

* **Declaración:**

```
private JButton button;
```

* **Método de construcción:**

```
public JButton construirJButton(
  String texto, int x, int y, int ancho, int alto, Cursor cursor, ImageIcon imagen, Font fuente,
  Color colorFondo, Color colorFuente, Border borde, String direccion, boolean esSolido
) {
  button = new JButton(texto);
  button.setLocation(x, y);
  button.setSize(ancho, alto);
  button.setFocusable(false);
  button.setCursor(cursor);
  button.setFont(fuente);
  button.setBackground(colorFondo);
  button.setForeground(colorFuente);
  button.setIcon(imagen);
  button.setBorder(borde);
  button.setContentAreaFilled(esSolido);
  switch (direccion) {
    case "l":
      button.setHorizontalAlignment(SwingConstants.LEFT);
      break;
    case "r":
      button.setHorizontalAlignment(SwingConstants.RIGHT);
      button.setHorizontalTextPosition(SwingConstants.LEFT);
      break;
    case "t":
      button.setVerticalTextPosition(SwingConstants.TOP);
      button.setHorizontalTextPosition(SwingConstants.CENTER);
      break;
    case "b":
      button.setVerticalTextPosition(SwingConstants.BOTTOM);
      button.setHorizontalTextPosition(SwingConstants.CENTER);
      break;
    default:
      break;
  }
  return button;
}
```

Podemos observar que el método recibe por parámetros lo siguiente:

* **texto del botón:** Recibe un String.
* **posición x:** Recibe un entero (int).
* **posición y:** Recibe un entero (int).
* **ancho:** Recibe un entero (int).
* **alto:** Recibe un entero (int).
* **cursor:** Recibe un objeto decorador tipo Cursor.
* **imagen:** Recibe un objeto decorador tipo ImageIcon.
* **fuente:** Recibe un objeto decorador tipo Font.
* **color de Fondo**: Recibe un objeto decorador tipo Color.
* **color de Fuente:** Recibe un objeto decorador tipo Color.
* **borde:** Recibe un objeto decorador tipo Border.
* **dirección:** Recibe un String que representa la posición horizontal de lo que contenga el botón. Esta puede ser:
  * 'c' (CENTER): Contenido centrado (por defecto).
  * 't' (TOP): Contenido centrado con texto arriba de una imágen.
  * 'l' (LEFT): Contenido en la izquierda \[Si tiene imágen y texto la imágen se posiciona primero].
  * 'r' (RIGHT): Contenido en la derecha \[Si tiene imágen y texto el texto se posiciona primero].
  * 'b' (BOTTOM): Contenido centrado con texto abajo de una imágen.
* **¿es Solido?:** Recibe un booleano, y pregunta si se quiere crear un botón solido o transparente. Si se manda en True dejara las propiedades de contenido de Java, si se pasa como False le quitara esas propiedades dejándolo transparente.

Ahora desde la clase **LoginTemplate** se puede llamar a este método para la construcción de los botones, para lo que se entra al método encargado de la creación de los botones. A continuación se muestran 2 botones diferentes para ver algunas particularidades:

```
bEntrar = sObjGraficos.construirJButton(
  "Entrar", 
  (pDerecha.getWidth() - 250) / 2, 330, 250, 45, 
  cMano, 
  null, null, 
  colorPrincipal, 
  Color.WHITE, 
  null, 
  "c", 
  true
);
pDerecha.add(bEntrar);

iDimAux = new ImageIcon(
  iCerrar.getImage()
    .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
);

bCerrar = sObjGraficos.construirJButton(
  null, 
  350, 10, 45, 30, 
  cMano, 
  iDimAux, 
  null, null, null, null, 
  "c", 
  false
);
pDerecha.add(bCerrar);
```

Se puede observar lo siguiente en la creación de los dos anteriores botones:

* **Primer botón:**
  * Este botón contiene texto asi que se enviá en forma de comillas " ".
  * Va posicionado en la mitad del panel por lo que se envía el calculo, solo que ahora enviando el ancho del botón como numero directamente.
  * Tiene incorporado un cursor y se envía como argumento.
  * Tiene color de fondo y color de fuente por lo que se envía como argumento.
  * No contiene ni un borde ni una imagen ni una fuente asi que se envía como argumentos null.
  * Su contenido esta centrado por lo que se envía una "c" como argumento.
  * Como este botón tiene color de fondo entonces es un botón solido y se envía True.
* **Segundo botón:**
  * Este botón no tiene texto asi que se enviá null como argumento.
  * Este botón contiene una imagen, pero esta debe ser previamente redimensionada para que al enviarse quede como se quiere.
  * Tiene incorporado un cursor y se envía como argumento.
  * No contiene ningún color asi que se envía como argumentos null.
  * No contiene ni un borde ni una fuente asi que se envía como argumentos null.
  * Su contenido esta centrado por lo que se envía una "c" como argumento.
  * Como este botón no tiene color de fondo entonces es un botón transparente y se envía un False como parámetro.

Se debe hacer uso del servicio para crear los otros botones en la clase **LoginTemplate**. Si se corre la aplicación se puede verificar que corre perfectamente y se ve igual a como estaba, esto quiere decir que el servicio esta funcionando correctamente:

<figure><img src="https://camo.githubusercontent.com/51a811d97bd5566a53555f2dabb22aa55c47db1cbc2f49874e787a6dde2c9687/68747470733a2f2f692e696d6775722e636f6d2f4f4f616d6948572e706e67" alt=""><figcaption></figcaption></figure>

Interfaz gráfica funcionando correctamente con la incorporación del servicio ObjGraficosService.

El resto de métodos del servicio esta contenido dentro de este repositorio, puede observar todo el código entrando a la carpeta **Clase4** luego a la carpeta **src/app** seguido de la carpeta **services** y entrando a la clase **objGraficosService.java**. Allí podrá ver una versión actualizada del servicio con su debida documentación para empezar a implementarlos desde la clase **LoginTemplate** y así realizar la optimización del código.

<figure><img src="https://camo.githubusercontent.com/68bfe2e9075287e83c696811828d737e748c48557294ef00443559cbdeb6754d/68747470733a2f2f692e696d6775722e636f6d2f3675754b6e79772e706e67" alt=""><figcaption></figcaption></figure>

Carpeta Clase4 dentro del repositorio.

<figure><img src="https://camo.githubusercontent.com/9d82d85c16255bbb38197cec7d0f2e27c862ac37170f24f6252ae9fc2d8f449a/68747470733a2f2f692e696d6775722e636f6d2f75437448517a702e706e67" alt=""><figcaption></figcaption></figure>

Carpeta src/app dentro del repositorio.

<figure><img src="https://camo.githubusercontent.com/e798efd14b50ffa846cb94b01e93eca8184c22dc60bc499974087750adf88c24/68747470733a2f2f692e696d6775722e636f6d2f6c564343344e312e706e67" alt=""><figcaption></figcaption></figure>

Carpeta services dentro del repositorio.

<figure><img src="https://camo.githubusercontent.com/6d60a322c7fd145056b8c8b385a3e5843d437a3ced7443725978df04152cbda3/68747470733a2f2f692e696d6775722e636f6d2f346767785778382e706e67" alt=""><figcaption></figcaption></figure>

Clase ObjGraficosService.java dentro del repositorio.

<figure><img src="https://camo.githubusercontent.com/decc36d45bb4333395fd5056b9a56b46cf108521f3f98db0a0813cacb4b9084c/68747470733a2f2f692e696d6775722e636f6d2f395861486e54452e706e67" alt=""><figcaption></figcaption></figure>

Código del servicio dentro del repositorio.

_**Nota:** Usted puede crear el servicio por su cuenta, sin embargo, la versión proporcionada en el repositorio le sera util ya que esta actualizada y además la documentación de este aporta un soporte adicional cuando se usen los métodos. A continuación se muestra como:_

<figure><img src="https://camo.githubusercontent.com/6caa411dbf120b7501d03a8d26cb30a8c9b9e348880c34ecc914eaca80d1ba40/68747470733a2f2f692e696d6775722e636f6d2f787437615855552e706e67" alt=""><figcaption></figcaption></figure>

Documentación como soporte al usar el servicio.

Una vez haya completado todo el servicio, este estará listo para usarse en todas las clases **template** que se creen posteriormente. Este servicio podrá usarse también en todos sus proyectos frontend para hacer más fácil la creación de objetos gráficos. Recuerde que cuando tenga el servicio completo podrá usarlo en la clase **loginTemplate** para la construcción de todos los objetos gráficos y probar que todo esta bien corriendo la aplicación.

**Nota:** Una particularidad que vale la pena recalcar es cuando se crea un **JComboBox** a traves del servicio, este recibirá un argumento llamado cadena que representa las diferentes opciones que contendrá el ComboBox y deberán enviarse separando cada una de las opciones con un **"\_"** como se observa a continuación:

<figure><img src="https://camo.githubusercontent.com/29e306bfafcbf55e8a3f603f5a589875004ca06208bbbfb45fa7bdea10207230/68747470733a2f2f692e696d6775722e636f6d2f4159344b306f712e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo creación JComboBox con el servicio.

## Optimización de recursos

Hasta este punto se ha realizado una moduralización del código y ademas una optimización de este. Pero es posible dar un paso más, en esta sección se explica la optimización de recursos. Esto intenta resolver la creación desproporcionada de objetos que estaremos creando en las clases UI.

Se debe hallar una forma de controlar la creación de objetos que muy posiblemente se usen en varias clases. Por ejemplo los objetos decoradores son muy propensos a ser utilizados en diferentes partes del proyecto. Por ejemplo, es probable que el cursor que se usa para pasar sobre los botones del login sea usado también en otras clases que tengan botones también. El color principal posiblemente se usará en la clase **VistaPrincipalTemplate** y en muchas otras más.

Imagine que por cada clase **template** dentro del proyecto se crea un objeto nuevo para el cursor de mano que pasa sobre los botones o varios objetos para usar las mismas fuentes, colores, bordes o imágenes. La cantidad de recursos en memoria sería exorbitante.

Se va a crear a continuación otro servicio llamado **RecursosService** y se realiza el mismo mecanismo de única ejemplificación explicada previamente.

<figure><img src="https://camo.githubusercontent.com/7c5bf6238aa3996bbd5f89ee0a4334814e7a64264f9bbf74ce39f7df9fad7971/68747470733a2f2f692e696d6775722e636f6d2f62524a724664692e706e67" alt=""><figcaption></figcaption></figure>

Creación de servicio Recursos en paquete Servicios.

<figure><img src="https://camo.githubusercontent.com/2f41d4fc9a3ce491831658b76e376ce8c57b98c411e803e2efc63f57e0df41b1/68747470733a2f2f692e696d6775722e636f6d2f4e7838724f61782e706e67" alt=""><figcaption></figcaption></figure>

Creación de servicio Recursos.

Ahora en la clase **loginTemplate** se debe igualmente obtener el objeto de este servicio:

**importación**

```
import app.services.RecursosService;
```

**declaración**

```
private RecursosService sRecursos;
```

**obtención de servicio**

```
sRecursos = RecursosService.getService();
```

Veamos que objetos decoradores se pueden usar en varias clases **template**:

* El cursor de mano para los botones seguramente se use en varias clases que tengan botones.
* Los colores también se usaran en varias partes del proyecto, es común que un proyecto entero de Interfaz Gráfica de usuario maneje una gama especifica de colores.
* Las fuentes se usaran claramente en otras clases, no todas las fuentes se usaran en todo el proyecto podrían existir unas particulares en una clase pero es bueno manejar una tipografía común en todas las interfaces de un mismo proyecto.
* El borde azul en la parte inferior es probable que se utilice en otras clases que contengan JTextField.
* La imágen de cerrar ventana se podría volver a utilizar en la Vista principal.

Ahora se va a realizar la creación de estos objetos decoradores en el servicio (se pueden crear dentro del constructor del servicio o modularizar por métodos encargados de la creación de objetos decoradores dentro del servicio). Una vez estos estan creados en el servicio se pueden borrar en la clase **LoginTemplate**:

<figure><img src="https://camo.githubusercontent.com/ef4a6e275830ae65d9b8791f12de4c5eabebe31ed8cfd04b251c2b2795c3fb0e/68747470733a2f2f692e696d6775722e636f6d2f3478686537474c2e706e67" alt=""><figcaption></figcaption></figure>

Objetos decoradores que se pueden a utilizar en varias partes del proyecto creados dentro del servicio.

Por otro lado el método que se encarga de generar las fuentes puede ir dentro del servicio ya que este al encargarse primordialmente de objetos decoradores debe también encargarse de temas como estos y como se ve en la anterior imágen este debe ser el primer método en ser llamado para asegurar la visualización de las fuentes:

<figure><img src="https://camo.githubusercontent.com/02df1a32bc20377ff69197e9f6953daa14e412ce2dfed510559589388c7e4e79/68747470733a2f2f692e696d6775722e636f6d2f5258377a394a6c2e706e67" alt=""><figcaption></figcaption></figure>

Método encargado del registro de fuentes dentro del servicio recursos.

Por otro lado dentro de la clase LoginService ahora solo se tienen estos objetos decoradores:

<figure><img src="https://camo.githubusercontent.com/0c889be7f830756a6785e992bb0841f33875f890e834d5662cb825181a36a761/68747470733a2f2f692e696d6775722e636f6d2f4a45476559496c2e706e67" alt=""><figcaption></figcaption></figure>

Objetos decoradores que serán necesarios unicamente en la clase LoginTemplate.

<figure><img src="https://camo.githubusercontent.com/e4948c0e2ba27c648ea13474d9546c418a5d7d5cfade6df33695dfa05d0e5fc0/68747470733a2f2f692e696d6775722e636f6d2f44765a737771312e706e67" alt=""><figcaption></figcaption></figure>

El método crearObjetosDecoradores de la clase LoginTemplate con solo los objetos decoradores necesarios unicamente en esa clase.

Ahora para que cualquier clase **template** pueda obtener los objetos decoradores a traves del servicio es necesario crear unos métodos **get** que retornen estos objetos:

```
public Color getColorPrincipal(){ return colorPrincipal; }

public Color getColorGrisOscuro(){ return colorGrisOscuro; }

public Font getFontTPrincipal(){ return fontTPrincipal; }

public Font getFontTitulo(){ return fontTitulo; }

public Font getFontSubtitulo(){ return fontSubtitulo; }

public Cursor getCMano(){ return cMano; }

public Border getBorderInferiorAzul(){ return borderInferiorAzul; }

public ImageIcon getICerrar(){ return iCerrar; }
```

El servicio esta listo para ser usado. Ahora desde la clase **LoginTemplate** cuando se necesite uno de estos objetos decoradores solo se llama al servicio seguido del método **get** que se necesite. A continuación un ejemplo de esto:

<figure><img src="https://camo.githubusercontent.com/a844c41f5e6f1d3ed228b192805ae48b1146799bced1c2f56a320c7b10489012/68747470733a2f2f692e696d6775722e636f6d2f67616b6a3847352e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo de implementación de servicio de Recursos para obtener objetos decoradores compartidos entre clases.

Se debe hacer esto con todos los objetos decoradores que necesarios de la clase **LoginTemplate** y correr la aplicación para verificar que esta ocurriendo todo con normalidad.

<figure><img src="https://camo.githubusercontent.com/51a811d97bd5566a53555f2dabb22aa55c47db1cbc2f49874e787a6dde2c9687/68747470733a2f2f692e696d6775722e636f6d2f4f4f616d6948572e706e67" alt=""><figcaption></figcaption></figure>

Interfaz gráfica funcionando correctamente con la incorporación del servicio RecursosService.

Ahora si por ejemplo en la clase **VistaPrincipalTemplate** es necesario utilizar alguno de estos objetos decoradores como el color principal para dejar el fondo de la ventana con ese color simplemente basta con llamar al servicio para obtenerlo:

<figure><img src="https://camo.githubusercontent.com/009585c5b4e792ef3e7f2ccbd544c7b5f945ebde89fb4572df7557c87b45cdbe/68747470733a2f2f692e696d6775722e636f6d2f7a6d326a326c582e706e67" alt=""><figcaption></figcaption></figure>

Servicio Recursos utilizado en la clase VistaPrincipalTemplate para obtener el color principal.

<figure><img src="https://camo.githubusercontent.com/cef9ce23c3d80acb1d0eb62f2e521c103384efd052f4b85e1fc514e7d0a5969e/68747470733a2f2f692e696d6775722e636f6d2f4b5075374631322e706e67" alt=""><figcaption></figcaption></figure>

Ventana VistaPrincipalTemplate.

Aunque el objeto decorador **colorPrincipal** se ve reflejado en dos ventanas distintas solo existe una vez en memoria. De igual forma el servicio **RecursosService** solo existirá una vez en memoria sin importar en cuantas clases sea llamado.

## Orden adicional

Si alguno de los métodos de creación hasta el momento queda demasiado largo es posible que sea difícil identificar donde esta cada objeto gráfico, una buena forma de dar un orden adicional es mediante comentarios que servirán de títulos y guiás indicándo donde esta cada objeto gráfico, esto no es obligatorio y es preferible usarlo en métodos de creación que quedan muy largos, en este caso se realizara para los métodos **crearJButtons** y **crearJLabels**:

<figure><img src="https://camo.githubusercontent.com/ac5b4bbaf57eb7769472f86b8e5999ec876d3d0304b51def1a031b9ce17b13fa/68747470733a2f2f692e696d6775722e636f6d2f51374a3248304d2e706e67" alt=""><figcaption></figcaption></figure>

Creación de comentarios que guían la creación de objetos gráficos

## Resultado

Si has llegado hasta aquí **!Felicidades!** ahora no solo se tiene una interfaz gráfica agradable para el usuario, también se tiene un código mucho más organizado, modularizado, optimizado, responsable con los recursos y mantenible.

En la siguiente clase se va a revisar el concepto de **Componente gráfico** y su importancia en la creación de interfaces gráfica con proyectos grandes. También se se introducirá a los eventos empezando con los eventos básicos de acción.

## Actividad

Implementar los servicios de construcción de objetos gráficos y de recursos para agregar optimización de código y recursos en los Login propios. Ademas de realizar modularizacion en el código.

## Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 5

### Objetivos

* Comprender el termino general de componente gráfico, como identificarlos para su construcción en una interfaz gráfica y de que partes esta compuesto dicho componente.
* Aprender el uso de eventos por acción para generar interactividad a las interfaces gráficas de forma general.
* Generar una discriminación de eventos para una especificación de acciones y explorar las distintas formas de hacerse.
* Explicar y realizar preparativos previos para la implementación de una aplicación **Single-Page App**.

## Antes de comenzar

En la sesión anterior se realizó la incorporación de nuevos servicios encargados proveer una lógica que ayudan a que el código este optimizado y exista un control con la creación de objetos compartidos.

#### **Ajustes en la clase VistaPrincipal**

En la clase **VistaPrincipal** ya se esta haciendo uso del servicio **RecursosService**, ahora se va a obtener el servicio **ObjGraficosService** ya que se va a utilizar en el futuro:

**Declaración:**

```
private ObjGraficosService sObjGraficos;
```

**Obtención de Servicio:**

```
sObjGraficos = ObjGraficosService.getService(); // dentro del constructor
```

#### **Ajustes en el servicio Recursos Service**

Se va a crear un nuevo color en el servicio **RecursosService** este será el colorSecundario y se usará en varios componentes gráficos en el futuro.

**Declaración**

```
// Al inicio de la clase
private Color colorSecundario;
```

**Ejemplificación**

```
// Dentro del método crearColores
colorSecundario = new Color(151, 0, 158);
```

**Método get**

```
public Color getColorSecundario(){ return colorSecundario; }
```

#### **Estructura de la aplicación**

La estructura de la aplicación puede observarse mediante un diagrama de clases y este hasta el momento se representa así:

<figure><img src="https://camo.githubusercontent.com/966cd9bb8c2ba08c78fb437fb90014518fdd9e6ffbd49f55db29d547548611d1/68747470733a2f2f692e696d6775722e636f6d2f4c4649323950742e706e67" alt=""><figcaption></figcaption></figure>

Modelo Estructural de clases aproximado del proyecto hasta el momento

El anterior modelo estructural muestra de forma general y aproximada como esta conformado el proyecto, ademas de resaltar que paquetes y dependencias existen hasta el momento.

#### **Recordatorio**

Recordando un poco el recorrido se creo la clase **LoginTemplate** donde su código ya se modularizó y optimizó. La interfaz gráfica se ve asi:

<figure><img src="https://camo.githubusercontent.com/e822717467d8a2c0cfdd012b37c838a83439b7a2cced835d1a35a7674978795c/68747470733a2f2f692e696d6775722e636f6d2f4c6f564c756c352e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario del proyecto

También se tiene la clase **VistaPrincipalTemplate** que esta vacía y tiene un color de fondo así:

<figure><img src="https://camo.githubusercontent.com/6fb7c66650d830e946f08f6afb0d56fee9e210de47c39a3660ebc79a1ee607d6/68747470733a2f2f692e696d6775722e636f6d2f4c4b6c6154764a2e706e67" alt=""><figcaption></figcaption></figure>

Vista Principal del proyecto

## Componentes Gráficos y Eventos por Acción

En esta sesión se van a abarcar 3 Temas principales cada uno con sus respectivos items, relacionados con componentes gráficos, eventos y preparación de una Single Page App:

### Temas

* **Componentes Gráficos**.
  * **Concepto general de Componente Gráfico**.
  * **Creación de un componente Gráfico y sus partes**.
  * **Explicación Inyección de dependencias**.
* **Eventos: ActionListener (Evento por acción)**.
  * **Discriminación por Texto o Comando**.
  * **Discriminación por Objeto**.
  * **Obtención de información desde formularios**.
  * **Abriendo otras ventanas**.
* **Preparación para construcción de una Single-Page App**.

## Componentes Gráficos

### Concepto general de Componente Gráfico

Muchos proyectos normalmente necesitan bastantes interfaces gráficas para soportar todos los requerimientos, funcionalidades y datos que un cliente necesita en la aplicación. Se podría crear una ventana separada por cada vista que se quiere mostrar al cliente, sin embargo, las aplicaciones actuales se caracterizan por manejar toda su información, acciones y vistas a traves de una sola ventana. Esto se conoce como una aplicación **Single-Page App**.

<figure><img src="https://camo.githubusercontent.com/943fce6f1854b210e2b5dfcb5167b6fbf2647b3bf8f8b32ed4c91776a5110906/68747470733a2f2f692e696d6775722e636f6d2f6e6b6538534e302e706e67" alt=""><figcaption></figcaption></figure>

Spotify ejemplo de una aplicación Single-Page App

Un ejemplo es la aplicación de escritorio de **Spotify**, puede notar que cuando se usa este programa en el computador este no esta abriendo una ventana nueva por cada botón que se oprime. La aplicación se encarga de gestionar qué elementos mostrar en la misma ventana y qué elementos ocultar dependiendo de la petición del usuario.

Si todo el código de la aplicación estuviera contenido en un solo archivo que representa la única ventana sería realmente desastroso, habría una cantidad inmensa de objetos gráficos en una sola clase, una cantidad de lineas de código incalculable y el entendimiento y mantenibilidad del código serían muy difícil.

Una buena forma de tener un código organizado, con una responsabilidad clara de cada parte del proyecto y una modularidad coherente es mediante la implementación de **Componentes gráficos**. De esta forma las aplicaciones estarán separadas adecuadamente y manteniendo una coherencia repartida que será mucho mas fácil de entender. Por ejemplo una posible separación por componentes para la aplicación de Spotify seria la siguiente:

<figure><img src="https://camo.githubusercontent.com/f00f7ccdac85f6174d7f90a9a305f0cb1855b6012921e42c483bc71f104aca15/68747470733a2f2f692e696d6775722e636f6d2f6c4e6c6b776e792e706e67" alt=""><figcaption></figcaption></figure>

Spotify posible componetización de la aplicación

De la anterior imágen se puede observar varias particularidades:

* Un Componente gráfico puede contener a otros componentes, por ejemplo el **Componente Panel Principal** contiene varios componentes mas.
* Un Componente puede cambiar de contenido, por ejemplo si el usuario escoge una lista o si oprime cualquier botón es muy probable que el **Componente Panel Principal** remueva su contenido y llame a otros componentes para satisfacer lo que quiera ver el usuario.
* Un componente puede ser **reutilizable**, note por ejemplo que el **componente Recomendaciones** se esta llamando varias veces y no se necesita crear distintas clases para mostrarlo en pantalla las veces que sea necesario, simplemente se puede reutilizar. Incluso si en otra parte de la aplicación se requiera este componente podría fácilmente ser llamado y usarse nuevamente.
* Cada componente cumple una función especifica lo que le da la cualidad a la aplicación de dividir responsabilidades y ademas es mucho mas fácil asi comprender el código de una sola parte en especifico que de toda la aplicación junta.

La componetización de una aplicación depende del programador, se podría ser demasiado riguroso y crear un componente gráfico por cada aspecto, o se podrían crear algunos grandes componentes gráficos que conformen toda la aplicación.

A continuación se verá como esta conformado un **componente gráfico**.

### Creación de un componente Gráfico y sus partes.

Un componente gráfico en Java se conforma principalmente de 2 clases:

* **Clase Template:** Que se encarga unicamente de la muestra de objetos gráficos por pantalla ademas de la muestra de información que el usuario requiera y es el medio por el cual el usuario podrá interactuar, mostrar y recolectar información.
* **Clase Component:** Esta clase es la encargada de soportar la lógica del componente. Esta incluye el manejo de eventos, el manejo de la información a mostrar o recolectar en la clase Template, el llamado a servicios lógicos necesarios para la traer o entregar información externa etc.

Para crear el primer componente gráfico se crea la clase **LoginComponent** que estará ubicada dentro del paquete **login**:

<figure><img src="https://camo.githubusercontent.com/b0adc0fb497460ed43fe5cdf7ea375ca93a193ec3aa6da3646b1212a227bc8bf/68747470733a2f2f692e696d6775722e636f6d2f5753504955426b2e706e67" alt=""><figcaption></figcaption></figure>

Creación clase Component dentro del paquete vistaPrincipal

A continuación se explican ciertas características de cada una de las clases que conforman un componente.

_**Nota:** Aunque ya se ha trabajado con clases Template habrán nuevas características que serán necesarias e importantes._

#### **Clase Template**

Esta clase se encargara unicamente de mostrar en pantalla los diferentes objetos gráficos con las que el usuario interactuará, ademas mostrará los valores obtenidos de la lógica realizada por la clase **Component**.

Se caracteriza por:

* Hereda de una clase que le da propiedades gráficas y ademas tenga la capacidad de contener objetos gráficos, estas podría ser por ejemplo **JFrame**, **JPanel**, **Canvas** etc. Esta es la clase que va a ser mostrada al usuario.

<figure><img src="https://camo.githubusercontent.com/a30cae68102d64f86e185f7b3527b5e27e6926fb852af56c9ee62ff9b02df9c7/68747470733a2f2f692e696d6775722e636f6d2f7435375678684e2e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo Herencia en clase Template

Note que aunque en este ejemplo y hasta el momento se han creado clases **Template** que heredan de un **JFrame** también puede heredar de un **JPanel** por ejemplo.

* Importa las librerías necesarias para crear objetos gráficos y mostrarlos en pantalla.
* Recibe como parámetro en el constructor un objeto de la clase **Component** y la iguala a un objeto declarado de la misma referencia, esta técnica es llamada **inyección de dependencia** y se explica más adelante en esta lección.

<figure><img src="https://camo.githubusercontent.com/c600775ef89ad105473a8fdd2c8a074a6a805167235f3ab7faefdafff2ea8516/68747470733a2f2f692e696d6775722e636f6d2f38796f49435a552e706e67" alt=""><figcaption></figcaption></figure>

Inyección de la clase Component

Algo que se debe aclarar es que una vez es recibido el objeto desde el constructor se realiza esa igualdad para que el objeto recibido sea conocido por toda la clase (atributo) de lo contrario el objeto solo existiría para el constructor y no para los otros métodos que puedan necesitar una comunicación con la lógica del componente.

* Para que la clase **Component** pueda realizar acciones sobre los objetos gráficos, la clase **Template** deben contener métodos **get** de los objetos gráficos que serán necesarios manipular en la parte lógica. Por ejemplo para la clase **LoginTemplate** se generan los siguientes:

```
public JButton getBCerrar(){ return this.bCerrar; }

public JButton getBEntrar(){ return this.bEntrar; }

public JButton getBRegistrarse(){ return this.bRegistrarse; }

public JButton getBOpcion1(){ return this.bOpcion1; }

public JTextField getTNombreUsuario(){ return this.tNombreUsuario; }

public JPasswordField getTClaveUsuario(){ return this.tClaveUsuario; }

public JComboBox<String> getCbTipoUsuario(){ return this.cbTipoUsuario; }

public JCheckBox getCheckSi(){ return this.checkSi; }

public JCheckBox getCheckNo(){ return this.checkNo; }
```

#### **Clase Component**

Esta clase se encarga de manejar toda la lógica que la clase **Template** podría necesitar, esta puede incluir manejo de eventos (cuando se oprime un botón con el mouse, cuando se oprime una tecla, cuando se pasa por un objeto gráfico etc.) manejo de servicios para traer información externa, manejo y validación de información etc.

Tiene ciertas Características como:

* Puede implementar las interfaces (interfaz es diferente a interfaz Gráfica) que proporcionan la escucha de eventos en caso de ser necesario, un ejemplo de estas interfaces es **ActionListener** que se encarga de gestionar eventos de acciones como cuando el usuario oprime un botón. Puede implementar también otras interfaces que gestionan otro tipo de eventos como **MouseListener**, **MouseMotionListener**, **KeyListener** etc. Ademas se pueden implementar dos o mas interfaces desde una misma clase **Component**.

<figure><img src="https://camo.githubusercontent.com/c601c97cb38b61163412233c401d0d83a116f476d584275ba38efc9fe16a088d/68747470733a2f2f692e696d6775722e636f6d2f4e4451475379502e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo de implementación de una interfaz

* Cuando se implemente cualquier interfaz esta pedirá que por obligación se implementen también los métodos de dicha interfaz. En este ejemplo la Interfaz **ActionListener** exige la implementación del método **actionPerformed**, por lo general el IDE o editor de código informará la advertencia y se podrá implementar de forma automática los métodos que se exigen.

<figure><img src="https://camo.githubusercontent.com/d338ec1a07a0158c1a0fd1738659cf6e00ca517f2646130accba45d88940776d/68747470733a2f2f692e696d6775722e636f6d2f6443716a485a672e706e67" alt=""><figcaption></figcaption></figure>

Método implementado de la interfaz ActionListener

_**Nota:** El decorador **@Override** indica que una clase esta implementando y sobre-escribiendo un método que proporciona cierta interfaz, este decorador es clave ya que el compilador sabe a traves de este que el método fue implementado y dará ciertas capacidades._

* Se tiene un objeto del tipo de la clase **template** y para ejemplificar este objeto se debe enviar como parámetro una referencia de si misma, para eso se utiliza la palabra **this**, que indica que se esta enviando como parámetro a la clase misma y asi completar la inyección de dependencia.

<figure><img src="https://camo.githubusercontent.com/a58003a82b9a3663df005fddf4480658896e2816eded7da78d93a69bde751182/68747470733a2f2f692e696d6775722e636f6d2f396f72654f75752e706e67" alt=""><figcaption></figcaption></figure>

Inyección desde la clase Component

* La comunicación entre componentes se realiza exclusivamente mediante el llamado de las clase **Component** de los respectivos componentes, debido a esto, para que se pueda obtener la parte gráfica del componente es necesario crear un método **get** que retorne la clase **Template** y asi se pueda obtener desde otro componente:

<figure><img src="https://camo.githubusercontent.com/969acd59a2dd7dc4db12342d46a57755a4a15ed187acf784d5fe641cfbe19ea8/68747470733a2f2f692e696d6775722e636f6d2f66584d48587a712e706e67" alt=""><figcaption></figcaption></figure>

Método get para que desde otro componente se pueda obtener la clase Template que contiene las características gráficas

**IMPORTANTE!!**

Como la clase **Template** ahora necesita un objeto en su constructor, dentro de la clase ejecutora **App** se va a llamar a la clase **Component** en su lugar.

<figure><img src="https://camo.githubusercontent.com/6f9a6cc90ed89a5afbf9451b669671fc340b1b538a121dfae37176687de6b57b/68747470733a2f2f692e696d6775722e636f6d2f50343553374c642e706e67" alt=""><figcaption></figcaption></figure>

Llamada a la clase LoginComponent desde App

### Otras particularidades

Algunas particularidades adicionales que hay que explicar son:

* Ambas clases deben estar en un único paquete y deben tener una comunicación única bidireccional ya que la clase **Template** necesitará conocer partes de la clase **Component** y viceversa.
* La clase **Template** es una clase aislada y solo es conocida directamente por su clase **Component** que la acompaña.
* Para la comunicación entre varios componentes se realiza siempre llamando a la clase **Component**.

<figure><img src="https://camo.githubusercontent.com/bd3f09db29197af52da659929cda404da97e9e901b0d61e762901232411c4947/68747470733a2f2f692e696d6775722e636f6d2f6f54364263326c2e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo de comunicación entre componentes

<figure><img src="https://camo.githubusercontent.com/d76ae355c86f59237c88fb3e463fb55bff03650e84826d71f7966cd6edd55fb5/68747470733a2f2f692e696d6775722e636f6d2f76564e783431502e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo de comunicación errónea entre componentes

_**Nota:** Aunque se explico previamente que la clase **Component** es la encargada de la comunicación con servicios, existe una excepción con los servicios creados anteriormente ( **ObjGraficosService** y **RecursosService** ) ya que están orientados a la construcción de las clases template y se conocen como **Servicios Gráficos**. Por otra parte los **Servicios Lógicos** están orientados al manejo de datos e información que puede ser obtenida o enviada a entidades externas y esos son los que podrán comunicarse con las clases **Component** de ser necesario. Sobre los servicios existirá una clase que se enfocará en explicar esto con más detalle._

### Explicación Inyección de dependencias

La inyección de dependencias se realiza para que exista una comunicación permanente y bidireccional entre las dos clases que conforman un componente gráfico. Asi cuando la clase **Template** necesite algo de la lógica de la clase **Component** podrá hacerlo a traves de la referencia que obtiene desde el constructor y de igual manera cuando la clase **Component** quiera enviar o recibir información de la interfaz gráfica podrá hacerlo a traves del objeto que referencia a la clase **Template**. A continuación se puede ver un esquema general de un componente Gráfico y en especial como se manifiesta la inyección de dependencias.

<figure><img src="https://camo.githubusercontent.com/7ed5d4d198c5ae87fee5eb8a3ce90d63b9f1acb62951d0c352e30a3974f833c7/68747470733a2f2f692e696d6775722e636f6d2f623772565265722e706e67" alt=""><figcaption></figcaption></figure>

Diagrama de clases de un componente Gráfico

Visto esto en objetos en memoria se ve de la siguiente manera, y se puede denotar una comunicación directa entre los objetos de forma bidireccional:

<figure><img src="https://camo.githubusercontent.com/4c0cee60cc01474ca339880291fc39f89d370fe772f4e2edc7efd6acd7b97c9a/68747470733a2f2f692e696d6775722e636f6d2f476d4530786c562e706e67" alt=""><figcaption></figcaption></figure>

Comunicación bidireccional entre objetos

Una forma diferente (pero errónea) de hacer esto, sería la de la ejemplificación del objeto de la clase contraria de forma individual de la siguiente manera:

* En la clase **LoginComponent**:

<figure><img src="https://camo.githubusercontent.com/00d0632084790c6b01a3e3d98d6ba59dd9da0f3f832aa0533b6ff424d9ff014f/68747470733a2f2f692e696d6775722e636f6d2f486c43316e36722e706e67" alt=""><figcaption></figcaption></figure>

Ejemplificación común desde la clase LoginComponent

Se puede notar que ya no se envía el **this** por parámetro.

* En la clase **LoginTemplate**:

<figure><img src="https://camo.githubusercontent.com/c45f1edceb37e238d1880397b139946ab9e7a00510041ec0bc654344447f53a7/68747470733a2f2f692e696d6775722e636f6d2f494c565567676a2e706e67" alt=""><figcaption></figcaption></figure>

Ejemplificación común desde la clase LoginTemplate

Se puede notar que en este caso ya no recibe nada por parámetro y ejemplifica el objeto como se haría normalmente.

De esta forma se podría pensar que se realizo de manera correcta un canal de comunicación entre ambas clases, sin embargo, si se observa el modelo de objetos es posible darse cuenta que no es asi:

<figure><img src="https://camo.githubusercontent.com/571ac6dbbbc39463f2047b170a07b48cd536298fc0cf511b8f16f8310da500fb/68747470733a2f2f692e696d6775722e636f6d2f37774a597654772e706e67" alt=""><figcaption></figcaption></figure>

Comunicación unidireccional entre objetos

Lo que en realidad sucede es que la clase **LoginComponent** crea un objeto de tipo **LoginTemplate** y la clase **LoginTemplate** crea a su vez **otro** objeto de tipo **LoginComponent** por lo que ahora en tiempo de ejecución hay dos objetos de la misma clase (LoginComponent) y no existe una sola comunicación directa entra ambos objetos.

_**Nota:** El anterior proceso de creación de clase **Component**, implementación de inyección de dependencia se debe realizar también con **VistaPrincipal**._

## ActionListener (Evento por acción)

Un evento ocurre cuando el usuario realiza alguna acción sobre la interfaz gráfica y desencadena un proceso que al final devolverá un resultado (traer información requerida, guardar información, mostrar una parte de la aplicación, cerrar la aplicación etc). Un **ActionListener** es el evento más básico pero a la vez mas importante, se puede realizar con una gran variedad de objetos gráficos aunque lo ideal es que se use con los botones de la interfaz gráfica.

La clase **LoginTemplate** contiene ciertos botones en la ventana, y la clase **LoginComponent** esta implementando la interfaz **ActionListener** y esta lista para recibir eventos. Para poder crear estas acciones se debe realizar una configuración adicional a los botones, esta será **addActionListener**.

```
bEntrar.addActionListener(loginComponent);
```

Se puede observar que el método:

* **addActionListener:** Recibe por parámetro un objeto tipo ActionListener.

Como la clase **LoginComponent** implementa de esta interfaz automáticamente se convierte en un objeto de ese tipo, por lo que es posible enviar como argumento del método el objeto que referencia a esta clase.

**Nota:** Como **addActionListener**es un método de la etapa de **Configuración** deberá estar ubicado justo después de la llamada al servicio y antes de que se adicione el botón:

<figure><img src="https://camo.githubusercontent.com/3b977cbf4470df10bbe0fb15153cf652f1930c9f33cd1d6b86583e49b46fc840/68747470733a2f2f692e696d6775722e636f6d2f716946683731522e706e67" alt=""><figcaption></figcaption></figure>

Se añade método de configuración addActionListener

También se va a adicionar acciones al botón de Registrarse, al botón de cerrar y al botón opción 1:

```
bCerrar.addActionListener(loginComponent);
```

```
bRegistrarse.addActionListener(loginComponent);
```

```
bOpcion1.addActionListener(loginComponent);
```

Ahora en la clase **LoginComponent** se puede probar la escucha de estos eventos, para eso se va a mostrar un mensaje en pantalla como primera prueba. Dentro del método implementado **actionPerformed** se escribe:

<figure><img src="https://camo.githubusercontent.com/698ace0a33ab2dbe3874c75749d3bf82fd789fd4f24241a12872ff400fbef88a/68747470733a2f2f692e696d6775722e636f6d2f513147703646792e706e67" alt=""><figcaption></figcaption></figure>

Prueba 1 del evento

Note que se está llamando un método:

* **JOptionPane.ShowMessageDialog():** Muestra un mensaje de alerta por pantalla a traves de una ventana emergente y recibe por parámetros:
  * **Componente (Ventana):** Recibe como parámetro la ventana relativa donde se quiere mostrar la ventana emergente, si se envía como null, el mensaje se vera en la mitad del monitor, si se enviá el objeto de una ventana, se vera en la mitad de la ventana enviada como parámetro.
  * **Mensaje:** Recibe un String y representa el mensaje que se quiere mostrar en pantalla.
  * **Titulo:** Recibe un String por parámetro y representa el titulo de la ventana emergente.
  * **Tipo de Mensaje:** Recibe un entero donde se le indica el tipo de mensaje representado con un icono, donde:
    * 0: Representa un mensaje de error.
    * 1: Representa un mensaje Informativo.
    * 2: Representa un mensaje de Advertencia.
    * 3: Representa un mensaje de Pregunta.

Una vez se corre la aplicación es posible notar que al dar click sobre cualquiera de los 4 botones a los cuales se les adiciono el **ActionListener** saldrá un mensaje emergente.

<figure><img src="https://camo.githubusercontent.com/28adfc50d5dca3c5f4a8d22a4fbaee0764db3df18e4249c203da0a8efd7f1d08/68747470733a2f2f692e696d6775722e636f6d2f746751563633792e706e67" alt=""><figcaption></figcaption></figure>

Mensaje emergente al oprimir el botón bEntrar

Cabe recalcar que si se intenta dar click alguno de los dos botones excluidos (bOpcion2 o bOpcion3) no tendrá ningún efecto debido a que no se agrego la propiedad de adicionar un **ActionListener**.

Sin embargo, no se quiere que todos los botones realicen la misma acción, de hecho muchas veces es necesario que cada botón desencadene una acción diferente. Se debe realizar una discriminación de los botónes para separar acciones.

### Discriminación por Texto o Comando

La discriminación por texto o comando, realiza una separación de acciones dependiendo del texto que contiene cada botón, por ejemplo:

<figure><img src="https://camo.githubusercontent.com/3215d1d23f3e2ff29e2bd107ec6a86e1a01cacc3119084f1d5b393139c1a5dc0/68747470733a2f2f692e696d6775722e636f6d2f594864617348782e706e67" alt=""><figcaption></figcaption></figure>

Discriminación por medio de Texto o comando

Se puede notar que para realizar esta discriminación se debe usar el objeto recibido por defecto **e** de tipo **ActionEvent** y llamar a su método:

* **getActionCommand**: Que devuelve un String del comando del botón oprimido (**El texto del botón**) y se compara con la coincidencia del texto deseada.

Si se corre la aplicación y se da click sobre el botón Cerrar, como este no contiene texto sino una imagen mostrara el mensaje **"Botón Cerrar"**, al dar click sobre el botón entrar mostrara el mensaje **"Botón Entrar"**, sin embargo si se da click sobre el botón bRegistrarse no tendrá ningún efecto asi se le haya añadido la propiedad **addActionListener** ya que no se ha configurado ninguna acción para ese botón.

Sin embargo este enfoque tiene una pequeña particularidad que podría ser una desventaja, si por ejemplo se da click sobre el botón (bOpcion1), saldrá el mismo mensaje que en el botón cerrar, esto debido a que ninguno de los dos tiene texto.

<figure><img src="https://camo.githubusercontent.com/7c009216f4f22f46438b34b0a81a2ef9e4552eb7a57a617ef4af1b1a86b41f70/68747470733a2f2f692e696d6775722e636f6d2f30444d31765a702e706e67" alt=""><figcaption></figcaption></figure>

Mismo mensaje de alerta en diferentes botones

En las interfaces se van a tener varios botones que no contienen texto (Botones que solo contienen una imagen) ¿Como es posible discriminarlos unos con los otros?. Quizás se deba tomar otro enfoque.

### Discriminación por Objeto

La discriminación por objeto realiza una separación de acciones de acuerdo al objeto del botón que fue activado, por ejemplo:

<figure><img src="https://camo.githubusercontent.com/47bfc2ef93fa48564a59cd1abb5b0c853bcde762c409dd7511411c13686c38c1/68747470733a2f2f692e696d6775722e636f6d2f463439667530342e706e67" alt=""><figcaption></figcaption></figure>

Discriminación por medio de Objetos

De igual forma se debe usar el objeto recibido por parámetro **e** de tipo **ActionEvent** y esta vez se llama al método:

* **getSource**: Que devuelve el objeto del botón el cual fue oprimido y se compara con el objeto deseado para separar la acción.
* Como se debe comparar con el objeto del botón al que se desea configurar su acción, es necesario obtenerlo a traves del objeto de la clase **Template** y su método **get** correspondiente.

Si se ejecuta la aplicación y se da click sobre el botón Cerrar se mostrará el mensaje **"Botón Cerrar"** y al dar click sobre el botón opcion1 mostrará el mensaje **"Botón opción"** por lo que se ha solucionado el problema, igualmente si se da click sobre el botón bRegistrarse no tendrá ningún efecto asi se le haya añadido la propiedad **addActionListener** ya que no se configurado ninguna acción para ese botón aun.

Ahora una buena practica es llamar desde el método **actionPerformed** a otros métodos que realicen los procesos en caso de ser muy extenso el código.

Por ejemplo:

* El botón **bCerrar** Se encarga de cerrar la aplicación y el código no es para nada extenso asi que se puede mantener adentro del método **actionPerformed**.
* Los botones **bRegistrarse y bOpcion2** solo mostrarán por pantalla un mensaje asi que el código permanece adentro del método **actionPerformed**.
* El botón **bEntrar** va a obtener lo que escriba el usuario en tNombreUsuario, tClaveUsuario, cmbTipoUsuario y en los CheckBox y luego va a ingresar a la vista principal por lo que es preferible escribir un método externo que realice esta acción.

**Agregando mensajes en los botones bRegistrarse y bOpcion2**

```
if(e.getSource()== loginTemplate.getBOpcion1()){
    JOptionPane.showMessageDialog(null, "Boton Opcion", "Advertencia", 1);
}
if(e.getSource()== loginTemplate.getBRegistrarse()){
    JOptionPane.showMessageDialog(null, "Boton Registro", "Advertencia", 1);
}
```

**Cerrando la aplicación a traves del botón bCerrar**

```
if(e.getSource()== loginTemplate.getBCerrar()){
    System.exit(0);
}
```

Se puede observar en el código anterior que la forma para cerrar la aplicación es usando el código **System.exit(0)**.

**Agregando funcionalidad de muestra de datos y entrada a vista principal desde bEntrar**

```
if(e.getSource()== loginTemplate.getBEntrar()){
    this.mostrarDatosUsuario();
    this.entrar();
}
```

Es necesario entonces crear los métodos **mostrarDatosUsuario** y **entrar** en la clase, estos métodos pueden ir al final de la clase, justo por debajo del método **ActionPerformed**:

```
public void mostrarDatosUsuario(){
}

public void entrar(){
}
```

### Obtención de información desde formularios

#### **Obtención de información desde un JTextField**

Para obtener el texto desde un JTextField es necesario obtener primero el objeto gráfico, esto se realizara a traves del objeto de la **clase Template** seguido del método **get** correspondiente de la siguiente manera:

```
public void mostrarDatosUsuario(){
    loginTemplate.getTNombreUsuario();
}
```

Una vez obtenido el objeto es posible obtener el valor de lo escrito por el usuario mediante el método:

* **getText:** que retorna el texto escrito por el usuario en forma de String.

```
public void mostrarDatosUsuario(){
    loginTemplate.getTNombreUsuario().getText();
}
```

Sin embargo para usar el texto obtenido se debe igualar a una variable, por lo que se crea una variable de tipo String llamada **nombreUsuario** y se iguala a la sentencia:

```
public void mostrarDatosUsuario(){
    String nombreUsuario = loginTemplate.getTNombreUsuario().getText();
}
```

#### **Obtención de información desde un JPasswordField**

El anterior proceso se podría realizar de la misma manera con el JPasswordField:

```
// Dentro del método mostrarDatosUsuario
String claveUsuario = loginTemplate.getTClaveUsuario().getText();
```

El anterior código funciona, sin embargo, es posible que el editor de texto lo marque como tachado o saque una advertencia, esto es debido a que en versiones posteriores de Java este código dejará de funcionar, o es una forma insegura de hacerse.

Una alternativa para los objetos gráficos tipo JPasswordField es la siguiente:

```
// Dentro del método mostrarDatosUsuario
String claveUsuario = new String(loginTemplate.getTClaveUsuario().getPassword());
```

Se puede notar varias cosas:

* Se usa el método **getPassword** que devuelve un arreglo de tipo **char** es decir un arreglo donde cada posición es un carácter escrito.
* Como se desea manejar la clave en forma de String es necesario crear un String en forma de objeto (java permite esto) y es necesario ejemplificarlo haciendo **new String()** donde en su constructor obtendrá el arreglo de char y así lo convertirá en un String común.

#### **Obtención de información desde un JComboBox**

Para obtener información desde un **JComboBox** es necesario llamar al método:

* **getSelectedItem:** que retorna un objeto de la selección realizada por el usuario.

Como se quiere obtener el resultado en forma de String se debe realizar un **Cast** de datos a String y de igual modo se iguala con una variable String creada, de la siguiente manera:

```
// Dentro del método mostrarDatosUsuario
String tipoUsuario = ((String) loginTemplate.getCbTipoUsuario().getSelectedItem());
```

#### **Obtención de información desde un JCheckBox**

Para saber cual de las dos opciones de los JCheckBox fue escogida primero se crea una variable String que estará vacía:

```
// Dentro del método mostrarDatosUsuario
String check = "";
```

Seguido de eso se va a preguntar si alguno de los dos botones fue seleccionado mediante el método:

* **isSelected:** Retorna un booleano que estará en true si se seleccionó o false en caso de que no.

En caso de ser seleccionado se dará un nuevo valor a la variable **Check** ("Si" en caso de seleccionar el **checkSi** o "No" en caso de seleccionar el **checkNo**).

```
// Dentro del método mostrarDatosUsuario
if(loginTemplate.getCheckSi().isSelected())
    check = "si";
if(loginTemplate.getCheckNo().isSelected())
    check = "no";
```

Ahora se muestra a modo de prueba un mensaje mediante un JOptionPane de la siguiente manera:

```
// Dentro del método mostrarDatosUsuario
JOptionPane.showMessageDialog(
  null, 
  "Nombre Usuario: " + nombreUsuario +
  "\n Clave Usuario: " + claveUsuario + 
  "\nTipo Usuario: " + tipoUsuario + 
  "\n¿Notificaciones?: " + check, 
  "Advertencia", 
  1
);
```

Pueden notar que la forma de encadenar un texto es mediante el uso de **+** y también recalcar que con  se realiza un salto de linea.

El método esta listo para usarse y se ve asi:

<figure><img src="https://camo.githubusercontent.com/eeef5b95a12285113443cd6a1274200692179921c55dbc4f8bbfd4b33384704e/68747470733a2f2f692e696d6775722e636f6d2f6b656c465064472e706e67" alt=""><figcaption></figcaption></figure>

Método para obtener los datos del usuario

Si se abre la aplicación y se da click sobre el botón entrar se podrá ver un resultado como el siguiente:

<figure><img src="https://camo.githubusercontent.com/fca2775427acccf2ebd8ebeee86e37e0db86d6022c19ddbf12d4593faeedafb4/68747470733a2f2f692e696d6775722e636f6d2f505777337778742e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo de obtención de datos a través de evento de botón

De esta forma se se comprueba que los métodos para la obtención de información de los objetos gráficos funciona perfectamente.

### Abriendo otras ventanas

Suponiendo que ya se ha creado previamente todo el componente de vista principal (Clase Template y Clase Component con su Inyección de dependencia)

<figure><img src="https://camo.githubusercontent.com/7fc960b39c8205cbeffb13b81b3515766be3b01b062ed426893c419e50041812/68747470733a2f2f692e696d6775722e636f6d2f464a3730326a362e706e67" alt=""><figcaption></figcaption></figure>

Creación previa del componente VistaPrincipal

Ahora en la clase **LoginComponent** se va a declarar un objeto de tipo **VistaPrincipalComponent**

<figure><img src="https://camo.githubusercontent.com/3f466ad3518e3abbd1c3cd8aa29234014c05ad3eb2d47000c4fa133753f2c7d1/68747470733a2f2f692e696d6775722e636f6d2f556d724d776c332e706e67" alt=""><figcaption></figcaption></figure>

Declaración objeto de tipo VistaPrincipalComponent desde LoginComponent

Aquí se evidencia que la comunicación entre componentes se realizará desde las clases **Component**.

Ahora dentro del método **entrar** se escribe la lógica para entrar a la vista principal:

```
this.vistaPrincipal = new VistaPrincipalComponent();
loginTemplate.setVisible(false);
```

En el anterior código suceden 2 cosas:

* Se ejemplifica el objeto de la clase **VistaPrincipalComponent**, este internamente ejemplifica al objeto de la ventana haciendo que esta se muestre en pantalla.
* Se le indica al objeto de la clase **LoginTemplate** que ya no sea visible mediante el método **setVisible**.

Ahora cuando se oprime el botón entrar primero mostrará el mensaje con los datos proporcionados por el usuario y después abrirá la vista principal ademas que cerrara el login.

## Preparación para construcción de una Single-Page App

Ya es posible abrir desde la aplicación la vista principal, en realidad esta será la ventana que tendrá la característica de ser una **Single-Page App**. Se podría haber creado una aplicación con una única ventana para ser mas fiel al concepto y dentro de esta contener el componente de login, sin embargo, en la propuesta del curso se realizo varias ventanas para ver también la gestión de diferentes ventanas en una aplicación. Otra posible ventana extra podría ser la del registro de un usuario, sin embargo, debido a la finalidad del curso esta no será construida.

Como la ventana principal será la ventana que contendrá todos los componentes realizados posteriormente, los componentes de ahora en adelante se van a crear dentro de un paquete llamado **components**, esto para diferenciar los componentes principales (Las ventanas) de los componentes secundarios (los paneles).

<figure><img src="https://camo.githubusercontent.com/b827b639ad53e43efd25ece14d191eae5f4ed7ade2acac2cba9abf65b3ad770e/68747470733a2f2f692e696d6775722e636f6d2f653031327665482e706e67" alt=""><figcaption></figcaption></figure>

Creación de paquete components que contendrá los componentes secundarios dentro de la ventana Single-Page App

Efectivamente como se acabo de explicar, los componentes que se van a crear de ahora en adelante se caracterizan por que su clase **Template** ahora hereda de un **JPanel**.

### Preparación de la Ventana Principal

Dentro de la Vista principal se van a crear varios paneles, estos paneles cumplen la función de maquetación de la aplicación y posteriormente van a ser reemplazados por componentes que se crearan en clases siguientes.

Primero se debe quitar el color de fondo de la ventana, también se ocultará la barra por defecto de Java y se ajustará su tamaño:

```
setUndecorated(true);
setSize(1100, 650);
```

Se declaran 3 paneles y se crean con ayuda del servicio **objGraficosService**:

**Declaración de paneles**

```
private JPanel pNavegacion, pBarra, pPrincipal;
```

**Creación de método crearJPanels**

```
public void crearJPanels(){
}
```

**Construcción y adición de paneles**

```
// Dentro del método crearJPanels
pNavegacion = sObjGraficos.construirJPanel(0, 0, 250, 700,sRecursos.getColorSecundario(), null);
this.add(pNavegacion);

pBarra = sObjGraficos.construirJPanel(250, 0, 850, 50,sRecursos.getColorPrincipal(), null);
this.add(pBarra);

pPrincipal = sObjGraficos.construirJPanel(250, 50, 850, 600, Color.WHITE, null);
this.add(pPrincipal);
```

**Adición de método en el constructor**

```
this.crearJPanels();
```

Por ultimo se debe agregar los métodos **get** correspondientes a los 3 paneles ya que la clase **Component** de seguro va a necesitar manipularlos en el futuro.

```
public JPanel getPNavegacion() { return this.pNavegacion; }

public JPanel getPPrincipal() { return this.pPrincipal; }

public JPanel getPBarra() { return this.pBarra; }
```

Por ahora la ventana principal se verá así:

<figure><img src="https://camo.githubusercontent.com/5d71a40bf4c758b24baa92afae1cc79596a3c700f0640c1f76fb4013ac0f400c/68747470733a2f2f692e696d6775722e636f6d2f377657427738382e706e67" alt=""><figcaption></figcaption></figure>

Clase Vista Principal

La vista Principal esta lista para empezar a ser construida a traves de componentes, los colores se utilizan solo para comprobar que los paneles se crearon correctamente pero serán reemplazados en futuras sesiones.

## Resultados

Si llegaste hasta aquí **¡Felicitaciones!** se ha aprendido qué son los componentes gráficos, se vio una introducción de su concepto y se exploro cada una de sus partes. Se aprendido a utilizar eventos de **ActionListener**, cómo realizar la discriminación de acciones por botones, cómo obtener información de formularios además de cómo mostrar y ocultar ventanas. Tenemos lista la clase **VistaPrincipal** que será construida a través de **Componentes Gráficos**.

Si se explora la estructura del proyecto de nuevo y con la implementación de componentes gráficos se verá de la siguiente manera:

<figure><img src="https://camo.githubusercontent.com/7bab954a1f1429141611ad9e03a88193b8a8b8e494e0ecea1b64afbbf1864956/68747470733a2f2f692e696d6775722e636f6d2f333375513761662e706e67" alt=""><figcaption></figcaption></figure>

Diagrama de clases general de la aplicación

En la siguiente sesión se verá cómo hacer la construcción de la vista principal a través de componentes gráficos y cómo gestionar la vista de componentes mediante el routing o navegación.

## Actividad

Desarrollar los componentes gráficos del login y la vista principal en los proyectos y realizar la gestión de eventos con los botones para que cierre la aplicación y abra la vista principal.

### About

Clase 5 del curso de Interfaz Gráfica con Java, en donde se muestran conceptos relacionados con componentes gráficos, su implementacion y eventos por accion ActionListener.

## Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 6

### Objetivos

* Identificar la forma de incorporar componentes gráficos dentro de una **Single-page app** para que puedan ser visualizados desde la ventana principal.
* Comprender el concepto de navegación y como se gestiona la visibilidad de los diferentes componentes dentro de la vista principal.
* Reconocer la comunicación entre componentes para el paso de acciones e información.
* Considerar la importancia del control en la creación de objetos en memoria y como gestionar la producción desmesurada de estos.

## Antes de comenzar

#### **Actualización de Imágenes en recursos**

Para continuar con la lección deberá actualizar la carpeta **resources/images** ya que se han agregado nuevas imágenes. Estas las puede descargar en este mismo repositorio entrando a la carpeta **Clase6** seguido de **resources/images**. Puede notar que adentro existe una nueva carpeta llamada perfiles, esta también deberá ser agregada ya que tendrá utilidad.

<figure><img src="https://camo.githubusercontent.com/54787bfd31d154299ae400209671ef140e5709dd1ba23dc401a43ff1498fd173/68747470733a2f2f692e696d6775722e636f6d2f64645574735a4e2e706e67" alt=""><figcaption></figcaption></figure>

Carpeta perfiles dentro de resources/images en el repositorio

#### **Ajustes en el servicio Recursos Service**

En el servicio **RecursosService** se crea un nuevo objeto decorador **Font**:

**Declaración:**

```
// Al inicio del servicio
private Font fontLigera;
```

**Ejemplificación:**

```
// Dentro del método crearFuentes
fontLigera = new Font("LuzSans-Book", Font.PLAIN, 12);
```

**Método get:**

```
public Font getFontLigera() { return fontLigera; }
```

También se crea un objeto tipo **ImageIcon**:

**Declaración:**

```
// Al inicio del servicio
private ImageIcon iMinimizar;
```

**Ejemplificación:**

```
// Dentro del método crearImagenes
iMinimizar = new ImageIcon("Clase6/resources/images/minimizar.png");
```

**Método get:**

```
public ImageIcon getIMinimizar() { return iMinimizar; }
```

#### **Recordatorio**

Recordando el recorrido, el componente gráfico **login** esta listo y funcional, tiene una vista agradable para los usuarios, un código modularizado y optimizado, además realiza eventos por acción permitiendo cerrar la aplicación, mostrar la información recibida del usuario o abrir la ventana principal.

<figure><img src="https://camo.githubusercontent.com/2bb1690d8010e3e2d2157749f3195d68eb492bc1d5babac28083ec95ee2ef7a0/68747470733a2f2f692e696d6775722e636f6d2f6a4253383979592e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario en funcionamiento

La ventana principal ya quedo lista para empezar a construir la Single-Page App a traves de componentes gráficos.

<figure><img src="https://camo.githubusercontent.com/ab9af162ec17588ed3a7af9dd2cb30f6374bdc444660d8706a663fad235ed06c/68747470733a2f2f692e696d6775722e636f6d2f624a65517243532e706e67" alt=""><figcaption></figcaption></figure>

Vista Principal lista para construirse

## Componentes Gráficos dentro de un Single-Page App y navegación.

En esta sesión se verán tres items importantes relacionados con la creación, gestión y navegación de componentes gráficos:

* **Construcción e incorporación de componentes gráficos dentro de Single-Page app**.
* **Navegación y gestión de visibilidad de componentes gráficos**.
* **Control en la creación de componentes gráficos en memoria**.

## Construcción e incorporación de componentes gráficos dentro de Single-Page app.

### Ajustes

Ya se realizo una maquetización en la ventana principal y esta cuenta con sus respectivos paneles, los cuales se evidencian por medio de sus colores, sin embargo, su contenido será reemplazado, asi que se procede a retirar el color a los paneles.

<figure><img src="https://camo.githubusercontent.com/b86c55c2ff865840f19f4fcaf991501afa8ad1c34a96e3f3a0d64d511d5edbe0/68747470733a2f2f692e696d6775722e636f6d2f6b39484e4d78702e706e672e706e67" alt=""><figcaption></figcaption></figure>

Paneles de VistaPrincipalTemplate sin color

Realmente en la ventana principal no se usaran objetos decoradores asi que también se removerá el uso del servicio RecursosService y la importación de la librería Color.

<figure><img src="https://camo.githubusercontent.com/293aba0946ae9b3309e18aaa366ba3bed3d71b279ab8ab9cedd798da61910714/68747470733a2f2f692e696d6775722e636f6d2f415945375672312e706e67" alt=""><figcaption></figcaption></figure>

A la izquierda se ve el código removido y a la derecha el resultado

### Creación e incorporación del Componente Barra Titulo

Se va a incorporar el componente encargado de mostrar la barra de titulo, primero se crea un nuevo paquete **barraTitulo** dentro del paquete **Components**, en el paquete **barraTitulo** se crearán las clases **BarraTituloTemplate** y **BarraTituloComponent**:

<figure><img src="https://camo.githubusercontent.com/091dc0e350544e62681e19c0fdacb6ac4dd996c8d0f0b9ea74410dcfa19ff02c/68747470733a2f2f692e696d6775722e636f6d2f6f366237744b632e706e67" alt=""><figcaption></figcaption></figure>

Creación componente barraTitulo con su respectivo paquete y clases

Como se menciono en la sesión anterior, la clase **Component** puede implementar de alguna interfaz que gestiona eventos de ser necesario, en este caso el componente **barraTitulo** contendrá varios botones para realizar acciones como minimizar o cerrar la aplicación por lo que será necesaria la implementación:

**implementación de interfaz**

```
public class BarraTituloComponent implements ActionListener{
}
```

**implementación de métodos de la interfaz**

```
@Override
public void actionPerformed(ActionEvent e) {
}
```

Se crea el atributo que hace referencia a la clase **Template** y se ejemplifica enviándose como argumento una referencia a si misma con la palabra clave **this** para realizar la inyección de dependencias:

**Declaración**

```
private BarraTituloTemplate barraTituloTemplate;
```

**Ejemplificación**

```
// Dentro del constructor
this.barraTituloTemplate = new BarraTituloTemplate(this); 
```

Se debe añadir un método **get** de su único atributo **barraTituloTemplate**, para que otros componentes puedan acceder a la clase gráfica del componente como se explico con anterioridad.

```
public BarraTituloTemplate getBarraTituloTemplate() {
  return this.barraTituloTemplate;
}
```

Ahora se codifica a la clase **BarraTituloTemplate**, esta al tener propiedades gráficas va heredar de un **JPanel**:

```
public class BarraTituloTemplate extends JPanel{
}
```

Recibe por parámetro dentro del constructor a la clase **Component** para igualarla con un atributo global de la misma referencia para cerrar la inyección, ademas obtendrá los servicios de **ObjGraficosService** y **RecursosService**:

**Declaración:**

```
private BarraTituloComponent barraTituloComponent;
private ObjGraficosService sObjGraficos;
private RecursosService sRecursos;
```

**Obtención de servicios y recibimiento de la clase Component:**

```
public BarraTituloTemplate(BarraTituloComponent barraTituloComponent){
  this.barraTituloComponent = barraTituloComponent;
  this.sObjGraficos= ObjGraficosService.getService();
  this.sRecursos = RecursosService.getService();
}
```

Como la clase hereda de un **JPanel** es necesario darle propiedades gráficas asi que se realizan varias configuraciones:

```
// Dentro del constructor al final
this.setSize(850, 50);
this.setBackground(Color.WHITE);
this.setLayout(null);
this.setVisible(true);
```

Note que el tamaño del panel de esta clase **Template** debe ser exactamente igual que el panel en la **VistaPrincipal** al que se incorporará, en este caso a el panel **pBarra**:

<figure><img src="https://camo.githubusercontent.com/08154eca1129982d4005be4124906d366c682b17f15dcc783b53b088ab602333/68747470733a2f2f692e696d6775722e636f6d2f4d7544445444412e706e67" alt=""><figcaption></figcaption></figure>

Mismo tamaño de componente con Panel al que se incorporará

Se agregarán en el componente 4 objetos gráficos principales, un **Logo**, un **Título**, un **Botón de minimizar** y un **Botón de cerrar**, también se agregarán algunos objetos decoradores, por lo que se realiza el proceso de creación reflejado en las sesiones anteriores:

**Declaración**

```
//Declaración objetos gráficos
private JLabel lLogoApp, lTituloApp;
private JButton bCerrar, bMinimizar;

//Declaración Objetos Decoradores
private ImageIcon iLogoApp, iDimAux;
private Font fontTituloBarra;
```

Se puede observar que se creará una fuente que solo se utilizará para el titulo de la interfaz asi que se crea dentro del componente especifico y no en **RecursosService**

**Método crearObjetosDecoradores:**

```
public void crearObjetosDecoradores(){
  iLogoApp = new ImageIcon("Clase6/resources/images/logo_app.png");
  fontTituloBarra= new Font("Britannic Bold", Font.PLAIN, 24);
}
```

**Método crearJButtons:**

```
public void crearJButtons(){
  // BOTÓN CERRAR ----------------------------------------------------
  iDimAux = new ImageIcon(
    sRecursos.getICerrar().getImage()
      .getScaledInstance(23, 23, Image.SCALE_AREA_AVERAGING)
  );
  bCerrar = sObjGraficos.construirJButton(
    null, 
    800, 10, 45, 30,
    sRecursos.getCMano(), 
    iDimAux, 
    null, null, null, null, 
    "c", 
    false
  );
  bCerrar.addActionListener(barraTituloComponent);
  this.add(bCerrar);

  // BOTÓN MINIMIZAR ----------------------------------------------------
  iDimAux = new ImageIcon(
    sRecursos.getIMinimizar().getImage()
      .getScaledInstance(28, 28, Image.SCALE_AREA_AVERAGING)
  );
  bMinimizar = sObjGraficos.construirJButton(
    null,
    750, 10, 45, 30,
    sRecursos.getCMano(),
    iDimAux,
    null, null, null, null,
    "c",
    false
  );
  bMinimizar.addActionListener(barraTituloComponent);
  this.add(bMinimizar);
}
```

Como el botón cerrar va a utilizar la misma imagen usada en el login se llama al servicio **RecursosService** para obtener dicha imagen compartida. También se observa que se agrego de una vez la propiedad **addActionListener** en ambos botones.

**Método crearJLabels:**

```
public void crearJLabels(){
  // LABEL LOGO APP--------------------------------------------------------------------
  iDimAux = new ImageIcon(
    iLogoApp.getImage()
      .getScaledInstance(50, 50, Image.SCALE_AREA_AVERAGING)
  );
  lLogoApp = sObjGraficos.construirJLabel(
    null,
    20, 0, 50, 50,
    null,
    iDimAux,
    null, null, null, null,
    "c"
  );
  this.add(lLogoApp);

  // LABEL TITULO APP--------------------------------------------------------------------
  lTituloApp = sObjGraficos.construirJLabel(
    "ProductList",
    40, 5, 200, 40,
    null, null,
    fontTituloBarra,
    null,
    sRecursos.getColorPrincipal(),
    null,
    "c"
  );
  this.add(lTituloApp);
}
```

Note que en el label **lTituloApp** se esta usando la fuente exclusiva de este componente gráfico.

**Llamada de métodos de creación desde el constructor:**

```
//Dentro del constructor después de obtener servicios 
this.crearObjetosDecoradores();
this.crearJLabels();
this.crearJButtons();
```

Por ultimo se crean métodos **get** para los botones para puedan ser manipulados desde la clase **Component**:

```
public JButton getBCerrar() { return bCerrar; }

public JButton getBMinimizar() { return bMinimizar; }
```

La clase **Template** del componente **barraTitulo** esta lista. Por otro lado para la clase **Component** solo falta añadir la configuración de los eventos de acción. En este caso serán el de minimizar y salir de la aplicación, primero se procede a crear una discriminación por objetos:

```
@Override
public void actionPerformed(ActionEvent e) {
  if (e.getSource() == barraTituloTemplate.getBMinimizar())
    // Acción para minimizar
  if (e.getSource() == barraTituloTemplate.getBCerrar())
    // Acción para Cerrar
}
```

#### **Comunicación bidireccional entre componentes gráficos**

Note que aunque el componente **barraTitulo** contiene los botones que realizan estas acciones, el componente que se debe encargar realmente de cerrar o minimizar la ventana debe ser **vistaPrincipal**. Así que se crean los métodos encargados de realizar estas acciones dentro de la clase **VistaPrincipalComponent**:

```
// Dentro de la clase VistaPrincipalComponent
public void cerrar() {
    System.exit(0);
  }

public void minimizar() {
  this.vistaPrincipalTemplate.setExtendedState(Frame.ICONIFIED);
}
```

El anterior código para minimizar la ventana se debe llamar a la clase de la ventana **VistaPrincipalTemplate** y se usa el método:

* **setExtendedState:** Que recibe como parámetro un estado de la clase Frame y que cambia la perspectiva de la ventana haciendo posible acciónes como minimizar, expandir etc. El Argumento **Frame.ICONIFIED** le indica a la ventana que se minimize.

Es necesario para llamar a este estado importar la librería del Frame dentro de la clase VistaPrincipalComponent:

```
import java.awt.Frame;
```

Ahora se debe llamar a los métodos correspondientes de la vista principal dentro del componente **barraTitulo**, sin embargo es necesario obtener una referencia del componente **vistaPrincipal**, así que se recibirá por parámetro un objeto que haga referencia a la clase component y luego se utilizará:

* **Declaración:**

```
private VistaPrincipalComponent vistaPrincipalComponent;
```

* **Obtención de referencia por inyección**

```
public BarraTituloComponent(VistaPrincipalComponent vistaPrincipalComponent) {
  this.vistaPrincipalComponent = vistaPrincipalComponent;
  ...
  ...
}
```

* **Uso de objeto recibido para llamar a los métodos:**

```
@Override
public void actionPerformed(ActionEvent e) {
  if (e.getSource() == barraTituloTemplate.getBMinimizar())
    vistaPrincipalComponent.minimizar();
  if (e.getSource() == barraTituloTemplate.getBCerrar())
    vistaPrincipalComponent.cerrar();
}
```

En este caso se esta recibiendo una referencia del componente padre **VistaPrincipal** por el constructor creando así una inyección de dependencia y esto crea a su vez una comunicación bidireccional entre ambos componentes, Ahora el componente padre **VistaPrincipal** puede enviar peticiones a **barraTitulo** y viceversa. (Este proceso de comunicación bidireccional entre componentes se explica con mas detalle en la sección de navegación.)

Esta comunicación entre componentes solo se debe realizar en caso de ser necesario, por lo general solamente existe una comunicación unidireccional donde el componente padre realiza peticiones al hijo nada mas.

El Componente esta totalmente listo, sin embargo, falta incorporarlo a la ventana principal:

#### **Incorporación de componente en la Single-Page app**

En la clase **VistaPrincipalComponent** se va a declarar un objeto del componente **barraTitulo** y como se explico en la sesión anterior, debe hacerse el llamando exclusivamente a la clase **Component**:

**Declaración:**

```
//Declaración componentes
private BarraTituloComponent barraTituloComponent;
```

**Ejemplificación:**

```
//Dentro del constructor
this.barraTituloComponent = new BarraTituloComponent(this);
```

Note que dentro de la ejemplificación se enviá una referencia asi misma con la palabra clave **this** para terminar la inyección de dependencias.

Ahora se realiza la parte **más importante** que es la incorporación del componente a la ventana, como se quiere que al abrir la ventana este componente ya este incorporado se realiza el siguiente proceso dentro del constructor:

* Primero se obtiene el panel que incorporará al componente, en este caso **pBarra** y para esto se llama al método **get** correspondiente de la clase **VistaPrincipalTemplate**:

```
//Dentro del constructor
vistaPrincipalTemplate.getPBarra();
```

* Una vez obtenido el panel, se le indica al panel que se agregará un objeto, para eso se llama a su método de configuración **add**:

```
//Dentro del constructor
vistaPrincipalTemplate.getPBarra().add();
```

* Se debe especificar que se va a incorporar, entonces dentro de los paréntesis se llama a la clase **Component** que antes se ha ejemplificado:

```
//Dentro del constructor
vistaPrincipalTemplate.getPBarra().add(barraTituloComponent);
```

* Sin embargo la clase **BarraTituloComponent** no cuenta con propiedades gráficas, es la clase **BarraTituloTemplate** la que si las tiene ya que hereda de un **JPanel**, es por eso que el editor muestra un error con el código anterior. Sin embargo, la clase **BarraTituloComponent** tiene un método **get** que devuelve la clase **Template**, asi que se invoca:

```
//Dentro del constructor
vistaPrincipalTemplate.getPBarra().add(
    barraTituloComponent.getBarraTituloTemplate()
);
```

Por cuestiones de espacio horizontal se acomoda la linea de código.

Si se ejecuta la aplicación y abrimos la ventana principal se observa que se ha incorporado exitosamente su primer componente gráfico:

<figure><img src="https://camo.githubusercontent.com/8ecb7d2eed97887799d6014dd27b65d2fd765a0e5360ec2f7e66437bbc14a87f/68747470733a2f2f692e696d6775722e636f6d2f3631634854486c2e706e67" alt=""><figcaption></figcaption></figure>

Vista principal con su primer componente agregado

Incluso al darle click al botón de cerrar o al botón minimizar estos funcionarán de forma adecuada.

### Creación e incorporación del Componente Navegación Usuario

Se va a repetir el mismo proceso para el componente gráfico **navegacionUsuario** este componente es el encargado de mostrar en pantalla los botones con los que el usuario podrá navegar dentro de la aplicación. Se crea a continuación su paquete con sus respectivas clases dentro del paquete **components**:

<figure><img src="https://camo.githubusercontent.com/2f5a063584079142e47e7cdd3c32f72be39c0e9178c2790edc16a023ff392b4f/68747470733a2f2f692e696d6775722e636f6d2f416679395833482e706e67" alt=""><figcaption></figcaption></figure>

Creación del componente gráfico navegacionUsuario

Se empieza con la clase **Component**, como el componente contendrá botones, es necesaria la implementación de la interfaz **ActionListener** y su método:

```
public class NavegacionUsuarioComponent implements ActionListener {

    @Override
	public void actionPerformed(ActionEvent e) {
    }
}
```

Se crea el atributo que referencia a la clase **Template** y se ejemplifica enviándose como argumento a si mismo con la palabra clave **this** para realizar la inyección:

**Declaración**

```
private NavegacionUsuarioTemplate navegacionUsuarioTemplate;
```

**Ejemplificación**

```
//dentro del constructor
this.navegacionUsuarioTemplate =  new NavegacionUsuarioTemplate(this); 
```

Se debe generar también el método **get** de su clase **Template** correspondiente:

```
public NavegacionUsuarioTemplate getNavegacionUsuarioTemplate() {
    return this.navegacionUsuarioTemplate;
}
```

Ahora en la clase **NavegacionUsuarioTemplate** esta debe heredar de un **JPanel**:

```
public class NavegacionUsuarioTemplate extends JPanel{
}
```

Se obtienen los servicios y la clase **Component** desde el constructor:

**Declaración de servicios y clase Component**

```
private NavegacionUsuarioComponent navegacionUsuarioComponent;
private ObjGraficosService sObjGraficos;
private RecursosService sRecursos;
```

**Obtención de servicios y recibimiento del objeto de clase Component**

```
public NavegacionUsuarioTemplate(NavegacionUsuarioComponent navegacionUsuarioComponent){
    this.navegacionUsuarioComponent = navegacionUsuarioComponent;
    this.sObjGraficos= ObjGraficosService.getService();
    this.sRecursos = RecursosService.getService();
}
```

Se dan las propiedades gráficas al componente gráfico y se debe prestar atención al tamaño ya que debe ser el mismo al panel en la ventana principal que lo va a incorporar, en este caso el panel **pNavegacion**:

```
// Dentro del constructor
this.setSize(250, 700);
this.setLayout(null);
this.setVisible(true);
```

Este componente va a contener los siguientes objetos gráficos:

* Panel que muestra información del usuario:
  * Label con un icono de usuario.
  * Label con el nombre del usuario.
  * Label con fotografiá del usuario.
  * Label con un pequeño eslogan.
* Panel que contiene los botones de navegación:
  * Botones de navegación (serán 6 en total)

**Declaraciones:**

```
//Declaración objetos gráficos
private JPanel pSuperior, pInferior;
private JLabel lNombreUsuario, lEslogan, lImagenUsuario, lIconoUsuario;
private JButton bInicio, bPerfil, bAmigos, bProductos, bConfiguracion, bCerrarSesion;

//Declaración Objetos Decoradores
private ImageIcon iIconoUsuario, iInicio, iPerfil, iAmigos, iProductos, 
iConfiguracion, iCerrarSesion, iImagenUsuario, iDimAux;
private Border bVacio;
```

**Método construirJPanels:**

```
public void crearJPanels(){
  this.pSuperior = sObjGraficos.construirJPanel(
    0, 0, 250, 300, 
    sRecursos.getColorPrincipal(), 
    null
  );
  this.add(pSuperior);

  this.pInferior = sObjGraficos.construirJPanel(
    0, 300, 250, 400, 
    sRecursos.getColorPrincipal(), 
    null
  );
  this.add(pInferior);
}
```

**Método crearObjetosDecoradores:**

```
public void crearObjetosDecoradores(){
    this.iIconoUsuario = new ImageIcon("Clase6/resources/images/usuario_navegacion.png");
    this.iInicio = new ImageIcon("Clase6/resources/images/inicio.png");
    this.iPerfil = new ImageIcon("Clase6/resources/images/perfil.png");
    this.iAmigos = new ImageIcon("Clase6/resources/images/amigos.png");
    this.iProductos = new ImageIcon("Clase6/resources/images/productos.png");
    this.iConfiguracion = new ImageIcon("Clase6/resources/images/configuracion.png");
    this.iCerrarSesion = new ImageIcon("Clase6/resources/images/salir.png");
    this.iImagenUsuario = new ImageIcon("Clase6/resources/images/perfiles/perfil1.png");
    this.bVacio = new EmptyBorder(2, 20, 2, 2);
}
```

Se puede observar que se crea un borde vació, este borde será utilizado para crear un espació interno o Padding entre el borde de los botones y el contenido de los mismos.

**Método crearJLabels:**

```
public void crearJLabels(){
  // LABEL ICONO USUARIO--------------------------------------------------------------------
  iDimAux = new ImageIcon(
    iIconoUsuario.getImage()
      .getScaledInstance(40, 40, Image.SCALE_AREA_AVERAGING)
  );
  this.lIconoUsuario = sObjGraficos.construirJLabel(
    null,
    10, 20, 40, 40,
    null,
    iDimAux,
    null, null, null, null,
    "c"
  );
  this.pSuperior.add(lIconoUsuario);

  // LABEL NOMBRE USUARIO--------------------------------------------------------------------
  this.lNombreUsuario = sObjGraficos.construirJLabel(
    "Nombre de Usuario", 
    ((this.pSuperior.getWidth() - 200) / 2) + 10, 20, 200, 40,
    null, null, 
    sRecursos.getFontTitulo(), 
    null,
    Color.WHITE,
    null,
    "c"
  );
  this.pSuperior.add(lNombreUsuario);

  // LABEL IMAGEN USUARIO--------------------------------------------------------------------
  iDimAux = new ImageIcon(
    iImagenUsuario.getImage()
      .getScaledInstance(180, 180, Image.SCALE_AREA_AVERAGING)
  );
  this.lImagenUsuario = sObjGraficos.construirJLabel(
    null, 
    (this.pSuperior.getWidth() - 180) / 2, 75, 180, 180,
    null,
    iDimAux, 
    null, null, null, null,
    "c"
  );
  this.pSuperior.add(lImagenUsuario);

  // LABEL ESLOGAN--------------------------------------------------------------------
  this.lEslogan = sObjGraficos.construirJLabel(
    "<html><div align='center'> Nuestros clientes son <br/>lo mas importante</div></html>",
    (this.pSuperior.getWidth() - 180) / 2, 265, 180, 40, 
    null, null, 
    sRecursos.getFontLigera(), 
    null, 
    Color.WHITE, 
    null,
    "c");
  this.pSuperior.add(lEslogan);
}
```

Note que en el label **lEslogan** hay algo diferente, y es que el texto se ha escrito dentro de etiquetas **HTML**. Esto es debido a que java no permite dar saltos de linea dentro de un label, es decir que si se escribe  que representa un salto de linea en consola no va a funcionar para los Labels, es por eso que se usan etiquetas HTML para poder dar saltos de linea al texto y ademas brindar de varias otras características como:

* **`<html>`** indica que se va a iniciar un formato html y se debe cerrar al final con **`</html>`**.
* **`<div align='center'>`** Le da al texto propiedad de centrado, la etiqueta **div** debe tener una etiqueta de cerrado **`</div>`**.
* **`<div align='justify'>`** Le da al texto propiedad de texto justificado, la etiqueta **div** debe tener una etiqueta de cerrado **`</div>`**.
* **`<br/>`** indica un salto de linea, esto es solo cuando se quiere dar un salto de linea explicito, si no se coloca esta etiqueta de todos modos el html realiza el salto de linea automático una vez ocupa todo el espacio de ancho.

**Método crear JButtons**

```
public void crearJButtons(){
  // BOTÓN INICIO--------------------------------------------------------------------
    iDimAux = new ImageIcon(
      iInicio.getImage()
        .getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
    );
    this.bInicio = sObjGraficos.construirJButton(
      "      Inicio",
      30, 30, 200, 40,
      sRecursos.getCMano(),
      iDimAux,
      sRecursos.getFontMediana(),
      null,
      Color.WHITE,
      bVacio,
      "l",
      false
    );
    this.bInicio.addActionListener(navegacionUsuarioComponent);
    this.pInferior.add(bInicio);

    // BOTÓN PERFIL--------------------------------------------------------------------
    iDimAux = new ImageIcon(
      iPerfil.getImage()
        .getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
    );
    this.bPerfil = sObjGraficos.construirJButton(
      "      Perfil",
      30, 80, 200, 40,
      sRecursos.getCMano(),
      iDimAux,
      sRecursos.getFontMediana(),
      null,
      Color.WHITE,
      bVacio,
      "l",
      false
    );
    this.bPerfil.addActionListener(navegacionUsuarioComponent);
    this.pInferior.add(bPerfil);

    // BOTÓN AMIGOS--------------------------------------------------------------------
    iDimAux = new ImageIcon(
      iAmigos.getImage()
        .getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
    );
    this.bAmigos = sObjGraficos.construirJButton(
      "      Amigos",
      30, 130, 200, 40,
      sRecursos.getCMano(),
      iDimAux,
      sRecursos.getFontMediana(),
      null,
      Color.WHITE,
      bVacio,
      "l",
      false
    );
    this.bAmigos.addActionListener(navegacionUsuarioComponent);
    this.pInferior.add(bAmigos);

    // BOTÓN PRODUCTOS--------------------------------------------------------------------
    iDimAux = new ImageIcon(
      iProductos.getImage()
        .getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
    );
    this.bProductos = sObjGraficos.construirJButton(
      "      Productos",
      30, 180, 200, 40,
      sRecursos.getCMano(),
      iDimAux,
      sRecursos.getFontMediana(),
      null,
      Color.WHITE,
      bVacio,
      "l",
      false
    );
    this.bProductos.addActionListener(navegacionUsuarioComponent);
    this.pInferior.add(bProductos);

    // BOTÓN CONFIGURACIÓN--------------------------------------------------------------------
    iDimAux = new ImageIcon(
      iConfiguracion.getImage()
        .getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
    );
    this.bConfiguracion = sObjGraficos.construirJButton(
      "      Configuraciones",
      30, 230, 200, 40,
      sRecursos.getCMano(),
      iDimAux,
      sRecursos.getFontMediana(),
      null,
      Color.WHITE,
      bVacio,
      "l",
      false
    );
    this.bConfiguracion.addActionListener(navegacionUsuarioComponent);
    this.pInferior.add(bConfiguracion);

    // BOTÓN CERRAR SESIÓN--------------------------------------------------------------------
    iDimAux = new ImageIcon(
      iCerrarSesion.getImage()
        .getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
    );
    this.bCerrarSesion = sObjGraficos.construirJButton(
      "      Cerrar Sesión",
      30, 280, 200, 40,
      sRecursos.getCMano(),
      iDimAux,
      sRecursos.getFontMediana(),
      null,
      Color.WHITE,
      bVacio,
      "l",
      false
    );
    this.bCerrarSesion.addActionListener(navegacionUsuarioComponent);
    this.pInferior.add(bCerrarSesion);
}
```

Estos botones tienen unas características peculiares:

* Todos cuentan con una imagen y ademas un texto, esto es posible y el servicio **ObjGraficosService** esta configurado para estos casos.
* Para que exista una separación visible entre el icono y el texto, este ultimo empieza con unos espacios de la forma:

<figure><img src="https://camo.githubusercontent.com/0c014c783c9046784c99ca8f26c0e5719bcf7e596d5b31fecef6d41a16c6deda/68747470733a2f2f692e696d6775722e636f6d2f344e6f465a706a2e706e67" alt=""><figcaption></figcaption></figure>

Separación de texto con icono dentro del botón

* El botón esta vez cuenta con una dirección hacia la izquierda para que la imágen este antes que el texto, por lo que se envía como argumento **"l"** para el parámetro **dirección**.
* Cuenta con un padding para que exista una separación entre el borde y el contenido, por lo que se utiliza el borde **bVacio**, esto no se verá reflejado aun ya que el botón no cuenta con fondo, pero en futuras sesiones cuando se hable de eventos del Mouse se resaltará la importancia del uso de este borde.
* No tienen fondo por lo que se envía como argumento un **false** para el parámetro **esSolido**.

**Llamada de métodos de creación desde el constructor:**

```
//Dentro del constructor después de obtener servicios 
this.crearObjetosDecoradores();
this.crearJPanels();
this.crearJLabels();
this.crearJButtons();
```

El componente gráfico esta casi listo solo falta realizar la configuración de los eventos de acción pero esto se discutirá en la siguiente sección **Navegación y gestión de visibilidad de componentes gráficos**. Por el momento se va a incorporar en la vista principal.

#### **Incorporación de componente en la Single-Page app**

Nuevamente en la clase **VistaPrincipalComponent** se declara un objeto del componente **navegacionUsuario** y como se explico en la sesión anterior, debe hacerse el llamando exclusivamente a la clase **Component**.

**Declaración:**

```
//Declaración componentes
private NavegacionUsuarioComponent navegacionUsuarioComponent;
```

**Ejemplificación:**

```
//Dentro del constructor
this.navegacionUsuarioComponent = new NavegacionUsuarioComponent();
```

La incorporación se realiza de la misma manera que se explicó con el anterior componente gráfico, esta vez será incorporado sobre el panel **pNavegacion**:

```
//Dentro del constructor
vistaPrincipalTemplate.getPNavegacion().add(
    navegacionUsuarioComponent.getNavegacionUsuarioTemplate()
);
```

Si se corre la aplicación y se abre la ventana principal se observa que se ha incorporado exitosamente el segundo componente:

<figure><img src="https://camo.githubusercontent.com/a016d2a011fc5eb436f5811f022d5aa8d60b2ac611e6ab081ccb8857ddc4ff15/68747470733a2f2f692e696d6775722e636f6d2f745777456762472e706e67" alt=""><figcaption></figcaption></figure>

Vista principal con el componente Navegación usuario agregado

Sin embargo al dar click sobre cualquiera de los botónes, estos no hacen nada aun, esto se discutirá en la siguiente sección.

## Navegación y gestión de visibilidad de componentes gráficos.

Ya están incorporados los dos componentes a la ventana principal, esto da una ventaja enorme ya que cada componente tiene su propia responsabilidad y su código será mucho más entendible. Lo que se quiere hacer ahora es que cuando se oprima cualquiera de los botones del componente **navegacionUsuario** la ventana principal gestione que componentes se verán dentro del panel **pPrincipal** este proceso se conoce como **navegación** que para paginas web se conoce como **enrutamiento** ya que esta gestión de visibilidad de componentes se hace mediante rutas en el navegador, sin embargo dentro del curso se referirá a este proceso como navegación, al final es el mismo resultado lo que se quiere realizar.

La clase que se debe encargar de gestionar que es visible y que no dentro de la misma es solamente la clase **VistaPrincipalComponent**, se podría pensar que el componente **navegacionUsuario** al tener los botones se debería encargar de esta labor pero es erróneo, es la misma ventana principal la que debe hacer su propia gestión.

### Creación de componentes Gráficos

Primero se van a crear los componentes gráficos a los cuales se quiere gestionar su visibilidad en la ventana principal.

<figure><img src="https://camo.githubusercontent.com/8e3dc5b4c89c9c527d50f3c36e1f71a32697a0b6612c698dfeb5757b87638088/68747470733a2f2f692e696d6775722e636f6d2f4c5033457237742e706e67" alt=""><figcaption></figcaption></figure>

Creación de componentes para gestionar la navegación

A continuación se realiza el proceso de creación de uno de estos componentes (**inicio**), los demás tendrán el mismo proceso salvo por un pequeño cambio en cada uno que se explicará más adelante:

Se inicia con la codificación de la clase **InicioComponent**:

* Como por ahora este componente no va a contar con ningún botón no es necesario que implemente ninguna interfaz aun, si en el futuro cuando se este creando este componente con mas detalle se nota que contendrá botónes o necesita eventos se realizará en ese caso la implementación, pero por ahora no:

```
public class InicioComponent{
}
```

* Se un objeto de la clase **Template** correspondiente y se realiza la inyección:

**Declaración:**

```
private InicioTemplate inicioTemplate;
```

**Ejemplificación:**

```
// Dentro del constructor
this.inicioTemplate=  new InicioTemplate(this);
```

* Se crea el método **get** Correspondiente:

```
public InicioTemplate getInicioTemplate() {
  return this.inicioTemplate;
}
```

Ahora en la clase **InicioTemplate**:

* Al igual que con los otros componentes creados, esta clase esta heredada de un **JPanel**:

```
public class InicioTemplate extends JPanel{
}
```

* Se recibe la inyección como se ha explicado previamente:

**Declaración:**

```
private InicioComponent inicioComponent;
```

**Recibimiento de inyección e igualación:**

```
public InicioTemplate(InicioComponent inicioComponent){
    this.inicioComponent = inicioComponent;
}
```

* Se configuran las propiedades gráficas al componente:

```
// Dentro del constructor
this.setSize(850, 600);
this.setBackground(Color.DARK_GRAY);
this.setLayout(null);
this.setVisible(true);
```

Como se ha explicado antes este debe tener exactamente el mismo tamaño que el panel que lo incorporará, en este caso sera el panel **pPrincipal**.

_**Nota:** Para la creación de los otros componentes gráficos (amigos, configuraciones, perfil, productos) el proceso será exactamente el mismo con la diferencia del color en el **setBackground**, deben ser distintos, esto para diferenciar cada uno de los componentes._

### Comunicación bidireccional entre componentes

Como lo que se quiere es realizar la gestión de visibilidad desde la clase **VistaPrincipalComponent** pero los botones de activación se encuentra en el componente **navegacionUsuario** debe existir una comunicación bidireccional entre ambos componentes, para lo que realizaremos una **inyección de dependencia entre componentes gráficos** tal y como se realizó con el componente **barraTitulo**.

* En la clase **NavegacionUsuarioComponent** y se va a recibir por parámetro un objeto de referencia a **VistaPrincipalComponent**:

```
public NavegacionUsuarioComponent(VistaPrincipalComponent vistaPrincipalComponent) {

    ...
```

* Se declará un objeto (Atributo) de la misma referencia y se iguala al objeto recibido para que sea conocido de forma global en la clase:

```
private VistaPrincipalComponent vistaPrincipalComponent;

public NavegacionUsuarioComponent(VistaPrincipalComponent vistaPrincipalComponent) {
  this.vistaPrincipalComponent = vistaPrincipalComponent;

  ...
```

* Ahora en la clase **VistaPrincipalComponent** va a salir un error en la linea en la que se ejemplifico a la clase **NavegacionUsuarioComponent** ya que este exige el envío de un parámetro por constructor de un objeto de tipo **VistaPrincipalComponent**, simplemente entre los paréntesis se coloca un **this** enviándose a si mismo como argumento:

```
this.navegacionUsuarioComponent = new NavegacionUsuarioComponent(this);
```

Ya se ha creado la inyección y con esto hay comunicación bidireccional entre componentes gráficos.

Antes de continuar, como la clase **VistaPrincipalComponent** se va a encargar de la navegación, se crea un método llamado **mostrarComponente** y recibirá por parámetro un String llamado **comando**:

```
public void mostrarComponente(String comando){
}
```

### Configurando eventos en componente NavegaciónUsuario

Aprovechando que todos los botones dentro del componente tienen texto, se va a tomar su comando (texto del botón) para ser enviado a la clase **VistaPrincipalComponent** y asi gestionar la navegación. De esta forma se puede evitar también la creación de los métodos **get** dentro de la clase **NavegacionUsuarioTemplate** por cada botón.

Dentro de la clase **NavegacionUsuarioComponent** específicamente en el método implementado **ActionPerformed** se va a enviar el comando del botón a la vista principal:

```
@Override
public void actionPerformed(ActionEvent e) {
  this.vistaPrincipalComponent.mostrarComponente(e.getActionCommand());
}
```

Del anterior código se pueden notar varias cosas:

* Como la gestión de navegación se hace desde la vista principal no es necesario realizar una discriminación de acción desde aquí, esto se realizara en la clase **VistaPrincipalComponent**.
* Es posible notar aquí la importancia de declarar un objeto inyectado para igualarlo dentro del constructor, si esto no se hiciera el objeto inyectado solo existiría dentro del constructor y cuando se intente llamar al método **mostrarComponente** desde el método **actionPerformed** sacaría un error en ejecución ya que para este entorno no existiría el objeto **vistaPrincipalComponent**.
* Recordar que el método **getAtionCommand()** va a retornar el texto que contiene el botón que activo el evento (el que se oprimió) en forma de String asi que puede enviarse sin problema como argumento al método **mostrarComponente**.

Sin embargo, como se vió anteriormente, para hacer la separación del texto con el icono en cada botón el texto iniciaba con unos espaciós, para probar esto, se realiza una muestra por consola asi:

```
@Override
public void actionPerformed(ActionEvent e) {
    System.out.println(e.getActionCommand());
    this.vistaPrincipalComponent.mostrarComponente(e.getActionCommand());
}
```

Cuando se ejecuta el programa y se oprime cualquier botón del componente **navegacionUsuario** y se observa la consola se puede notar lo siguiente:

<figure><img src="https://camo.githubusercontent.com/b2a61db0b3f5fc7cd641a248587647af881795322cfa3264d2d59104476cfcdb/68747470733a2f2f692e696d6775722e636f6d2f6e6f45536f59542e706e67" alt=""><figcaption></figcaption></figure>

Texto de cada botón con espacios al inicio

No se quieren enviar esos espacios que tiene cada botón en su texto por que no se tiene la certeza de cuantos espacios son o si son los mismos en cada botón, ademas contarlos seria un desperdicio de tiempo.

Se va a hacer uso del método **trim** este método:

* **trim()**: Quita todos los espacios que existan antes y al finalizar un texto dentro de un String. la configuración queda asi:

```
@Override
public void actionPerformed(ActionEvent e) {
    System.out.println(e.getActionCommand().trim());
    this.vistaPrincipalComponent.mostrarComponente(e.getActionCommand().trim());
}
```

Una vez se ejecuta la aplicación y se ve la consola se puede notar lo siguiente:

<figure><img src="https://camo.githubusercontent.com/dc770c919370d023b1763ddaf068a1f16ce44be426c96a0ef9e74efce2ba2567/68747470733a2f2f692e696d6775722e636f6d2f7a49726632767a2e706e67" alt=""><figcaption></figcaption></figure>

Texto de cada botón sin espacios al inicio

Se puede observar que incluso si existe espacio entre el texto este se conserva como es el caso del comando **cerrar Sesión**.

_**Nota:** El método para mostrar por consola **(System.out.println)** se uso como una prueba, asi que se puede retirar._

### Configuración de la navegación

Ya esta casi todo listo para configurar la navegación, ahora se codificará en el método **mostrarComponente** de la clase **VistaPrincipalComponent**. Una vez se recibe el comando del botón desde el componente **navegacionUsuario** se puede llamar a los demás componentes de acuerdo a la petición del usuario. Esto se realiza con un **switch / case** de la siguiente forma:

```
public void mostrarComponente(String comando){
    switch(comando){
        case "Inicio":
            break;
        case "Perfil":
            break;
        case "Amigos":
            break;
        case "Productos":
            break;
        case "Configuraciones":
            break;
        case "Cerrar Sesión":
            break;
    }
}
```

Note que cada caso dentro del **switch** corresponde al comando de cada botón. Ahora dentro de cada caso se va a realizar la incorporación de cada uno de los componentes de acuerdo a la petición. Se realiza el ejemplo para el componente **inicio**, sin embargo para el resto de los componentes es igual:

_**Nota:** La opción cerrar sesión tendrá un tratamiento diferente y se discutirá de esto en la sección final **Control en la creación de componentes gráficos en memoria** por ahora se deja vacía._

* Primero se obtiene el panel que va a incorporar al componente gráfico desde la clase **VistaPrincipalTemplate** con su método **get** correspondiente, en este caso se llama al panel **pPrincipal**:

```
case "Inicio":
    vistaPrincipalTemplate.getPPrincipal();
    break;
```

* Se le indica al panel que va a agregar un Objeto gráfico:

```
case "Inicio":
    vistaPrincipalTemplate.getPPrincipal().add();
    break;
```

* Ahora se debe indicar al panel que componente será agregado, para esto es posible realizar una **ejemplificación anónima del componente** en cuestión. Para este caso será el componente gráfico **inicio**, se realiza entonces la ejemplificación de la clase **InicioComponent**:

```
case "Inicio":
    vistaPrincipalTemplate.getPPrincipal().add(new InicioComponent());
    break;
```

* Sin embargo como se sabe, la clase **Component** no cuenta con características gráficas por lo que se debe llamar a su clase **Template** correspondiente, se hace a traves del método **get** de esta:

```
case "Inicio":
    vistaPrincipalTemplate.getPPrincipal().add(
        new InicioComponent().getInicioTemplate()
    );
    break;
```

Se re acomoda el código para no ocupar mucho espacio horizontal.

Esto se realiza con los demás componentes y en teoría estaría listo, sin embargo, si se ejecuta la aplicación y se oprimen los botones se puede notar que este no realiza ningún cambio aparente.

**¿Por qué sucede esto?**

Hacen falta un par de configuraciones adicionales:

* Para empezar cada vez que se vuelva a llamar un nuevo componente para ser incorporado en el panel **pPrincipal** es necesario que antes de la incorporación se remueva todo lo que este panel contiene, para que esto sea posible se debe llamar al método **removeAll()**. Esto debe hacerse justamente antes de que empiece el switch:

```
public void mostrarComponente(String comando){
    vistaPrincipalTemplate.getPPrincipal().removeAll();
    switch(comando){
        ...
        ...
    }
```

* Cada vez que un componente sea agregado en el panel **pPrincipal** se debe actualizar toda la ventana para que esta esta pueda mostrar en la pantalla los cambios ocurridos. Para esto se debe llamar al método **repaint()**. Como este método se realiza una vez se haya incorporado el componente en el panel se debe escribir justo debajo del switch:

```
public void mostrarComponente(String comando){
    vistaPrincipalTemplate.getPPrincipal().removeAll();
    switch(comando){
        ...
        ...
    }
    vistaPrincipalTemplate.repaint();
}
```

Si se la aplicación y se oprimen los botones de la navegación se puede observar que ya reemplaza los componentes en el panel principal:

<figure><img src="https://camo.githubusercontent.com/e4f2ea7ae51b14c057129f7cdc06dc0894ced654891066087cefb5ce5069bf15/68747470733a2f2f692e696d6775722e636f6d2f324631725847372e706e67" alt=""><figcaption></figcaption></figure>

VentanaPrincipal una vez se oprimió el botón Inicio

<figure><img src="https://camo.githubusercontent.com/2e490429e2ecdcb15acb9c33f7998e3755c9ae3c7e00dd068686eef56f3d8216/68747470733a2f2f692e696d6775722e636f6d2f306e37596842522e706e67" alt=""><figcaption></figcaption></figure>

VentanaPrincipal una vez se oprimió el botón Configuraciones

## Control en la creación de componentes gráficos en memoria

Cuando se oprima el botón **Cerrar sesión** se quiere que la vista principal deje de ser visible y pueda verse de nuevo el Login. Una opción simple para esto puede ser declarar un objeto de tipo **LoginComponent** desde la clase **VistaPrincipalComponent**, ejemplificarla y decirle a la clase **VistaPrincipalTemplate** que deje de ser visible:

<figure><img src="https://camo.githubusercontent.com/21d13998015d02e02901c29a3643fa203cdea51831506e112c6c9531dde20e35/68747470733a2f2f692e696d6775722e636f6d2f7a7a49525176372e706e67" alt=""><figcaption></figcaption></figure>

Posible caso de regreso al Login

El anterior ejemplo funciona, sin embargo, es necesario recordar que cuando se inicio la aplicación la clase ejecutora **App** ya creo un objeto en memoria del componente **login**, y si se realiza el proceso anterior descrito se estaría creando otro objeto en memoria nuevo del componente **login** cada vez que se cierre sesión, ´por ende el objeto que se creo desde **App** quedaría en el _limbo_.

De hecho si se hecha un vistazo a la clase **LoginComponent** en su método **Entrar** se observa que cada vez que se entra a la ventana principal crea un nuevo objeto de esta:

<figure><img src="https://camo.githubusercontent.com/0f34a5b369c85726427725220be32207ed69a659dc7b0b7e3afe39510f4a3d11/68747470733a2f2f692e696d6775722e636f6d2f4c634e6538445a2e706e67" alt=""><figcaption></figcaption></figure>

Creación de un nuevo objeto cada vez que se entra a la aplicación

Esto es un problema enorme, imagine que un usuario entra y cierra sesión 10 veces, en memoria se estarían creando 10 objetos tanto del componente **login** como de **VistaPrincipal**, incluso cuando se habla de objetos en memoria de componentes gráficos en realidad se hace alusión a todas las clases que conforman un componente por lo que el problema se extiende a medida que se entra en mas detalle. Este problema debe ser arreglado.

Para empezar se va a hacer una **inyección de dependencia entre componentes** esta vez no con el propósito de crear una comunicación bidireccional, lo importante de esta inyección es garantizar que solo existirá un objeto en memoria para el componente de login y uno solo para el componente de la vista principal. **Esto no significa que siempre que se quiera controlar la creación de objetos de algún componente se deba realizar inyección de dependencia**, en este caso se hace por que desde el login se va a gestionar la visibilidad de la ventana principal una vez se inicie sesión y desde la ventana principal se va a gestionar la visibilidad del login una vez se cierre sesión y para eso es necesaria una comunicación bidireccional.

Como el programa inicia con el login la inyección se realizará desde la clase **LoginComponent** a la clase **VistaPrincipalComponent**:

* En la clase **LoginComponent**, específicamente en el método **entrar**, cuando se ejemplifica la clase **VistaPrincipalComponent**, se pasa ahora como argumento el **this** para mandar el objeto de esta clase inyectado:

```
this.vistaPrincipal = new VistaPrincipalComponent(this);
```

* En la clase **VistaPrincipalComponent**, ahora se va a recibir por parámetro un objeto de la clase **LoginComponent** y se iguala a un objeto (atributo) declarado del mismo:

```
private LoginComponent loginComponent;

public VistaPrincipalComponent(LoginComponent loginComponent){
    this.loginComponent = loginComponent;
    ...
}
```

La inyección ya esta hecha y ahora se tiene una comunicación bidireccional entre ambos componentes gráficos, sin embargo, aun no se ha evitado la creación de muchos objetos del componente **VistaPrincipal** para esto dentro del método **entrar** de la clase **LoginComponent** se realiza el siguiente cambio:

```
public void entrar(){
    if(vistaPrincipal == null)
        this.vistaPrincipal = new VistaPrincipalComponent(this);
    else
        this.vistaPrincipal.getVistaPrincipalTemplate().setVisible(true);
    loginTemplate.setVisible(false);
}
```

En el anterior código se realiza lo siguiente:

* Se pregunta si el objeto de la clase **VistaPrincipalComponent** no se ha ejemplificado, si aun no se ha entrado a la vista principal este objeto efectivamente estará vacío ya que no se ha ejemplificado antes.
  * Si este esta vacío se ejemplifica enviando como argumento una referencia de la clase **LoginComponent** con un **this** y asi realizar la inyección.
  * Si este ya se ha ejemplificado previamente (por ejemplo se inicio sesión una vez, se cerro la sesión y se volvió a iniciar) entonces se obtiene la clase **VistaPrincipalTemplate** mediante el método **get** y se le indica que sea Visible nuevamente.
* Para ambos casos la visibilidad del Login cambiara para que no se vea en pantalla.

Ya se ha arreglado una parte del problema, ahora solo queda configurar finalmente la opción de cerrar sesión. Dentro del método **mostrarComponente** de la clase **VistaPrincipalComponent** en la opción **Cerrar Sesión** se codifica:

```
case "Cerrar Sesión":
    this.loginComponent.getLoginTemplate().setVisible(true);
    this.vistaPrincipalTemplate.setVisible(false);
    break;
```

De esta manera se ha controlado la forma de iniciar y cerrar sesión gestionando correctamente la creación de objetos en los componentes gráficos.

Ahora si se observa a las demás opciónes de navegación se puede notar nuevamente que cada vez que se oprime cualquier botón que incorpora los componentes gráficos que se muestran en el panel **pPrincipal** se esta creando un objeto nuevo de estos. Esto es el mismo problema que acabamos de tratar.

<figure><img src="https://camo.githubusercontent.com/63adf7af2d0719718f511052a02d749bdf61338ab63132a9b880096d057e4141/68747470733a2f2f692e696d6775722e636f6d2f386373545a58532e706e67" alt=""><figcaption></figcaption></figure>

Problema en creación descontrolada de objetos de los componentes gráficos

Para corregir esto, una alternativa puede ser la de **declarar** los objetos de los componentes, **ejemplificarlos** en el constructor e **incorporar** ese objeto en las opciones de navegación:

_**Nota:** Se realizara el proceso solo con el componente gráfico **inicio** pero será igual para los demás componentes_.

**Declaración:**

```
// Al inicio de la clase VistaPrincipalComponent
private InicioComponent inicioComponent;
```

**Ejemplificación:**

```
// Dentro del constructor
this.inicioComponent = new InicioComponent();
```

**Incorporación:**

```
// Dentro del método mostrarComponente
case "Inicio":
    vistaPrincipalTemplate.getPPrincipal().add(
        inicioComponent.getInicioTemplate()
    );
    break;
```

Es posible notar que este enfoque funciona y se tiene de forma controlada la creación de sus componentes, sin embargo, como todos los componentes gráficos se van a cargar desde el constructor esto le va a restar rendimiento a la aplicación, imaginen que algún usuario ingresa solamente a revisar los productos y nunca oprime el botón de configuración o amigos, se habrá cargado todo el componente de configuraciones o amigos en vano y gastará memoria y rendimiento.

Una mejor alternativa es la que se uso en la clase **LoginComponent** donde con un condicional se controla la ejemplificación del objeto asi:

```
case "Inicio":
    if (this.inicioComponent == null)
        this.inicioComponent = new InicioComponent();
    vistaPrincipalTemplate.getPPrincipal().add(
        inicioComponent.getInicioTemplate()
    );
    break;
```

_**Nota:** Como se esta ejemplificando ahora desde el método mostrarComponente se debe retirar la ejemplificación que se realizó en el constructor_.

De esta forma la primera vez que se oprima el botón inicio se creara el objeto en memoria y se incorporara en la ventana principal, pero cuando se vuelva a oprimir simplemente incorporará el objeto que previamente se ejemplifico. Ademas de controlar la cantidad de objetos también lo se crean solamente en caso de ser necesario y de esta forma se gana también en el rendimiento de la aplicación.

## Resultado

Si has llegado hasta aquí **!felicitaciones!** se ha aprendido como incorporar componentes gráficos a la ventana principal para crear un Single-Page App. Se aprendió también como realizar navegación para gestionar la visibilidad de los componentes dentro de la ventana principal. Ademas se ha corregido la creación masiva de objetos de los componentes cuando se quiere gestionar su visibilidad.

## Actividad

Realizar la incorporación de componentes gráficos sobre la ventana principal de su proyecto y realizar navegación de tal forma que se controle la creación de objetos en memoria de los componentes.

### About

Clase 6 del curso de Interfaz Gráfica con Java, en donde se muestran conceptos relacionados con la incorporación de componentes gráficos en una Single-page app, enrutamiento y control de objetos en memoria de los componentes.

## Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemás de la Universidad Distrital Francisco Jose de Caldas

## Clase 7

### Objetivos

* Comprender el concepto de reutilización de componentes gráficos y las ventajas que provee al desarrollar interfaces gráficas de usuario.
* Reconocer los diferentes enfoques que existen para realizar reutilización de componentes gráficos y en que casos es mejor utilizar alguno de ellos.
* Identificar en que momento es necesario realizar la reutilización de componentes y que enfoque es acorde según la situación presentada.

## Antes de Comenzar

#### **Actualización de Imágenes en recursos**

Para continuar con la lección deberá actualizar la carpeta **resources/images** ya que se han agregado nuevas imágenes. Estas las puede descargar en este mismo repositorio entrando a la carpeta **Clase7** seguido de **resources/images**. Es recomendable seguir la misma estructura que se realiza dentro de esta carpeta ya que se estarán creando subcarpetas:

<figure><img src="https://camo.githubusercontent.com/43eb52256ba0b95eeefb27d558611113491e40915d4c89731f850775c252ce63/68747470733a2f2f692e696d6775722e636f6d2f6674467033476e2e706e67" alt=""><figcaption></figcaption></figure>

Divisiones dentro de la carpeta Images de Resources

#### **Ajustes en el servicio Recursos Service**

En el servicio **RecursosService** se crea un nuevo objeto decorador **Border**:

**Declaración:**

```
private Border borderGris;
```

**Ejemplificación:**

```
// Dentro del método crearBordes
borderGris = BorderFactory.createLineBorder(Color.LIGHT_GRAY, 2, true);
```

**Método get:**

```
public Border getBorderGris(){ return borderGris; }
```

Por ultimo se crea un objeto decorador tipo **Color**:

**Declaración:**

```
// Al inicio del servicio
private Color colorGrisClaro;
```

**Ejemplificación:**

```
// Dentro del método crearColores
colorGrisClaro = new Color(249, 246, 249);
```

**Método get:**

```
public Color getColorGrisClaro(){ return colorGrisClaro; }
```

_**Nota:** Recordar que estos objetos decoradores dentro del servicio **RecursosService** se crean pensando en que serán utilizados en varias partes del proyecto, si ese no es el caso entonces el objeto decorador debe ser creado unicamente en el componente gráfico donde se necesita._

#### **Ajustes en Vista Principal**

En esta sesión se va a construir el componente **inicio** y se quiere que una vez se abra la vista principal este sea visible. Para esto se realizan unas pequeñas modificaciones en la clase **VistaPrincipalComponent**:

* **Ejemplificación de componente dentro de constructor**

Anteriormente se había configurado la ejemplificación del componente **inicio** dentro del método **mostrarComponente** en su respectivo caso en el Switch, sin embargo ahora se realiza su ejemplificación dentro del constructor para que pueda ser visualizado una ez se abre la ventana principal:

```
// Dentro del constructor
this.inicioComponent = new InicioComponent();
```

* **Incorporación de componente dentro de constructor**

Para que el componente sea visible inmediatamente al abrir la ventana principal se debe incorporar el componente al panel **pPrincipal** dentro del constructor:

```
// Dentro del constructor
vistaPrincipalTemplate.getPPrincipal()
  .add(inicioComponent.getInicioTemplate());
```

* **Ajuste en el caso de incorporación del componente inicio**

Como el componente **inicio** ya fue ejemplificado dentro del constructor ya se tiene la certeza de que este ya fue creado previamente por lo que tener el condicional preguntando esto es algo redundante, es por esto que en el caso de incorporación del componente **inicio** basta con indicar que se va a incorporar al panel **pPrincipal** solamente:

```
case "Inicio":
  vistaPrincipalTemplate.getPPrincipal()
    .add(inicioComponent.getInicioTemplate());
  break;
```

#### **Recordatorio**

Recordando el recorrido, se tiene la vista principal con una integración de varios componentes gráficos, además existe un control de visibilidad mediante la navegación de componentes. También se reviso la importancia de controlar la creación de objetos de los componentes gráficos.

<figure><img src="https://camo.githubusercontent.com/e4f2ea7ae51b14c057129f7cdc06dc0894ced654891066087cefb5ce5069bf15/68747470733a2f2f692e696d6775722e636f6d2f324631725847372e706e67" alt=""><figcaption></figcaption></figure>

Vista Principal y Single-Page App

## Reutilización de componentes gráficos

En esta sesión se explicará un tema de gran importancia, la reutilización de componentes y en que casos realizar esta practica:

* Reutilizacion de componentes gráficos.
  * Enfoque de reutilización por incorporación.
  * Enfoque de reutilización por posicionamiento.

## Reutilización de componentes gráficos

En la sesión pasada se creo una serie de componentes que pueden ser visible una vez el usuario lo solicite oprimiendo los botones ubicados en el componente **navegacionUsuario**. Algunos de estos componentes gráficos son: **inicio**, **perfil**, **amigos**, **productos** y **configuraciones**. Sin embargo, estos componentes aun no tienen nada más que un color de fondo.

Esta lección esta enfocada en la construcción el componente gráfico **inicio** haciendo uso de la reutilizacion de otros componentes que se crearán para este propósito.

### Concepto de reutilización

Para entender mejor el concepto de reutilización se va a mostrar primero cual es el diseño deseado al crear el componente gráfico **inicio** a continuación:

<figure><img src="https://camo.githubusercontent.com/f2549cfcaee2f8773d94f061842e4823d5f80aa81ab795a47ebeb73ca90f658b/68747470733a2f2f692e696d6775722e636f6d2f364c63573972622e706e67" alt=""><figcaption></figcaption></figure>

Resultado de construcción de componente gráfico Inicio

Es posible notar con un pequeño grado de detalle que el componente gráfico **inicio** esta conformado por varios objetos gráficos, tiene algunos paneles, bastantes imágenes, títulos y párrafos. Sin embargo, aumentando el grado de detalle es posible notar que existen ciertas particularidades con los objetos gráficos que conforman al componente gráfico **inicio**.

Primero se observa la parte superior del componente, se puede ver que hay tres paneles y los tres contienen los mismos objetos gráficos, cada uno de ellos tiene una imágen en la parte superior, seguido de un título y un párrafo justificado en la parte inferior.

<figure><img src="https://camo.githubusercontent.com/1d2a527cf57030ca9788499fc786492827410013b5279c1192e23512d6162d10/68747470733a2f2f692e696d6775722e636f6d2f496935446f70762e706e67" alt=""><figcaption></figcaption></figure>

Paneles de la parte superior con un mismo patrón en sus objetos gráficos

Ahora se observa la parte inferior, se puede notar que hay un panel principal que contiene un conjunto de paneles que están distribuidos uniformemente a lo largo del panel contenedor. Observe que cada uno de estos paneles cuentan con un patrón, todos tienen un borde gris que los separa unos de otros, un icono centrado, seguido de un título y un párrafo centrados de igual forma.

<figure><img src="https://camo.githubusercontent.com/f547e328ee1dae22f12227cedf7d7d7a7467e868d999688bc061391172c9e2e6/68747470733a2f2f692e696d6775722e636f6d2f6d5a4676504a342e706e67" alt=""><figcaption></figcaption></figure>

Paneles de la parte inferior con un mismo patrón en sus objetos gráficos

Lo único que cambia en ambos casos es el contenido en cada panel, pero la estructura interna es idéntica. Otro factor importante es que dicha similitud en estructura está conformada por distintos objetos gráficos y aquí está la **clave para usar un componente reutilizable**, para crear un componente que se pueda reutilizar en varias partes este debe estar conformado por varios objetos gráficos que cumplen un patrón de estructura que se desea repetir en la interfaz gráfica.

No vale la pena construir un componente que repita el patrón de un simple objeto gráfico (piense en los botones del componente **navegacionUsuario**), aunque estos botones se conforman de varios elementos (Imágenes y texto) y cumplen con un patron de estructura que se repite, es solo un botón que puede ser construido con el servicio **ObjGraficosService**. Por otro lado si hay un patrón que se repite y vincula a varios objetos gráficos si vale la pena revisar si realizar la reutilización de componentes gráficos.

El componente **inicio** podría escribirse completamente en la clase **Template** sin depender de ningún otro componente para su construcción y no está mal, es una forma de hacerlo. Sin embargo, imagine todo el código repetido que va existir dentro de esta clase para mostrar 3 paneles que tienen una misma estructura y otros 6 paneles que tienen esta misma condición. Realmente es muy tedioso y llenará la clase **Template** de un extenso código que afectara en la forma en que se analiza, mantiene y se entiende el código.

Una alternativa a esto es la construcción de componentes gráficos que encapsulen el código de este patrón de estructura identificado y se pueda hacer uso de él, las veces que sean necesarias. A continuación se muestra a ver como hacer esto posible.

Cuando un componente depende de otros componentes para su construcción se crea una relación de **Componente Padre** Y **Componente Hijo** (No tiene que ver con el concepto de herencia) ya que el componente padre contiene al componente hijo. Es común encontrar este tipo de relaciónes, un ejemplo que ya se ha realizado es entre el componente **VistaPrincipal** y los componente **inicio**, **barraTitulo**, **navegacionUsuario** etc. Ahora el mismo componente **inicio** tendrá otros componentes para su construcción y estos serán los hijos de **inicio**, esta construcción estará basada en la reutilización de componentes que a su vez se basará en dos enfoques principales.

### Construcción base del componente inicio

Se va a construir a continuación la base del componente **inicio**, en su clase **Template** se va a crear unos paneles que sirven de soporte a los componentes a construir y además se crearán ciertos objetos más:

* Primero se obtienen los servicios **ObjGraficosService** y **RecursosService** que serán necesarios en la construcción de algunos objetos gráficos:

**Declaración:**

```
private ObjGraficosService sObjGraficos;
private RecursosService sRecursos; 
```

**Obtención de servicios:**

```
// Dentro del Constructor
sObjGraficos = ObjGraficosService.getService();
sRecursos = RecursosService.getService();
```

* Se proporciona de otro color de fondo al componente:

```
// Dentro del Constructor
this.setBackground(sRecursos.getColorGrisClaro());
```

* Se van a crear paneles base para contener los objetos gráficos que serán visibles en la ventana principal además de un Label que representará el título principal en el panel inferior (**pAcciones**):

**Declaración:**

```
// Declaración Objetos Gráficos 
private JPanel pMision, pVision, pNosotros, pAcciones;
private JLabel lAcciones;
```

**Método crearJPanels:**

```
public void crearJPanels(){
  this.pMision = sObjGraficos.construirJPanel(20, 15, 256, 230, Color.WHITE, null);
  this.add(pMision);

  this.pVision = sObjGraficos.construirJPanel(296, 15, 256, 230, Color.WHITE, null);
  this.add(pVision);
  
  this.pNosotros = sObjGraficos.construirJPanel(572, 15, 256, 230, Color.WHITE, null);
  this.add(pNosotros);

  this.pAcciones = sObjGraficos.construirJPanel(20, 260, 810, 330, Color.WHITE, null);
  this.add(pAcciones);
}
```

**llamada del método dentro del constructor:**

```
// Dentro del constructor
this.crearJPanels();
```

Cuando se ejecuta la aplicación y se oprime el botón que llama al componente **inicio**, la interfaz gráfica luce de la siguiente manera:

<figure><img src="https://camo.githubusercontent.com/df57aa68aada8181f48325414d0c81f126d0b869dcac79617185baa9c85c61a9/68747470733a2f2f692e696d6775722e636f6d2f4a7350766b50332e706e67" alt=""><figcaption></figcaption></figure>

Componente inicio con sus paneles base adicionados

Para este componente se va a realizar la modularización un tanto distinta, esta vez no se va a separar la creación por tipo de objetos gráficos, **se va a separar la creación por el contenido en cada panel**, con una pequeña excepción en la creación de objetos decoradores, por ahora solo se declaran los métodos:

```
public void crearObjetosDecoradores(){
}
```

```
public void crearContenidoPMision(){
}
```

```
public void crearContenidoPVision(){
}
```

```
public void crearContenidoPNosotros(){
}
```

```
public void crearContenidoPAcciones(){
}
```

## Enfoque de reutilización por incorporación.

Este enfoque se caracteriza por que cuando se crea el **componente hijo**, este va a ser incorporado a un panel que exista previamente en el **componente padre**, por ejemplo, ya fueron creados los paneles **pMision, pVision, pNosotros** en el componente padre. Esto quiere decir que no es necesario preocuparse con la locación del componente hijo, esta ya se configuro cuando se crearon los paneles de incorporación, lo que si se debe tener pendiente es que tanto el panel de incorporación como el componente hijo tengan el mismo tamaño y de esa forma no habrán problemás de posicionamiento. Este enfoque ya se ha realizado en sesiones anteriores, donde **navegaciónUsuario** y **barraTitulo** fueron incorporados a unos paneles creados previamente en **vistaPrincipal**.

Se crea un nuevo component que encapsule la estructura del contenido de los paneles superiores, este componente será llamado **tarjeta**, para esto se crea su respectivo paquete y clases dentro del directorio **components**:

<figure><img src="https://camo.githubusercontent.com/66f20e8889674125a6e92bfedf8c5bdfd092ecbbf7fdab06db8748e2c780ba56/68747470733a2f2f692e696d6775722e636f6d2f4b77544f4e72732e706e67" alt=""><figcaption></figcaption></figure>

Componente tarjeta creado dentro del paquete components

* Se empieza con la clase **Component** y como de costumbre se realizan los siguientes pasos:

Como el componente no tiene botones no se va a necesitar la implementación de ninguna interfaz.

```
public class TarjetaComponent{
}
```

Se crea un objeto de la clase **Template** y se realiza la inyección enviándose por argumento la referencia de si mismo con la palabra **this**:

**Declaración:**

```
private TarjetaTemplate tarjetaTemplate;
```

**Ejemplificación:**

```
// Dentro del constructor
tarjetaTemplate = new TarjetaTemplate(this);
```

Se crea el método **get** de su respectivo **Template**:

```
public TarjetaTemplate getTarjetaTemplate(){
  return tarjetaTemplate;
}
```

* Ahora se codifica la clase **Template**:

Esta al representar las características gráficas del componente debe heredar de un **JPanel**:

```
public class TarjetaTemplate extends JPanel{
}
```

Como se ha realizado anteriormente, se va a obtener los servicios **ObjGraficosService** y **RecursosService** además de obtener por constructor la inyección de la clase **Component**:

**Ejemplificación**

```
private TarjetaComponent tarjetaComponent;
private ObjGraficosService sObjGraficos;
private RecursosService sRecursos;
```

**Obtención de servicios e inyección:**

```
public TarjetaTemplate(TarjetaComponent tarjetaComponent){
  this.tarjetaComponent = tarjetaComponent;
  sObjGraficos= ObjGraficosService.getService();
  sRecursos = 
  RecursosService.getService();
}
```

Ahora se configuran las propiedades gráficas al componente:

```
// Dentro del constructor
this.setSize(256, 230);
this.setBackground(Color.white);
this.setLayout(null);
this.setVisible(true);
```

Note que el tamaño del componente debe ser igual panel al cual será incorporado. En este caso en los paneles **pMision, pVision y pNosotros**.

<figure><img src="https://camo.githubusercontent.com/a4eb04ebf8b225a45d735f067a76bc68c2c73cd9657572a1a81520b087e178be/68747470733a2f2f692e696d6775722e636f6d2f68474c684272632e706e67" alt=""><figcaption></figcaption></figure>

Mismo tamaño del componente con los paneles a reemplazar

Este componente va a contener:

* Label que contiene la imagen.
* Label que contiene el título.
* Label que contiene el párrafo.
* Objeto decorador iDimAux para redimensionar imágenes.

**declaración:**

```
// Declaración Objetos Gráficos
private JLabel lTitulo, lImagen, lParrafo;

// Declaración Objetos Decoradores
private ImageIcon iDimAux;
```

Como el contenido del título, el contenido del párrafo y la imagen van a ser las propiedades que serán dinámicas (que van a variar). Estas deben ser recibidas de alguno modo. Se podría tomar el enfoque de **setters y getters**, sin embargo, se opta por recibir estos parámetros desde el constructor:

<figure><img src="https://camo.githubusercontent.com/7c98d6e64a203b74cfffa3e40b1bf2f47920b579703b4a4affa116e228686807/68747470733a2f2f692e696d6775722e636f6d2f4e724f36384e652e706e67" alt=""><figcaption></figcaption></figure>

Parámetros recibidos en el constructor

Se puede notar que ahora el constructor a parte de recibir la **inyección de dependencia** recibe también ahora:

* Un **String** que representa el título.
* Un **ImageIcon** que representa la imágen del componente.
* Un **String** que representa el párrafo.

_**Nota:** Como el código de este componente es corto y para evitar la declaración de más atributos en la clase se van a crear los objetos gráficos dentro del constructor:_

**Imagen:**

```
// Dentro del constructor
iDimAux = new ImageIcon(
  iImagen.getImage()
    .getScaledInstance(246, 110, Image.SCALE_AREA_AVERAGING)
);
lImagen = sObjGraficos.construirJLabel(
  null, 
  5, 5, 246, 110, 
  sRecursos.getCMano(),
  iDimAux, 
  null, null, null, null,
  "c"
);
this.add(lImagen);
```

Se puede observar que la imágen que redimensiona la variable auxiliar **iDimAux** es la que fue recibida por parámetro el constructor.

**título:**

```
// Dentro del constructor
this.lTitulo = sObjGraficos.construirJLabel(
  titulo,
  15, 120, 180, 30,
  null, null,
  sRecursos.getFontTitulo(),
  null,
  sRecursos.getColorPrincipal(),
  null,
  "l"
);
this.add(lTitulo);
```

Se puede observar que el texto que se envía para la construcción del Label es el String **título** recibido por parámetro desde el constructor.

**Párrafo:**

```
// Dentro del constructor
lParrafo = sObjGraficos.construirJLabel(
  "<html><div align='justify'>" + parrafo + "</div></html>", 
  20, 120, 206, 120, 
  null, null,
  sRecursos.getFontLigera(), 
  null, 
  sRecursos.getColorGrisOscuro(), 
  null,
  "c"
);
this.add(lParrafo);
```

Se puede observar que el texto que se envía para la construcción del Label es el String **parrafo** recibido por parámetro desde el constructor. También se puede observar que el párrafo está contenido dentro de etiquetas html. Esto se realiza para darle la estructura de texto justificado ya que es el componente quien se debe encargar de la estructura.

En teoría el componente esta listo, sin embargo, ahora el editor de texto indica que hay un error en la clase **Component** justamente en la ejemplificación de la clase **Template**, esto es debido a que ahora por constructor se están pidiendo más parámetros y como argumento solo se esta enviando la **inyección**.

<figure><img src="https://camo.githubusercontent.com/0a4e935d36c4f1e9c98893cf68ade8c62a3a062ed9ebafafe2a0673ce9efbabb/68747470733a2f2f692e696d6775722e636f6d2f50314a565452352e706e67" alt=""><figcaption></figcaption></figure>

Error en clase Component ya que se piden más parámetros

Para resolver esto se debe recibir por parámetro en el constructor de la clase **Component** los mismos parámetros (**título, Imagen, Párrafo**), para después pasarlos a su clase **Template**:

```
public TarjetaComponent(String titulo, ImageIcon iImagen, String parrafo) {
  tarjetaTemplate = new TarjetaTemplate(this, titulo, iImagen, parrafo);
}
```

El componente **Tarjeta** esta listo para ser incorporado, se debe hacer dicha incorporación en el componente **inicio**. En la clase **InicioTemplate** se van a declarar las imágenes necesarias para los componentes, luego se ejemplifican:

**Declaración:**

```
private ImageIcon iTarjeta1, iTarjeta2, iTarjeta3;
```

**Ejemplificación:**

```
// Dentro del método crearObjetosDecoradores
this.iTarjeta1 = new ImageIcon("clase7/resources/images/tarjetas/tarjeta1.jpg");
this.iTarjeta2 = new ImageIcon("clase7/resources/images/tarjetas/tarjeta2.jpg");
this.iTarjeta3 = new ImageIcon("clase7/resources/images/tarjetas/tarjeta3.jpg");
```

Note algo importante, aunque es el componente **tarjeta** el que va a mostrar las imágenes en pantalla estas van a ser creadas de su componente padre que es **inicio** en este caso. Ya que el componente **tarjeta** exige unas imágenes como parámetros y estas deben ser creadas previamente. Sin embargo el componente **Tarjeta** si se encarga de la redimensión en las imágenes.

Se va a realizar la incorporación de este componente primero en el método **crearContenidoPMision**, como este enfoque es **por medio de incorporación** lo que se debe realizar es adicionar el componente al panel que incorporará el componente gráfico:

* Se llama al panel en cuestión y se indica que se añadirá un objeto gráfico con el método **add**:

```
public void crearContenidoPMision() {
  this.pMision.add();
}
```

* Dentro de los paréntesis se puede crear una **Ejemplificación anónima** del componente:

```
public void crearContenidoPMision() {
    this.pMision.add(new TarjetaComponent());
}
```

* Sin embargo la clase **Component** pide por parámetros 3 cosas **(String título, ImageIcon imagen, String párrafo)** asi que se debe enviar por argumento lo que se pide:

```
public void crearContenidoPMision() {
  this.pMision.add(
    new TarjetaComponent(
      "Nuestra Misión", 
      iTarjeta1, 
      "Brindar cursos a la comunidad académica para" + 
      "complementar habilidades fuera del pensum común." 
    )
  );
}
```

Hasta el momento la incorporación esta fallando y es que es necesario recordar que la clase **Component** no cuenta con características gráficas, es la clase **Template** la que las tiene asi que se debe obtener mediante el método **get** de la clase **Component**.

```
public void crearContenidoPMision() {
  this.pMision.add(
    new TarjetaComponent(
      "Nuestra Misión", 
      iTarjeta1, 
      "Brindar cursos a la comunidad académica para" + 
      "complementar habilidades fuera del pensum común." 
    ).getTarjetaTemplate()
  );
}
```

* Ahora el componente ha quedado incorporado, solo falta llamar al método **crearContenidoPMision** desde el constructor para que el contenido pueda ser visible:

```
// Dentro del constructor
this.crearObjetosDecoradores();
this.crearContenidoPMision();
```

_**Nota:** También faltaba llamar al método **crearObjetosDecoradores** dentro del constructor._

Si se corre la aplicación y se oprime el botón que muestra el componente **inicio** la interfaz se ve asi:

<figure><img src="https://camo.githubusercontent.com/54dbee8ef349ad7960acd34f3dac9fe4589d82caac50869e5642b35055c29c4c/68747470733a2f2f692e696d6775722e636f6d2f4375685859764a2e706e67" alt=""><figcaption></figcaption></figure>

Interfaz gráfica con la llamada del componente tarjeta 1 vez

Ahora se realiza el mismo proceso con los otros 2 paneles, claramente el contenido será distinto asi que los argumentos enviados al componente también lo serán:

**Panel pVision:**

```
public void crearContenidoPVision() {
  this.pVision.add(
    new TarjetaComponent(
      "Nuestra Visión", 
      iTarjeta2, 
      "Brindar cursos académicos al 80% de los" +
      "estudiantes de ingeniería de Sistemás." 
    ).getTarjetaTemplate()
  );
}
```

**Panel pNosotros:**

```
public void crearContenidoPNosotros() {
  this.pNosotros.add(
    new TarjetaComponent(
      "Sobre Nosotros", 
      iTarjeta3, 
      "Somos un grupo de trabajo de la Universidad" +
      "distrital Francisco jose de Caldas."
    ).getTarjetaTemplate()
  );
}
```

**llamada de métodos dentro del constructor**

```
// Dentro del constructor
this.crearContenidoPVision();
this.crearContenidoPNosotros(); 
```

Ejecutando la aplicación nuevamente ahora la interfaz se ve asi:

<figure><img src="https://camo.githubusercontent.com/12aeccee57ee622873d58f3fc4773c0a87386d683cb1e8a4a679d22b3d6105cb/68747470733a2f2f692e696d6775722e636f6d2f307741445a556e2e706e67" alt=""><figcaption></figcaption></figure>

Componente inicio con la reutilización del componente Tarjeta

## Enfoque de reutilización por Posicionamiento.

A menudo existen casos donde se requiere un componente reutilizable una n cantidad de veces y no se tiene con certeza el numero de veces que se va a reutilizar, un ejemplo puede ser una lista de películas obtenidas externamente donde cada película va a ser un componente hijo, sin embargo podría ser un listado largo de películas que se va a mostrar y no se sabe cuantas sean exactamente. Por lo que crear paneles base para incorporar cada componente hijo es una mala idea, una buena opción es traer el componente gráfico hijo y posicionarlo dentro de un espacio dado.

Este enfoque se caracteriza por que cuando se cree el **componente hijo**, este no va se va incorporar a ningún objeto gráfico directamente sino que va a ocupar un espacio dentro del **componente padre**. Por lo que ahora se debe tener presente la locación del componente aunque por otro lado ya no es una preocupación que el componente hijo tenga el mismo tamaño de algún objeto gráfico previo ya que al no incorporar nada esta libre de tener un tamaño independiente.

Se crea un nuevo component que encapsule la creación del contenido de los paneles inferiores, este componente será llamado **accion**, para esto se crea su respectivo paquete y clases dentro del directorio **components**:

<figure><img src="https://camo.githubusercontent.com/8ed31d211245d427e9744a5ced54c16bae5cb3a809b1ae691eb61377f89ae8e8/68747470733a2f2f692e696d6775722e636f6d2f6869574b6754742e706e67" alt=""><figcaption></figcaption></figure>

Componente accion creado dentro del paquete components

* Se empieza con la clase **Component** y como de costumbre se realizan los siguientes pasos:

Como el componente no tiene botones no va a necesitar la implementación de ninguna interfaz.

```
public class AccionComponent {
}
```

Se crea un objeto de la clase **Template** y se realiza la inyección enviándose por argumento la referencia de si mismo con la palabra **this**:

**Declaración:**

```
private AccionTemplate accionTemplate;
```

**Ejemplificación:**

```
// Dentro del constructor
this.accionTemplate= new AccionTemplate(this);
```

Se crea su método **get** de su respectivo **Template**:

```
public AccionTemplate getAccionTemplate(){
  return accionTemplate;
}
```

* Ahora se va a codificar la clase **Template**:

Esta al representar las características gráficas del componente debe heredar de un **JPanel**:

```
public class AccionTemplate extends JPanel {
}
```

Se obtienen los servicios **ObjGraficosService** y **RecursosService** además de obtener por constructor la inyección de la clase **Component**:

**Ejemplificación**

```
private AccionComponent accionComponent;
private ObjGraficosService sObjGraficos;
private RecursosService sRecursos;
```

**Obtención de servicios e inyección:**

```
public AccionTemplate(AccionComponent accionComponent){
  this.accionComponent = accionComponent;
  sObjGraficos= ObjGraficosService.getService();
  sRecursos = RecursosService.getService();
}
```

Ahora se configuran las propiedades gráficas al componente:

```
// Dentro del constructor
this.setSize(250, 125);
this.setBackground(Color.WHITE);
this.setBorder(sRecursos.getBorderGris());
this.setLayout(null);
this.setVisible(true);
```

Note que el componente tiene un borde que se llama del servicio **RecursosService** para poder diferenciarse. Además el tamaño del componente no tiene la restricción de ser igual a ningún objeto gráfico del componente padre ya que se usará un enfoque de **posicionamiento**.

Este componente va a contener:

* Label que contiene el título.
* Label que contiene el icono.
* Label que contiene el párrafo.
* Objeto decorador iDimAux para redimensionar imágenes.

**declaración:**

```
// Declaración Objetos Gráficos
private JLabel lImagen, lTitulo, lParrafo;

// Declaración Objetos Decoradores
private ImageIcon iDimAux;
```

Como el contenido del título, el contenido del párrafo y el icono van a ser las propiedades que serán dinámicas (que van a variar). Estas deben ser recibidas de alguno modo. Nuevamente se opta por recibir estos parámetros desde el constructor:

<figure><img src="https://camo.githubusercontent.com/3e95e8cb121b44ec3ed2305ae064c2bf395794e747b2fb07f84a2f89485f4af7/68747470733a2f2f692e696d6775722e636f6d2f66316f6e634c512e706e67" alt=""><figcaption></figcaption></figure>

Parámetros recibidos en el constructor

Se puede notar que ahora el constructor a parte de recibir la **inyección de dependencia** recibe también ahora:

* Un **ImageIcon** que representa el icono del componente.
* Un **String** que representa el título.
* Un **String** que representa el párrafo.

_**Nota:** Como el código de este componente también es corto y para evitar la declaración de más atributos en la clase se crean los objetos gráficos dentro del constructor:_

**Imagen:**

```
// Dentro del constructor
iDimAux = new ImageIcon(
  imagen.getImage()
    .getScaledInstance(45, 45, Image.SCALE_AREA_AVERAGING)
);
this.lImagen = sObjGraficos.construirJLabel(
  null, 
  (250 - 60) / 2, 5, 45, 45,
  null,
  iDimAux, 
  null, null, null, null,
  "c"
);
this.add(lImagen);
```

Se puede observar que la imagen que redimensiona la variable auxiliar **iDimAux** es la que fue recibida por parámetro en el constructor.

**título:**

```
// Dentro del constructor
this.lTitulo = sObjGraficos.construirJLabel(
  titulo,
  (250 - 220) / 2, 50, 220, 30,
  null, null,
  sRecursos.getFontTitulo(),
  null,
  sRecursos.getColorGrisOscuro(),
  null,
  "c"
);
this.add(lTitulo);
```

Se puede observar que el texto que se envía para la construcción del Label es el String **título** recibido como parámetro desde el constructor.

**Párrafo:**

```
// Dentro del constructor
this.lParrafo = sObjGraficos.construirJLabel(
  "<html><div align='center'>" + parrafo + "</div></html>",
  (250 - 230) / 2, 75, 230, 50, 
  null, null,
  sRecursos.getFontLigera(), 
  null, 
  sRecursos.getColorGrisOscuro(),
  null,
  "c"
);
this.add(lParrafo);
```

Se puede observar que el texto que se envía para la construcción del Label es el String **parrafo** recibido como parámetro desde el constructor. Además el parrafo esta envuelto en etiquetas HTML que le proporcionan una estructura al texto de estar centrado. Recordar que este componente se debe encargar de encapsular aspectos de estructura como este.

Como se vio con el anterior componente **tarjeta** la clase **Component** ahora debe ser modificada ya que la clase **Template** exige nuevos parámetros que deben ser enviados como argumento.

Para resolver esto se debe recibir por parámetro en el constructor de la clase **Component** los mismos parámetros (**Imagen, titulo, Párrafo**), para después pasárselos a su clase **Template**:

```
public AccionComponent(ImageIcon imagen, String titulo, String parrafo) {
    this.accionTemplate= new AccionTemplate(this, imagen, titulo, parrafo);
}
```

El componente gráfico **Accion** esta listo para usarse ahora se explica de que manera se reutilizará desde su componente padre.

En la clase **InicioTemplate** primero se van a declarar las imágenes necesarias para los componentes, luego se ejemplifican:

**Declaración:**

```
private ImageIcon iClase, iPantalla, iIdea, iCelular, iEstadistica, iDireccion; 
```

**Ejemplificación:**

```
// Dentro del método crearObjetosDecoradores
this.iClase = new ImageIcon("clase7/resources/images/acciones/clases.png");
this.iPantalla = new ImageIcon("clase7/resources/images/acciones/pantalla.png");
this.iCelular = new ImageIcon("clase7/resources/images/acciones/celular.png");
this.iIdea = new ImageIcon("clase7/resources/images/acciones/ideas.png");
this.iEstadistica = new ImageIcon("clase7/resources/images/acciones/estadisticas.png");
this.iDireccion = new ImageIcon("clase7/resources/images/acciones/direccion.png");
```

* Previo a la llamada del componente gráfico **Accion** se va crear un título al panel inferior **pAcciones**:

```
public void crearContenidoPAcciones(){
  this.lAcciones = sObjGraficos.construirJLabel(
    "Nuestros Servicios",
    10, 10, 160, 30,
    null, null,
    sRecursos.getFontTitulo(),
    null,
    sRecursos.getColorPrincipal(),
    null,
    "c"
  );
  this.pAcciones.add(lAcciones);
}
```

Como esta vez no se va a incorporar ningún componente no es posible crear la ejemplificación de forma anónima, es necesario crear variables de objeto para representar al componente hijo:

```
// Dentro del método crearContenidoPAcciones
AccionTemplate p1= new AccionComponent();
```

Se debe recordar que:

* la clase **AccionComponent** exige el envío de algunos argumentos.
* Se debe obtener la clase **Template** del componente ya que el objeto que se debe agregar debe contener características gráficas y se declaro inicialmente como un **ActionTemplate**.

```
// COMPONENTE ACCIÓN 1 ------------------------------------
AccionTemplate p1= new AccionComponent(
  iClase, 
  "Clases", 
  "Clases a la comunidad que complementan el pensum."
).getAccionTemplate();
```

_**Nota:** Puede observar que se crea un objeto tipo Template del Componente Accion pero se esta igualando a la ejemplificación de la clase Component, esto claramente generaría error pero esto se hace por que inmediatamente en la ejemplificación se va a traer la clase template a traves del método **getAccionTemplate()** y asi la igualdad será cierta._

Ya se tiene un objeto del componente hijo dentro de **inicio** pero aun se debe indicar la posición y además realizar la agregación en el panel inferior **pAcciones**:

```
p1.setLocation(15, 50);
this.pAcciones.add(p1);
```

Para probar el método se llama en el constructor:

```
// Dentro del constructor
this.crearContenidoPAcciones();
```

Al ejecutar la aplicación, la interfaz luce asi:

<figure><img src="https://camo.githubusercontent.com/4df20161dd597f6a10334e5afdc888aff43c81e8224988e1bf789bd04b1904d8/68747470733a2f2f692e696d6775722e636f6d2f327078667931482e706e67" alt=""><figcaption></figcaption></figure>

Componente inicio con la agregación de un componente accion

este proceso se repite varias veces más:

```
// COMPONENTE ACCIÓN 2 ------------------------------------
AccionTemplate p2 = new AccionComponent(
  iPantalla, 
  "Clases Virtuales", 
  "Cursos virtuales como medio de enseñanza."
).getAccionTemplate();
p2.setLocation(30 + p2.getWidth(), 50);
this.pAcciones.add(p2);

// COMPONENTE ACCIÓN 3 ------------------------------------
AccionTemplate p3 = new AccionComponent(
  iIdea, 
  "Generación de ideas", 
  "Desarrollo de ideas con tecnologías actuales."
).getAccionTemplate();
p3.setLocation(45 + p3.getWidth() * 2, 50);
this.pAcciones.add(p3);

// COMPONENTE ACCIÓN 4 ------------------------------------
AccionTemplate p4 = new AccionComponent(
  iCelular, 
  "Notificaciones", 
  "Notificaión el estado de tus cursos y actividades."
).getAccionTemplate();
p4.setLocation(15, 65 + p4.getHeight());
this.pAcciones.add(p4);

// COMPONENTE ACCIÓN 5 ------------------------------------
AccionTemplate p5 = new AccionComponent(
  iEstadistica, 
  "Estadisticas", 
  "Gestión de participación en nuestros cursos."
).getAccionTemplate();
p5.setLocation(30 + p5.getWidth(), 65 + p5.getHeight());
this.pAcciones.add(p5);

// COMPONENTE ACCIÓN 6 ------------------------------------
AccionTemplate p6 = new AccionComponent(
  iDireccion, 
  "Dirección", 
  "Damos direcciónamiento a nuestros estudiantes."
).getAccionTemplate();
p6.setLocation(45 + p6.getWidth() * 2, 65 + p6.getHeight());
this.pAcciones.add(p6);
```

Corriendo la aplicación es posible ver el resultado propuesto desde el comienzo:

<figure><img src="https://camo.githubusercontent.com/f2549cfcaee2f8773d94f061842e4823d5f80aa81ab795a47ebeb73ca90f658b/68747470733a2f2f692e696d6775722e636f6d2f364c63573972622e706e67" alt=""><figcaption></figcaption></figure>

Vista Principal con el panel inicio terminado

El anterior enfoque queda un tanto desperdiciado debido a que se esta repitiendo el código las 6 veces que fue reutilizado el componente. Si existieran 10 acciones más se tendría que volver a repetir este código y no es para nada optimo hacer esto. Un enfoque apropiado es crear un arreglo de objetos donde cada objeto contenga la información necesaria (Imagen, titulo, Párrafo) y recorrerlo mediante un ciclo para que de esta forma el código solo sea escrito una sola vez y asi ahorrar lineas de código. Sin embargo este enfoque se discutirá en futuras clases cuando se hable acerca de **Servicios Lógicos**.

### Pequeña Reflexión de la reutilización

El concepto de reutilización es quizás el factor que más le da reconocimiento al uso de los componentes gráficos, de esta forma no solo se tiene un código mucho más entendible y organizado. También se esta encapsulado la estructura de una plantilla dentro de un componente lo cual dota del código de una estructuración y modularizacion alta. Incluso el concepto de reutilización puede ser tan util que si por ejemplo en algún otro componente como puede ser **Productos** se quiere usar uno de estos componentes reutilizables perfectamente se puede hacer haciendo de su función mucho más amplia para el proyecto.

Otro criterio que podría tomarse a favor es el dinamismo hacia el tamaño y posición de objetos gráficos dentro de la estructura de un componente altamente reutilizable, piense por un momento, que tal si se quiere usar de nuevo el componente **tarjeta** en otra parte del proyecto pero esta vez con más altura o menos ancho, podría entonces el componente pedir el ancho y alto por parámetros para incorporarlo o posicionarlo en la interfaz. Además se puede usar un posicionamiento y tamaño de los objetos gráficos internos basado en **porcentajes** para que no se pierda la estructura deseada.

Este posicionamiento basado en **porcentajes** es un enfoque que mejora el enfoque de posicionamiento en pixeles pero esta basado en el. En este curso no veremos dicho enfoque pero se menciona para motivar a la investigación al estudiante de este curso.

## Resultado

Si has llegado hasta aquí **!Felicidades!** se ha aprendido a realizar reutilización de componentes gráficos, cuando utilizarse y los diferentes enfoques de **incorporación y posicionamiento** para encapsular la estructura de una plantilla en un componente que se puede usar varias veces.

En la siguiente clase se revisará de nuevo el tema de **Eventos** y esta vez vamos a estudiar los eventos del **Mouse**.

## Actividad

Utilizar reutilización de componentes en sus proyectos para encapsular la lógica y estructura de una plantilla que pueda utilizarse varias veces.

Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 8

### Objetivos

* Identificar los diferentes eventos de Mouse disponibles con sus respectivas características, forma de activación, limites y casos particulares.
* Reconocer las diferentes interfaces encargadas de escuchar eventos del Mouse y cada uno de sus métodos de implementación para activar y manipular los eventos.
* Identificar algunos métodos auxiliares relacionados con la posición del puntero del mouse o el movimiento del Scroll que ayudan con la manipulación de eventos.

## Antes de Comenzar

#### **Recordatorio**

Recordando el recorrido, se tiene la vista principal con una integración de varios componentes, se ha construido el componente **inicio** a base de la **reutilización de otros componentes** encargados de encapsular la estructura de una plantilla y se utilizó ademas varios enfoques para realizar dicha reutilización.

<figure><img src="https://camo.githubusercontent.com/f2549cfcaee2f8773d94f061842e4823d5f80aa81ab795a47ebeb73ca90f658b/68747470733a2f2f692e696d6775722e636f6d2f364c63573972622e706e67" alt=""><figcaption></figcaption></figure>

Resultado de construcción de componente Inicio

## Eventos de Mouse

A continuación se mostrará el uso de los eventos del Mouse y estos están divididos en 3 grandes grupos, estos grupos se derivan de las diferentes interfaces que se ocupan de la escucha de eventos por Mouse:

* **Eventos MouseListener**
* **Eventos MouseMotionListener**
* **Eventos MouseWheelListener**

Esta sesión se concentra en identificar las características de todos los métodos implementados por cada uno de los 3 grandes grupos para lo cual se va a construir el componente **configuraciones**. Dentro de este, se experimentará con cada uno de los eventos y asi reconocer cuando usar cada evento, como se activan, en que momento dejan de funcionar, casos particulares etc. Una vez reconocida la función de cada tipo de evento en la siguiente lección se identificarán las partes en el proyecto donde será util implementar estos eventos para darle más interactividad a la aplicación.

_**Nota:** Estos eventos tienen la particularidad de ser usados comúnmente para una alta variedad de objetos gráficos a diferencia de los eventos por acción donde casi siempre suele usarse exclusivamente a los botones. Los eventos de Mouse buscan darle interactividad a más objetos gráficos._

## Construcción Componente Gráfico Configuraciones

En esta sección se va a ver de manera rápida la construcción del componente **configuraciones** que va a servir como medio para poder reconocer las características de cada uno de los eventos. Cuando hablamos de eventos por Mouse un aspecto importante a resaltar es el **posicionamiento del puntero**, este sera el enfoque con el cual se va a identificar las características de cada tipo de evento.

Para lo anterior el componente **Configuraciones** va tomar el papel de una herramienta para configuración de la sensibilidad y funcionamiento del Mouse, donde el usuario podrá interactuar a manera de prueba con el mouse sobre un panel y comprobar que este funciona adecuadamente.

El componente **Configuraciones** contendrá:

* **Panel de interacción:** Un panel vacío que tendrá las propiedades de interactividad con las que el usuario podrá probar su Mouse.
* **Panel de control:** Un panel que contiene una serie de **JLabels** y que le darán al usuario información importante relacionada con el posicionamiento del puntero del mouse y entre varios de sus datos esta:
  * Posición (x,y) una vez se realiza un click.
  * Posición (x,y) una vez se presiona el botón izquierdo del mouse.
  * Posición (x,y) una vez se suelta el botón izquierdo del mouse.
  * Posición (x,y) en tiempo real del puntero del Mouse.
  * Posición (x,y) en tiempo real del puntero del Mouse una vez se tiene presionado el botón izquierdo del mouse.
  * La cantidad de Zoom hacia el panel una vez se mueve el scroll del mouse.
  * El estado de **Adentro o Afuera** del mouse con respecto al panel de interacción.

### Construcción de objetos gráficos dentro de Configuraciones

El componente **Configuraciones** puede ser visible en pantalla gracias a la gestión de **navegación** realizada en previas lecciones por lo que se puede directamente iniciar con la construcción del componente, en la clase **configuracionesTemplate** primero se van a obtener los servicios **ObjGraficosService** y **RecursosService** para la creación los objetos gráficos:

* **Declaración:**

```
private ObjGraficosService sObjGraficos;
private RecursosService sRecursosService;
```

* **Obtención de servicios:**

```
// Dentro del constructor
sObjGraficos = ObjGraficosService.getService();
sRecursosService = RecursosService.getService();
```

Ahora se da un cambio de color al componente:

```
// Dentro del constructor
this.setBackground(sRecursosService.getColorGrisClaro());
```

### Objetos Decoradores

A continuación se muestra la creación de los objetos decoradores necesarios, en este caso solo se creara un **Cursor**:

* **Declaración:**

```
private Cursor cCruz;
```

* **método CrearObjetosDecoradores:**

```
public void crearObjetosDecoradores(){
    this.cCruz = new Cursor(Cursor.CROSSHAIR_CURSOR);
}
```

* **llamada del método dentro del constructor:**

```
// Dentro del constructor
this.crearObjetosDecoradores();
```

### Paneles

A continuación se muestra la creación de los paneles necesarios para realizar la funcionalidad del componente.

* **Declaración:**

```
private JPanel pDibujo, pDatos;
```

* **método crearJPanels:**

```
public void crearJPanels(){
  // PANEL P-DIBUJO---------------------------------
  pDibujo = sObjGraficos.construirJPanel(
    15, 15, 500, 570, 
    Color.WHITE, 
    sRecursosService.getBorderGris()
  );
  pDibujo.setCursor(cCruz);
  this.add(pDibujo);

  // PANEL P-DATOS---------------------------------
  pDatos = sObjGraficos.construirJPanel(
    530, 15, 305, 570, 
    Color.WHITE, 
    sRecursosService.getBorderGris()
  );
  this.add(pDatos);
}
```

Note que al panel de interacción pDibujo se le agrega el cursor previamente creado mediante el método de configuración **setCursor**.

* **llamada del método dentro del constructor:**

```
// Dentro del constructor
this.crearJPanels();
```

Hasta el momento el componente se ve asi:

<figure><img src="https://camo.githubusercontent.com/95dee71874afade27bf87eb14d132fc4f4911d71c576932c6bf686941c35308b/68747470733a2f2f692e696d6775722e636f6d2f4e5373724967712e706e67" alt=""><figcaption></figcaption></figure>

Componente Configuraciones con los paneles creados

### Labels

A continuación se muestra la creación de los **JLabel** necesarios para la funcionalidad del componente, en este caso se va crear una gran cantidad de JLabels, así que estos serán divididos en 2 categorías:

* **Labels Estáticos:** Son aquellos que representan información que no va a cambiar con el tiempo, pueden ser títulos, indicaciones etc.
* **Labels Dinámicos:** Son aquellos que representan valores y que con seguridad va a cambiar su contenido a medida que el usuarió interactué.

Es decir que se va a realizar la modularizacion de código con los JLabel a través de 2 métodos **crearJLabelsEstaticos** y **crearJLabelsDinamicos**.

* **Declaración:**

```
// Declaración Labels Estáticos
private JLabel lTitulo, lTituloPosicion, lTituloEstado;
private JLabel lPOnClickX, lPOnClickY, lPInicialX, lPInicialY, lPFinalX, lPFinalY;
private JLabel lPActualX, lPActualY, lLadoX, lLadoY, lZoom, lEstado; 

// Declaración Labels Dinámicos
private JLabel lPOnClickXValor, lPOnClickYValor, lPInicialXValor, lPInicialYValor;
private JLabel lPFinalXValor, lPFinalYValor, lPActualXValor, lPActualYValor;
private JLabel lLadoXValor, lLadoYValor, lZoomValor, lEstadoValor;
```

* **Método crearJLabelsEstaticos:**

```
public void crearJLabelsEstaticos(){
  // LABEL TITULO -------------------------------------------------------------------------
  lTitulo = sObjGraficos.construirJLabel(
    "Datos de Eventos",
    (this.pDatos.getWidth() - 200) / 2, 15, 200, 40,
    null, null,
    sRecursosService.getFontTitulo(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "c"
  );
  pDatos.add(lTitulo);

  // LABEL TITULO POSICIÓN-----------------------------------------------------------------
  lTituloPosicion = sObjGraficos.construirJLabel(
    "Datos de Posiciones",
    20, 60, 180, 40,
    null, null,
    sRecursosService.getFontTitulo(),
    null,
    sRecursosService.getColorSecundario(),
    null,
    "l"
  );
  pDatos.add(lTituloPosicion);

  // LABEL TITULO ESTADO--------------------------------------------------------------------
  lTituloEstado = sObjGraficos.construirJLabel(
    "Datos de Estado",
    20, 440, 180, 40,
    null, null,
    sRecursosService.getFontTitulo(),
    null,
    sRecursosService.getColorSecundario(),
    null,
    "l"
  );
  pDatos.add(lTituloEstado);

  // LABEL POSICIÓN EN X CON CLICK----------------------------------------------------------
  lPOnClickX = sObjGraficos.construirJLabel(
    "Posición en X al dar click: ",
    40, 100, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPOnClickX);

  // LABEL POSICIÓN EN Y CON CLICK----------------------------------------------------------
  lPOnClickY = sObjGraficos.construirJLabel(
    "Posición en Y al dar click: ",
    40, 120, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPOnClickY);

  // LABEL POSICIÓN EN X INICIAL----------------------------------------------------------
  lPInicialX = sObjGraficos.construirJLabel(
    "Posición en X inicial: ",
    40, 160, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPInicialX);

  // LABEL POSICIÓN EN Y INICIAL----------------------------------------------------------
  lPInicialY = sObjGraficos.construirJLabel(
    "Posición en Y inicial: ",
    40, 180, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPInicialY);

  // LABEL POSICIÓN EN X FINAL----------------------------------------------------------
  lPFinalX = sObjGraficos.construirJLabel(
    "Posición en X final: ",
    40, 220, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPFinalX);

  // LABEL POSICIÓN EN Y FINAL----------------------------------------------------------
  lPFinalY = sObjGraficos.construirJLabel(
    "Posición en Y final: ",
    40, 240, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPFinalY);

  // LABEL POSICIÓN EN X ACTUAL----------------------------------------------------------
  lPActualX = sObjGraficos.construirJLabel(
    "Posición en X actual: ",
    40, 280, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPActualX);

  // LABEL POSICIÓN EN Y ACTUAL----------------------------------------------------------
  lPActualY = sObjGraficos.construirJLabel(
    "Posición en Y actual: ",
    40, 300, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPActualY);

  // LABEL LADO EN X -------------------------------------------------------------------
  lLadoX = sObjGraficos.construirJLabel(
    "Valor lado X: ",
    40, 340, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lLadoX);

  // LABEL LADO EN Y --------------------------------------------------------------------
  lLadoY = sObjGraficos.construirJLabel(
    "Valor lado Y: ",
    40, 360, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lLadoY);

  // LABEL ZOOM --------------------------------------------------------------------------
  lZoom = sObjGraficos.construirJLabel(
    "Zoom en el panel: ",
    40, 400, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lZoom);

  // LABEL ESTADO ------------------------------------------------------------------------
  lEstado = sObjGraficos.construirJLabel(
    "Estado: ",
    40, 480, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lEstado);
}
```

* **Método crearJLabelsDinamicos:**

```
public void crearJLabelsDinamicos() {
  // LABEL POSICIÓN EN X CON CLICK VALOR -----------------------------------------------------
  lPOnClickXValor = sObjGraficos.construirJLabel(
    "0",
    200, 100, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPOnClickXValor);

  // LABEL POSICIÓN EN Y CON CLICK VALOR -----------------------------------------------------
  lPOnClickYValor = sObjGraficos.construirJLabel(
    "0",
    200, 120, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPOnClickYValor);

  // LABEL POSICIÓN EN X INICIAL VALOR -----------------------------------------------------
  lPInicialXValor = sObjGraficos.construirJLabel(
    "0",
    200, 160, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPInicialXValor);

  // LABEL POSICIÓN EN Y INICIAL VALOR -----------------------------------------------------
  lPInicialYValor = sObjGraficos.construirJLabel(
    "0",
    200, 180, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPInicialYValor);

  // LABEL POSICIÓN EN X FINAL VALOR -----------------------------------------------------
  lPFinalXValor = sObjGraficos.construirJLabel(
    "0",
    200, 220, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPFinalXValor);

  // LABEL POSICIÓN EN Y FINAL VALOR -----------------------------------------------------
  lPFinalYValor = sObjGraficos.construirJLabel(
    "0",
    200, 240, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPFinalYValor);

  // LABEL POSICIÓN EN X ACTUAL VALOR -----------------------------------------------------
  lPActualXValor = sObjGraficos.construirJLabel(
    "0",
    200, 280, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPActualXValor);

  // LABEL POSICIÓN EN Y ACTUAL VALOR -----------------------------------------------------
  lPActualYValor = sObjGraficos.construirJLabel(
    "0",
    200, 300, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lPActualYValor);

  // LABEL LADO EN X VALOR --------------------------------------------------------------
  lLadoXValor = sObjGraficos.construirJLabel(
    "0",
    200, 340, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lLadoXValor);

  // LABEL LADO EN Y VALOR ---------------------------------------------------------------
  lLadoYValor = sObjGraficos.construirJLabel(
    "0",
    200, 360, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lLadoYValor);

  // LABEL ZOOM VALOR ----------------------------------------------------------------------
  lZoomValor = sObjGraficos.construirJLabel(
    "0",
    200, 400, 160, 40,
    null, null,
    sRecursosService.getFontLigera(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lZoomValor);

  // LABEL ESTADO VALOR -------------------------------------------------------------------
  lEstadoValor = sObjGraficos.construirJLabel(
    "NINGUNO",
    80, 520, 160, 40,
    null, null,
    sRecursosService.getFontTitulo(),
    null,
    sRecursosService.getColorPrincipal(),
    null,
    "l"
  );
  pDatos.add(lEstadoValor);
}
```

* **llamada de métodos dentro del constructor:**

```
// Dentro del Constructor
this.crearJLabelsEstaticos();
this.crearJLabelsDinamicos();
```

Al ejecutar la aplicación, el componente **Configuraciones** se vera de la siguiente manera:

<figure><img src="https://camo.githubusercontent.com/93af557a1559a7d1233bc174f33fa6eeac72752df4f5e75befd41e70b76d1d4a/68747470733a2f2f692e696d6775722e636f6d2f545a634466646c2e706e67" alt=""><figcaption></figcaption></figure>

Componente Configuraciones con la creación de todos los JLabels

Por ultimo y para acabar con la clase **Template** del componente **Configuraciones** se crean los métodos **get** necesarios, en este caso se crean unicamente para los **JLabel dinámicos**:

```
public JLabel getLPOnClickXValor() { return lPOnClickXValor; }

public JLabel getLPOnClickYValor() { return lPOnClickYValor; }

public JLabel getLPInicialXValor() { return lPInicialXValor; }

public JLabel getLPInicialYValor() { return lPInicialYValor; }

public JLabel getLPFinalXValor() { return lPFinalXValor; }

public JLabel getLPFinalYValor() { return lPFinalYValor; }

public JLabel getLPActualXValor() { return lPActualXValor; }

public JLabel getLPActualYValor() { return lPActualYValor; }

public JLabel getLLadoXValor() { return lLadoXValor; }

public JLabel getLLadoYValor() { return lLadoYValor; }

public JLabel getLZoomValor() { return lZoomValor; }

public JLabel getLEstadoValor() { return lEstadoValor; }
```

## Eventos MouseListener

Dentro de la clase **ConfiguracionesComponent** específicamente en la declaración de la clase se va a implementar de la interfaz **MouseListener**:

<figure><img src="https://camo.githubusercontent.com/9c0040cc3b3476c8289d0b27c76c0c3a7885dd722722cfe78348478f7bc0ba8c/68747470733a2f2f692e696d6775722e636f6d2f54454c59364a322e706e67" alt=""><figcaption></figcaption></figure>

Implementación de la interfaz MouseListener en la clase ConfiguracionesComponent

_**Nota:** Se debe tener en cuenta la importación de las librerías que soporta la implementación de la interfaz._

Al igual que con la implementación de la interfaz **ActionListener** esta va a pedir que se importen todos los métodos por defecto, por lo general el mismo editor de código va a mostrar el error y va a sugerir la importación automática de estos.

<figure><img src="https://camo.githubusercontent.com/fb52cd8c5b819b32e666d30c15171ec9a3bb0f07845a0d71e51258afdef13f6a/68747470733a2f2f692e696d6775722e636f6d2f773032473745572e706e67" alt=""><figcaption></figcaption></figure>

Métodos implementados por defecto de la interfaz MouseListener

Se puede observar que esta vez la interfaz **MouseListener** implementa un total de 5 métodos por defecto y cada uno de ellos será explicado en esta sección.

Antes de continuar con la explicación se debe adicionar la capacidad de escuchar los eventos tipo **MouseListener** al panel de interacción **pDibujo**, el proceso es muy parecido a cuando se agregaba un **ActionListener** solo que esta vez se usa el método **addMouseListener**:

```
// Dentro del método crearJPanels
pDibujo.addMouseListener(this.configuracionesComponent);
```

Como la clase **configuracionesComponent** implementa de la interfaz **MouseListener** es posible pasar como argumento el objeto de esta clase igual como se haría con una clase que implementa un **ActionListener**.

_**Nota:** Como este método hace parte de la etapa de configuración debe ir entre la construcción del panel y la adición de este en el componente._

<figure><img src="https://camo.githubusercontent.com/a944c992c734109dc75f135534035c832921432b2d30d0728229fa8e6122158e/68747470733a2f2f692e696d6775722e636f6d2f4749584f4d53352e706e67" alt=""><figcaption></figcaption></figure>

Método de configuración entre su construcción y su agregación

### MouseClicked

Un evento **MouseClicked** se activa una vez el usuario da un "**Click**" en el objeto gráfico al cual fue proporcionado la adición del **MouseListener** en este caso el panel de interacción **pDibujo**. Cuando se menciona hacer un "_Click_" se hace referencia a la acción de **Oprimir** el botón del Mouse (por lo general el botón izquierdo) y luego **Soltarlo**.

Esto tiene varias implicaciones, por ejemplo si se **oprime** el botón del Mouse, luego se **arrastra** el Mouse manteniendo oprimido el botón y luego se **suelta**, este ya no va a funcionar. Es decir que para que se considere que se ha dado un **click** el Mouse se debe mantener en la misma posición una vez se **presiona** y se **suelta**.

Se procede a configurar el evento, en este caso se quiere que cuando el usuario de un **Click** sobre el panel de interacción **pDibujo**, se muestre las coordenadas en X,Y de donde estaba el puntero al momento de realizar esa acción. Para esto se debe mostrar esos valores en los labels **lPOnClickXValor** y **lPOnClickYValor**.

Existen dos métodos para encontrar la coordenada del puntero una vez se realiza una acción, es necesario usar el objeto recibido como parámetro **MouseEvent** para hacer esto, los métodos en cuestión son:

* **e.getX() / e.getY():** Que darán la coordenada del puntero cuando se activo la acción en X o en Y con respecto al objeto gráfico que activo la función.
* **e.getXOnScreen() / e.getYOnScreen():** Que darán la coordenada del puntero cuando se activo la acción en X o en Y con respecto a la pantalla total del monitor del usuario.

Hay que tener esto en cuenta ya que ambos métodos arrojaran datos diferentes debido a la perspectiva como se puede evidenciar en la siguiente imagen:

<figure><img src="https://camo.githubusercontent.com/990a97e01813cf6d436ad6de26416d233b8484ec3704fd7685127a674e9876b5/68747470733a2f2f692e696d6775722e636f6d2f395538376a73682e706e67" alt=""><figcaption></figcaption></figure>

Comparación perspectivas entre métodos que nos dan la posición del puntero

Por ahora solo es de interés la posición con respecto al objeto gráfico que activa la acción (**pDibujo**) por lo que se va a usar unicamente los métodos **e.getX() / e.getY()**.

* Como se quiere cambiar el texto de los Labels **lPOnClickXValor y lPOnClickYValor** se obtienen a través del objeto que referencia a la clase **Template** y sus métodos **get** correspondientes:

```
public void mouseClicked(MouseEvent e) {
  this.configuracionesTemplate.getLPOnClickXValor();
  this.configuracionesTemplate.getLPOnClickYValor();
}
```

* Se le indica ahora que va a cambiar el texto con el método:
  * **setText():** Que recibe como parámetro un String y representa el nuevo texto que tendrá el Label.

```
public void mouseClicked(MouseEvent e) {
  this.configuracionesTemplate.getLPOnClickXValor().setText();
  this.configuracionesTemplate.getLPOnClickYValor().setText();
}
```

* Ahora dentro de los paréntesis se pasan las coordenadas correspondientes:

```
public void mouseClicked(MouseEvent e) {
    this.configuracionesTemplate.getLPOnClickXValor().setText(e.getX());
    this.configuracionesTemplate.getLPOnClickYValor().setText(e.getY());
}
```

* Sin embargo como el método recibe por parámetro un **String** y se esta enviando como argumento un **entero** el IDE o editor de código indicará un error. Para pasar de un entero a String simplemente se puede usar la notación de: **(numeroEntero + "")** de esta forma Java entenderá que se esta haciendo una suma de caracteres y se hará la conversion automáticamente.

```
public void mouseClicked(MouseEvent e) {
    this.configuracionesTemplate.getLPOnClickXValor().setText(e.getX() + "");
    this.configuracionesTemplate.getLPOnClickYValor().setText(e.getY() + "");
}
```

Una vez se ejecuta la aplicación, se muestra el componente **Configuraciones** y se da click en cualquier parte del panel de interacción **pDibujo** se cambiara automáticamente la información de la posición de X,Y cuando se da Click:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase8/raw/master/gifs/MouseClick.gif" alt=""><figcaption></figcaption></figure>

Componente Configuraciones con la implementación de MouseClicked

Ahora bien, cabe recalcar que si se oprime click en cualquier otra parte que no sea el panel de interacción **pDibujo** o si se oprime el botón izquierdo del Mouse pero se suelta en otra posición no se verá reflejado el evento:

_**Nota:** En las siguientes secuencias se ve reflejado que el botón izquierdo del Mouse se mantiene oprimido cuando este tiene una circunferencia amarilla alrededor. Como ya se explico previamente es de esa forma en que el evento **MouseClicked** deja de funcionar._

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase8/raw/master/gifs/MouseClickFail.gif" alt=""><figcaption></figcaption></figure>

Forma incorrecta de activar el evento MouseClicked

### MousePressed

Un evento **MousePressed** se activa una vez el usuario presiona el botón izquierdo del Mouse, no ve la necesidad de saber cuando es soltado el botón, ni si se ha movido el Mouse posteriormente a la presión del botón, este solo se enfoca netamente al momento en que se presiono el botón del Mouse. La única condición de activación es que el puntero se encuentre dentro del objeto gráfico que tiene adicionada la escucha del **MouseListener** al momento de presionar el botón del Mouse, en este caso el panel de interacción **pDibujo**.

Se va a configurar este método y esta vez se que al presionar el botón del Mouse cambie la información de los Labels **LPInicialXValor y LPInicialYValor**:

```
public void mousePressed(MouseEvent e) {
  this.configuracionesTemplate.getLPInicialXValor().setText(e.getX() + "");
  this.configuracionesTemplate.getLPInicialYValor().setText(e.getY() + "");
}
```

Una vez se ejecuta la aplicación se evidencia la función de este evento:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase8/raw/master/gifs/MousePressed.gif" alt=""><figcaption></figcaption></figure>

Componente Configuraciones con la implementación de MousePressed

En el anterior video se ven varias particularidades:

* Siempre se va a ver reflejado primero el evento **MousePressed** ya que las milésimas de segundo en las que el usuario se demora en soltar el botón del mouse retrasa un poco al **MouseClicked**.
* Si se oprime el botón del Mouse y se espera unos segundos sin mover el mouse se va a ver reflejado primero el evento en el **MousePressed** y hasta que se suelte el botón del mouse se vera en el **MouseClicked**.
* Si se oprime el botón del Mouse y mientras se mantiene presionado se mueve el Mouse solo se vera reflejado el evento **MousePressed**.
* Si se oprime el botón afuera del panel de interacción **pDibujo** no se vera reflejado ningún evento.

### MouseReleased

Un evento **MouseReleased** se activa una vez el usuario suelta el botón del Mouse siempre y cuando este haya sido presionado previamente dentro del objeto gráfico que escucha los eventos **MouseListener**, no ve la necesidad de saber en que momento se oprimió el botón ni si se ha movido el mouse previamente de soltar el botón, este solo se enfoca netamente al momento en que se ha soltado el botón del Mouse. Una particularidad a mencionar es que si el botón del Mouse se suelta en alguna parte afuera del panel de interacción **pDibujo** puede funcionar siempre y cuando se haya presionado previamente el botón del Mouse dentro de el objeto gráfico que activo el evento.

Se va a configurar este método y esta vez se quiere que al soltar el botón del Mouse cambie la información de los Labels **LPFinalXValor y LPFinalYValor**:

```
public void mouseReleased(MouseEvent e) {
  this.configuracionesTemplate.getLPFinalXValor().setText(e.getX() + "");
  this.configuracionesTemplate.getLPFinalYValor().setText(e.getY() + "");
}
```

Se ejecuta la aplicación se es posible dar cuenta de la función de este evento:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase8/raw/master/gifs/MouseReleased.gif" alt=""><figcaption></figcaption></figure>

Componente Configuraciones con la implementación de MouseReleased

En la anterior secuencia se ven varias particularidades:

* Si se presiona y suelta el botón del Mouse en la misma posición (Hacer un Click), los tres eventos van a reflejar las mismas coordenadas.
* Si se presiona el botón del Mouse y se arrastra el Mouse mientras se tiene presionado el botón y luego se suelta se vera reflejado el evento **MousePressed** y el evento **MouseReleased** pero no el evento **MouseClicked**.
* Si se presiona el botón dentro del panel de interacción **pDibujo** y se suelta el botón del Mouse cuando este esta afuera del panel de interacción se vera reflejado el evento **MouseReleased** aun asi.
* Si se oprime el botón afuera del panel de interacción **pDibujo** no se vera reflejado ningún evento.

### MouseEntered

Este evento se activa una vez el usuario entra a través del puntero del Mouse al objeto gráfico que agrego al **MouseListener**, en este caso el panel de interacción **pDibujo**. No tiene la necesidad de oprimir ningún botón del Mouse, el simple hecho de que este sobre el objeto gráfico activa este evento.

Se va a configurar este método y esta vez se quiere que al entrar al panel **pDibujo** cambie el valor de **lEstadoValor** para indicar que el estado ahora es _ADENTRO_:

```
public void mouseEntered(MouseEvent e) {
    this.configuracionesTemplate.getLEstadoValor().setText("ADENTRO");
}
```

Una vez se ejecuta la aplicación se evidencia la función de este evento:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase8/raw/master/gifs/MouseEntered.gif" alt=""><figcaption></figcaption></figure>

Componente Configuraciones con la implementación de MouseEntered

Es posible ver que una vez el usuario ingresa con el puntero del mouse al panel de interacción **pDatos** el estado en el panel de datos pasa de **NINGUNO** a **ADENTRO**, sin embargo, este no parece cambiar más, se queda en el ultimo estado incluso si vuelve a salir y entrar de nuevo. Esto es por que aun no se ha configurado el evento en caso de que se salga del objeto gráfico.

### MouseExited

Este evento se activa una vez el usuario sale a través del puntero del Mouse del objeto gráfico que agrego al **MouseListener**, en este caso el panel de interacción **pDibujo** siempre y cuando haya entrado en el previamente. No tiene la necesidad de oprimir ningún botón del Mouse, el simple hecho de que este salga del objeto gráfico activa este evento.

Se va a configurar este método y esta vez se quiere que al salir del panel **pDibujo** cambie el valor de **lEstadoValor** para indicar que el estado ahora es _AFUERA_:

```
@Override
public void mouseExited(MouseEvent e) {
  this.configuracionesTemplate.getLEstadoValor().setText("AFUERA");
}
```

Una vez se ejecuta la aplicación se puede dar cuenta la función de este evento:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase8/raw/master/gifs/MouseExited.gif" alt=""><figcaption></figcaption></figure>

Componente Configuraciones con la implementación de MouseExited

Como se observa una vez se abre el componente **Configuraciones** el estado está en **NINGUNO**, cada vez que se entra al panel de interacción **pDibujo** el estado cambia a **ADENTRO** y una vez se sale del panel el estado ahora es **AFUERA**.

## MouseMotionListener

Este grupo de eventos para el Mouse da unas características especiales, ya que están enfocados en la muestra de información en tiempo real de acciónes con el Mouse. Estos eventos son útiles para acciones como las de arrastrar objetos, dibujar en tiempo real figuras por pantalla o crear efectos con el movimiento del Mouse.

En la clase **ConfiguracionesComponent**, específicamente en la declaración de esta se va a implementar la interfaz **MouseMotionListener**. Una ventaja con uso de interfaces para implementar es que una clase puede **implementar varias interfaces** al tiempo, esto no es posible con la herencia ya que en java no existe **Herencia Multiple**.

<figure><img src="https://camo.githubusercontent.com/4fe80c45f1070830b3d6bb9d418c8999288cfad58b799ce458d6ce16a4e822a5/68747470733a2f2f692e696d6775722e636f6d2f526c62786943762e706e67" alt=""><figcaption></figcaption></figure>

Implementación de la interfaz MouseMotionListener en la clase ConfiguracionesComponent

_**Nota:** Se debe tener en cuenta la importación de la librería que soporta la implementación de la interfaz._

Al igual que con la implementación de las demás interfaces esta va a pedir que se importen los métodos por defecto, por lo general el mismo IDE o editor de código va a mostrar el error y va a sugerir la importación automática de estos.

<figure><img src="https://camo.githubusercontent.com/04be04ab51b0491b9fd211d482f0db499de804a70ee02a204cf4ac616c0fd925/68747470733a2f2f692e696d6775722e636f6d2f536f774a4972682e706e67" alt=""><figcaption></figcaption></figure>

Métodos implementados por defecto de la interfaz MouseMotionListener

Se puede observar que esta vez la interfaz **MouseMotionListener** implementa un total de 2 métodos por defecto y cada uno de ellos serán explicados en esta sección.

Antes de continuar con la explicación se debe adicionar la capacidad de escuchar los eventos de tipo **MouseMotionListener** a la panel de interacción **pDibujo**, esta vez se usara el método **addMouseMotionListener**:

```
// Dentro del método crearJPanels
pDibujo.addMouseMotionListener(this.configuracionesComponent);
```

Como la clase **configuracionesComponent** implementa de la interfaz **MouseMotionListener** es posible pasar como argumento el objeto de esta clase.

_**Nota:** Como este método hace parte de la etapa de configuración debe ir entre la construcción del panel y la adición de este en el componente._

### MouseMoved

Este evento se activa cada vez que el usuario mueve el puntero del Mouse y este se encuentra dentro del objeto gráfico al cual se le adiciono el **MouseMotionListener**, en este caso el panel de interacción **pDibujo**. No tiene la necesidad de oprimir el botón del mouse, con el hecho de estar dentro del objeto gráfico y moverse dentro, este evento se va a activar.

Se va a configurar el método y esta vez se quiere que cada vez que el usuario este moviendo el Mouse dentro del panel **pDibujo** actualice la posición actual en tiempo real del Mouse, para eso se va a cambiar la información de los label **lPActualXValor y lPActualYValor**:

```
public void mouseMoved(MouseEvent e) {
  this.configuracionesTemplate.getLPActualXValor().setText(e.getX() + "");
  this.configuracionesTemplate.getLPActualYValor().setText(e.getY() + "");
}
```

Una vez se ejecuta la aplicación se evidencia la función de este evento:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase8/raw/master/gifs/MouseMoved.gif" alt=""><figcaption></figcaption></figure>

Componente Configuraciones con la implementación de MouseMoved

### MouseDragged

Este evento se activa una vez se oprime el botón del Mouse dentro del objeto gráfico que tiene agregado el **MouseMotionListener** en este caso el panel de interacción **pDibujo** y se mueve el puntero del Mouse mientras se mantiene oprimido el botón del Mouse, por otro lado termina de accionarse una vez se suelta el botón del Mouse. Se debe oprimir el botón del Mouse dentro del objeto gráfico o de lo contrario no funcionará este evento.

Se va a configurar el método y esta vez se quiere que cada vez que el usuario oprima el botón del Mouse y empiece a mover el Mouse actualice la posición actual en tiempo real del Mouse, para eso se va a cambiar la información de los label **lLadoXValor y lLadoYValor**:

```
public void mouseDragged(MouseEvent e) {
    this.configuracionesTemplate.getLLadoXValor().setText(e.getX() + "");
    this.configuracionesTemplate.getLLadoYValor().setText(e.getY() + "");
}
```

Una vez se ejecute la aplicación es posible ver la función de este evento:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase8/raw/master/gifs/MouseDragged.gif" alt=""><figcaption></figcaption></figure>

Componente Configuraciones con la implementación de mouseDragged

De la anterior secuencia se puede notar algunas particularidades:

* Una vez el usuario oprime el botón del mouse dentro del panel de interacción **pDibujo** y empieza a arrastrar el mouse sin soltar aun el botón, deja de funcionar el evento **MouseMoved** y empieza a funcionar el evento **MouseDragged**.
* Una vez el usuario suelta el botón del Mouse y está dentro del panel de interacción **pDibujo** dejara de funcionar el evento **MouseDragged** y empieza a funcionar el evento **MouseMoved**.
* Si el usuario presiono el botón del Mouse dentro del panel de interacción **pDibujo** previamente y se mantiene presionado el evento **MouseDragged** seguirá funcionando incluso si se sale del panel todo mientras se siga manteniendo presionado el botón del mouse.
* Si se presiona desde afuera del panel de interacción **pDibujo** ningún evento tendrán efecto.

## MouseWheelListener

Este grupo de eventos se concentran unicamente en el movimiento del **scroll del Mouse** (la rueda que por lo general tiene el Mouse en medio de los dos botones). Este evento se fija unicamente del movimiento de este Scroll, es decir que no tiene en cuenta cuando se **hace un click** con el Scroll, solo cuando el usuario lo mueve hacia arriba o hacia abajo.

En la clase **ConfiguracionesComponent**, específicamente en la declaración de la clase, se va a implementar la interfaz **MouseWheelListener**. Recordar que esto es posible ya que una clase puede **implementar varias interfaces** al tiempo.

<figure><img src="https://camo.githubusercontent.com/33febe2152bd208ea1e3c7236f25083202b0a6c054cf08fc69e1d17294f0defe/68747470733a2f2f692e696d6775722e636f6d2f5242686838436f2e706e67" alt=""><figcaption></figcaption></figure>

Implementación de la interfaz MouseWheelListener en la clase ConfiguracionesComponent

Como con todas las demás interfaces, se debe implementar los métodos por defecto que trae esta interfaz.

<figure><img src="https://camo.githubusercontent.com/b76415302584bf970aba0cb12e9d3c879232e97b70265c461df2c48c350af66e/68747470733a2f2f692e696d6775722e636f6d2f796c625134416f2e706e67" alt=""><figcaption></figcaption></figure>

Métodos implementados por defecto de la interfaz MouseWheelListener

Se puede observar que la interfaz **MouseWheelListener** implementa un solo método por defecto y este será explicado en esta sección.

Antes de continuar con la explicación se debe adicionar la capacidad de escuchar los eventos tipo **MouseWheelListener** al panel de interacción **pDibujo**, esta vez se usará el método **addMouseWheelListener**:

```
// Dentro del método crearJPanels
pDibujo.addMouseWheelListener(this.configuracionesComponent);
```

Como la clase **configuracionesComponent** implementa de la interfaz **MouseWheelListener** es posible pasar como argumento el objeto de esta clase.

_**Nota:** Como este método hace parte de la etapa de configuración debe ir entre la construcción del panel y la adición de este en el componente._

### MouseWheelMoved

Este evento se activa una vez el usuario mueve el **Scroll del Mouse**, es decir lo desliza hacia arriba o hacia abajo, para que este evento pueda ser activado debe estar dentro del objeto gráfico que tiene agregado la escucha de eventos tipo **MouseWheelListener** en este caso el panel de interacción **pDatos**. Si se realiza afuera de este no tendrá ningún efecto.

Se va a configurar el método y esta vez se quiere que cada vez que el usuario deslice el Scroll hacia arriba o hacia abajo se realice la simulación de acercamiento y alejamiento, esto se realiza cambiando el valor del label **lZoomValor**. Cuando el usuario mueva el Scroll hacia arriba va a aumentar el numero del zoom mientras que cuando el usuario mueva hacia abajo este numero va a disminuir.

Para saber si el usuario esta subiendo o bajando el scroll del Mouse se debe usar el método:

* **e.getWheelRotation():** Que retorna un numero entero.
  * Si el usuario esta subiendo con el scroll va a retornar el numero **-1**.
  * Si el usuario esta bajando con el scroll va a retornar el numero **1**.

Con este método se puede realizar la configuración del zoom explicada anteriormente:

```
public void mouseWheelMoved(MouseWheelEvent e) {
  if(e.getWheelRotation() == -1)
    // Acción Cuando el usuario sube con el Scroll
  if(e.getWheelRotation() == 1)
    // Acción Cuando el usuario baja con el Scroll
}
```

* Como se quiere cambiar el valor del label **lZoomValor**, se debe obtener a traves del objeto de la clase **Template** y su respectivo método **get**, una vez obtenido se debe indicar que cambiará su contenido con el método **setText**:

```
public void mouseWheelMoved(MouseWheelEvent e) {
  if(e.getWheelRotation() == -1)
    this.configuracionesTemplate.getLZoomValor().setText();
  if(e.getWheelRotation() == 1)
    this.configuracionesTemplate.getLZoomValor().setText();
}
```

* Ahora se debe indicar en cada caso que se le va a sumar o restar el valor de 1, pero para eso es necesario obtener antes el valor actual que tiene el label **lZoomValor**, ya que si solo se le indica que sume o reste 1 el valor del Label **lZoomValor** solo podría ser 1 o -1. Para obtener su valor nuevamente se debe llamar al Label a través del objeto de la clase **Template** y su respectivo método **get** seguido del método **getText()** que retorna en un String el contenido del Label:

```
public void mouseWheelMoved(MouseWheelEvent e) {
  if(e.getWheelRotation() == -1)
    this.configuracionesTemplate.getLZoomValor().setText(
      this.configuracionesTemplate.getLZoomValor().getText()
    );
  if(e.getWheelRotation() == 1)
    this.configuracionesTemplate.getLZoomValor().setText(
      this.configuracionesTemplate.getLZoomValor().getText()
    );
}
```

* Como se quiere sumar o restar un 1 al contenido actual del Label **lZoomValor** se debe convertir el dato de String a entero y de esta forma se puede realizar una suma o resta entre números:

```
public void mouseWheelMoved(MouseWheelEvent e) {
  if(e.getWheelRotation() == -1)
    this.configuracionesTemplate.getLZoomValor().setText(
      Integer.parseInt(this.configuracionesTemplate.getLZoomValor().getText())
    );
  if(e.getWheelRotation() == 1)
    this.configuracionesTemplate.getLZoomValor().setText(
      Integer.parseInt(this.configuracionesTemplate.getLZoomValor().getText()) 
    );
}
```

* Es posible notar que hasta el momento en ambos casos se esta haciendo el mismo proceso, se puede entonces encapsular el proceso de obtención y conversion del zoom actual en una variable antes de que empiecen las condiciones, para que no quede tan confuso el código:

```
public void mouseWheelMoved(MouseWheelEvent e) {
  int valorZoomActual = Integer.parseInt(this.configuracionesTemplate.getLZoomValor().getText());
  if(e.getWheelRotation() == -1)
    this.configuracionesTemplate.getLZoomValor().setText(valorZoomActual);
  if(e.getWheelRotation() == 1)
    this.configuracionesTemplate.getLZoomValor().setText(valorZoomActual);
}
```

* Ahora si se va a sumar y restar un 1 según sea el caso:

```
public void mouseWheelMoved(MouseWheelEvent e) {
   int valorZoomActual = Integer.parseInt(this.configuracionesTemplate.getLZoomValor().getText());
   if(e.getWheelRotation() == -1)
       this.configuracionesTemplate.getLZoomValor().setText(valorZoomActual + 1);
   if(e.getWheelRotation() == 1)
       this.configuracionesTemplate.getLZoomValor().setText(valorZoomActual - 1);
}
```

* Sin embargo el método **setText** exige enviar como argumento un String asi que se realiza otra conversion, esta vez de entero a String como se menciono antes:

```
public void mouseWheelMoved(MouseWheelEvent e) {
 int valorZoomActual = Integer.parseInt(this.configuracionesTemplate.getLZoomValor().getText());
 if(e.getWheelRotation() == -1)
   this.configuracionesTemplate.getLZoomValor().setText(valorZoomActual + 1 + "");
 if(e.getWheelRotation() == 1)
   this.configuracionesTemplate.getLZoomValor().setText(valorZoomActual - 1 + "");
}
```

Si se ejecuta la aplicación se puede ver el evento funcionando:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase8/raw/master/gifs/MouseWheel.gif" alt=""><figcaption></figcaption></figure>

Componente Configuraciones con la implementación de mouseWheelMoved

Sin embargo, es posible notar que si se baja demasiado con el scroll este empieza a mostrar números negativos y esto en términos de zoom no es correcto, por lo que seria bueno dejar un limite en caso de bajar el scroll para que no pueda pasar a menos de 0:

* Primero se debe indicar en el condicional que controla cuando el Scroll esta bajando que se va a realizar otra condición, esto se hace con el separador **&&**.

```
public void mouseWheelMoved(MouseWheelEvent e) {
  int valorZoomActual = Integer.parseInt(this.configuracionesTemplate.getLZoomValor().getText());
  if(e.getWheelRotation() == -1)
    this.configuracionesTemplate.getLZoomValor().setText(valorZoomActual + 1 + "");
  if(e.getWheelRotation() == 1 &&)
    this.configuracionesTemplate.getLZoomValor().setText(valorZoomActual - 1 + "");
}
```

* Ahora se debe obtener el valor actual del zoom para poder ser comparado, sin embargo, este proceso de obtención y conversion del Zoom actual ya está encapsulado en la variable **valorZoomActual** por lo que se usa esta:

```
public void mouseWheelMoved(MouseWheelEvent e) {
  int valorZoomActual = Integer.parseInt(this.configuracionesTemplate.getLZoomValor().getText());
  if(e.getWheelRotation() == -1)
    this.configuracionesTemplate.getLZoomValor().setText(valorZoomActual + 1 + "");
  if(e.getWheelRotation() == 1 && valorZoomActual)
    this.configuracionesTemplate.getLZoomValor().setText(valorZoomActual - 1 + "");
}
```

* Ahora solo nos hace falta realizar la comparación:

```
public void mouseWheelMoved(MouseWheelEvent e) {
  int valorZoomActual = Integer.parseInt(this.configuracionesTemplate.getLZoomValor().getText());
  if(e.getWheelRotation() == -1)
    this.configuracionesTemplate.getLZoomValor().setText(valorZoomActual + 1 + "");
  if(e.getWheelRotation() == 1 && valorZoomActual > 0)
    this.configuracionesTemplate.getLZoomValor().setText(valorZoomActual - 1 + "");
}
```

En la anterior condición se indicando al programa que solo cuando el valor del Zoom actual sea mayor a 0 este podrá ser restado, de lo contrario este valor será 0 y por ende no podrá entrar a la condición.

Si se ejecuta de nuevo la aplicación se puede notar que se cumple la condición que queríamos:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase8/raw/master/gifs/MouseWheelFinal.gif" alt=""><figcaption></figcaption></figure>

Restricción en la resta del zoom

## Resultado

Si llegaste hasta aquí **!Felicidades!**, se ha aprendido las características principales de los diferentes eventos del mouse. Se ha revisado en que momentos se activa y deja de funcionar cada uno de ellos, además de algunas particularidades que tienen los eventos del mouse. En la siguiente clase se van a implementar estos eventos al resto del proyecto para darle una interactividad mayor a la interfaz gráfica de usuario.

## Actividad

Revisa los diferentes tipos de eventos poniendo comentarios a la funcionalidad, particularidades y en que casos no funciona cada uno de estos.

### About

Clase 8 del curso de Interfaz Gráfica con Java, en donde se muestran conceptos relacionados con el uso de eventos de Mouse, sus diferentes interfaces y métodos donde nos enfocamos en sus características principales.

#### Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 9

### Objetivos

* Identificar los usos principales de los eventos del Mouse para añadirle interactividad al proyecto de interfaz gráfica de usuario.
* Reconocer el enfoque de discriminación de clases para gestionar la interactividad con diferentes tipos de objetos gráficos a la vez desde un método implementado de eventos.
* Examinar el cambio indirecto de estado en objetos gráficos causado por la activación de un evento.
* Comprender el uso combinado de diferentes interfaces implementadas de eventos para realizar acciónes de interactividad a las interfaces gráficas.

## Antes de Comenzar

#### **Actualización de Imágenes en recursos**

***

Para continuar con la lección deberá actualizar la carpeta **resources/images** ya que se han agregado nuevas imágenes. Estas las puede descargar en este mismo repositorio entrando a la carpeta **Clase9** seguido de **resources/images**.

#### **Ajustes en el servicio Recursos Service**

***

* Se crea un nuevo color en el servicio **RecursosService**, y se recuerda el proceso de creación de un objeto decorador dentro de este servicio:

**Declaración:**

```
private Color colorPrincipalOscuro;
```

**Ejemplificación:**

```
// Dentro del método crearColores
colorPrincipalOscuro = new Color(30, 48, 90);
```

**Método get:**

```
public Color getColorPrincipalOscuro() { return colorPrincipalOscuro; }
```

* También se crea un borde gris inferior para ser usados en los campos de texto:

**Declaración:**

```
private Border bInferiorGris;
```

**Ejemplificación:**

```
// Dentro del método crearBordes
bInferiorGris = BorderFactory.createMatteBorder(0, 0, 1, 0, Color.LIGHT_GRAY);
```

**Método get:**

```
public Border getBInferiorGris() { return bInferiorGris; }
```

_**Nota:** Recordar que estos objetos decoradores dentro del servicio **RecursosService** se crean pensando en que serán utilizados en varias partes del proyecto, si ese no es el caso entonces el objeto decorador debe ser creado unicamente en el componente gráfico donde se necesita._

#### **Ajustes en el componente Login**

***

Dentro de esta lección se usarán nuevas imágenes para ilustrar los ejemplos del uso de eventos, dentro de la clase **LoginTemplate** se van a crear estas imágenes:

**Declaración:**

```
private ImageIcon iUsuario1, iClave1;
private ImageIcon iFacebook2, iTwitter2, iYoutube2;
```

* **Ejemplificación:**

```
// Dentro del método crearObjetosDecoradores
iUsuario1 = new ImageIcon("Clase9/resources/images/usuario1.png");
iClave1 = new ImageIcon("Clase9/resources/images/clave1.png");
iFacebook2 = new ImageIcon("Clase9/resources/images/facebook2.png");
iTwitter2 = new ImageIcon("Clase9/resources/images/twitter2.png");
iYoutube2 = new ImageIcon("Clase9/resources/images/youtube2.png");
```

#### **Recordatorio**

***

Recordando un poco el recorrido, se ha construido el componente **Configuraciones** el cual cuenta con la implementación de todos los **eventos del Mouse** y con el que el usuario puede interactuar para comprobar el funcionamiento correcto del Mouse. Gracias a esto se exploraron las principales características de cada uno de los eventos y se identificaron aspectos como la activación de estos, los momentos en que dejan de funcionar y casos particulares.

<figure><img src="https://camo.githubusercontent.com/93af557a1559a7d1233bc174f33fa6eeac72752df4f5e75befd41e70b76d1d4a/68747470733a2f2f692e696d6775722e636f6d2f545a634466646c2e706e67" alt=""><figcaption></figcaption></figure>

Componente Configuraciones con la implementación de todos los eventos de Mouse

## Implementación de eventos de Mouse

En esta sesión se va a realizar la implementación de los diferentes eventos del Mouse dentro de distintas partes el proyecto, paralelamente se verán a ver algunas particularidades de importancia que están relacionadas con el uso de estos eventos:

* **Representación única para objetos gráficos de una misma Clase**.
* **Discriminación de Clases**.
* **Uso de MouseAdapter**.
* **Efectos hacia otros objetos Gráficos**.
* **Uso combinado de varias interfaces implementadas de eventos**.

## Representación única para objetos gráficos de una misma Clase

Para empezar se puede proporcionar algo de interactividad a los **botones** de la navegación ya que estos realmente están estáticos, una buena manera de hacer esto es cambiar el color de fondo una vez el usuario pase con el mouse por encima de ellos.

Dentro del componente **NavegaciónUsuario**, específicamente en la clase **NavegacionUsuarioComponent** se añade la implementación de la interfaz **MouseListener**:

<figure><img src="https://camo.githubusercontent.com/537b202a443e45e24dca5d9ac41c7b4463c8ee9325d37988920738d71b1a2771/68747470733a2f2f692e696d6775722e636f6d2f5a4448673741612e706e67" alt=""><figcaption></figcaption></figure>

implementación de MouseListener en el componente Navegación Usuario

Recordar nuevamente que esta implementación exige que se implementen también los métodos que por defecto tiene la interfaz **MouseListener**:

```
@Override
public void mouseClicked(MouseEvent e) {}

@Override
public void mousePressed(MouseEvent e) {}

@Override
public void mouseReleased(MouseEvent e) {}

@Override
public void mouseEntered(MouseEvent e) {}

@Override
public void mouseExited(MouseEvent e) {}
```

Por otro lado, en la clase **NavegacionUsuarioTemplate** se va a añadir a los botones de la navegación la capacidad de escuchar los eventos de tipo **MouseListener**, para eso se usa el método **addMouseListener**:

```
// En el respectivo espacio de configuración de cada objeto
this.bInicio.addMouseListener(navegacionUsuarioComponent);
this.bPerfil.addMouseListener(navegacionUsuarioComponent);
this.bAmigos.addMouseListener(navegacionUsuarioComponent);
this.bProductos.addMouseListener(navegacionUsuarioComponent);
this.bConfiguracion.addMouseListener(navegacionUsuarioComponent);
this.bCerrarSesion.addMouseListener(navegacionUsuarioComponent);
```

_**Nota:** Recordar que en el anterior código se ven todas estas lineas juntas, sin embargo, estos son métodos de configuración por lo que cada una de ellas debe estar organizada junto al proceso de creación de su respectivo botón._

Como la clase **NavegacionUsuarioComponent** ahora implementa a la interfaz **MouseListener** es posible ingresar como argumento al objeto que representa esta clase dentro del método **addMouseListener**.

Se va a probar el evento con un solo botón por ahora, para ello primero se debe realizar el método **get** del botón **bInicio** en la clase **Template** del componente:

```
public JButton getBInicio(){ return this.bInicio; }
```

Ahora dentro de la clase **NavegaciónUsuarioComponent**, dentro del método **mouseEntered** se configura el cambio del color de fondo del botón **bInicio**.

* Primero se crea una discriminación por objetos, para esto se crea un condicional en el cual se pregunta si el objeto que ha activado el evento es igual al botón **bInicio**:

```
public void mouseEntered(MouseEvent e) {
  if(e.getSource() == navegacionUsuarioTemplate.getBInicio()) {
  } 
}
```

* Para obtener el botón se debe usar el objeto de la clase **Template** y llamar al método **get** correspondiente:

```
public void mouseEntered(MouseEvent e) {
  if(e.getSource() == navegacionUsuarioTemplate.getBInicio()) {
    navegacionUsuarioTemplate.getBInicio()
  } 
}
```

* Una vez obtenido el botón se agrega el color de fondo, pero antes se deben habilitar las propiedades de contenedor de botón nuevamente ya que en el momento de su construcción se configuró este con características de transparencia por lo que si cambia simplemente el color no será reflejado:

```
public void mouseEntered(MouseEvent e) {
  if(e.getSource() == navegacionUsuarioTemplate.getBInicio()) {
    navegacionUsuarioTemplate.getBInicio().setContentAreaFilled(true);
    navegacionUsuarioTemplate.getBInicio()
      .setBackground(RecursosService.getService().getColorPrincipalOscuro());
  } 
}
```

Note que para poder agregarle el color azul oscuro, se debe llamar al servicio **RecursosService**, en este caso se tomo el enfoque en el cual se llama directamente al servicio, se obtiene dicho servicio y se llama al método **get** correspondiente, aunque no es la única forma de hacerse, más adelante se verá otro enfoque igualmente valido.

El botón ahora cambiará de color a un **Azul mas oscuro** una vez se pasa sobre el, sin embargo, esto implica que se debe configurar la acción una vez se sale de la zona del botón para que este vuelva a la normalidad, para eso se configura el método **mouseExited**:

* Nuevamente se realiza una discriminación de objetos para indicar que se active solo cuando este salga del botón **bInicio**:

```
public void mouseExited(MouseEvent e) {
  if(e.getSource() == navegacionUsuarioTemplate.getBInicio())
}
```

* Se obtiene el botón mediante el objeto de la clase **Template** y su método **get** correspondiente:

```
public void mouseExited(MouseEvent e) {
  if(e.getSource() == navegacionUsuarioTemplate.getBInicio())
    navegacionUsuarioTemplate.getBInicio()
}
```

* Para que el botón vuelva a su estado normal solo hace falta con volver a configurar sus características de transparencia, de ese modo el botón eliminara cualquier color de fondo que contenga:

```
public void mouseExited(MouseEvent e) {
  if(e.getSource() == navegacionUsuarioTemplate.getBInicio())
    navegacionUsuarioTemplate.getBInicio().setContentAreaFilled(false);
}
```

Una vez se ejecuta la la aplicación es posible ver el siguiente resultado:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase9/raw/master/gifs/MouseEvent1.gif" alt=""><figcaption></figcaption></figure>

Interacción con eventos a un solo botón

_**Nota:** Con este ejemplo se evidencia la importancia del uso del **Borde Vació** ya que cuando se pasa por encima del botón y este hace un cambio de color de fondo es posible notar que ni la imágen ni el texto están pegados con el borde del botón lo que hace que luzca estéticamente mucho mejor, en caso de no usar un borde vació la imágen escaria pegada con el borde de la izquierda._

Ahora se podría realizar el anterior proceso con los demás botones dentro de la navegación, sin embargo, note las siguientes particularidades:

* La anterior acción del cambio de color de fondo se quiere realizar con los demás botónes, es decir que a diferencia de un **ActionListener** donde cada botón generalmente busca realizar una acción distinta en estos eventos es común que varios objetos gráficos puedan compartir los mismos comportamientos.
* Esta navegación solo cuenta con 6 botones, sin embargo, si un menu contiene 20 botónes o incluso más, habría que crear una gran cantidad de código para representar el mismo comportamiento en cada botón lo cual hace que el código sea mas difícil de entender y mantener. Esto implicaría crear un método **get** dentro de la clase Template por cada botón, crear un nuevo condicional dentro de los métodos de los eventos para realizar la discriminación por objeto y realizar exactamente las mismas lineas de código por cada botón **resultando en demasiado código para representar la misma acción**.
* Una posible solución a pensar frente a esta situación es no realizar ninguna discriminación y escribir el código directamente en el método del evento, de esta forma todos los botónes que escuchen dicho evento realizarán el mismo comportamiento. Sin embargo, en esta ocasión no es posible ya que se están configurando características a un objeto gráfico en un tiempo determinado, esto quiere decir que a diferencia de mostrar un mensaje por pantalla el evento debe saber de algún modo a que botón se le cambiará el color y en que momento.

**¿Cómo se puede resolver esta situación?**.

Aquí entra en juego la **Representación única para objetos gráficos de una misma Clase**. Para entender este concepto se va a implementar en el código a la par que se va explicando en el proceso.

Dentro de la clase **NavegacionUsuarioComponent**, específicamente en el método **mouseEntered** se crea una variable tipo **JButton** en este caso se llamará **boton**:

```
public void mouseEntered(MouseEvent e) {
  JButton boton;
  // if(e.getSource() == navegacionUsuarioTemplate.getBInicio()){
  //     navegacionUsuarioTemplate.getBInicio().setContentAreaFilled(true);
  //     navegacionUsuarioTemplate.getBInicio().setBackground(RecursosService.getService().getColorPrincipalOscuro());
  // } 
}
```

Note que el resto del código se comento ya que no será necesario por ahora. Se implementa a continuación la **Representación única para objetos gráficos de una misma Clase**:

```
public void mouseEntered(MouseEvent e) {
  JButton boton = ((JButton) e.getSource());
  // if(e.getSource() == navegacionUsuarioTemplate.getBInicio()){
  //     navegacionUsuarioTemplate.getBInicio().setContentAreaFilled(true);
  //     navegacionUsuarioTemplate.getBInicio().setBackground(RecursosService.getService().getColorPrincipalOscuro());
  // } 
}
```

En el anterior código se realiza lo siguiente:

* A traves del objeto de evento **e** se obtiene el objeto gráfico que ha activado el evento, esto mediante el método **getSource**.
* El método **getSource** va a retornar al objeto que activo el evento con el tipo de dato **Object** es decir la forma mas general del objeto, por eso es necesario especificar el tipo de clase a la cual pertenece el objeto que activo el evento. Para esto se realiza un **Cast** o cambio de tipado obligatorio de objeto, convirtiéndolo a un **JButton** en este caso.
* Una vez se convierte el objeto se iguala al objeto variable que se creó previamente.

Esto implica que la variable **boton** va tener la capacidad de representar cualquier botón que active el evento. Este es un concepto muy poderoso y una solución perfecta a la situación planteada. Ahora solo basta con indicarle al botón que le se va a cambiar el color de fondo:

_**Nota:** Se puede borrar el anterior código comentado ya que no será necesario en el futuro._

```
public void mouseEntered(MouseEvent e) {
  JButton boton = ((JButton) e.getSource());
  boton.setContentAreaFilled(true);
  boton.setBackground(RecursosService.getService().getColorPrincipalOscuro()); 
}
```

Lo mismo se realiza con el método **mouseExited** para indicar que se dejarán los botones en su estado inicial una vez se sale de ellos:

```
public void mouseExited(MouseEvent e) {
  JButton boton = ((JButton) e.getSource());
  boton.setContentAreaFilled(false);
}
```

_**Nota:** También se puede borrar el método **get** del primer botón creado con anterioridad en la clase **NavegacionUsuarioTemplate** ya que no se usará._

Ahora se ha representado e implementado el mismo comportamiento para varios botones en unas cuantas lineas de código y para comprobarlo se abre la aplicación:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase9/raw/master/gifs/MouseEvent2.gif" alt=""><figcaption></figcaption></figure>

Implementación de Representación única para objetos gráficos de una misma Clase

## Uso de MouseAdapter

Se puede observar que en la clase **NavegacionUsuarioComponent** se implemento la interfaz **MouseListener** y esto trajo consigo la implementación automática de los 5 métodos que exige la interfaz. Sin embargo, en este componente solo se hizo uso de dos de los cinco métodos implementados haciendo que los métodos no usados ocupen código y estorben:

<figure><img src="https://camo.githubusercontent.com/b8993aa8c5221ddcc273621943283c07cb0d698ffd6c1891ea8dcac3ee0f70ea/68747470733a2f2f692e696d6775722e636f6d2f35754b463645642e706e67" alt=""><figcaption></figcaption></figure>

Métodos sin usar que se implementaron de MouseListener

El problema está en que como la interfaz **MouseListener** contiene estos métodos exige que se implementen cada uno de ellos, si se intenta borrar alguno de estos métodos el IDE o editor de código notificará un error. Para esto es posible hacer uso de una clase que proporciona Java llamada **MouseAdapter**, esta es una clase que tiene implementadas todas las interfaces relacionadas con los eventos del Mouse:

<figure><img src="https://camo.githubusercontent.com/d9289b6e70a07ddff0857f7d8c506b9b7f5540b51aa9f59521a47802303bdd0c/68747470733a2f2f692e696d6775722e636f6d2f584451395165772e706e67" alt=""><figcaption></figcaption></figure>

Definición de la clase MouseAdapter proporcionada por Java.

Esto quiere decir que ya tiene implementado todos los métodos que controlan los eventos del Mouse, gracias a esto podemos hacer uso de esta clase realizando una herencia y de esta forma es posible implementar a los eventos del Mouse que se necesiten sin la obligación de implementar otros métodos que realmente no serán untados. Dentro de la clase **NavegaciónUsuarioComponent** se procede a realizar esta acción:

<figure><img src="https://camo.githubusercontent.com/bb3190dd9bb4d4926a6918f605eacba446d07cdbf496455e8bae7ff1d8871d18/68747470733a2f2f692e696d6775722e636f6d2f776234495678692e706e67" alt=""><figcaption></figcaption></figure>

Realizando herencia a la clase MouseAdapter

Note que como **MouseAdapter** es una clase y no una interfaz se debe hacer una **Extension** de ella y no una **implementación**, también es necesario tener en cuenta que se debe importar la librería para soportar esta clase, por ultimo se puede observar que de todas formas es posible implementar de otras interfaces como es el caso de **ActionListener**.

Gracias a esto es posible borrar los métodos **mouseClicked, mousePressed y mouseReleased** sin que haya conflicto alguno quedando unicamente los eventos del Mouse que necesariamente serán usados.

## Discriminación de Clases

A continuación se va a realizar la configuración de eventos del mouse al componente **login**, para esto dentro de la clase **LoginComponent** específicamente en la declaración se va a extender de la clase **MouseAdapter** como se acabo de hacer con el anterior componente.

<figure><img src="https://camo.githubusercontent.com/b42f0853b7bd5e9f3d0351a31d26d3e1bcba013ffb724ffac2be75243b18f076/68747470733a2f2f692e696d6775722e636f6d2f756268594b51422e706e67" alt=""><figcaption></figcaption></figure>

Extensión de la clase MouseAdapter en la clase LoginComponent

En este caso solo se usarán los siguientes métodos de eventos de Mouse:

```
@Override
public void mouseClicked(MouseEvent e) {}

@Override
public void mouseEntered(MouseEvent e) {}

@Override
public void mouseExited(MouseEvent e) {}
```

En este caso se quiere que al pasar sobre los botones **bEntrar** y **bRegistrarse** se cambie el color de fondo a un Azul más oscuro, pero también se quiere que al pasar por encima de los labels **lFacebook**, **lTwitter** y **lYoutube** se cambie la imágen que contienen los labels para darle un aspecto naranja. Para esto dentro de la clase **LoginTemplate** es necesario añadir la escucha de este tipo de eventos a estos objetos gráficos.

```
bEntrar.addMouseListener(loginComponent);
bRegistrarse.addMouseListener(loginComponent);
lFacebook.addMouseListener(loginComponent);
lTwitter.addMouseListener(loginComponent);
lYoutube.addMouseListener(loginComponent);
```

_**Nota:** Recordar que en el anterior código se ven todas estas lineas juntas, sin embargo, estos son métodos de configuración por lo que cada una de ellas debe estar organizada junto al proceso de creación de su respectivo botón y label._

Ademas se van a crear nuevos métodos **get** que a continuación serán explicados:

* Se va a realizar un cambio de imágen desde la clase **LoginComponent** esto quiere decir que se debén obtener estas imágenes de algún modo, sin embargo para no realizar un método get por cada imágen y aprovechando el uso de eventos se crearán dos métodos get separados por dos categorías: Imágenes blancas, Imágenes Naranjas:

```
public ImageIcon getIBlanca(JLabel label) {
  if (label == lFacebook) 
    iDimAux = new ImageIcon(
      iFacebook1.getImage()
        .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
    );
  if (label == lTwitter) 
    iDimAux = new ImageIcon(
      iTwitter1.getImage()
        .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
    );
  if (label == lYoutube) 
    iDimAux = new ImageIcon(
      iYoutube1.getImage()
        .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
    );
  return iDimAux;
}

public ImageIcon getINaranja(JLabel label) {
  if (label == lFacebook) 
    iDimAux = new ImageIcon(
      iFacebook2.getImage()
        .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
    );
  if (label == lTwitter) 
    iDimAux = new ImageIcon(
      iTwitter2.getImage()
        .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
    );
  if (label == lYoutube) 
    iDimAux = new ImageIcon(
      iYoutube2.getImage()
        .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
    );
  return iDimAux;
}
```

Note que ambos métodos reciben un Label como parámetro y de acuerdo a este devolverán la imágen correspondiente, dicha imágen se retorna escalada de una vez.

* Se va a disponer al servicio **RecursosService** para que la clase **LoginComponent** pueda interactuar con el servicio sin la necesidad de obtenerlo ni depender de el:

```
public RecursosService getRecursosService(){ return sRecursos; }
```

Cuando se gestionaban eventos de acción mediante un **ActionListener** solo existía la preocupación por realizar discriminación a nivel de objetos ya que solo se utilizaban a los botones para gestionar estos eventos. Sin embargo, cuando se quiere que diferentes objetos de distintos tipos hagan un comportamiento basado en un mismo evento es necesario realizar una **Discriminación de clases**. Tal es el caso actual donde se quiere que los botones y los Labels realicen una acción todos estos dentro de un **mouseEntered / mouseExited** (Al pasar y salir de la zona del objeto).

De hecho es posible simplemente realizar una discriminación por objetos y especificar la acción por cada botón y por cada label, sin embargo, en este caso todos los botónes realizarán un mismo comportamiento, mientras que los labels también tendrán su comportamiento similar, asi que de nuevo se crearía código de mas para repetir un mismo comportamiento.

Dentro del método **mouseEntered** se va a configurar el comportamiento para los botones y labels. Primero se realiza la **Discriminación de clases**.

* Primero se crean los condicionales necesarios para realizar la discriminación:

```
@Override
public void mouseEntered(MouseEvent e) {
  if(/* Discriminación para botones */){
  }

  if(/* Discriminación para Labels */){
  }
}
```

* Ahora se va a obtener el objeto que ha activado el evento para ambos casos:

```
@Override
public void mouseEntered(MouseEvent e) {
  if(e.getSource()){
  }
  
  if(e.getSource()){
  }
}
```

* A continuación se realiza la comparación con la clase:

```
@Override
public void mouseEntered(MouseEvent e) {
  if(e.getSource() instanceof JButton){
  }

  if(e.getSource() instanceof JLabel){
  }
}
```

En el anterior código se esta realizando lo siguiente:

* Se obtiene el objeto que esta activando el evento.
* Mediante la palabra clave **instanceof** se esta preguntando si el objeto que ha activado el evento es una **ejemplificación** de la clase **JButton** o **JLabel**.

Ya se ha realizado la **Discriminación de clases** ahora en cada condición se puede escribir el código correspondiente. Primero se crean dos atributos en la clase **LoginComponent** para realizar una **Representación única para objetos gráficos de una misma Clase** tanto para un botón como para un label:

* **Declaración:**

```
// Al Inicio de la Clase
private JButton boton;
private JLabel label;
```

* **Uso de los atributos:**

```
@Override
public void mouseEntered(MouseEvent e) {
  if(e.getSource() instanceof JButton){
    boton = ((JButton) e.getSource());
    boton.setBackground(loginTemplate.getRecursosService().getColorPrincipalOscuro()); 
  }
  if(e.getSource() instanceof JLabel){
    label = ((JLabel) e.getSource());
    label.setIcon(loginTemplate.getINaranja(label));
  }
}
```

Se pueden mencionar varios aspectos:

* Note que para realizar el cambio de color es necesario llamar al servicio **RecursosService**, en este caso se opto por el enfoque en el cual el recurso es pasado desde la clase **Template** y asi la clase **LoginComponent** no se ve en la necesidad de obtener el servicio, este enfoque al igual que el usado en el componente **NavegacionUsuario** es valido ya que al final de cuentas se esta utilizando un único objeto en memoria del servicio.
* Para realizar el cambio de icono se llama a al método get **getINaranja** y este pide por parámetro un label asi que se enviá como argumento la representación única de los labels.
* También se puede observar que se realizó una **Representación única para objetos gráficos de una misma Clase** tanto para los botones como para los labels, ya que con el caso de los botones todos tenían el mismo comportamiento de cambiar de color de fondo, para los labels es el mismo caso cambiando la imágen.
* Note además que solo se agrego la escucha de estos eventos a los botónes y labels que iban a tener un mismo comportamiento, es decir que botones como el **bCerrar** o **bOpcion 1,2 o 3** no están incluidos por que no se planea que realicen este comportamiento y lo mismo pasa con los labels que no se incluyeron.
* Se utilizo esta vez atributos en lugar de variables para la representación única de botónes y labels, sin embargo, tanto este enfoque como el de el uso de variables funciona de igual manera, ya que estos objetos no van a adicionar nada en memoria, estos objetos son conocidos como **Objetos contenedores** y lo único que hacen es apuntar en la memoria al objeto que ya fue previamente creado y que activo el evento.

Ahora se debe configurar el método **mouseExited** para que los objetos gráficos regresen a su estado inicial una vez se sale del area del objeto, realizamos de nuevo la **Discriminación de clases** y **Representación única para objetos gráficos de una misma Clase**.

```
@Override
public void mouseExited(MouseEvent e) {
  if(e.getSource() instanceof JButton){
    boton = ((JButton) e.getSource());
    boton.setBackground(loginTemplate.getRecursosService().getColorPrincipal());  
  } 
  if(e.getSource() instanceof JLabel){
    label = ((JLabel) e.getSource());
    label.setIcon(loginTemplate.getIBlanca(label));
  }
}
```

Una vez ejecutamos la aplicación podemos ver el resultado esperado:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase9/raw/master/gifs/MouseEvent3.gif" alt=""><figcaption></figcaption></figure>

Implementación de discriminación de clases en el componente Login

## Efectos hacia otros objetos Gráficos

Cuando se usan eventos de Mouse también es posible generar efectos hacia otros objetos gráficos a traves de un objeto que activo el evento. Para explicar lo anterior planteado se van a generar unas modificaciones al componente **login** específicamente en la clase **LoginTemplate**:

* Primero se va a cambiar los bordes por defecto y el color de fuente de los campos de texto por grises usando el servicio **RecursosService**:

<figure><img src="https://camo.githubusercontent.com/d5e6facfb942ecb3d2fab7818897fa35410b6d03b09d57b142147dfcfb614202/68747470733a2f2f692e696d6775722e636f6d2f367733543267442e706e67" alt=""><figcaption></figcaption></figure>

Cambio de bordes y color de texto por gris por defecto

<figure><img src="https://camo.githubusercontent.com/8a29d123df213e56d5e04e45e649ffb67efe769dbb16a3bc8707c30b0273ca06/68747470733a2f2f692e696d6775722e636f6d2f64496f5765445a2e706e67" alt=""><figcaption></figcaption></figure>

Cambio de bordes y color de texto por gris por defecto

* También se va a cambiar la imágen que viene por defecto en los labels **lUsuario y lClave**:

<figure><img src="https://camo.githubusercontent.com/2d409429baed7bad565a8c764c2c044baad6d4d5d6aa71827bba1118eda748e8/68747470733a2f2f692e696d6775722e636f6d2f657365726139732e706e67" alt=""><figcaption></figcaption></figure>

Cambio de imágenes en los labels lUsuario y lClave

El Login de usuario se ve ahora así:

<figure><img src="https://camo.githubusercontent.com/accc597af585532a69c986e41a934526e00a754f6769d008796d9dff987e1c85/68747470733a2f2f692e696d6775722e636f6d2f72324556676b412e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario con campos de texto e iconos que los acompañan de color gris

* Además se crean nuevos método **get** que serán explicados a continuación:

```
public JLabel getLabels(JTextField text) {
  if (text == tNombreUsuario) return lUsuario;
  if (text == tClaveUsuario) return lClave;
  return null;
}

public ImageIcon getIAzul(JLabel label) {
  if (label == lUsuario) 
    iDimAux = new ImageIcon(
      iUsuario2.getImage()
        .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
    );
  if (label == lClave) 
    iDimAux = new ImageIcon(
      iClave2.getImage()
        .getScaledInstance(30, 30, Image.SCALE_AREA_AVERAGING)
    );
  return iDimAux;
}
```

* El método **getLabels** va a retornar el label correspondiente que acompaña a cada campo de texto, siendo el label **lUsuario** quien acompaña al TextField **tNombreUsuario** y el label **lClave** quien acompaña al passwordField **tClaveUsuario** para esto recibe como parámetro un TextField y esto es posible por que un objeto **JPasswordField** en realidad hereda de un **JTextField** asi que se puede tratar también como si fuere este ultimo.
* El método **getIAzul** va a retornar las imágenes de color azul que corresponden al Label adecuado y para esto reciben un Label como parámetro, la imágen retornada esta redimensionada de una vez.

En este caso se quiere usar los eventos de Mouse para realizar lo siguiente:

* Una vez se oprima click en el campo de texto correspondiente, este cambie el color del borde y texto a color azul.
* A su vez cuando se oprima click sore el campo de texto este borre automáticamente el placeholder o texto que trae por defecto para que el usuario pueda escribir sus datos sin la engorrosa tarea de borrar el contenido que estaba antes.
* Adicionalmente y como item a resaltar se quiere cambiar la imágen del label que acompaña al campo de texto correspondiente una vez se oprima click en dicho campo.

Dentro de la clase **loginComponent**, específicamente en el método **MouseClicked** se inicia realizando una **discriminación por clases** para TextField, esto debido a varíos factores:

* Aprovechando que un **JPasswordField** puede ser tratado como un **JTextField** esta discriminación abarcará el comportamiento de los dos campos de texto que es justo lo que se quiere.
* Aunque dentro del método **MouseClicked** solo se van a manipular los campos de texto, es necesarió aclarar que ya existen ademas unos **botones y labels** que están escuchando a eventos tipo **MouseListener**, esto quiere decir que cada uno de estos botones o labels van a revisar el código presente en los 5 métodos que por defecto trae un **MouseListener** y esto incluye al **MouseClicked** y si por ejemplo se quiere cambiar alguna característica de un JTextField un Botón no va a entender esa linea de código y saltará un error. Por otro lado si hay una discriminación el objeto de botón no podrá entrar al código dentro de esa condición y por ende no habrá errores.

```
@Override
public void mouseClicked(MouseEvent e) {
  if (e.getSource() instanceof JTextField) {
  }
}
```

Dentro de la condición se realiza ahora una **representación única** ya que el comportamiento deseado para ambos campos de texto es similar, para esto se crea un nuevo atributo tipo **JTextField**:

**Declaración de objeto**:

```
// Al Inicio de la Clase
private JTextField text;
```

**Representación Única:**

```
@Override
public void mouseClicked(MouseEvent e) {
  if (e.getSource() instanceof JTextField) {
    text = ((JTextField) e.getSource());
  }
}
```

* Lo primero que se configurará es el placeholder en los campos de texto para que el contenido sea borrado cada vez el usuario de click sobre el campo. Para esto basta con llamar al método **setText** y dentro colocar unas comillas vaciás representando que ahora el texto que contendrá estará vació:

```
@Override
public void mouseClicked(MouseEvent e) {
  if (e.getSource() instanceof JTextField) {
    text = ((JTextField) e.getSource());
    text.setText("");
  }
}
```

Él anterior código funciona, sin embargo, existe un problema, si el usuario se posiciona en el JTextField de nombre de usuario se borrara lo que esta escrito previamente y el usuario podrá escribir tranquilamente su nombre de usuario, pero si mas adelante se da cuenta que se equivoco en una pequeña parte y vuelve a dar click al JTextField **tNombreUsuario** para corregir dicha parte de lo que escribió, este de nuevo se borrara completamente:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase9/raw/master/gifs/MouseEvent4.gif" alt=""><figcaption></figcaption></figure>

Primera prueba de la implementación de MouseClicked

Para corregir esto se debe indicar que solamente se borrará el contenido de la caja de texto cuando el contendió sea el **placeholder** es decir el contenido inicial que viene por defecto, para el caso del JTextField **tNombreUsuario** es _"Nombre Usuario"_ y para el JPasswordField **tClaveUsuario** es _"Clave Usuario"_, con ayuda de un atributo tipo arreglo podemos realizar esta condición:

```
private String[] placeholders = { "Nombre Usuario", "Clave Usuario" };
```

Gracias a este arreglo que contiene los placeholder es posible crear una condición preguntando si el campo de texto contiene alguno de esos placeholder, en ese caso sea borrado su contenido:

```
@Override
public void mouseClicked(MouseEvent e) {
  if (e.getSource() instanceof JTextField) {
    text = ((JTextField) e.getSource());
    if (
      text.getText().equals(placeholders[0]) || 
      text.getText().equals(placeholders[1])
    ) 
      text.setText("");
  }
}
```

Se comprueba ejecutando la aplicación:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase9/raw/master/gifs/MouseEvent5.gif" alt=""><figcaption></figcaption></figure>

Arreglo de placeholder en el Login de usuario

Lo siguiente a configurar es el cambio de color dentro del campo de texto una vez se oprima click sobre el, como ya se tiene la representación única, basta con indicarle el cambio a este objeto:

```
@Override
public void mouseClicked(MouseEvent e) {
  if (e.getSource() instanceof JTextField) {
    text = ((JTextField) e.getSource());
    text.setForeground(loginTemplate.getRecursosService().getColorPrincipal());
    text.setBorder(loginTemplate.getRecursosService().getBInferiorAzul());
    if (
      text.getText().equals(placeholders[0]) || 
      text.getText().equals(placeholders[1])
    ) 
      text.setText("");
  }
}
```

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase9/raw/master/gifs/MouseEvent6.gif" alt=""><figcaption></figcaption></figure>

Cambio de color a caja de texto donde se escribe actualmente

Finalmente para dar un toque más de interactividad se configura el cambio de imágen a azul para el label que acompaña al campo de texto, primero se debe obtener el label correspondiente dependiendo del textField que active el evento, para esto se usa el método **getLabels** de la clase **LoginTemplate**:

```
@Override
public void mouseClicked(MouseEvent e) {
  if (e.getSource() instanceof JTextField) {
    text = ((JTextField) e.getSource());
    label = loginTemplate.getLabels(text);
    text.setForeground(loginTemplate.getRecursosService().getColorPrincipal());
    text.setBorder(loginTemplate.getRecursosService().getBInferiorAzul());
    if (
      text.getText().equals(placeholders[0]) || 
      text.getText().equals(placeholders[1])
    ) 
      text.setText("");
  }
}
```

Note que para obtener el label se debe enviar por parámetro un JTextField y para esto se enviá como argumento a la representación única de los campos de texto, ademas el objeto que se usa para representar al label es el atributo antes utilizado **label** una vez se ha obtenido el label, se puede hacer el cambio de imágen con ayuda del método **getIAzul** creado en el **LoginTemplate**:

```
@Override
public void mouseClicked(MouseEvent e) {
  if (e.getSource() instanceof JTextField) {
    text = ((JTextField) e.getSource());
    label = loginTemplate.getLabels(text);
    label.setIcon(loginTemplate.getIAzul(label));
    text.setForeground(loginTemplate.getRecursosService().getColorPrincipal());
    text.setBorder(loginTemplate.getRecursosService().getBInferiorAzul());
    if (
      text.getText().equals(placeholders[0]) || 
      text.getText().equals(placeholders[1])
    ) 
      text.setText("");
  }
}
```

Se ejecuta la aplicación para comprobar la funcionalidad del evento:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase9/raw/master/gifs/MouseEvent7.gif" alt=""><figcaption></figcaption></figure>

Implementación de efectos hacia otros objetos

Queda evidenciado en el anterior código que se puede cambiar el estado de otros objetos gráficos incluso si estos ni siquiera están a la escucha de eventos del Mouse, en este caso los campos de texto **tNombreUsuario o tClaveUsuario** activaron el evento para realizar cambios de estado en si mismos pero a su vez realizaron cambios en el estado de los labels **lUsuario y lClave** note que ninguno de estos dos labels tiene activada la escucha a ningún evento pero gracias a la activación de otro objeto gráfico se cambio el estado de estos.

## Uso combinado de varias interfaces implementadas de eventos

Algunos eventos del Mouse pueden compartir y complementar un comportamiento, un ejemplo son los eventos **mouseEntered y mouseExited** que en la mayoría de los casos están relacionados. También podría ser el caso de los métodos **mousePressed y mouseReleased** ya que el oprimir el botón del mouse muchas veces se ve relacionado con el momento en que este es soltado. Sin embargo, puede existir también combinaciones entre eventos de mouse que normalmente no están relacionados y que incluso pueden ser de diferentes interfaces.

En este caso se quiere dar la propiedad de arrastre a la ventana principal, hasta el momento tanto el login como la ventana principal se mantienen en una posición en la pantalla y el usuario no es capaz moverla, esto muchas veces puede resultar algo incomodo, sería bueno para la experiencia del usuario añadir este comportamiento a la ventana principal. Cuando el usuario mantenga oprimido el botón del mouse sobre el espacio de la barra superior de la ventana tendrá la posibilidad de arrastrarla.

Se procede a configurar el componente **barraTitulo**, específicamente su clase **BarraTituloComponent** y se va a extender de la clase **MouseAdapter**.

<figure><img src="https://camo.githubusercontent.com/99defe7b09ced51e743af00e1d868c79817d0d23e3e648b7f5502d5af875c648/68747470733a2f2f692e696d6775722e636f6d2f494f48484c5a732e706e67" alt=""><figcaption></figcaption></figure>

Extension de la clase MouseAdapter

Esta vez se van a implementar los siguientes métodos:

```
// MÉTODOS MOUSELISTENER
@Override
public void mousePressed(MouseEvent e) {}

// MÉTODOS MOUSEMOTIONLISTENER
@Override
public void mouseDragged(MouseEvent e) {}
```

Note que los métodos a usar son de diferentes interfaces siendo **mousePressed** parte de la interfaz **MouseListener** mientras que **mouseDragged** es parte de **MouseMotionListener**.

Se debe configurar la adición de la escucha de estos tipos de eventos en la clase **BarraTituloTemplate**, como en este caso todo el panel escuchará a los eventos se realizan en las configuraciones de la clase:

```
// DENTRO DEL CONSTRUCTOR
this.addMouseListener(barraTituloComponent);
this.addMouseMotionListener(barraTituloComponent);
```

Ahora bien, el evento de arrastre se va a activar desde el componente **barraTitulo**, sin embargo, como se va a mover toda la ventana principal el componente que se debe encargar en ultima instancia del movimiento de esta es la misma **vistaPrincipal**. Por este motivo se va a entrar al código de la clase **VistaPrincipalComponent** y se crea un método que se encargara de mover la ventana:

```
// DENTRO DE LA CLASE VISTA PRINCIPAL COMPONENT
public void moverVentana(){
}
```

* Como se modificará la posición de la ventana principal, es necesario que el evento reciba por parámetros la nueva posición en X y la nueva posición en Y:

```
// DENTRO DE LA CLASE VISTA PRINCIPAL COMPONENT
public void moverVentana(int posicionX, int posicionY){
}
```

* Ahora para cambiar de posición a la ventana principal se debe indicar a la parte del componente que representa las características gráficas del mismo que va a tener una nueva locación, es decir la clase **VistaPrincipalTemplate** y se realiza con el método **setLocation**:

```
public void moverVentana(int posicionX, int posicionY){
    this.vistaPrincipalTemplate.setLocation();
}
```

* Por ultimo dentro del método es necesario indicarle la posición nueva por lo que se ingresan los parámetros recibidos **posicionX y posicionY**:

```
public void moverVentana(int posicionX, int posicionY){
    this.vistaPrincipalTemplate.setLocation(posicionX, posicionY);
}
```

El método que se encarga de mover la ventana esta listo y además ya existe una comunicación bidireccional entre los componentes **vistaPrincipal y barraTitulo**, ahora se procede a configurar los eventos para que el movimiento de la ventana principal sea posible. En la sesión anterior se pudo observar que el método **mouseDragged** se activa una vez el usuario mantiene el botón del mouse oprimido y a su vez va arrastrando el mouse. Justamente ese es el comportamiento que se busca asi que es en este método donde se configura el comportamiento.

Dentro de este método se va a llamar al método **moverVentana** del la **VentanaPrincipal**:

```
@Override
public void mouseDragged(MouseEvent e) {
  this.vistaPrincipalComponent.moverVentana();
}
```

Ahora, se sabe que este método exige por parámetros las nuevas coordenadas, recordando un poco la sesión anterior se habían mencionado dos tipos de coordenadas que se pueden obtener:

* **getX()** Coordenadas con respecto al objeto gráfico que activo el evento.
* **getXOnScreen()** Coordenadas con respecto al monitor.

Como en este caso se quiere mover la ventana sobre el espacio del monitor es necesario obtener las coordenadas con la perspectiva de toda la pantalla.

```
@Override
public void mouseDragged(MouseEvent e) {
  this.vistaPrincipalComponent.moverVentana(
    e.getXOnScreen(), 
    e.getYOnScreen()
  );
}
```

Al correr la aplicación sucede lo siguiente:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase9/raw/master/gifs/MouseEvent8.gif" alt=""><figcaption></figcaption></figure>

Intento de arrastre de la ventana utilizando el evento mouseDragged

Se puede observar que efectivamente la ventana puede ser arrastrada y movida en la posicion que se quiere, sin embargo, hay un inconveniente, cada vez que se oprime el botón del Mouse y se arrastra la ventana principal, esta va a cambiar su posicion inmediatamente a donde esta el puntero del Mouse y va a empezar a seguir al puntero desde la esquina superior izquierda. Esto se ve muy extraño y poco natural, debe haber algún modo de corregir esto.

Para empezar, como se está indicando a la ventana principal que su nueva posicion va a ser justamente donde se encuentra el puntero del Mouse con respecto al Monitor esta inmediatamente se posicionara en esa locación, es por eso que se da ese movimiento antinatural y ademas esto provoca que la ventana este siguiendo al Mouse desde su esquina superior izquierda.

Se debe tener en cuenta también la posición del puntero del Mouse con respecto a la ventana y para comprobar esto se verá un ejemplo:

Suponga que el puntero del Mouse se encuentra en:

* La posicion **300px en el eje X con respecto al Monitor** del usuario.
* La posicion **100px en el eje X con respecto a la ventana**.
* La ventana por su parte esta en la posicion **200px en el eje X con respecto al monitor**.

<figure><img src="https://camo.githubusercontent.com/e6d2db38ff2b61f7884e37219e9b7c80a6a54b3d2cb3a0d495a0c840853481a5/68747470733a2f2f692e696d6775722e636f6d2f52786b7177656c2e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo de posicionamiento con el eje X

Con estas condiciones iniciales, suponga que el usuario oprime el botón del Mouse y mientras lo mantiene oprimido avanza 5 pixeles hacia la derecha, esto quiere decir que ahora el puntero esta en la posicion 305px **en el eje X con respecto al monitor**. Si se le indica a la ventana que su nueva posicion será la del puntero con respecto al monitor con el método **getXOnScreen()** su posicion en el eje X cambiara abruptamente **de 200px a 305px** en cuestión de milisegundos.

Si en cambio se le indica que su posicion va a ser igual a la posición del puntero con respecto al monitor **menos la posicion inicial del mismo con respecto a la ventana** la nueva posicion de la ventana sera:

* **305px - 100px = 205px**.

Se puede ver que la ventana avanzaría los 5 pixeles que corresponde a la derecha, esto es justo lo que se busca, esta lógica funciona de igual manera con el eje Y. Ahora se va a implementar esta solución en el código:

```
@Override
public void mouseDragged(MouseEvent e) {
  this.vistaPrincipalComponent.moverVentana(
    e.getXOnScreen() - e.getX(), 
    e.getYOnScreen() - e.getY()
  );
}
```

Al ejecutar la aplicación sucede lo siguiente:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase9/raw/master/gifs/MouseEvent9.gif" alt=""><figcaption></figcaption></figure>

Intento de arrastre de la ventana utilizando el evento mouseDragged

Al parecer algo muy raro ha ocurrido, una vez se oprime el botón del Mouse y se arrastra la ventana, esta desaparece de inmediato, bueno esto en realidad ocurre por que la **posicion en el eje X con respecto a la ventana** esta mal configurada y esto confunde al programa, recuerde que el método **getX() o getY()** da la posicion desde la perspectiva del objeto gráfico que ha activado el evento, en este caso ha sido el componente **barraTitulo** y si se entra a detalle este panel esta posicionado a 250px en el eje X de la ventana principal:

<figure><img src="https://camo.githubusercontent.com/88d043dae0c1f7fedc774666db2fa7ba3c61c38c42fb5a264117314164bec5f5/68747470733a2f2f692e696d6775722e636f6d2f55666a5a624e712e706e67" alt=""><figcaption></figcaption></figure>

Posición en el eje X del componente panelBarra en la ventana principal

Sin embargo, el método **getX()** no esta tomando en cuenta estos 250px asi que hay que añadirlos, con respecto al eje Y no hay problemas ya que el componente inicia desde la posición 0 de la Ventana principal.

```
@Override
public void mouseDragged(MouseEvent e) {
  this.vistaPrincipalComponent.moverVentana(
    e.getXOnScreen() - (e.getX() + 250), 
    e.getYOnScreen() - e.getY()
  );
}
```

Al ejecutar la aplicación una vez más sucede lo siguiente:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase9/raw/master/gifs/MouseEvent10.gif" alt=""><figcaption></figcaption></figure>

Intento de arrastre de la ventana utilizando el evento mouseDragged

Ahora existe otro problema, al parecer la ventana no se mueve de nuevo aunque se este oprimiendo el botón del Mouse y se arrastre. Esto se debe a que tanto **la posición con respecto al monitor** como **la posición con respecto a la ventana** se están actualizando constantemente, volviendo al anterior ejemplo, suponiendo estas mismas condiciones:

* La posicion **300px en el eje X con respecto al Monitor** del usuario.
* La posicion **100px en el eje X con respecto a la ventana**.
* La ventana por su parte esta en la posicion **200px en el eje X con respecto al monitor**.

Si el usuario avanza 5 posiciones a la derecha y se actualiza la posición del puntero con respecto al monitor y también la posicion del puntero con respecto a la ventana ahora estas serán:

* **305 en el eje X con respecto al Monitor** del usuario.
* **105 en el eje X con respecto a la ventana**.

Y si se restan estos dos valores la nueva posición de la ventana será entonces:

* **305 - 105 = 200**

Esto quiere decir que la posición no cambio en nada, ahora si el usuario se mueve otros 5 pixeles a la derecha y se actualizan ambas posiciones estas serán:

* **310 en el eje X con respecto al Monitor** del usuario.
* **110 en el eje X con respecto a la ventana**.

Si se restan nuevamente estos dos nuevos valores la nueva posición de la ventana será entonces:

* **310 - 110 = 200**

Es por esto que la ventana nunca se mueve con la solución antes planteada y aquí se resalta algo muy importante **Se debe actualizar la posicion del puntero del Mouse con respecto al Monitor** con cada movimiento del Mouse pero **la posicion con respecto a la ventana solo se debe capturar una vez al inicio y no actualizarse más**.

**¿Cómo es posible realizar esto?**

Si se recuerda la lección anterior, el método **mousePressed** realiza una acción una vez el usuarió presiona el botón del Mouse y no le importa que pueda ocurrir de ahi en adelante, asi que se puede aprovechar esta propiedad.

Primero se declaran dos atributos ya que será necesario poder manipularlos desde diferentes métodos, estos representaran la posicion inicial tanto en X como en Y:

```
private int posicionInicialX, posicionInicialY;
```

Ahora en el método **mousePressed** y se va a indicar que una vez se oprima el botón del Mouse va a capturar la posición del puntero del Mouse **con respecto a la Ventana** y la va a guardar en los atributos anteriormente creados:

```
@Override
public void mousePressed(MouseEvent e) {
  posicionInicialX = e.getX()+250;
  posicionInicialY = e.getY();
}
```

_**Nota:** Recordar que en el eje X se le suman los 250 pixeles que no tiene en cuenta el método **getX()** y que es la posicion del componente barraTitulo con respecto a la ventana Principal._

Una vez ya se tiene la posición inicial se debe restar con la posicion que se actualizará constantemente y es la posición con respecto al monitor:

```
@Override
public void mouseDragged(MouseEvent e) {
  this.vistaPrincipalComponent.moverVentana(
      e.getXOnScreen() - posicionInicialX, 
      e.getYOnScreen() - posicionInicialY
  );
}
```

Una vez se correr la aplicación sucede lo siguiente:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase9/raw/master/gifs/MouseEvent11.gif" alt=""><figcaption></figcaption></figure>

Implementación de arrastre de la ventana utilizando el evento mouseDragged y MousePressed

En este caso se vio la importancia que tiene combinar varios métodos de eventos que pareciera que no tienen ninguna relación, incluso entre eventos que hacen parte de diferentes interfaces de escucha de eventos. Cuando se tienen más acciones con los eventos seguramente habrán más combinaciones entre estos para lograr efectos avanzados.

## Resultado

Si llegaste hasta aquí **!Felicidades!** se ha aprendido como utilizar los eventos del Mouse para darle mayor interactividad al proyecto, se aprendió ademas varios aspectos importantes como **Representación única para objetos gráficos de una misma Clase** para representar un mismo comportamiento a varios objetos gráficos, **Uso de la clase MouseAdapter** para el uso de métodos que unicamente serán utilizados, **Discriminación de Clases** para los casos en que varios objetos de distintas clases quieren usar un mismo evento, **Efectos hacia otros objetos Gráficos** para cambiar cualquier parte de la interfaz mediante un objeto que activa el evento y el **Uso combinado de varias interfaces implementadas de eventos** para lograr ciertos comportamientos corelacionados.

La siguiente clase se va a centrar nuevamente en la arquitectura del proyecto y esta vez se va a explicar que son los **Servicios** y el uso de **Servicios Lógicos**.

## Actividad

Implementar los eventos del Mouse a todo el proyecto para que este tenga una mayor interactividad con los usuarios.

Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 10

### Objetivos

* Examinar las características principales de los servicios y su forma de construcción.
* Reconocer el propósito del uso de Servicios lógicos dentro del proyecto para la obtención de información externa desde cualquier componente gráfico.
* Identificar las distintas funcionalidades que puede tomar un servicio lógico para el manejo de información externa.
* Comprender la forma en que distintas partes del proyecto pueden dar uso de un servicio en común para obtener información.

## Antes de Comenzar

#### **Actualización de Imágenes en recursos**

***

Para continuar con el ejercicio deberá actualizar la carpeta **resources/images/perfiles** ya que se han agregado nuevas imágenes. Estas las puede descargar en este mismo repositorio entrando a la carpeta **Clase10** seguido de **resources/images/perfiles**.

#### **Estructura del proyecto**

***

Se puede observar mediante un modelo estructural general como es la estructura del proyecto hasta el momento:

<figure><img src="https://camo.githubusercontent.com/35321928e46a6562bba50d003cb4e5e0f5e4afe9a6044b3b59081441ddc9fb77/68747470733a2f2f692e696d6775722e636f6d2f387136557136432e706e67" alt=""><figcaption></figcaption></figure>

Modelo Estructural del Proyecto

El anterior es un esquema general de como esta conformado el proyecto, algunos aspectos y detalles se han omitido y solo se muestra lo más relevante en cuanto a la estructura en aspectos como atributos, métodos y relaciones entre clases.

#### **Ajustes en el proyecto**

***

* Se va a crear un nuevo paquete desde la carpeta raíz **src** el cual es llamado **archives**, ahi estarán contenidos dos archivos planos que servirán como una simulación de información externa para el propósito de la clase.

<figure><img src="https://camo.githubusercontent.com/86e26e2ab9a13135f9c003b04d148649447eab68f69bd5b2b5b59d65cd54cbc9/68747470733a2f2f692e696d6775722e636f6d2f394f6f334654362e706e67" alt=""><figcaption></figcaption></figure>

Creación de paquete archives para contener archivos planos

Estos archivos planos los puede encontrar en este mismo repositorio entrando a la carpeta **Clase10** seguido de la carpeta **src** y luego en la carpeta **archives**.

<figure><img src="https://camo.githubusercontent.com/edfe308912e776c851a9da4871f838f40c0db5882a13a2275e58e1225ea10b52/68747470733a2f2f692e696d6775722e636f6d2f774f64645154622e706e67" alt=""><figcaption></figcaption></figure>

Carpeta Clase10 dentro del repositorio

<figure><img src="https://camo.githubusercontent.com/0bf5406d801ed575064d5abf2fa87b98053796448f1d8616f0a3c718061f2263/68747470733a2f2f692e696d6775722e636f6d2f366f79757a31312e706e67" alt=""><figcaption></figcaption></figure>

Carpeta src dentro del repositorio

<figure><img src="https://camo.githubusercontent.com/140882d63489917d4197514bdb25b303b62a148a916d7b82c11e455e3a671bc1/68747470733a2f2f692e696d6775722e636f6d2f4d504f5269756c2e706e67" alt=""><figcaption></figcaption></figure>

Carpeta archives dentro del repositorio

<figure><img src="https://camo.githubusercontent.com/2defe0c76a59c6b11ca48aa391af55577f444aa8cf071c81d3af313c377b3554/68747470733a2f2f692e696d6775722e636f6d2f464651756861672e706e67" alt=""><figcaption></figcaption></figure>

Archivos planos dentro del repositorio

#### **Ajustes con los servicios**

***

Se van a crear dos paquetes donde se va a separar y contener los servicios de acuerdo a su propósito, estos dos paquétes serán:

* **graphicServices**
* **logicServices**

Adicionalmente se dejan los servicios ya creados **ObjGraficosService y RecursosService** dentro del páquete **graphicServices**:

<figure><img src="https://camo.githubusercontent.com/446cf1b0139906cb841bef04cb07211365ae06ace28d9dc73ad6382c0f3c47c8/68747470733a2f2f692e696d6775722e636f6d2f514a6b334578562e706e67" alt=""><figcaption></figcaption></figure>

Creación de folders para separación de servicios

#### **Recordatorio**

***

Recordando un poco el recorrido, se ha implementado los eventos de Mouse para proporcionar interactividad a varias partes del proyecto, acciones como el arrasate de la ventana, el cambio de color de varios botones y labels, la gestión del contenido y color de los JTetField etc. Paralelamente se vieron algunos temas importantes relacionados con los eventos como: **Representación única para objetos gráficos de una misma Clase** , **Uso de la clase MouseAdapter**, **Discriminación de Clases**, **Efectos hacia otros objetos Gráficos** y el **Uso combinado de varias Interfaces implementadas de eventos**.

## Servicios

En esta sesión se verá el uso y características de los servicios em general y la implementación de servicios lógicos, para abarcar el tema, la lección esta divida en los siguientes items principales:

* **Explicación general de los servicios**.
* **Servicio lógico contenedor de información externa**.
* **Servicio lógico que recibe información externa**.
* **Ajustes del proyecto para el uso de servicios**.

## Explicación general de los servicios

Antes se ha hablado de los **Componentes Gráficos** y se sabe que estos están conformados por una parte gráfica (**Template**), y una parte lógica (**Component**). Aunque la clase **Component** utiliza lógica detrás para que todas las funcionalidades del componente se puedan cumplir, hay un limite en su responsabilidad, es necesario recordar que esta clase se debe encargar unicamente de soportar la lógica que requiere el componente.

Las aplicaciónes de interfaz Gráfica siempre van a depender de la obtención de información externa que el usuario va a solicitar, ya sea de un servidor web, una base de datos externa, una Api publica etc. Una opción puede ser delegar la obtención de esta información a las clases **Components**, lógicamente puede ser una propuesta valida. Sin embargo, esto puede restar reutilización y modularidad dentro del proyecto. Esta información externa tiene ciertos datos que seguramente van a ser solicitados por varias partes del proyecto y si en cada componente que se necesite dicha información se va a consumir un mismo servicio web externo existirá una acumulación grande de peticiones lo que podría generar un mal rendimiento.

Otra forma para obtener esta información sin afectar el rendimiento es obtener la información externa una vez desde cualquier componente y empezar a pasar dicha información entre componentes, sin embargo, esta practica hará que el proyecto esté muy acoplado y exista una dependencia alta entre componentes gráficos.

Una solución mas coherente es hacer uso de servicios que van a tener un propósito bien definido y que puede encapsular alguna funcionalidad o información externa que será requerida por varias partes del proyecto. De esta manera el servicio hará solo las peticiones necesarias a las entidades externas y ademas si algún componente necesita de esta información puede solicitarla al servicio haciendo que los componentes sean independientes entre si y no exista un acoplamiento masivo.

Estas clases entonces se encargan principalmente de contener la información que se va a obtener externamente. Pueden existir varios tipos de servicios:

* **Servicios Lógicos:** Que se encargan de contener información externa y que será solicitada por varas partes del proyecto. Siempre serán solicitados por las clases **Component** de los componentes.
* **Servicios Gráficos:** Que contiene una funcionalidad o información especifica que está relacionada con la creación de objetos gráficos. Siempre serán solicitados por las clases **Template**.

Independientemente de su clasificación la estructura de los servicios es similar, es posible crear servicios **Singleton** o en su defecto realizar varios objetos de un servicio (Esto en ocasiones muy especiales).

Se han visto a lo largo del curso el uso de **Servicios Gráficos**, específicamente:

* El servicio Gráfico **ObjGraficosService** encargado de encapsular la construcción de objetos gráficos.
* El servicio Gráfico **RecursosService** encargado de la creación responsable de objetos decoradores que puedan ser solicitados por varios template.

En los anteriores servicios se evidencian los dos propósitos principales de los servicios:

* **Contener Funcionalidad común**: El servicio **ObjGraficosService** tiene encapsulada una funcionalidad que es usada por la mayoría de clases Template que se han creado. Este servicio contiene una serie de métodos encargados de la construcción de objetos gráficos y que ayuda a las clases **Template** con el proceso de **creación de objetos gráficos**. Esta funcionalidad es común y general por lo que permite que se use en varias partes del proyecto e incluso en varios proyectos.
* **Contener Información común**: El servicio **RecursosService** de alguna manera se esta conteniendo información, no es información externa evidentemente ni tampoco información compuesta de datos comúnes. Pero desde una perspectiva general, este servicio crea objetos decoradores (información) que son solicitados desde varias partes de la aplicación.

El factor más importante del uso de Servicios esta en su propósito de contener algo que será solicitado por varias partes del proyecto, evitando así el acoplamiento extremo entre componentes gráficos. Por ejemplo si el servicio **RecursosService** no existiera pero se quisiera controlar la creación de objetos decoradores como colores, fuentes, bordes etc. La única forma de realizar esto es creándolos todos desde la clase **App** y empezar a repartir estos objetos mediante los constructores de los componentes lo que generaría un altísimo acoplamiento entre clases.

## Servicio lógico contenedor de información externa

Varias veces la información externa es necesaria solo para propósitos visuales, es decir información que será mostrada pero que no necesariamente está contenida en algún servidor web o una base de datos, simplemente es información que se quiere mostrar en la interfaz gráfica, pero que no es tan importante para guardarse en una base de datos o un servidor web externo.

En este caso se va a contener información relacionada con las acciónes que se muestran en el componente **inicio**. Como recordatorio estas acciónes se muestran a través de la **reutilización de componentes gráficos** pero había una cantidad considerable de código debido a esta reutilización, esta vez se va a recibir la información de las acciones a través de un archivo plano (Simulación de información externa) y se contendrá en un servicio para reducir el código de la clase.

<figure><img src="https://camo.githubusercontent.com/f547e328ee1dae22f12227cedf7d7d7a7467e868d999688bc061391172c9e2e6/68747470733a2f2f692e696d6775722e636f6d2f6d5a4676504a342e706e67" alt=""><figcaption></figcaption></figure>

Acciones dentro del componente Inicio.

Primero se analiza la estructura de los archivos plano acciones:

<figure><img src="https://camo.githubusercontent.com/8c094ba3d4d9d93fde0dd14c3ce3a968f8c2a9cab88d74f8fe9805684d934c1d/68747470733a2f2f692e696d6775722e636f6d2f776a53416259422e706e67" alt=""><figcaption></figcaption></figure>

Estructura de archivo plano, acciones

Pueden notar que el archivo plano contiene cierta información sobre cada acción y se debe resaltar que cada parte de la información por acción esta separada por una coma **(,)** y cada acción esta separada por un salto de linea. Entre sus partes están:

* **Titulo de Acción**.
* **Descripción de Acción**.
* **Dirección de Imagen**.

Ahora se crea el servicio **AccionService**, esta clase se crea dentro del paquete **logicServices**:

<figure><img src="https://camo.githubusercontent.com/49c08358ceec01f9d9009582d2d803dc3baf01aac1fce02c3a30082f61183322/68747470733a2f2f692e696d6775722e636f6d2f527074346164462e706e67" alt=""><figcaption></figcaption></figure>

Creación de servicio AccionService

Para tener un control de la creación del objeto del servicio se va a implementar el patron **Singleton** de igual manera, sin embargo, se deja una pequeña variación y es que el constructor va a quedar publico. Esto debido a que puede que en algún momento una parte del proyecto va a necesitar un objeto del servicio en el cual no se le haya cargado ninguna información previamente y con esto tendrá la posibilidad de crear una ejemplificación del servicio diferente para sus propósitos individuales, por otro lado si necesita información que puede ser compartida entre varios componentes de seguro preferirá obtener el objeto del servicio que están usando los demás a través del singleton.

* Primero se declará un objeto de si mismo, recuerde que debe ser un atributo tipo **static**.

```
    private static AccionService servicio;
```

* Se crea el método estático para la creación única del servicio:

```
public static AccionService getService() {
  if(servicio == null)
    servicio = new AccionService();
  return servicio;
}
```

* Como se explico el constructor se deja publico (es decir en su forma normal).

Antes de continuar con el servicio se procede a crear otro paquete desde la carpeta raíz **src**, la cual será llamada **models**, adentro se crea una clase llamada **Accion** y será la representación en objeto de las acciones.

<figure><img src="https://camo.githubusercontent.com/0a8ef20fd5232446d400a24077233839619f4d630afce4fedcd78ee5e0aa49c9/68747470733a2f2f692e696d6775722e636f6d2f75734b45724e302e706e67" alt=""><figcaption></figcaption></figure>

Creación de paquete models y la clase Accion.java

* Dentro de esta clase se declaran los atributos:

```
// Dentro de la clase Accion
private String nombreAccion;
private String descripcionAccion;
private ImageIcon imagenAccion;
```

* Ahora se generan los métodos **get y set** correspondientes a sus atributos:

```
public String getNombreAccion () { return nombreAccion; }

public String getDescripcionAccion () { return descripcionAccion; } 

public ImageIcon getImagenAccion () { return imagenAccion; }

public void setNombreAccion (String nombreAccion){
  this.nombreAccion = nombreAccion;
}

public void setDescripcionAccion (String descripcionAccion){
  this.descripcionAccion = descripcionAccion;
}

public void setImagenAccion (ImageIcon imagenAccion){
  this.imagenAccion = imagenAccion;
}
```

_**Nota:** El anterior es un esquema general de una clase del modelo. Es bueno manejar la información por medio de objetos que encapsulen la información y es un pilar fundamental en la programación orientada a objetos_

Dentro del servicio **AccionService**, este servicio va a contener un atributo que sera una lista de todas las acciones necesarias dentro del proyecto, para hacer esto es necesario un objeto tipo **arrayList**, este es un tipo de arreglo que tiene ciertas ventajas, por ejemplo puede contener objetos y ademas no tiene un tamaño fijo por lo que puede agregarse o quitarse objetos dentro de la lista en tiempo de ejecución:

* **Declaración:**

```
// Dentro del servicio AccionService
private ArrayList<Accion> acciones;
```

* **ejemplificación:**

```
public AccionService() {
  acciones = new ArrayList<Accion>();
}
```

_**Nota:** Entre los signos **<>** esta el tipo de objetos que va a contener, en este caso el arreglo **acciones** va a contener objetos de tipo **Accion**, aunque el arreglo es dinámico, al ser un arreglo es preferible que contenga un solo tipo de dato._

Como este servicio se va a encargar de obtener la información externa, es necesario crear un método encargado de recibir la información del archivo plano. Muchas veces esta información que no proviene de algún servidor o base de datos externa esta contenida en archivos planos y es una ayuda para la encapsulación de información que puede cambiar con el tiempo y que solo tiene propósitos visuales en la aplicación.

```
public void cargarDatos() {
  File archivo = null;
  FileReader fr = null;
  BufferedReader br = null;
  try {
    archivo = new File ("Clase10/src/archives/aciones.txt");
    fr = new FileReader (archivo);
    br = new BufferedReader(fr);

    String linea;
    while((linea=br.readLine())!=null){
      String[] atributos = linea.split(",");
      Accion accion = new Accion();
      accion.setNombreAccion(atributos[0]);
      accion.setDescripcionAccion(atributos[1]);
      accion.setImagenAccion(new ImageIcon(atributos[2]));
      acciones.add(accion);
    }
    fr.close(); 
  } catch(Exception e) {
    e.printStackTrace();
  }
}
```

El anterior código se encarga de leer la información contenida en el archivo plano **acciones.txt**, una vez se ha leído una linea dentro del archivo se crea un objeto de la acción y se inserta en la lista de acciones. La explicación de este método no es el fin de esta clase pero se va a explicar a grandes rasgos su función en la siguiente imágen.

<figure><img src="https://camo.githubusercontent.com/669b9b815dc82306814914d7c37290e0c37ce1f1c7acd20b53a865dca4430197/68747470733a2f2f692e696d6775722e636f6d2f79706c6351764c2e706e67" alt=""><figcaption></figcaption></figure>

Explicación de código de obtención de información del archivo plano

Para que la información pueda ser cargada una vez se obtenga el servicio se debe llamar este método desde el constructor:

```
public AccionService() {
  acciones = new ArrayList<Accion>();
  cargarDatos();
}
```

Ahora se crea un método encargado de retornar una accion cuando algún componente gráfico lo necesite:

* El método debe retornar un objeto tipo **Accion** y debe recibir por parámetro un entero que representa la posición en el arreglo de la accion solicitada.

```
public Accion devolverAccion(int posicion){
}
```

* Se va a hacer la petición mediante un **try/catch**, esto para el control de errores. Dentro del Try se va a intentar retornar un objeto **Accion**, en caso de que se genere un error en el momento de retornar una acción se puede gestionar el error a través del catch.

```
public Accion devolverAccion(int posicion){
  try{
  }
  catch(Exception e){
  }
}
```

* Dentro del Try se retorna la acción dentro de la lista que se pida mediante la posición enviada como argumento, en dado caso en que la posición no exista dentro del arreglo, se va a retornar un null.

```
public Accion devolverAccion(int posicion){
  try{
    return acciones.get(posicion);
  }
  catch(Exception e){
    return null;
  }
}
```

El servicio esta listo y puede usarse en varias partes del proyecto, por ahora será usado en un lugar especifico, el componente **Inicio**. Dentro de la clase **InicioComponent** y lo primero que se debe hacer es obtener el servicio:

* **Declaración:**

```
private AccionService sAccion;
```

* **Obtención del Servicio:**

```
// Dentro del constructor
sAccion = AccionService.getService();
```

_**Nota:** Es importante aclarar que la obtención del servicio debe hacerse antes de cargar la parte gráfica del componente ya que se van a pedir datos al servicio para ser mostrados en pantalla y si se muestra primero el componente antes de obtener el servicio esta información no existirá y saldrá un error._

Una vez obtenido el servicio de acciones, se crea un método que se comunique con el servicio y que de igual forma retorne una **Accion** que obtiene del Servicio:

* De igual forma retornara un objeto tipo **Accion** y recibe por parámetro la posicion de la acción en el arreglo dinámico.

```
public Accion obtenerAccion(int numeroAccion){

}
```

* Ahora se debe llamar al método creado en el servicio **AccionService** pasándole como argumento la posicion de la acción que se recibió como parámetro:

```
public Accion obtenerAccion(int numeroAccion){
  return sAccion.devolverAccion(numeroAccion);
}
```

Ahora, en la clase **InicioTemplate** se puede obercar como esta escrito el código del método **crearContenidoPAcciones()**, en el se establece la creación de cada componente **Accion** de forma manual.

<figure><img src="https://camo.githubusercontent.com/707a9e501f842d0b9422cf9edeb6876cb4a229fe7ebb9a7a217491412b6673ea/68747470733a2f2f692e696d6775722e636f6d2f5055745a7158662e706e67" alt=""><figcaption></figcaption></figure>

Creación manual del Componente Gráfico Accion

Ahora que se tiene la información de todas las acciones, es posible automatizar la creación del componente gráfico **Acción** varias veces (Aprovechando también la reutilización de componentes). Se procede a borrar la creación manual de todas las acciones y solo se deja la creación del título intacta:

```
public void crearContenidoPAcciones() {
  this.lAcciones = sObjGraficos.construirJLabel(
    "Nuestros Servicios", 
    10, 10, 160, 30, 
    null, 
    sRecursos.getColorPrincipal(), 
    null, 
    sRecursos.getFontTitulo(), 
    "c"
  );
  this.pAcciones.add(lAcciones);
}
```

Ahora se va a crear un **Contador** esta variable va a servir como la posición a buscar dentro del arreglo de acciones que contiene el servicio **AccionService**, también se crea otro entero que será responsable de la posición en las filas de los componentes de Accion:

```
public void crearContenidoPAcciones() {
  // Creación del Titulo
  ...

  int numeroAccion = 0, fila = 0;
}
```

Ahora se crea un objeto de tipo **Accion** (que se encuentra en el paquete **Models**) y se iguala con la llamada del método que esta en la clase **Component** que a su vez va a llamar al método que se encuentra en el servicio **ActionService**:

```
public void crearContenidoPAcciones(){
  // Creación del Titulo
  ...
  
  int numeroAccion = 0, fila = 0;
  Accion accion = inicioComponent.obtenerAccion(numeroAccion);
}
```

En el anterior código se ha llamado al método **obtenerAccion** de la clase **InicioComponent** y como argumento se pasa el **Contador** que vale 0 inicialmente, esto quiere decir que se ha obtenido desde el servicio **AccionService** la **acción** que se encuentra en la primera posición de la lista **acciones**.

Se crea ahora un ciclo **while** y la condición para que el ciclo continue es que al llamar al servicio para obtener una accion este no retorne un dato tipo **nulo** o en otras palabras que una vez ya no existan más acciones en el arreglo el ciclo se termine.

```
public void crearContenidoPAcciones() {
  // Creación del Titulo
  ...
  
  int numeroAccion = 0, fila = 0;
  Accion accion = inicioComponent.obtenerAccion(numeroAccion);
  while(accion != null) {
    
  }
}
```

Como ya se recibió la primera accion antes de entrar al ciclo la condición se cumple y puede entrar, dentro del ciclo se crea el componente gráfico **Accion** y como se sabe, se debe llamar a su clase **AccionComponent** para acceder a este.

* Primero se ejemplifica la clase **Component**:

```
public void crearContenidoPAcciones() {
  // Creación del Titulo
  ...
  
  int numeroAccion = 0, fila = 0;
  Accion accion = inicioComponent.obtenerAccion(numeroAccion);
  while(accion != null) {
    AccionTemplate pAccion = new AccionComponent();
  }
}
```

_**Nota:** Puede observar que se crea un objeto tipo Template del Componente Accion pero se esta igualando a la ejemplificación de la clase Component, esto claramente va a traer error de compatibilidad de objetos, sin embargo, esto se hace por que de una vez en la ejemplificación se va a traer la clase template para asegurar que la igualdad sea cierta._

Recordando, la clase **AccionComponent** pide ciertas cosas por parámetros como **una imagen, un título y un párrafo de descripción**.

<figure><img src="https://camo.githubusercontent.com/5b167f3a44500f15d5bd3f96cc426742e8f3b15f989e69fb0fcfe7f196ca8090/68747470733a2f2f692e696d6775722e636f6d2f5168525a5147642e706e67" alt=""><figcaption></figcaption></figure>

Parámetros exigidos por el componente Acción

Ahora que se tiene toda esta información encapsulada en un objeto, conviene cambiar un poco la estructura del componente reutilizable para que solo exija un objeto de tipo Accion como parámetro:

<figure><img src="https://camo.githubusercontent.com/8aaf41a37e14870bae0eab6cef3de97f22f3b15f7ce554696569b2838da0b29d/68747470733a2f2f692e696d6775722e636f6d2f3165515566784b2e706e67" alt=""><figcaption></figcaption></figure>

Cambio en la petición de parámetros dentro de la clase AccionComponent

<figure><img src="https://camo.githubusercontent.com/b14a3bd81b39a4fc6961564233c7a1fe8c3b8aaacc18cd4ca9f456aa1642c31a/68747470733a2f2f692e696d6775722e636f6d2f7034714d6f51632e706e67" alt=""><figcaption></figcaption></figure>

Cambio en la petición de parámetros y ajusto en la clase AccionTemplate

Una vez realizadas estas modificaciones se enviá como argumento a la acción que se tiene actualmente:

```
public void crearContenidoPAcciones() {
  // Creación del Titulo
  ...
  
  int numeroAccion = 0, fila = 0;
  Accion accion = inicioComponent.obtenerAccion(numeroAccion);
  while(accion != null) {
    AccionTemplate pAccion = new AccionComponent(accion);
  }
}
```

Ahora el editor o IDE muy seguramente debe estar sacando error y esto es por que la igualdad **Clase Template = Clase Component** no es verdadera, se debe llamar a la clase **Template** del componente para que esta igualdad se cumpla:

```
public void crearContenidoPAcciones() {
  // Creación del Titulo
  ...
  
  int numeroAccion = 0, fila = 0;
  Accion accion = inicioComponent.obtenerAccion(numeroAccion);
  while(accion != null) {
    AccionTemplate pAccion = 
      new AccionComponent(accion).getAccionTemplate();
  }
}
```

El componente **Accion** ya ha sido ejemplificado de manera exitosa, sin embargo, es necesario recordar que se esta realizando una **reutilización por posicionamiento** esto quiere decir que se debe dar la posición a cada componente acción que se llame. En este caso se sabe que se tienen 6 acciones, sin embargo esto podría cambiar con el tiempo y se podrían agregar mas acciones en el archivo plano, para generar un posicionamiento general se realiza el siguiente calculo basado en el modulo, se muestra el código y a continuación se explica:

```
public void crearContenidoPAcciones(){
  // Creación del Titulo
  ...
  

  int numeroAccion = 0, fila = 0;
  Accion accion = inicioComponent.obtenerAccion(numeroAccion);
  while (accion != null) {
    AccionTemplate pAccion = 
      new AccionComponent(accion).getAccionTemplate();
    pAccion.setLocation(
      15 + ((pAccion.getWidth() + 15) * (numeroAccion % 3)),
      50 + ((pAccion.getHeight() + 15) * fila)
    );
    if (numeroAccion % 3 == 2) fila++;
  }
}
```

Para explicar el calculo anteriormente realizado se va a explorar la posición por cada eje:

* **Eje X**
  * Se tiene un numero inicial 15 que será constante, esto debido a que las acciones de la primera columna siempre van a empezar 15px sobre el eje X.
  * Los siguientes criterios para el posicionamiento son el **ancho del componente accion** y una **distancia de 15px entre cada componente**. Esto quiere decir que los componentes de la columna 1 siempre están en la coordenada 15px, mientras que los de la segunda columna deberán sumar a esos 15px los 250px del ancho mas 15px para una distancia entre componentes.
  * El criterio mas importante es el **modulo con 3**, se sabe que cada fila va a tener un total de 3 columnas, el modulo con 3 indicará el numero de columna en que se posicionará cada componente (cada columna contada desde 0 hasta 2), el modulo es clave ya que va a generar un limite haciendo que los resultados puedan variar solamente desde 0 hasta 2, esto quiere decir que:
    * Si el numero de acción esta en 0, se realiza la operación 0 % 3 lo que arroja un resultado de 0 indicando que la primera acción se ubica en la columna 0.
    * Si el numero de acción esta en 2, se realiza la operación 2 % 3 lo que arroja un resultado de 2 indicando que la tercera acción se ubica en la columna 2.
    * Si el numero de acción esta en 3, se realiza la operación 3 % 3 lo que arroja un resultado de 0 indicando que la cuarta acción se ubica en la columna 0.
  * Como el modulo va a retornar números de 0 a 2 este resultado es multiplicado con el ancho del componente y la distancia para generar su posición final en el eje X de esta forma:
    * La acción 1 (cuyo numero de Accion es 0) Genera un modulo en 0, lo que hace que su posición final quede en 15px.
    * La acción 3 (cuyo numero de Accion es 2) genera un modulo en 2, lo que hace que su posición final quede en **15px (constante) + ((250px (ancho) + 15px (distancia)) \* 2 (modulo)) = 545px**.
    * La acción 4 (cuyo numero de Accion es 3) Genera un modulo en 0, lo que hace que su posición final quede en 15px.
* **eje Y**
  * Se tiene un numero inicial 50 que será constante, esto debido a que las acciones de la primera fila siempre van a empezar 50px sobre el eje Y.
  * Los siguientes criterios para posicionamiento son **la altura del componente** y una **Distancia entre componentes** y se basa en el mismo principio explicado en el eje X.
  * El principal criterio es el entero llamado **fila**, este inicia en 0 y puede aumentar su valor dependiendo de cuantas acciones existan.
  * La fila va a depender nuevamente del **modulo con 3** ya que gracias a este se establece el numero de columna donde se posiciona la acción actual, y con esto se crea un condicional donde se indica que si la columna actual es la ultima (2) se aumente el valor de la fila para que se posicionen los siguientes componentes de accion debajo.

Para finalizar el ciclo de manera correcta es necesario:

* Agregar el componente al panel.
* Aumentar el Contador.
* Llamar al siguiente objeto de acción en la lista.

```
public void crearContenidoPAcciones(){
  // Creación del Titulo
  ...
  

  int numeroAccion = 0, fila = 0;
  Accion accion = inicioComponent.obtenerAccion(numeroAccion);
  while (accion != null) {
    AccionTemplate pAccion = 
      new AccionComponent(accion).getAccionTemplate();
    pAccion.setLocation(
      15 + ((pAccion.getWidth() + 15) * (numeroAccion % 3)),
      50 + ((pAccion.getHeight() + 15) * fila)
    );
    if (numeroAccion % 3 == 2) fila++;
    this.pAcciones.add(pAccion);
    numeroAccion++;
    accion = inicioComponent.obtenerAccion(numeroAccion);
  }
}
```

Las Acciones están listas y se muestran correctamente, podemos ejecutar la aplicación y verificar:

<figure><img src="https://camo.githubusercontent.com/f2549cfcaee2f8773d94f061842e4823d5f80aa81ab795a47ebeb73ca90f658b/68747470733a2f2f692e696d6775722e636f6d2f364c63573972622e706e67" alt=""><figcaption></figcaption></figure>

Componentes Accion creados de forma automática.

Ya se realizó la automatización de la creación de **componentes gráficos reutilizables** y es un complemento de lo que se había visto previamente sobre ese tema. Sin embargo, vale la pena aclarar que el fin del servicio **AccionService** no es solamente poder realizar esta automatización, como se explico previamente este servicio contiene la información de estas acciónes que se pueden usar en varias partes del proyecto. Aprovechando el concepto de reutilización de componentes podría de alguna forma crearse el listado de dichas acciones en otra parte del proyecto y ya no habría necesidad de solicitar los datos nuevamente a la entidad externa ya que esta esta contenida en el servicio ni tampoco realizar una comunicación innecesaria entre componentes para el traspaso de información.

Esta acción no se realizará en el momento, pero para explicar lo anterior referente al uso compartido de servicios lógicos se va a ver en la siguiente sección el uso de otro servicio en donde si conviene realizar lo anterior descrito ya que se necesita en varias partes del proyecto.

_**Nota:** Como ya se realizó la automatización de los paneles de accion, es posible borrar las imágenes que se habían creado en la clase **InicioTemplate** y que contenía las imágenes de las acciones ya que no se estan usando mas, de esta forma el método **crearObjetosDecoradores()** queda asi:_

<figure><img src="https://camo.githubusercontent.com/513ffc92a906c77e6e8005e3240e09a076e4fdc6062af8ac18dca8798d30014c/68747470733a2f2f692e696d6775722e636f6d2f31793432416a362e706e67" alt=""><figcaption></figcaption></figure>

Método crearObjetosDecoradores sin las imágenes de acción

## Servicio lógicos que recibe información externa

Este tipo de servicios no contienen la información externa directamente, mas bien deben obtenerla desde algún sistema ajeno primero, estos pueden ser algún servidor externo, una base de datos, una Api publica etc. En este caso se va a manejar la información de los usuarios que ya están registrados en el sistema y estos serán los únicos que pueden entrar. Esta información esta contenida en el archivo plano **usuarios.txt**.

<figure><img src="https://camo.githubusercontent.com/98a29bbb616e184396645f71ee058442e93f6beeb13e1f0cc90a67710ddc89fe/68747470733a2f2f692e696d6775722e636f6d2f365572544a636f2e706e67" alt=""><figcaption></figcaption></figure>

Información contenida de los usuarios

La información incluye el **Nombre del usuario, clave del usuario, tipo usuario e imagen usuario**. Para aclarar normalmente las contraseñas se guardan en las bases de datos de forma encriptada, sin embargo, estos son temas del Backend que este curso no va a tocar, en este caso solo se simula un ejemplo de información externa.

Similarmente a la gestión de las acciones se va a crear un objeto en el modelo que represente el objeto de los usuarios:

<figure><img src="https://camo.githubusercontent.com/2ac0cbb0936dcf86d26aedbcd5767f101ccce5c8bcc79679b23524865f96a630/68747470733a2f2f692e696d6775722e636f6d2f4758304b4269322e706e67" alt=""><figcaption></figcaption></figure>

Creación de clase Usuario dentro del paquete Models

Dentro de la clase **Usuario** se declaran los atributos de un usuario que ya fueron descritos y ademas se crean sus respectivos métodos **set y get**.

```
public class Usuario {
  private String nombreUsuario;
  private String claveUsuario;
  private String tipoUsuario;
  private ImageIcon imagenUsuario;

  public String getNombreUsuario() { return nombreUsuario; }

  public String getClaveUsuario() { return claveUsuario; }

  public String getTipoUsuario() { return tipoUsuario; }

  public ImageIcon getImagenUsuario() { return imagenUsuario; }

  public void setNombreUsuario (String nombreUsuario){
    this.nombreUsuario = nombreUsuario;
  }

  public void setClaveUsuario (String claveUsuario){
    this.claveUsuario = claveUsuario;
  }
  
  public void setTipoUsuario (String tipoUsuario){
    this.tipoUsuario = tipoUsuario;
  }

  public void setImagenUsuario (ImageIcon imagenUsuario){
    this.imagenUsuario = imagenUsuario;
  }
}
```

Ahora se va a simular un controlador de información externa de forma local, (esto por motivos de ejemplo), normalmente la aplicación frontend se comunicara con Apis, servicios o bases de datos externas.

Se crea un nuevo paquete desde la carpeta raíz **src** la cual será llamada **logic** y dentro se crea una clase llamada **ControlUsuarios**, esta será la clase encargada de obtener, contener y gestionar la información.

<figure><img src="https://camo.githubusercontent.com/5d1425127d46a77a39811a290b02263dcb0fa877e49eb3bff3f8ca65a4ae049d/68747470733a2f2f692e696d6775722e636f6d2f34567a567672312e706e67" alt=""><figcaption></figcaption></figure>

Creación del paquete Logic y su controlador.

Como el controlador va a contener la información, esta va a obtenerse a través del archivo plano:

* Se declara una lista de Usuarios:

```
// En la clase ControlUsuarios
private ArrayList<Usuario> usuarios;
```

* Se ejemplifica el arreglo dinámico:

```
// Dentro del Constructor
usuarios = new ArrayList<Usuario>();
```

* Se crea el método para cargar la información del archivo plano:

```
public void cargarDatos() {
  File archivo = null;
  FileReader fr = null;
  BufferedReader br = null;
  try {
    archivo = new File ("Clase10/src/archives/usuarios.txt");
    fr = new FileReader (archivo);
    br = new BufferedReader(fr);

    String linea;
    while((linea=br.readLine())!=null) {
      String[] atributos = linea.split(",");
      Usuario usuario = new Usuario();
      usuario.setNombreUsuario(atributos[0]);
      usuario.setClaveUsuario(atributos[1]);
      usuario.setTipoUsuario(atributos[2]);
      usuario.setImagenUsuario(new ImageIcon(atributos[3]));
      usuarios.add(usuario);
    }
    fr.close(); 
  } catch(Exception e) {
    e.printStackTrace();
  }
}
```

* Se llama al método desde el constructor:

```
// Dentro del Constructor
cargarDatos();
```

* Se crea un método que recibe el nombre de un usuario y retorna un objeto de tipo Usuario en caso de que exista un usuario en la lista que coincida con el nombre:
* **Declaración del método**

```
public Usuario devolverUsuario(String nombreUsuario) {

}
```

* **Se crea un ciclo que recorra la lista:**

```
public Usuario devolverUsuario(String nombreUsuario) {
  for (Usuario usuario : usuarios) {
  
  }
}
```

_**Nota:** En el anterior ciclo se esta recorriendo cada posición del arrayList, pero en vez de usar un **Contador** que pase por cada posición de la lista, se esta usando directamente una variable objeto de tipo **Usuario** (creado en el modelo), que se va a convertir en el objeto que esta en la posición donde se esta revisando actualmente, este ciclo es normalmente conocido como **for each** o **for of**._

* **Se realiza la validación:**

```
public Usuario devolverUsuario(String nombreUsuario) {
  for (Usuario usuario : usuarios) {
    if (usuario.getNombreUsuario().equals(nombreUsuario))
      return usuario;
  }
  return null;
}
```

En este caso se pregunta si el objeto actual que se esta revisando en la lista tiene el nombre que coincide con el dato recibido como parámetro entonces retorne dicho objeto, de lo contrario retorne un dato nulo.

Ahora se crea el servicio **UsuarioService**

<figure><img src="https://camo.githubusercontent.com/dff4e7faf1bb43e70ff3326f79fa1c97856fdad5e7d132a6de18a16ca6c50251/68747470733a2f2f692e696d6775722e636f6d2f456b73453441652e706e67" alt=""><figcaption></figcaption></figure>

Creación del servicio UsuarioService

Se crea la estructura básica del servicio para ser obtenido:

* Declaración de la referencia estática a si mismo:

```
// Dentro del Servicio UsuarioService
private static UsuarioService servicio;
```

* Método estático para el control de una sola ejemplificación:

```
public static UsuarioService getService() {
  if(servicio == null)
    servicio = new UsuarioService();
  return servicio;
}
```

* El constructor se deja publico como ya se explico en la anterior sección.
* Este servicio va contener dos atributos que serán de vital importancia, un atributo será el objeto del controlador para que exista una comunicación hacia la entidad externa, el otro atributo es de tipo Usuario y se encargará de guardar en memoria que usuario ha iniciado sesión actualmente.
* **Declaración:**

```
// Dentro del Servicio UsuarioService
private ControlUsuarios cUsuario;
private Usuario usuarioConectado;
```

* **Ejemplificación**

```
// Dentro del Constructor
cUsuario = new ControlUsuarios();
```

### Validación de usuarios

Para realizar la validación se va a verificar cuatro cosas:

* Que todos los campos se hayan diligenciado.
* Que el nombre del usuario coincida con algún registro.
* Que la contraseña del usuario coincida con el nombre del usuario registrado.
* Que el tipo del usuario coincida con el nombre y clave del usuario registrado.

Para que una persona pueda ingresar a la aplicación debe proporcionar esos tres datos y estos deben estar guardados en el lugar de persistencia de datos (En este ejercicio el archivo plano), ademas de eso los 3 datos deben coincidir para un mismo usuario, de lo contrario no podrá entrar. Sin embargo esta gestión de verificación del usuario no la debe realizar la parte Frontend de un proyecto, normalmente esto lo realiza el Backend y el proyecto del cliente solo recibe la respuesta de la validación una vez enviá los datos que el usuario ha proporcionado.

Para simular esto, se va a realizar la respectiva validación dentro de la clase **ControlUsuarios** que recuerde, se supone es una clase externa del proyecto y solo se usa por motivos de simulación de una aplicación real.

Dentro de esta clase se va a crear el método **VerificarUsuario** el cual va a recibir por parámetros

* **String nombreUsuario**
* **String claveUsuario**
* **String tipoUsuario**

Y va a retornar un **Boolean** que indicará si la validación fue correcta o no.

```
public boolean verificarUsuario(String nombreUsuario, String claveUsuario, String tipoUsuario) {

}
```

Dentro de este método se va a recorrer el arreglo de usuarios llamado **usuarios** esto mediante el siguiente ciclo:

```
public boolean verificarUsuario(String nombreUsuario, String claveUsuario, String tipoUsuario) {
  for(Usuario usuario : usuarios) {
    
  }
}
```

Dentro de ese ciclo se realiza la respectiva validación:

```
public boolean verificarUsuario(String nombreUsuario, String claveUsuario, String tipoUsuario) {
  for(Usuario usuario : usuarios) {
    if(usuario.getNombreUsuario().equals(nombreUsuario))
      if(usuario.getClaveUsuario().equals(claveUsuario))
        if(usuario.getTipoUsuario().equals(tipoUsuario))
          return true;
  }
  return false;
}
```

En la anterior validación se indica que si en algún momento del recorrido del arreglo encuentra un objeto **Usuario** que cumple con la igualdad de los 3 datos dados por el usuario, se va a retornar un **True** indicando que se ha realizado la validación satisfactoriamente, en caso de no encontrar ningún objeto **Usuario** que cumpla con los requisitos, saldrá del ciclo y retornara un **False** indicando que el usuario no existe en el sistema.

Dentro de la clase del servicio **UsuarioService** (El cual ya es parte del proyecto) se crea un nuevo método llamado **verificarDatosUsuario** el cual recibirá de nuevo los tres datos que el usuario proporcionará y de igual forma retornará un **boolean**.

```
public boolean verificarDatosUsuario(
  String nombreUsuario, String claveUsuario, String tipoUsuario
) {

}
```

Dentro se realiza el llamado del método que validará los datos dentro del control y en caso de que la validación sea efectiva se realiza una acción de suma importancia.

```
public boolean verificarDatosUsuario(
  String nombreUsuario, String claveUsuario, String tipoUsuario
) {
  if (cUsuario.verificarUsuario(nombreUsuario, claveUsuario, tipoUsuario)) {
    this.usuarioConectado = cUsuario.devolverUsuario(nombreUsuario);
    return true;
  }
  return false;
}
```

Noten que dentro del **condicional** se ha llamado al método del Controlador encargado de la validación, en caso de que este retorne un **True** va a entrar dentro de las instrucciones dadas por el condicional, en este caso será que si el usuario efectivamente proporciono los datos de un usuario registrado va a realizar otra petición a la entidad externa pidiendo esta vez el objeto del usuario que coincida con el nombre proporcionado e igualandolo al atributo **usuarioConectado**. En caso de que la verificación haya retornado un **False** este método retornará un **False**.

Por ultimo y para que el atributo **usuarioConectado** tenga validez en el futuro se crea un método que retorne este atributo:

```
public Usuario getUsuarioConectado() {
  return this.usuarioConectado;
}
```

El Servicio esta listo para realizar la verificación ahora se debe configurar el componente **Login** para hacer uso de este servicio. Lo primero que se va a realizar es la obtención del servicio **UsuarioService** desde el componente, específicamente desde la clase **LoginComponent**.

* **Declaración:**

```
// Dentro de la clase LoginComponent
private UsuarioService sUsuario;
```

* **Obtención de Servicio:**

```
// Dentro del constructor
sUsuario = UsuarioService.getService();
```

_**Nota:** Es importante aclarar que la obtención del servicio debe hacerse antes de cargar la parte gráfica del componente ya que se van a pedir datos al servicio para ser mostrados en pantalla y si se muestra primero el componente antes de obtener el servicio esta información no existirá y saldrá un error._

Recordando, una vez el usuario oprime el botón de entrar dentro del Login el usuario podia ver un mensaje emergente que le indicaba los datos que había proporcionado y después entraba a la ventana principal.

<figure><img src="https://camo.githubusercontent.com/a58b727c1c53719b081361869fea62713a1c4767734ba3854825184f199a27b7/68747470733a2f2f692e696d6775722e636f6d2f3833746b6f64342e706e67" alt=""><figcaption></figcaption></figure>

Evento una vez se oprime el botón entrar del Login

Esta funcionalidad debe cambiar, ya no se van a mostrar esos datos, eso solo se hizo como una prueba para ver como se realizaba el recibimiento de información desde la parte gráfica. Para empezar se va a cambiar el nombre del método **mostrarDatosUsuario** por **enviarDatosUsuario**, y se va a quitar el llamado del método entrar, ya que ahora solo podrá entrar en el caso de que el usuario este registrado.

```
@Override
public void actionPerformed(ActionEvent e) {
  if (e.getSource() == loginTemplate.getBEntrar())
    this.enviarDatosUsuario();
  ...
```

```
public void enviarDatosUsuario() {
    ...
}
```

Dentro del método enviarDatosUsuario se va a dejar unicamente la obtención de los datos de los dos campos de texto y del combobox, el resto no será necesario.

```
public void enviarDatosUsuario() {
  String nombreUsuario = loginTemplate.getTNombreUsuario().getText();
  String claveUsuario = new String(loginTemplate.getTClaveUsuario().getPassword());
  String tipoUsuario = ((String) loginTemplate.getCbTipoUsuario().getSelectedItem());
}
```

Ahora se va a realizar una validación inicial donde se comprueba que el usuario haya proporcionado todos los datos, en caso contrario que muestre un mensaje de advertencia:

```
public void enviarDatosUsuario() {
  String nombreUsuario = loginTemplate.getTNombreUsuario().getText();
  String claveUsuario = new String(loginTemplate.getTClaveUsuario().getPassword());
  String tipoUsuario = ((String) loginTemplate.getCbTipoUsuario().getSelectedItem());
  if(!nombreUsuario.isBlank() && !claveUsuario.isBlank()) {
  
  } else
    JOptionPane.showMessageDialog(null, "No puede dejar un campo vacio", "Advertencia", 2);
}
```

Si el usuario proporcionó todos los datos, se van a enviar al servicio **UsuarioService** para realizar la respectiva validación, en caso de ser verificado satisfactoriamente mostrará un mensaje indicando el ingreso exitoso y entrará a la vista principal, en el caso contrario mostrará un mensaje indicando que algo ha salido mal.

```
public void enviarDatosUsuario() {
  String nombreUsuario = loginTemplate.getTNombreUsuario().getText();
  String claveUsuario = new String(loginTemplate.getTClaveUsuario().getPassword());
  String tipoUsuario = ((String) loginTemplate.getCbTipoUsuario().getSelectedItem());
  if(!nombreUsuario.isBlank() && !claveUsuario.isBlank()) {
    if (sUsuario.verificarDatosUsuario(nombreUsuario, claveUsuario, tipoUsuario)) {
      JOptionPane.showMessageDialog(null, "Ingreso Exitoso", "Advertencia", 1);
      entrar();
    } else
      JOptionPane.showMessageDialog(null, "Algo quedo mal", "Advertencia", 2);
  } else
    JOptionPane.showMessageDialog(null, "No puede dejar un campo vacio", "Advertencia", 2);
}
```

Una vez se ejecuta el programa es posible verificar su funcionamiento:

<figure><img src="https://camo.githubusercontent.com/509a6bbc8020af5ea62cb90315f6203e4cee3f2ab0d0e967a0a0dcd37efb3300/68747470733a2f2f692e696d6775722e636f6d2f6c63334c346b6f2e706e67" alt=""><figcaption></figcaption></figure>

Caso exitoso de ingreso de usuario

<figure><img src="https://camo.githubusercontent.com/d9a26e8ab9eeaece37cb701fb26f63488de2786c3fce8755a5a3d2316305cf25/68747470733a2f2f692e696d6775722e636f6d2f6b336b536c52692e706e67" alt=""><figcaption></figcaption></figure>

Caso fallido de ingreso de usuario

<figure><img src="https://camo.githubusercontent.com/3ac4440508ffeb5d334bcd567665948b4d3a3734d9c17030d201ab2b2894c5c3/68747470733a2f2f692e696d6775722e636f6d2f61464f52536a462e706e67" alt=""><figcaption></figcaption></figure>

Caso fallido de ingreso de usuario

Ahora se quiere que una vez el usuario haya entrado exitosamente, los datos de este como el nombre del usuario y la foto del perfil puedan observarse en la navegación del usuario, por el momento solo se esta utilizado una imagen y un texto de forma estática:

<figure><img src="https://camo.githubusercontent.com/ff6d37c5df71814dab136d77ccd99d6e7226da58a4a47e3e875c4c5cdf17c451/68747470733a2f2f692e696d6775722e636f6d2f676448354d647a2e706e67" alt=""><figcaption></figcaption></figure>

Información estática del usuario

Para cambiar esta información se debe llamar al servicio **UsuarioService** desde el componente **NavegaciónUsuario** para conseguir los datos del usuario que se ha conectado. De hecho toda la estructura tanto en el controlador como en el servicio esta lista para realizar esta acción.

En este caso se debe llamar al método **getUsuarioConectado** que retornará el objeto del usuario que actualmente ha iniciado sesión, recuerde que este atributo se estableció en el momento en que la verificación del usuario fue exitosa:

<figure><img src="https://camo.githubusercontent.com/c9ae7a0b46740af3a959194e661ba0663febfab8a8862ab930ceee0da6f5d37e/68747470733a2f2f692e696d6775722e636f6d2f503972503056562e706e67" alt=""><figcaption></figcaption></figure>

Momento en el que se le dio valor al atributo usuarioConectado

Mas adelante se realiza una reflexión de por que se realiza esta metodología, por ahora se va a hacer uso del servicio.

Dentro de la clase **NavegacionUsuarioComponent** vamos a realizar la obtención del servicio;

* **Declaración:**

```
// Dentro de la clase NavegacionUsuarioComponent
private UsuarioService sUsuario;
```

* **Obtención del servicio:**

```
// Dentro del Constructor
this.sUsuario = UsuarioService.getService();
```

_**Nota:** Es importante aclarar que la obtención del servicio debe hacerse antes de cargar la parte gráfica del componente ya que se van a pedir datos al servicio para ser mostrados en pantalla y si se muestra primero el componente antes de obtener el servicio esta información no existirá y saldrá un error._

Se crea un atributo que se llamara **usuarioConectado** y sera de tipo **Usuario**, una vez declarado, se usa el servicio **UsuarioService** para obtener el objeto del usuario conectado.

* **Declaración:**

```
// Dentro de la clase NavegacionUsuarioComponent
private Usuario usuarioConectado;
```

* **Obtención del objeto del usuario que ha ingresado:**

```
// Dentro del constructor
this.usuarioConectado = sUsuario.getUsuarioConectado();
```

Finalmente vamos a crear su método **get**, esto para que pueda ser obtenido por su clase gráfica **Template**:

```
public Usuario getUsuario(){
  return this.usuarioConectado;
}
```

Finalmente dentro de la clase **NavegacióUsuarioTemplate** se realizan unos pequeños cambios con los label que muestran la imagen y nombre del usuario:

<figure><img src="https://camo.githubusercontent.com/3b8af9410f063b3d8caa6a2728aaa01238742097e794966e94873959e075da9e/68747470733a2f2f692e696d6775722e636f6d2f62714a4b6b73512e706e67" alt=""><figcaption></figcaption></figure>

Cambios en los labels dentro del método crearJLabels de la clase NavegacionUsuarioTemplate

Noten que en el caso del Label **lNombreUsuario** Ahora se enviá como argumento en el texto al nombre del usuario que se obtiene a través de la clase **Component**. Lo mismo pasa con la imagen, cuando se va a redimensionar se llama a la imagen del objeto del usuario que se obtiene a través de la clase **Component**.

Se realizan algunas pruebas a ver que sucede:

<figure><img src="https://camo.githubusercontent.com/68ec70d2a059682ac1ce6ba3d56c935e5ba999217d780ca8a39d1d4f9a4b3898/68747470733a2f2f692e696d6775722e636f6d2f595379755148572e706e67" alt=""><figcaption></figcaption></figure>

Prueba 1 de ingreso de usuario

<figure><img src="https://camo.githubusercontent.com/c6095f726fe29c5f1bd7f247bb37eba8538c702119f119aec725fd14e57e35ea/68747470733a2f2f692e696d6775722e636f6d2f704d57786a36782e706e67" alt=""><figcaption></figcaption></figure>

Prueba 2 de ingreso de usuario

Esto funciona como se esperaba, sin embargo, las dos pruebas anteriores se realizaron por separado (en diferentes ejecuciones), en el caso en que desde una sola ejecución del programa un usuario ingrese, cierre sesión y después entre otro usuario, se van a ver los datos del anterior usuario. Esto es por que el programa requiere de una actualización no solo de este componente, también existen otras partes que requieren ser actualizadas y se mencionaran en la siguiente sección.

Por otro lado el uso del servicio **UsuarioService** cobra vital importancia ya que es un servicio que se esta utilizando en varias partes del proyecto, en este caso fue usado en el componente **login** y el componente **navegacionUsuario** y posiblemente se pueda usar en el componente **perfil** también. Note que ambos componentes usaron el servicio de forma independiente sin tener que estar comunicados entre ellos, en este caso el uso del atributo **usuarioConectado** fue crucial para realizar esta independencia, si no existiera este atributo no habría manera de que el componente **navegacionUsuario** sepa que usuario ha ingresado, la única forma de poder saberlo sin el uso del servicio es que el componente **login** le pase el dato del usuario que ingreso al componente **vistaPrincipal** y luego este ultimo se lo pase al componente **navegacionUsuario** y se formaría una dependencia entre componentes muy alta e innecesaria y solo en este caso pequeño, imagine con otras acciones cuanta dependencia mas habría. Es por eso que el uso de servicios se hace especialmente importante en estos casos, siempre hay que encontrar la manera de que estos servicios puedan proporcionar independencia del uso de la información a través de el y evitar el acoplamiento y envió de información entre componentes que no estar correlacionados.

## Ajustes del proyecto para el uso de servicios

Como se menciono en la anterior sección, hay partes del proyecto que requieren una actualización, a continuación se mencionan algunas de ellas:

* Cuando dos usuarios entran al sistema a través del login, es necesario actualizar los datos del componente **navegacionUsuario** para que se vean los datos del ultimo usuario que ingreso.
* Cuando un usuario cierra sesión y se ve nuevamente el Login, los campos de texto aun tienen los datos que escribió el usuario cuando ingreso, se debería ver justo como cuando se inicia la aplicación
* Cuando se ingresa por segunda vez en una misma ejecución a la vista principal, no se muestra el componente **inicio** y se ve vacía la parte del panel principal.

En esta sección se van a realizar estas respectivas actualizaciones. Dentro del componente **login**, se crea un método llamado **restaurarValores**, dentro de este se debe dejar todo como cuando el usuario ejecuta la aplicación.

Esto incluye:

* Dejar el **JTextField tNombreUsuario** con el placeholder **Nombre Usuario** y el **JPasswordField tClaveUsuario** con el placeholder **Calve Usuario**.
* Dejar el **JTextField tNombreUsuario y el JPasswordField** con el borde gris de nuevo.
* Dejar el **JTextField tNombreUsuario y el JPasswordField** con el color de letra gris de nuevo.
* Dejar el **ComboBox cmbTipoUsuario** con la primera selección de nuevo.

```
public void restaurarValores(){
  this.getLoginTemplate().getTNombreUsuario().setText("Nombre Usuario");
  this.getLoginTemplate().getTNombreUsuario().setBorder(
      this.getLoginTemplate().getRecursosService().getBorderInferiorGris()
  );
  this.getLoginTemplate().getTNombreUsuario().setForeground(
      this.getLoginTemplate().getRecursosService().getColorGrisOscuro()
  );
  this.getLoginTemplate().getTClaveUsuario().setText("Clave Usuario");
  this.getLoginTemplate().getTClaveUsuario().setBorder(
      this.getLoginTemplate().getRecursosService().getBorderInferiorGris()
  );
  this.getLoginTemplate().getTClaveUsuario().setForeground(
      this.getLoginTemplate().getRecursosService().getColorGrisOscuro()
  );
  this.getLoginTemplate().getCbTipoUsuario().setSelectedIndex(0);
}
```

Ahora cuando se cierre sesión dentro de la **ventana principal** específicamente en la clase **VistaPrincipalComponent** en su método **mostrarComponentes** se va a llamar a este método:

<figure><img src="https://camo.githubusercontent.com/0e280bfac0ed8a52cc44de79c4cac12deb1bb39c1b08b997b8d5b23d8d0d5823/68747470733a2f2f692e696d6775722e636f6d2f304d36415478482e706e67" alt=""><figcaption></figcaption></figure>

Llamada del método restaurar valores del componente Login

Dentro del componente **VistaPrincipal**, en este caso se quiere que cada vez que se inicie sesión siempre se vea el componente **Inicio** dentro de la ventana principal. De la misma manera, se crea un método llamado **restaurarValores** dentro de la clase **VistaPrincipalComponent**:

```
public void restaurarValores(){
}
```

En este caso solo se llamará al panel **pPrincipal** y se le indica que incorpore el componente **Inicio** esto a través del objeto de su clase compañera **VistaPrincipalTemplate**:

```
public void restaurarValores(){
  this.vistaPrincipalTemplate.getPPrincipal().add(inicioComponent.getInicioTemplate());
}
```

Ahora se debe llamar desde el **login** cada vez que se quiera ingresar:

<figure><img src="https://camo.githubusercontent.com/961861e77ede670c968e1e7494ef1c700cb75ebaf0b49112d1bd2e8b337ad733/68747470733a2f2f692e696d6775722e636f6d2f656d4d7874556a2e706e67" alt=""><figcaption></figcaption></figure>

llamada del método restaurarValores de la vistaPrincipal

Solo nos queda actualizar el componente **NavegaciónUsuario**, dentro de la clase **NavegaciónUsuarioComponent** se va a crear el método **ActualizarValores**:

```
public void actualizarValores (){
}
```

* Lo primero que se debe hacer es actualizar el usuario que ha ingresado actualmente, para esto se llama al servicio **UsuarioService** nuevamente:

```
public void actualizarValores (){
  this.usuarioConectado = sUsuario.getUsuarioConectado();
}
```

* Es necesario remover todo lo que este en el panel **pSuperior** ya que va a mostrar información nueva:

```
public void actualizarValores (){
  this.usuarioConectado = sUsuario.getUsuarioConectado();
  this.navegacionUsuarioTemplate.getPSuperior().removeAll();
}
```

* Una vez se ha retirado todo del panel se llama al método **crearJLabels** el cual tomaba los datos del objeto **Usuario** que acaba de actualizarse:

```
public void actualizarValores (){
  this.usuarioConectado = sUsuario.getUsuarioConectado();
  this.navegacionUsuarioTemplate.getPSuperior().removeAll();
  this.navegacionUsuarioTemplate.crearJLabels();
}
```

* Finalmente y para asegurarse de que el cambio se verá reflejado, se llama al método **repaint** para que realice la actualización de la ventana.

```
public void actualizarValores (){
  this.usuarioConectado = sUsuario.getUsuarioConectado();
  this.navegacionUsuarioTemplate.getPSuperior().removeAll();
  this.navegacionUsuarioTemplate.crearJLabels();
  this.navegacionUsuarioTemplate.repaint();
}
```

Ya esta lista la actualización, solo falta que sea llamado este método, es posible aprovechar el método **restaurarValores** de la vista principal para que de una vez realice la actualización del componente **navegacionUsuario**.

<figure><img src="https://camo.githubusercontent.com/4cee09fa59c334360319ad52496b496e0408ec5f33f3e33c1dabeae640ae7297/68747470733a2f2f692e696d6775722e636f6d2f5052323252324d2e706e67" alt=""><figcaption></figcaption></figure>

Llamada del método Actualizar Datos del componente NavegacionUsuario

Ya se realizaron los ajustes necesarios y el programa funciona correctamente. Ahora es posible ingresar varias veces a la ventana principal desde una sola ejecución y con varios usuario y siempre mostrara la información del usuario que acaba de ingresar, también se puede notar que en la vista principal siempre estará incorporado el componente **inicio**. Por otro lado, una vez se cierra sesión el Login de usuario se verá con los valores iniciales.

## Resultado

Si has llegado hasta aquí **!Felicidades!** se ha aprendido como crear, cuando utilizar y como funcionan los **Servicios** dentro de la arquitectura. Se aprendió como gestionar un flujo de información externa de forma en que cada componente sea independiente en cuanto a obtener o enviar información a través del uso de servicios. Se aprendió ademas, las características principales de los **Servicios**. En la proxima clase se sigue usando servicios para revisar un objeto Gráfico particular, estos son las **JTables**.

## Actividad

Implementar el uso de **Servicios Lógicos** en los proyectos para la gestión de la información externa.

Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 11

### Objetivos

* Examinar las características principales del objeto gráfico JTable ademas de su creación y gestión dentro de las interfaces gráficas.
* Reconocer el propósito del uso de tablas dentro de las interfaces y como manejar la información a través de estas.
* Identificar las acciónes principales de gestión de información en una tabla tal como insertar, modificar, filtrar y eliminar información.
* Personalizar la tabla con estilos para que esta pueda tener un aspecto conforme con el resto de la interfaz gráfica.

## Antes de Comenzar

#### **Ajustes en el proyecto**

***

Dentro del paquete **archives** se agrega otro archivo plano llamado **amigos.txt** que contendrá información general de los contactos a gestionar. Este archivo plano se puede encontrar en este mismo repositorio entrando a la carpeta **Clase11** seguido de la carpeta **src** y luego en la carpeta **archives**.

<figure><img src="https://camo.githubusercontent.com/6fb9df473ab2b23bf2bb37f54b7a12ee8bea2167bac0a5fb946f1750d8f6e732/68747470733a2f2f692e696d6775722e636f6d2f7151787a6139422e706e67" alt=""><figcaption></figcaption></figure>

Se inserta archivo plano dentro del paquete archives.

#### **Ajustes en el servicio Recursos Service**

***

Se crea un borde lineal de color azul en el servicio **RecursosService**.

* **Declaración:**

```
private Border bAzul;
```

* **Ejemplificación**

```
// Dentro del método crear Bordes
bAzul = BorderFactory.createLineBorder(colorPrincipal, 2, true);
```

* **Método get**

```
public Border getBAzul() { return bAzul; }
```

#### **Recordatorio**

***

Recordando un poco el recorrido, se han utilizado los servicios para gestionar varias cosas dentro del proyecto, una de estas fue la generación automática de la reutilización del componente **Accion** a traves de la obtención de la información externa. Por otra parte ahora se gestiona **el ingreso de la aplicación** a traves de algunos usuarios que han sido registrados y están contenidos de forma persistente (archivo plano) y gracias a los servicios no solo es posible controlar el ingreso único de estos usuarios sino que ademas se puede gestionar la información de estos a traves de varias partes del proyecto de forma independiente.

## Creación y gestión de tablas

En esta sesión se va a ver la creación y gestión del objeto gráfico avanzado **JTable** el cual es muy util para manejar y mostrar información de forma ordenada, para dar un recorrido completo al uso de este objeto se verán ciertos items como:

* Creación de servicios y preparativos para el uso de JTable.
* Creación de JTable y sus partes.
* Gestión de información dentro de un JTable.
* Personalización del JTable.

## Creación de servicios y preparativos para el uso de JTable.

En esta lección vamos a construir el componente gráficos **Amigos** con el cual un usuario podrá gestionar información de sus contactos, para esto vamos a necesitar traer información externa la cual contiene los datos de cada uno de los contactos. Vamos a ver la estructura del archivo plano.

<figure><img src="https://camo.githubusercontent.com/8aeec69610d455ed9b5c30680150c09ae9bbfdc49938ae4ee8cf99228a0d937e/68747470733a2f2f692e696d6775722e636f6d2f63796f6a3138492e706e67" alt=""><figcaption></figcaption></figure>

Archivo plano con información de los contactos

Podemos ver que los datos de un contacto (Amigo) son:

* **Id**.
* **Nombre:**.
* **Edad**.
* **Oficio**.
* **Numero Telefónico**.
* **Email**.

### Preparación de Servicio y clases para gestionar la información externa

Igual que en la sesión anterior, vamos a crear una clase que representará en objetos la información de un amigo, esta clase la creamos dentro del paquete **models**.

<figure><img src="https://camo.githubusercontent.com/848f6fef57325dc364ec4090f9c8d01608e5d530947592c1df297318eab57454/68747470733a2f2f692e696d6775722e636f6d2f464561677a73712e706e67" alt=""><figcaption></figcaption></figure>

Creación de la clase amigo.

Vamos a crear los atributos necesarios para representar esta información y sus respectivos métodos **set y get**.

```
public class Amigo {
    private int id;
    private String nombre, edad, oficio, telefono, email;

    public int getId(){
        return id;
    }

    public String getNombre(){
        return nombre;
    }

    public String getEdad(){
        return edad;
    }

    public String getOficio(){
        return oficio;
    }

    public String getTelefono(){
        return telefono;
    }

    public String getEmail(){
        return email;
    }

    public void setId(int id){
        this.id = id;
    }

    public void setNombre(String nombre){
        this.nombre = nombre;
    }

    public void setEdad(String edad){
        this.edad = edad;
    }

    public void setOficio(String oficio){
        this.oficio = oficio;
    }

    public void setTelefono(String telefono){
        this.telefono = telefono;
    }

    public void setEmail(String email){
        this.email = email;
    }
}
```

Como suponemos que esta información la vamos a recibir desde una fuente foránea vamos a crear un controlador externo que se encarga de gestionar esta información y con la cual la aplicación va a interactuar.

<figure><img src="https://camo.githubusercontent.com/b31102dee8cc30237fd65ce93023309ff2051ceca7d16e0f22ee08c618ca5ed0/68747470733a2f2f692e696d6775722e636f6d2f74794d6d7074362e706e67" alt=""><figcaption></figcaption></figure>

Creación de clase ControlAmigos en el paquete logic

Igual que en la sesión anterior como esta clase sera la que gestiona la información, va a contener un atributo en forma de arreglo que contenga los objetos de los amigos:

* **Declaración:**

```
private ArrayList<Amigo> amigos;
```

* **Ejemplificación:**

```
public ControlAmigos(){
    amigos = new ArrayList<Amigo>();
}
```

Vamos a escribir el método que se encarga de recibir la información externa desde el archivo plano y lo vamos a llamar desde el constructor:

```
public void cargarDatos(){
    File archivo = null;
    FileReader fr = null;
    BufferedReader br = null;
    try {
        archivo = new File ("Clase11/src/archives/amigos.txt");
        fr = new FileReader(archivo);
        br = new BufferedReader(fr);
        String linea;
        while((linea=br.readLine())!=null){
            String[] atributos = linea.split(",");
            Amigo amigo = new Amigo();
            amigo.setId(Integer.parseInt(atributos[0]));
            amigo.setNombre(atributos[1]);
            amigo.setEdad(atributos[2]);
            amigo.setOficio(atributos[3]);
            amigo.setTelefono(atributos[4]);
            amigo.setEmail(atributos[5]);
            amigos.add(amigo);
        }
        fr.close(); 
    }
    catch(Exception e){
        e.printStackTrace();
    }
}
```

```
// Dentro del Costructor
cargarDatos();
```

Finalmente vamos a crear un método con el cual se devolverá todo el arreglo, en este caso a diferencia del ejemplo de la lección pasada el controlador solo devolverá la información que obtuvo en forma del arreglo y en el servicio vamos a manipular este arreglo:

```
public ArrayList<Amigo> getAmigos(){
    return amigos;
}
```

Es hora de crear el servicio este sera el servicio **AmigoService** y estará dentro del paquéte **ServicesLogic**:

<figure><img src="https://camo.githubusercontent.com/9b15c041afd2f85b3bf7de502794c1e63f3922672a7dd7943b106ee744e91117/68747470733a2f2f692e696d6775722e636f6d2f5756527a7a32722e706e67" alt=""><figcaption></figcaption></figure>

Creación del servicio dentro del paquete ServicesLogic

Como ya vimos a lo largo del curso vamos a crear el mecanismo para una ejemplificación única del servicio dejando el constructor publica para dar posibilidad a la creación de mas ejemplificaciones en caso de ser necesario:

* **Declaración referencia estática de si mismo:**

```
private static AmigoService servicio;
```

* **Método estático para ejemplificación única:**

```
public static AmigoService getService(){
    if(servicio == null)
        servicio = new AmigoService();
    return servicio;
}
```

En este servicio vamos a realizar la manipulación de la información externa, por lo que vamos a crear un objeto que referencia al control externo y ademas un objeto contenedor del arreglo de amigos que sera igual al que reciba desde el controlador:

* **Declaración:**

```
private ControlAmigos cAmigos;
private ArrayList<Amigo> amigos;
```

* **Ejemplificación:**

```
public AmigoService(){
    cAmigos = new ControlAmigos();
    amigos = cAmigos.getAmigos();
}
```

Se puede notar que dentro del constructor estamos llamando al método **getAmigos** que nos devolverá el arreglo y lo igualamos al arreglo antes declarado.

Como vamos a manipular la información de los amigos desde este servicio vamos a crear 3 métodos que nos serán útiles, entre sus funcionalidades queremos:

* **Obtener un objeto de un Amigo a traves de su posición en el arreglo:**

```
public Amigo devolverAmigo(int posicion){
    try{
        return amigos.get(posicion);
    }
    catch(Exception e){
        return null;
    }
}
```

* **Agregar un nuevo Amigo al arreglo de objetos:**

```
public void agregarAmigo(Amigo amigo){
    this.amigos.add(amigo);
}
```

* **Devolver la cantidad de amigos que hay en el arreglo:**

```
public int devolverCantidadAmigos(){
    return amigos.size();
}
```

_**Nota:** Debido a que solo nos estamos concentrando en la parte Frontend del proyecto no vamos a gestionar la información más allá de propósitos de la clase, por lo que la información nueva que creemos no se guardara de forma persistente._

### Preparación del Componente Gráfico Amigos

Ya tenemos lista toda la parte del manejo de la información externa dentro del proyecto ahora vamos a construir el componente Gráfico **Amigos** y asi tener todo listo para el manejo de **JTable** dentro de el. Lo primero que vamos a realizar es la configuración necesaria dentro de la clase **AmigosComponent**, dentro de este componente vamos a gestionar algunos eventos por lo que vamos a implementar las interfaces que necesitemos:

```
public class AmigosComponent implements ActionListener, MouseListener, FocusListener {
    . . .
    . . .
}
```

Se puede notar que el componente va a implementar 3 interfaces, **ActionListener**, **MouseListener** y **FocusListener**. Hasta el momento hemos revisado las dos primeras interfaces, la tercera la estamos usando por primera vez. Esta interfaz va a escuchar eventos cada vez que un elemento que escuche a este tipo de eventos sea seleccionado, cuando implementemos este tipo de eventos se hará una mayor explicación, por ahora vamos a implementar todos los métodos correspondientes a cada interfaz:

```
// MÉTODO IMPLEMENTADO DE ACTIONLISTENER
@Override
public void actionPerformed(ActionEvent e) {}

// MÉTODOS IMPLEMENTADO DE FOCUSLISTENER
@Override
public void focusGained(FocusEvent e) {}

@Override
public void focusLost(FocusEvent e) {}

// MÉTODOS IMPLEMENTADO DE MOUSELISTENER
@Override
public void mouseClicked(MouseEvent e) {}

@Override
public void mousePressed(MouseEvent e) {}

@Override
public void mouseReleased(MouseEvent e) {}

@Override
public void mouseEntered(MouseEvent e) {}

@Override
public void mouseExited(MouseEvent e) {}
```

Vamos a realizar el llamado al servicio **AmigoService** para poder traer la información externa más adelante:

* **Declaración**:

```
private AmigoService sAmigos;
```

* **Ejemplificación**:

```
public AmigosComponent() {
    sAmigos = AmigoService.getService();
    ...
}
```

Ademas de esto vamos a declarar dos atributos que nos serán útiles para algunas cosas que realizaremos mas adelante, el primero sera un objeto de tipo **Amigo**(Modelo) el segundo sera un arreglo de Strings que contiene todos los _placeholders_ de los JTextFields:

```
private Amigo amigo;
private String[] placeholdes = {"Nombre","Edad","Oficio","Telefono","Email","Filtrar..."};
```

Ahora vamos a concentrarnos en la clase **AmigosTemplate**, primero realizaremos la llamada de los serviciós gráficos necesarios:

* **Declaración:**

```
private ObjGraficosService sObjGraficos;
private RecursosService sRecursos;
```

* **Obtención de servicios:**

```
// Dentro del constructor
this.sObjGraficos = ObjGraficosService.getService();
this.sRecursos = RecursosService.getService();
```

Vamos a quitar el background de prueba que tenia el componente y vamos a cambiarlo por el color gris claro que llamaremos desde el servicio **recursosService**:

```
// Dentro del constructor
this.setBackground(sRecursos.getColorGrisClaro());
```

Vamos a crear ademas un objeto decorador que sera un color gris con una tonalidad un poco mas oscura, lo vamos a crear dentro del componente gráfico ya que solo se usara por el momento aquí y realizaremos su ejemplificación dentro del constructor ya que solo crearemos un objeto decorador.

* **Declaración:**

```
private Color colorGris;
```

* **Ejemplificación:**

```
// Dentro del constructor
this.colorGris = new Color(235,235,235);
```

Vamos a empezar a crear los objetos gráficos necesarios. Para empezar vamos a necesitar 2 paneles:

* **pOpciones**: El cual contendrá varias opciones que el usuario tendrá disponible para manipular la información de la tabla.
* **pDatos**: El cual contendrá información de cada contacto y que también podrá editar el usuario.
* **Declaración:**

```
private JPanel pOpciones, pDatos;
```

* **Método encargado de la creación:**

```
public void crearJPanels(){
    pOpciones = sObjGraficos.construirJPanel(10, 10, 580, 200, Color.WHITE, null);
    this.add(pOpciones);

    pDatos = sObjGraficos.construirJPanel(600, 10, 240, 580, Color.WHITE, null);
    this.add(pDatos);
}
```

* **Llamada del método en el constructor:**

```
// Dentro del constructor
this.crearJPanels();
```

La aplicación se vera algo asi:

<figure><img src="https://camo.githubusercontent.com/44de6dc4bf591efda6753ad1e6c9f020199e462d2765d24979cae5381c2defcc/68747470733a2f2f692e696d6775722e636f6d2f4a526f764a66392e706e67" alt=""><figcaption></figcaption></figure>

Maquetación de los paneles dentro del componente Amigos

Vamos a crear el contenido del panel **pOpciones**, este va a estar conformado por una serie de botones y un JTextField, los botones serán el medio para que el usuario interactué con la tabla mientras que el JTextField sera un espacio para que el usuario pueda filtrar y buscar información dentro de la tabla.

* **Declaración Objetos Gráficos:**

```
private JButton bMostrar, bInsertar, bFiltrar, bModificar, bEliminar;
private JTextField tConsulta;
```

* **Método encargado de crear el contenido del panel pOpciones**:

```
public void crearContenidoPOpciones(){
    // LABEL TITULO--------------------------------------------------------------------
    lTitulo = sObjGraficos.construirJLabel(
        "Edición de Contactos", 20, 10, 200, 30, null, sRecursos.getColorGrisOscuro(), 
        null, sRecursos.getFontTitulo(), "c"
    );
    pOpciones.add(lTitulo);

    // TEXTFIELD CONSULTA--------------------------------------------------------------------
    tConsulta = sObjGraficos.construirJTextField(
        "Filtrar...", 30, 60, 380, 40, colorGris , sRecursos.getColorGrisOscuro(), 
        sRecursos.getColorGrisOscuro(), sRecursos.getFontBotones(), null, "c"
    );
    tConsulta.addFocusListener(amigosComponent);
    pOpciones.add(tConsulta);

    // BOTÓN FILTRAR--------------------------------------------------------------------
    bFiltrar = sObjGraficos.construirJButton(
        "Filtrar", 430, 65, 120, 35, sRecursos.getCMano(), null, sRecursos.getFontBotones(), 
        sRecursos.getColorPrincipal(), Color.WHITE, null, "c", true
    );
    bFiltrar.addMouseListener(amigosComponent);
    bFiltrar.addActionListener(amigosComponent);
    pOpciones.add(bFiltrar);

    // BOTÓN MOSTRAR--------------------------------------------------------------------
    bMostrar = sObjGraficos.construirJButton(
        "Mostrar", 20, 145, 120, 35, sRecursos.getCMano(), null, sRecursos.getFontBotones(), 
        sRecursos.getColorPrincipal(), Color.WHITE, null, "c", true
    );
    bMostrar.addMouseListener(amigosComponent);
    bMostrar.addActionListener(amigosComponent);
    pOpciones.add(bMostrar);

    // BOTÓN INSERTAR--------------------------------------------------------------------
    bInsertar = sObjGraficos.construirJButton(
        "Insertar", 160, 145, 120, 35, sRecursos.getCMano(), null, sRecursos.getFontBotones(), 
        sRecursos.getColorPrincipal(), Color.WHITE, null, "c", true
    );
    bInsertar.addMouseListener(amigosComponent);
    bInsertar.addActionListener(amigosComponent);
    pOpciones.add(bInsertar);

    // BOTÓN MODIFICAR--------------------------------------------------------------------
    bModificar = sObjGraficos.construirJButton(
        "Modificar", 300, 145, 120, 35, sRecursos.getCMano(), null, sRecursos.getFontBotones(), 
        sRecursos.getColorPrincipal(), Color.WHITE, null, "c", true
    );
    bModificar.addMouseListener(amigosComponent);
    bModificar.addActionListener(amigosComponent);
    pOpciones.add(bModificar);

    // BOTÓN ELIMINAR--------------------------------------------------------------------
    bEliminar= sObjGraficos.construirJButton(
        "Eliminar", 440, 145, 120, 35, sRecursos.getCMano(), null, sRecursos.getFontBotones(), 
        sRecursos.getColorPrincipal(), Color.WHITE, null, "c", true
    );
    bEliminar.addMouseListener(amigosComponent);
    bEliminar.addActionListener(amigosComponent);
    pOpciones.add(bEliminar);
}
```

Se puede observar que dentro de la construcción de cada botón estamos añadiendo de una vez la propiedad de escucha a los eventos de acción **ActionListener** y los eventos del mouse **MouseListener**. La primera interfaz se usara para ejecutar las acciónes de manipulación de la información mientras que la segunda sera para roles mas estéticos. Por otro lado el JTextField adiciona la escucha a los eventos **FocusListener**.

* **Llamada del método en el constructor:**

```
this.crearContenidoPOpciones();
```

La interfaz se vera algo así:

<figure><img src="https://camo.githubusercontent.com/f3a7a7994e68cde6eb2fb237ff8212ab98752724b2250bd95de01ca195c76465/68747470733a2f2f692e696d6775722e636f6d2f426876325556342e706e67" alt=""><figcaption></figcaption></figure>

Contenido integrado del panel pOpciones

Ahora vamos a crear el contenido del panel **pDatos**, en este habrá una serie de JLabes y JTextField donde el usuario podrá editar la información de algún amigo:

* **Declaración:**

```
private JLabel lTitulo, lInstrucciones, lEslogan;
private JLabel lId, lIdValor, lNombre, lEdad, lOficio, lTelefono, lEmail;
private JTextField tNombre, tEdad, tOficio, tTelefono, tEmail;
```

* **Método encargado de crear el contenido del panel pDatos:**

```
public void crearContenidoPDatos(){
    // LABEL INSTRUCCIONES ----------------------------------------------------------------
    lInstrucciones = sObjGraficos.construirJLabel(
        "<html>Datos de los contactos<html>", 20, 10, 120, 50, null, 
        sRecursos.getColorGrisOscuro(), null, sRecursos.getFontTitulo(), "l"
    );
    pDatos.add(lInstrucciones);

    // LABEL ESLOGAN ----------------------------------------------------------------
    lEslogan = sObjGraficos.construirJLabel(
        "<html>A continuación puede ver y editar la información del Contacto<html>", 
        20, 50, 180, 90, null, sRecursos.getColorGrisOscuro(), null, sRecursos.getFontPequeña(), "l"
    );
    pDatos.add(lEslogan);

    // LABEL ID ----------------------------------------------------------------
    lId = sObjGraficos.construirJLabel(
        "Id Contacto:", 20, 140, 160, 30, null, 
        sRecursos.getColorPrincipalOscuro(), null, sRecursos.getFontPequeña(), "l"
    );
    pDatos.add(lId);

    // LABEL ID CONTENIDO ----------------------------------------------------------
    lIdValor = sObjGraficos.construirJLabel(
        "0", 120, 140, 160, 30, null, sRecursos.getColorPrincipalOscuro(), 
        null, sRecursos.getFontPequeña(), "l"
    );
    pDatos.add(lIdValor);

    // LABEL NOMBRE ----------------------------------------------------------------
    lNombre = sObjGraficos.construirJLabel(
        "Nombre Contacto:", 20, 180, 160, 30, null, 
        sRecursos.getColorPrincipalOscuro(), null, sRecursos.getFontPequeña(), "l"
    );
    pDatos.add(lNombre);

    // TEXTFIELD NOMBRE ----------------------------------------------------------------
    tNombre = sObjGraficos.construirJTextField(
        "Nombre", 30, 215, 180, 30, colorGris, sRecursos.getColorGrisOscuro(),
        sRecursos.getColorGrisOscuro(), sRecursos.getFontPequeña(), null, "c"
    );
    tNombre.addFocusListener(amigosComponent);
    pDatos.add(tNombre);

    // LABEL EDAD ----------------------------------------------------------------
    lEdad = sObjGraficos.construirJLabel(
        "Edad Contacto:", 20, 265, 160, 30, null, 
        sRecursos.getColorPrincipalOscuro(), null, sRecursos.getFontPequeña(), "l"
    );
    pDatos.add(lEdad);

    // TEXTFIELD NOMBRE ----------------------------------------------------------------
    tEdad = sObjGraficos.construirJTextField(
        "Edad", 30, 300, 180, 30, colorGris, sRecursos.getColorGrisOscuro(),
        sRecursos.getColorGrisOscuro(), sRecursos.getFontPequeña(), null, "c"
    );
    tEdad.addFocusListener(amigosComponent);
    pDatos.add(tEdad);
    
    // LABEL OFICIO ----------------------------------------------------------------
    lOficio = sObjGraficos.construirJLabel(
        "Oficio Contacto:", 20, 350, 160, 30, null, 
        sRecursos.getColorPrincipalOscuro(), null, sRecursos.getFontPequeña(), "l"
    );
    pDatos.add(lOficio);

    // TEXTFIELD OFICIO ----------------------------------------------------------------
    tOficio = sObjGraficos.construirJTextField(
        "Oficio", 30, 385, 180, 30, colorGris, sRecursos.getColorGrisOscuro(),
        sRecursos.getColorGrisOscuro(), sRecursos.getFontPequeña(), null, "c"
    );
    tOficio.addFocusListener(amigosComponent);
    pDatos.add(tOficio);
    
    // LABEL TELEFONO ----------------------------------------------------------------
    lTelefono = sObjGraficos.construirJLabel(
        "Telefono Contacto:", 20, 425, 160, 30, null, 
        sRecursos.getColorPrincipalOscuro(), null, sRecursos.getFontPequeña(), "l"
    );
    pDatos.add(lTelefono);

    // TEXTFIELD TELEFONO ----------------------------------------------------------------
    tTelefono = sObjGraficos.construirJTextField(
        "Telefono", 30, 460, 180, 30, colorGris, sRecursos.getColorGrisOscuro(),
        sRecursos.getColorGrisOscuro(), sRecursos.getFontPequeña(), null, "c"
    );
    tTelefono.addFocusListener(amigosComponent);
    pDatos.add(tTelefono);

    // LABEL EMAIL ----------------------------------------------------------------
    lEmail = sObjGraficos.construirJLabel(
        "Email Contacto:", 20, 510, 160, 30, null, 
        sRecursos.getColorPrincipalOscuro(), null, sRecursos.getFontPequeña(), "l"
    );
    pDatos.add(lEmail);

    // TEXTFIELD EMAIL ----------------------------------------------------------------
    tEmail = sObjGraficos.construirJTextField(
        "Email", 30, 545, 180, 30, colorGris, sRecursos.getColorGrisOscuro(),
        sRecursos.getColorGrisOscuro(), sRecursos.getFontPequeña(), null, "c"
    );
    tEmail.addFocusListener(amigosComponent);
    pDatos.add(tEmail);
}
```

Podemos notar que los JTextFields adicionan la escucha a los eventos **FocusListener**.

* **Llamada del método dentro del constructor:**

```
// Dentro del Constructor
this.crearContenidoPDatos();
```

La aplicación se ve de la siguiente manera:

<figure><img src="https://camo.githubusercontent.com/c949aa4f21bf3065207448801e50f4188a2a7a9064ab8904aed3acaaa090acf7/68747470733a2f2f692e696d6775722e636f6d2f47616f6b4263772e706e67" alt=""><figcaption></figcaption></figure>

Incorporación de contenido del panel pDatos.

ahora vamos a crear los métodos **get** de los objetos gráficos que necesitaremos en la clase **AmigosComponent**:

```
public JButton getBMostrar(){
    return bMostrar;
}

public JButton getBInsertar(){
    return bInsertar;
}

public JButton getBModificar(){
    return bModificar;
}

public JButton getBEliminar(){
    return bEliminar;
}

public JButton getBFiltrar(){
    return bFiltrar;
}

public JLabel getLIdValor(){
    return lIdValor;
}

public JTextField getTNombre(){
    return tNombre;
}

public JTextField getTEdad(){
    return tEdad;
}

public JTextField getTOficio(){
    return tOficio;
}

public JTextField getTTelefono(){
    return tTelefono;
}

public JTextField getTEmail(){
    return tEmail;
}

public JTextField getTConsulta(){
    return tConsulta;
}
```

Ya esta casi todo listo, falta configurar los eventos, los eventos de **acción** los revisaremos en la siguiente sección, vamos a utilizar los eventos del **Mouse** y de tipo **Enfoque**(Focus) para darle algo de interactividad al componente, nos ubicamos en la clase **AmigosComponent**.

#### **Eventos MouseListener**

Para el caso de los botones vamos a configurar un cambio de color una vez se pase encima de ellos como hemos revisado en anteriores sesiones:

```
 @Override
public void mouseEntered(MouseEvent e) {
    if(e.getSource() instanceof JButton){
        JButton boton = ((JButton) e.getSource());
        boton.setBackground(RecursosService.getService().getColorPrincipalOscuro());
    }
}

@Override
public void mouseExited(MouseEvent e) {
    if(e.getSource() instanceof JButton){
        JButton boton = ((JButton) e.getSource());
        boton.setBackground(RecursosService.getService().getColorPrincipal());
    }
}
```

En el anterior código realizamos una **Ejemplificación única de objetos de una misma clase** y ademas una **Discriminación por clases**. Esta ultima parece no ser necesaría ya que solo estamos configurando a un tipo de clase (botones), sin embargo lo realizamos por un motivo que explicaremos una vez tengamos la tabla.

#### **Eventos FocusListener**

Ahora vamos a configurar los métodos relacionados con la interfaz **FocusListener**.

El método **focusGained** realiza una acción cada vez que un elemento esta seleccionado y se esta enfocando en el, en este caso los JTextfield son los que están escuchando este tipo de eventos, queremos que cuando se seleccione cualquiera de estos, cambie a tener un borde azul y en caso de contener el placeholder, este se retire. Para obtener el borde azul vamos a hacer uso del servicio **RecursosService** y para verificar si alguno de estos JTextfield contiene su placeholder correspondiente vamos a ayudarnos del atributo **placegolders** que contiene todos estos:

```
@Override
public void focusGained(FocusEvent e) {
    JTextField textField = ((JTextField) e.getSource());
    textField.setBorder(RecursosService.getService().getBorderAzul());
    if(
        textField.getText().equals(placeholdes[0]) || textField.getText().equals(placeholdes[1]) ||
        textField.getText().equals(placeholdes[2]) || textField.getText().equals(placeholdes[3]) ||
        textField.getText().equals(placeholdes[4]) || textField.getText().equals(placeholdes[5]) 
    )
        textField.setText("");
}
```

El Método **focusLost** realiza una acción una vez el objeto deja de estar seleccionado y pierde el enfoque, en este caso simplemente queremos que vuelva a estar sin ningún borde:

```
@Override
public void focusLost(FocusEvent e) {
    JTextField textField = ((JTextField) e.getSource());
    textField.setBorder(null);
}
```

Este enfoque es mucho mas acorde al que utilizamos por ejemplo en el login ya que ahora cada JTextfield se ocupa unicamente de su contenido y solo se activa cuando se selecciona sin necesidad de crear una gran cantidad de código ni varias condicionales.

## Creación de JTable y sus partes

Ya tenemos listo todo para poder crear un objeto **JTable** y obtener información a traves de ella. Un objeto **JTable** es un objeto avanzado ya que generalmente no se crea unicamente el objeto y se adiciona como cualquier otro, ya que este depende de algunas partes para su creación completa, a continuación mencionamos los objetos necesarios y su función:

* **JScrollPane**: Este es un tipo de panel especial que se caracteriza por contener Scrolls (Barras laterales) con las que el usuario puede navegar de forma vertical u horizontal, en el caso una tabla puede contener una cantidad considerable de filas o columnas y ademas no tiene un tamaño fijo ya que en tiempo de ejecución se pueden agregar mas filas o columnas, por lo que no se puede agregar simplemente a un panel y especificarle un tamaño fijo, de ser asi mucha información no será visible para el usuario, es por eso que este tipo de panel cobra importancia y gracias a este podremos navegar dentro de la tabla y ver información que esta mas allá de los limites de la interfaz.
* **JPanel**: Este panel es opcional y representa el **Corner** dentro de un ScrollPane, el Corner es el espacio que existe entre los ScrollBar del panel y este panel se usa para cubrir esas zonas y se vea mucho mejor.
* **JTable**: Este es el objeto principal y esta es la representación de la información en forma de tabla que el usuario podrá revisar, ademas es el medio por el cual se tendrá una interacción directa entre el usuario y la información.
* **JTableHeader**: Este objeto se utiliza para dar una personalización gráfica al encabezado de la tabla.
* **DefaultTableModel**: Este objeto es quizás el mas importante, ya que es el que realmente contiene la información y puede ser mostrada en la tabla, es decir que mientras la **JTable** muestra la información de forma organizada al usuario, es el **DefaultTableModel** el que se encarga de gestionar que información es la que contiene dicha tabla.
* **Arreglo tipo Strings** este arreglo es opcional pero muchas veces se utiliza, representa la información que estará en encabezado de la tabla, es decir que son los títulos de cada columna en la tabla.

Vamos a realizar la declaración de cada uno de estos objetos:

```
// Declaración objetos para JTable
private JScrollPane pTabla;
private JPanel pCorner;
private JTable tabla;
private JTableHeader header;
private DefaultTableModel modelo;
private String [] cabecera={"id", "Nombre", "Teléfono", "Email"};
```

Vamos a crear un método que se encargara de crear todo lo relacionado con la Tabla:

```
public void crearJTable(){
}
```

* Lo primero que haremos dentro de este método sera ejemplificar al objeto **DefaultTableModel** que en este caso llamamos **modelo**:

```
public void crearJTable(){
    modelo = new DefaultTableModel();
}
```

* Ahora vamos a agregar la información de los títulos de las columnas (la cabecera), para eso debemos decirle al modelo que se agregará con el método **setColumnIdentifiers** y le pasamos por parámetro al arreglo que contiene los títulos de las columnas en este caso **cabecera**:

```
public void crearJTable(){
    modelo = new DefaultTableModel();
    modelo.setColumnIdentifiers(cabecera);
}
```

* Ahora vamos a ejemplificar a la tabla y ademas vamos a agregarle el modelo que previamente configuramos esto con el método **setModel**:

```
public void crearJTable(){
    modelo = new DefaultTableModel();
    modelo.setColumnIdentifiers(cabecera);

    tabla = new JTable();
    tabla.setModel(modelo);
}
```

Teniendo la tabla ejemplificada vamos a obtener el **JTableHeader** de la tabla que recordemos sera el objeto para darle estilos a la cabecera de la tabla, por ahora solo realizaremos la obtención y los estilos se verán en la ultima sección. Para obtenerlo usamos el método **getTableHeader()**.

```
public void crearJTable(){
    modelo = new DefaultTableModel();
    modelo.setColumnIdentifiers(cabecera);

    tabla = new JTable();
    tabla.setModel(modelo);
    
    header = tabla.getTableHeader();
}
```

Finalmente vamos a crear a el **JScrollPane** que va a contener a la tabla y para esto nos vamos a ayudar del servicio **ObjGraficoService**.

```
public void crearJTable(){
    modelo = new DefaultTableModel();
    modelo.setColumnIdentifiers(cabecera);

    tabla = new JTable();
    tabla.setModel(modelo);
    
    header = tabla.getTableHeader();

    pTabla = sObjGraficos.construirPanelBarra(tabla, 10, 220, 580, 370, Color.WHITE, null);
    this.add(pTabla);
}
```

Noten que el primer argumento que se enviá cuando se construye un **JScrollPane** es un **Componente de java** y en este caso sera la tabla, todos los objetos gráficos de java heredan de un **componente de Java**.

* **Llamada del método en el constructor:**

```
// Dentro del constructor
this.crearJTable();
```

La aplicación luce asi:

<figure><img src="https://camo.githubusercontent.com/1ffb950fc18107399db125b48d85ce4f0c5b4d2c53a57737fa512d8d476a30a2/68747470733a2f2f692e696d6775722e636f6d2f346e70596445352e706e67" alt=""><figcaption></figcaption></figure>

Incorporación de la tabla dentro del componente amigos.

para finalizar vamos a crear los métodos **get** tanto de la tabla (**JTable**) como del modelo (**DefaultTableModel**):

```
public JTable getTabla(){
    return tabla;
}

public DefaultTableModel getModelo(){
    return modelo;
}
```

## Gestión de información dentro de un JTable

Ya hemos incorporado la tabla a la interfaz gráfica, es tiempo de empezar a gestionar la información de los contactos para que puedan ser vistos desde esta. Para lograr aquello vamos a utilizar los botónes del panel **pOpcion**, como recordaremos estos escuchan a los eventos de acción asi que vamos a usarlos para gestionar la información en la tabla. Nos ubicamos en la clase **AmigosComponent** y lo primero que vamos a hacer es la declaración de los métodos que vamos a utilizar:

```
public void restaurarValores(){
}

public void mostrarRegistrosTabla(){
}

public void insertarRegistroTabla(){
}

public void modificarRegistroTabla(){
}

public void eliminarRegistroTabla(){
}

public void filtrarRegistrosTabla(){
}

public void agregarRegistro(Amigo amigo){
}
```

* El método **mostrarRegistrosTabla()** mostrara toda la información externa contenida en el archivo plano en la tabla y se activara una vez oprimimos el botón **bMostrar**.
* El método **ingresarRegistroTabla()** insertará un nuevo registro capturado con lo que escribió el usuario en los JTextfield y se activara una vez oprimimos el botón **bInsertar**.
* El método **modificarRegistroTabla()** modificará un registro seleccionado de la tabla con la información que este en los JTextField y se activara una vez oprimimos el botón **bModificar**.
* El método **eliminarRegistroTabla()** eliminará un registro seleccionado de la tabla y se activara una vez oprimimos el botón **bEliminar**.
* El método **filtrarRegistroTabla()** va a mostrar una consulta de los registros en la tabla basados en lo que escriba el usuario en el JTextField **tFiltrar** y se activara una vez oprimimos el botón **bFiltrar**.
* Los método **restaurarValores()** y **agregarRegistro** son métodos auxiliares que nos van a ayudar con la funcionalidad de los demás métodos y se usaran varias veces.

Bueno entonces debemos configurar los eventos de acción para llamar al método correspondiente dependiendo del boton que se oprima:

```
@Override
public void actionPerformed(ActionEvent e) {
    if(e.getSource() == amigosTemplate.getBMostrar())
        mostrarRegistrosTabla();
    if(e.getSource() == amigosTemplate.getBInsertar())
        insertarRegistroTabla();
    if(e.getSource() == amigosTemplate.getBModificar())
        modificarRegistroTabla();
    if(e.getSource() == amigosTemplate.getBEliminar())
        eliminarRegistroTabla();
    if(e.getSource() == amigosTemplate.getBFiltrar())
        filtrarRegistrosTabla();
}
```

A continuación vamos a configurar todos los métodos paso a paso y explicaremos ciertas particularidades.

### Mostrar registros en la tabla

En este método queremos obtener todos los Amigos que están en el ArrayList que contiene el servicio **AmigoService** y mostrar su información en la tabla. Lo primero que vamos a realizar es un ciclo que recorra el arreglo, para eso necesitaremos saber el tamaño del arreglo, en este caso no podemos realizar un **For Each** ya que el arreglo no esta precisamente dentro del componente, esta en el servicio, para saber el tamaño del arreglo nos podemos ayudar del método **devolverCantidadAmigos()** que tiene el servicio:

```
public void mostrarRegistrosTabla(){
    for(int i=0; i<sAmigos.devolverCantidadAmigos(); i++){

    }
}
```

Ahora para obtener a un amigo nos ayudamos del atributo que creamos previamente **amigo** y lo igualamos con el método del servicio **devolverAmigo()** que nos va a devolver un amigo de acuerdo a su posición, pero debemos enviar como argumento la posición, para esto vamos a enviar a la variable i del ciclo:

```
public void mostrarRegistrosTabla(){
    for(int i=0; i<sAmigos.devolverCantidadAmigos(); i++){
        amigo = sAmigos.devolverAmigo(i);
    }
}
```

Ahora teniendo al objeto **amigo** de la posición actual ahora queremos agregarlo a la tabla, para eso vamos ayudarnos del método **agregarRegistro** que recibe como parámetro a un objeto de tipo **Amigo** asi que le pasamos como argumento al objeto que ya tenemos cargado:

```
public void mostrarRegistrosTabla(){
    for(int i=0; i<sAmigos.devolverCantidadAmigos(); i++){
        amigo = sAmigos.devolverAmigo(i);
        this.agregarRegistro(amigo);
    }
}
```

Sin embargo este método aun no ha sido configurado, vamos a realizar su codificación, como vamos a añadir una nueva fila a la tabla necesitamos llamar al **modelo** de la tabla ya que es este quien contiene la información que se mostrara en la tabla, para esto llamamos al método get correspondiente de la clase compañera **AmigosTemplate**:

```
public void agregarRegistro(Amigo amigo){
    amigosTemplate.getModelo();
}
```

Ahora le vamos a indicar que vamos a adicionar una nueva fila, esto se realiza con el método **addRow**:

```
public void agregarRegistro(Amigo amigo){
    amigosTemplate.getModelo().addRow();
}
```

Para poder insertar una nueva fila debemos crear un nuevo Objeto de tipo arreglo, esto se hace de la siguiente manera:

```
public void agregarRegistro(Amigo amigo){
    amigosTemplate.getModelo().addRow(
        new Object[]{}
    );
}
```

Ahora lo que tendrá ese arreglo adentro, sera la información que contendrá la nueva fila, en este caso queremos el **id, el nombre, el numero telefónico y el email** de cada contacto, para esto nos ayudaremos del objeto **amigo** que ha recibido por parámetro.

```
public void agregarRegistro(Amigo amigo){
    amigosTemplate.getModelo().addRow(
        new Object[]{amigo.getId(), amigo.getNombre(), amigo.getTelefono(), amigo.getEmail()}
    );
}
```

El método **agregarRegistro** ya esta listo, vamos a continuar con el método **mostrarRegistrosTabla**, en teoría ya debe mostrar todos los registros de la tabla, sin embargo hacen falta algunas configuraciones adicionales, por ejemplo debemos cambiar el label que muestra el valor del Id de un contacto por el siguiente numero al ultimo registro en la tabla, ya que si el usuario desea ingresar un nuevo contacto, el ID de este nuevo amigo debe ser siguiente al ultimo registro que esta en la tabla. Para esto vamos a obtener el tamaño del arreglo de amigos ya que su tamaño siempre será la cantidad de contactos mas uno.

```
public void mostrarRegistrosTabla(){
    for(int i=0; i<sAmigos.devolverCantidadAmigos(); i++){
        amigo = sAmigos.devolverAmigo(i);
        this.agregarRegistro(amigo);
    }
    amigosTemplate.getLIdValor().setText(sAmigos.devolverCantidadAmigos()+"");
}
```

Ahora debemos deshabilitar el botón mostrar registros ya que estos ya se están mostrando en la tabla y quedemos evitar que se duplique la información en caso de que el usuario lo vuelva a oprimir, esto lo realizamos con el método **setEnable**:

```
public void mostrarRegistrosTabla(){
    for(int i=0; i<sAmigos.devolverCantidadAmigos(); i++){
        amigo = sAmigos.devolverAmigo(i);
        this.agregarRegistro(amigo);
    }
    amigosTemplate.getLIdValor().setText(sAmigos.devolverCantidadAmigos()+"");
    amigosTemplate.getBMostrar().setEnabled(false);
}
```

Ya esta listo el método, vamos a probarlo:

<figure><img src="https://camo.githubusercontent.com/d48444b179050146c2843d214b7401518e73a48acc5bbcb8bc495d774f31c0c2/68747470733a2f2f692e696d6775722e636f6d2f47714c706c6d732e706e67" alt=""><figcaption></figcaption></figure>

Muestra de registros en la tabla

Se puede notar que ademas se inhabilito el boton **bMostrar** y el proximo id para ingresar un nuevo contacto quedo en 10.

### Ingresar un nuevo registro a la tabla

Para insertar un registro nuevo debemos obtener todo lo que haya escrito el usuario en los JTextfield del panel **pDatos**, de esta forma podemos agregar una nueva fila ayudándonos del método **agregarRegistro**, vamos a verlo:

* Primero vamos a utilizar al atributo **amigo** esta vez para crear un nuevo objeto, asi que lo ejemplificamos:

```
public void insertarRegistroTabla(){
    amigo = new Amigo();
}
```

* Ahora vamos a configurar sus atributos, como el Id, el nombre, edad, etc. Con ayuda de los métodos **set**, y le vamos a pasar la información que recibe desde los JTextField.

```
public void insertarRegistroTabla(){
    amigo = new Amigo();
    amigo.setId(sAmigos.devolverCantidadAmigos());
    amigo.setNombre(amigosTemplate.getTNombre().getText());
    amigo.setEdad(amigosTemplate.getTEdad().getText());
    amigo.setOficio(amigosTemplate.getTOficio().getText());
    amigo.setTelefono(amigosTemplate.getTTelefono().getText());
    amigo.setEmail(amigosTemplate.getTEmail().getText());
}
```

* Ya tenemos listo el objeto, ahora vamos a agregar el registro a la tabla con la ayuda del método **agregarRegistro** y le pasamos como argumento al objeto que recién configuramos

```
public void insertarRegistroTabla(){
    amigo = new Amigo();
    amigo.setId(sAmigos.devolverCantidadAmigos());
    amigo.setNombre(amigosTemplate.getTNombre().getText());
    amigo.setEdad(amigosTemplate.getTEdad().getText());
    amigo.setOficio(amigosTemplate.getTOficio().getText());
    amigo.setTelefono(amigosTemplate.getTTelefono().getText());
    amigo.setEmail(amigosTemplate.getTEmail().getText());
    this.agregarRegistro(amigo);
}
```

En teoría el registro ya se muestra en la tabla una vez oprimamos el botón de insertar registro, sin embargo vamos a realizar unas cosas adicionales, por ejemplo vamos a agregar el objeto dentro del arreglo de amigos del servicio para que el numero de contactos total este actualizado, para esto llamaremos al método **agregarAmigo** del servicio. Ademas vamos a dejar todos los JTextfield como estaban por defecto con sus respectivos placeholders y ademas vamos a actualizar el Id para el proximo registro, para esto nos vamos a ayudar del método **restaurarValores**.

```
public void insertarRegistroTabla(){
    amigo = new Amigo();
    amigo.setId(sAmigos.devolverCantidadAmigos());
    amigo.setNombre(amigosTemplate.getTNombre().getText());
    amigo.setEdad(amigosTemplate.getTEdad().getText());
    amigo.setOficio(amigosTemplate.getTOficio().getText());
    amigo.setTelefono(amigosTemplate.getTTelefono().getText());
    amigo.setEmail(amigosTemplate.getTEmail().getText());
    this.agregarRegistro(amigo);
    sAmigos.agregarAmigo(amigo);
    restaurarValores(); 
}
```

sin embargo debemos configurar el método **restaurarValores()**. En este simplemente vamos a dejar los placeholders que tenían por defecto ayudándonos de nuevo del arreglo **placeholders** que el componente tiene como atributo. Para el caso del label **lIdValor** vamos a actualizar su valor con el tamaño del arreglo nuevamente:

```
public void restaurarValores(){
    amigosTemplate.getLIdValor().setText(sAmigos.devolverCantidadAmigos()+"");
    amigosTemplate.getTNombre().setText(placeholdes[0]);
    amigosTemplate.getTEdad().setText(placeholdes[1]);
    amigosTemplate.getTOficio().setText(placeholdes[2]);
    amigosTemplate.getTTelefono().setText(placeholdes[3]);
    amigosTemplate.getTEmail().setText(placeholdes[4]);
}
```

Si probamos la aplicación e insertamos nuevos contactos veremos algo como esto:

<figure><img src="https://camo.githubusercontent.com/3813f8ee9e9eee32259e5e4dfd88e243b7a3ace223dead78b4cc7585973c939c/68747470733a2f2f692e696d6775722e636f6d2f4149514f5642752e706e67" alt=""><figcaption></figcaption></figure>

Ingreso de nuevos contactos en la tabla

### Modificación de un registro en la tabla

Ya tenemos información dentro de la tabla, ahora el usuario tiene la posibilidad de modificar esta información, para esto el usuario puede seleccionar el registro (fila) que quiere modificar y a traves de los JTextfield cambiar esta información. Lo primero que debemos hacer es identificar la fila que el usuario ha seleccionado, esto lo haremos con ayuda del método **getSelectedRow** del objeto **JTable**.

```
public void modificarRegistroTabla(){
    int fSeleccionada = amigosTemplate.getTabla().getSelectedRow();
}
```

Ahora bien el usuario puede oprimir el boton modificar sin haber seleccionado ninguna fila y esto puede provocar un error asi que vamos a gestionarlo. Si el usuario no ha seleccionado ninguna fila el método **getSelectedRow** devolverá por defecto el valor de -1, con esto podemos ayudarnos para preguntar si se ha seleccionado una fila a modificar.

```
public void modificarRegistroTabla(){
    int fSeleccionada = amigosTemplate.getTabla().getSelectedRow();
    if(fSeleccionada != -1){

    }
    else
        JOptionPane.showMessageDialog(null,"seleccione una fila", "Error" , JOptionPane.ERROR_MESSAGE);
}
```

En el anterior if estamos preguntando si el valor devuelto es diferente a -1, de ser asi vamos a realizar la modificación de los datos, en caso contrario mostraremos un mensaje que indique que debe seleccionar una fila.

Como vamos a modificar información de la tabla necesitamos manipularla a traves del **modelo** de la tabla asi que debemos obtenerlo, una vez lo obtenemos vamos a llamar a su método **setValueAt** Que recibe por parámetro 3 cosas:

* La nueva información que queremos poner ahora.
* El numero de la fila seleccionada.
* El numero de la columna.

```
public void modificarRegistroTabla(){
    int fSeleccionada = amigosTemplate.getTabla().getSelectedRow();
    if(fSeleccionada != -1){
        amigosTemplate.getModelo().setValueAt(
            // Informacion nueva, Numero Fila, Numero Columna
        );
    }
    else
        JOptionPane.showMessageDialog(null,"seleccione una fila", "Error" , JOptionPane.ERROR_MESSAGE);
}
```

Como en la tabla solo se muestran 3 valores editables (Nombre, telefono, email) (el id no lo puede cambiar el usuario) vamos a tomar estos 3 valores de los JTextField correspondientes y los pondremos como la nueva información

```
public void modificarRegistroTabla(){
    int fSeleccionada = amigosTemplate.getTabla().getSelectedRow();
    if(fSeleccionada != -1){
        amigosTemplate.getModelo().setValueAt(
            amigosTemplate.getTNombre().getText(), fSeleccionada, 1
        );
        amigosTemplate.getModelo().setValueAt(
            amigosTemplate.getTTelefono().getText(), fSeleccionada, 2
        );
        amigosTemplate.getModelo().setValueAt(
            amigosTemplate.getTEmail().getText(), fSeleccionada, 3
        );
    }
    else
        JOptionPane.showMessageDialog(null,"seleccione una fila", "Error" , JOptionPane.ERROR_MESSAGE);
}
```

Como se puede ver en el caso del nombre, pasamos la información que obtenemos del JTextField **tNombre**, la fila sera la que selecciono el usuario y la columna de los nombres siempre sera la numero 1 (la 0 es la del id), lo mismo ocurre con el telefono y email donde obtenemos la información correspondiente del JTextField y cambiamos el valor de la columna que para el telefono siempre sera la numero 2 y para el email será el numero 3.

Si ejecutamos la aplicación podemos ver que si funciona la modificación en la tabla sin embargo un usuario puede modificar mas datos a parte del nombre, telefono o email, ademas el cambio solo se ve en la tabla pero el objeto que contiene la información de ese objeto sigue intacta, asi que es necesario también realizar la modificación de esos datos en el objeto, vamos a obtener el objeto desde el servicio y la posición en el arreglo es justamente la misma que en la posición de la fila en la tabla asi que se la enviamos como argumento:

```
public void modificarRegistroTabla(){
    int fSeleccionada = amigosTemplate.getTabla().getSelectedRow();
    if(fSeleccionada != -1){
        amigosTemplate.getModelo().setValueAt(
            amigosTemplate.getTNombre().getText(), fSeleccionada, 1
        );
        amigosTemplate.getModelo().setValueAt(
            amigosTemplate.getTTelefono().getText(), fSeleccionada, 2
        );
        amigosTemplate.getModelo().setValueAt(
            amigosTemplate.getTEmail().getText(), fSeleccionada, 3
        );
        amigo = sAmigos.devolverAmigo(fSeleccionada);
    }
    else
        JOptionPane.showMessageDialog(null,"seleccione una fila", "Error" , JOptionPane.ERROR_MESSAGE);
}
```

Una vez obtenido ese objeto, procedemos a modificar sus atributos por la nueva información dejada por el usuario en los JTextField, una vez realizado esto, llamamos al método **restaurarValores** para que los JTextField vuelvan a su estado original:

```
public void modificarRegistroTabla(){
    int fSeleccionada = amigosTemplate.getTabla().getSelectedRow();
    if(fSeleccionada != -1){
        amigosTemplate.getModelo().setValueAt(
            amigosTemplate.getTNombre().getText(), fSeleccionada, 1
        );
        amigosTemplate.getModelo().setValueAt(
            amigosTemplate.getTTelefono().getText(), fSeleccionada, 2
        );
        amigosTemplate.getModelo().setValueAt(
            amigosTemplate.getTEmail().getText(), fSeleccionada, 3
        );
        amigo = sAmigos.devolverAmigo(fSeleccionada);
        amigo.setNombre(amigosTemplate.getTNombre().getText());
        amigo.setEdad(amigosTemplate.getTEdad().getText());
        amigo.setOficio(amigosTemplate.getTOficio().getText());
        amigo.setTelefono(amigosTemplate.getTTelefono().getText());
        amigo.setEmail(amigosTemplate.getTEmail().getText());
        restaurarValores();
    }
    else
        JOptionPane.showMessageDialog(null,"seleccione una fila", "Error" , JOptionPane.ERROR_MESSAGE);
}
```

Si probamos la aplicación vemos que funciona correctamente pero hay una situation incomoda para el usuario y es que cada vez que quiera modificar la información de un usuario este tendrá que reescribirla en los JTextField modificando a su vez los atributos que necesita actualizar, esto es muy engorroso para los usuarios. Una buena solución a esto puede ser que una vez el usuario seleccione una fila en la tabla, la información de este contacto se coloque automáticamente en los JTextfield y de esa forma el usuario solamente deba modificar lo que necesite.

Para esto necesitamos adicionarle la escucha de eventos MouseListener a la tabla para que una vez el usuario de click sobre una fila realice la acción previamente descrita

_**Nota:** se realiza con la interfaz MouseListener y no con la de ActionListener ya que un objeto tabla no cuenta con la adición de escucha de eventos de acción_.

<figure><img src="https://camo.githubusercontent.com/ec244e750de1d44c19dfb661d4f998b2a3a9ea344d7aeccfd8c07a27d1b7bb38/68747470733a2f2f692e696d6775722e636f6d2f587637685558762e706e67" alt=""><figcaption></figcaption></figure>

Adición de escucha de eventos MouseListener

Vamos al método **mouseClicked** y vamos a configurar esta acción, lo primero que debemos hacer es una discriminación de clase para indicar que solo se hará en caso de que sea la tabla quien active el evento.

```
@Override
public void mouseClicked(MouseEvent e) {
    if(e.getSource() instanceof JTable){

    }
}
```

Y esta discriminación aunque parece obsoleta es muy importante, recordando un poco en los métodos **mouseEntered y mouseExited** también se realizo una discriminación de clases pero para los botones, y esto es importante ya que ahora tenemos dos clases de objetos que escuchan a estos eventos **Tabla y botones** y aunque cada objeto esta gestionando un evento distinto (mouseClicked en la tabla y mouseEntered con mouseExited para los botones) recordemos que todos estos métodos hacen parte de la misma familia **MouseListener** asi que todos están compaginados de alguna forma, si no realizamos esta discriminación en estos métodos y pasamos sobre la tabla con el puntero del Mouse, el programa sacara un error ya que la tabla al escuchar eventos MouseListener va a entrar al evento MouseEntered y va a tratar de convertirse en un Botón, algo que es imposible, lo mismo sucede si damos un click al boton y va a tratar de buscar información que este no posee.

<figure><img src="https://camo.githubusercontent.com/c5ddcb83b1a8bd76dc781f339d94c5634bd59268a2faf2754cebb707bb7d0fd1/68747470733a2f2f692e696d6775722e636f6d2f42507558534d762e706e67" alt=""><figcaption></figcaption></figure>

Discriminación en métodos separados del MouseListener

Ahora dentro de la discriminación de clase de la tabla queremos obtener la fila que ha seleccionado el usuario, esto ya lo vimos previamente usando el método **getSelectedRow**:

```
@Override
public void mouseClicked(MouseEvent e) {
    if(e.getSource() instanceof JTable){
        int fila = amigosTemplate.getTabla().getSelectedRow();
    }
}
```

Ahora vamos a obtener el objeto del **amigo** dentro del arreglo que contiene el servicio pasandole como posición la fila seleccionada.

```
@Override
public void mouseClicked(MouseEvent e) {
    if(e.getSource() instanceof JTable){
        int fila = amigosTemplate.getTabla().getSelectedRow();
        amigo = sAmigos.devolverAmigo(fila);
    }
}
```

Una vez tenemos el amigo seleccionado por el usuario debemos cambiar el valor de los JTextField y del Label del Id con la información del amigo seleccionado y esto con el método **setText** que hemos manejado varias veces en el curso:

```
@Override
public void mouseClicked(MouseEvent e) {
    if(e.getSource() instanceof JTable){
        int fila = amigosTemplate.getTabla().getSelectedRow();
        amigo = sAmigos.devolverAmigo(fila);
        amigosTemplate.getLIdValor().setText(amigo.getId()+"");
        amigosTemplate.getTNombre().setText(amigo.getNombre());
        amigosTemplate.getTEdad().setText(amigo.getEdad());
        amigosTemplate.getTOficio().setText(amigo.getOficio());
        amigosTemplate.getTTelefono().setText(amigo.getTelefono());
        amigosTemplate.getTEmail().setText(amigo.getEmail());
    }
}
```

Ya esta todo listo, ahora cada vez que queramos modificar la información de algún contacto basta con seleccionarlo en la tabla, la información de este se pondrá automáticamente en los JTextField y una vez cambiemos la información necesaria no solo se vera reflejada en la tabla sino que el objeto que contiene esta información también quedara actualizado, ademas los JTextfield tomaran su estado inicial de nuevo.

<figure><img src="https://camo.githubusercontent.com/1555147028f076a01a31c878e714bf4f90ac53bec1aeb6e70c0072b10aabbba0/68747470733a2f2f692e696d6775722e636f6d2f475065777869572e706e67" alt=""><figcaption></figcaption></figure>

Implementación de modificación de registros completada

### Eliminar un registro en la tabla

La acción de eliminar es muy parecida a la de modificar, ya que para eliminar un registro de la tabla debemos nuevamente seleccionarlo desde la tabla, y para que no ocurra un error por no haber seleccionado nada vamos a gestionar de nuevo el error.

```
public void eliminarRegistroTabla(){
    int fSeleccionada = amigosTemplate.getTabla().getSelectedRow();
    if(fSeleccionada!= -1)
        
    else
        JOptionPane.showMessageDialog(null,"seleccione una fila","Error",JOptionPane.ERROR_MESSAGE);
}
```

Ahora para poder eliminar un registro de la tabla vamos a llamar al **modelo** de esta y luego usar el método **removeRow** que va a pedir como parámetro el numero de la fila que se ha seleccionado.

```
public void eliminarRegistroTabla(){
    int fSeleccionada = amigosTemplate.getTabla().getSelectedRow();
    if(fSeleccionada!= -1)
        amigosTemplate.getModelo().removeRow(fSeleccionada);
    else
        JOptionPane.showMessageDialog(null,"seleccione una fila","Error",JOptionPane.ERROR_MESSAGE);
}
```

En este caso solo eliminaremos el registro de la tabla y no del arreglo ya que no se acostumbra eliminar objetos de los arreglos.

### Filtrar registros de la tabla

Los filtros dentro de la tabla se usan a menudo cuando existe una cantidad considerable de registros dentro de esta y queremos buscar alguno en especifico o algunos bajo algún criterio. Para realizar esto debemos llamar a un objeto especial que se encarga de realizar estos filtros. Este objeto es un **TableRowSorter** este objeto crea una copia del modelo de la tabla (quien contiene la información de esta) por lo que es un arreglo dinámico que podrá cambiar su contenido de acuerdo a un criterio, primero vamos a ejemplificarlo y como este sera una copia del **modelo**, al momento de la ejemplificación debemos enviar al modelo como argumento.

```
public void filtrarRegistrosTabla(){
    TableRowSorter<DefaultTableModel> trs = new TableRowSorter<>(amigosTemplate.getModelo());
}
```

Ahora debemos indicarle a la tabla que va a contener este elemento y asi puede estar preparada para realizar un filtro de la información, esto lo realizamos con el método **setRowStorter**:

```
public void filtrarRegistrosTabla(){
    TableRowSorter<DefaultTableModel> trs = new TableRowSorter<>(amigosTemplate.getModelo());
    amigosTemplate.getTabla().setRowSorter(trs);
}
```

Finalmente vamos a realizar el filtrado de filas, para esto necesitamos primero indicarle al **TableRowSorter** que vamos a configurar un filtro a traves del método **setRowFilter**:

```
public void filtrarRegistrosTabla(){
    TableRowSorter<DefaultTableModel> trs = new TableRowSorter<>(amigosTemplate.getModelo());
    amigosTemplate.getTabla().setRowSorter(trs);
    trs.setRowFilter();
}
```

Dentro del método y como argumento debemos crear el filtro, para esto debemos llamar al objeto **RowFilter** que se encarga de dejar unicamente las filas que cumplen con el criterio de filtrado

```
public void filtrarRegistrosTabla(){
    TableRowSorter<DefaultTableModel> trs = new TableRowSorter<>(amigosTemplate.getModelo());
    amigosTemplate.getTabla().setRowSorter(trs);
    trs.setRowFilter(RowFilter);
}
```

Pero es necesario para hacer efectivo el filtro la llamada a su método **regexFilter** que recibe como parámetro al criterio del filtrado, que en este caso va a ser lo que escriba el usuario dentro del JTextfield **tFiltrar**.

```
public void filtrarRegistrosTabla(){
    TableRowSorter<DefaultTableModel> trs = new TableRowSorter<>(amigosTemplate.getModelo());
    amigosTemplate.getTabla().setRowSorter(trs);
    trs.setRowFilter(RowFilter.regexFilter(amigosTemplate.getTConsulta().getText()));
}
```

El filtro esta listo, ahora si corremos la aplicación, escribimos algún criterio de filtro en el JTextField **tFiltrar** y luego oprimimos el boton **bFiltrar** veremos algo como esto:

<figure><img src="https://camo.githubusercontent.com/8227930002b4f6c3b0610cbf4893cb1f00abadbc186fd74058d1f9d7523257f9/68747470733a2f2f692e696d6775722e636f6d2f62664a56354e4d2e706e67" alt=""><figcaption></figcaption></figure>

Incorporación de filtro dentro de la tabla

## Personalización del JTable

La tabla funciona de maravilla y ya podemos gestionar la información a traves de ella. Sin embargo, esta tabla se ve un poco mal con respecto a la interfaz que hemos estado manejando, es hora de personalizarla un poco y que tome un mejor aspecto. Vamos a dirigirnos al método **crearTable** de la clase **AmigosTemplate** y vamos a realizar algunas configuraciones que le darán un mejor aspecto.

Para empezar podemos agregarle un alto a cada fila, ya que las filas están muy pegadas la una de la otra, esto con el método **setRowHeight** que recibe como parámetro un entero que representa la altura de cada fila. También podemos quitar las lineas que separan cada fila y cada columna, esto va dependiendo del diseño de cada desarrollador en este caso creemos que se vera mejor si omitimos estas lineas, para ocultar estas lineas podemos usar los métodos **setShowHorizontalLines y setShowVerticalLines**, ambos reciben como parámetro un booleano que si se deja en false, ocultara estas lineas

```
public void crearJTable(){
    tabla.setRowHeight(40);
    tabla.setShowHorizontalLines(false);
    tabla.setShowVerticalLines(false);
}
```

<figure><img src="https://camo.githubusercontent.com/092d9bb1481e935f75a654fe6a4eaa0577dd497d13c366ae9326286c5f3a7b68/68747470733a2f2f692e696d6775722e636f6d2f647949706461732e706e67" alt=""><figcaption></figcaption></figure>

Tabla con filas mas altas y sin las lineas que separan los registros

La cabecera de la tabla esta un poco angosta ahora con respecto a los registros de la tabla, vamos a añadirle mas altura, para esto debemos tomar el objeto **header** que ya obtuvimos previamente de la tabla. Para darle un tamaño al header tenemos que utilizar el método **setPreferredSize**.

```
header.setPreferredSize();
```

Este método nos va a pedir por parámetro la creación de una dimension que es un objeto en java para darle tamaño a objetos especiales, asi que lo crearemos:

```
header.setPreferredSize(new Dimension());
```

Para finalizar, dentro del constructor de la Dimension que acabamos de crear debemos pasarle dos parámetros que serán el ancho y el alto, dejaremos el ancho igual al **ScrollPane** pero e alto lo dejaremos en 30 pixeles.

```
header.setPreferredSize(new Dimension(580, 30));
```

<figure><img src="https://camo.githubusercontent.com/bfd593db0c5e3cab5b9be417683888341f042ff5ac2cd5b90f0161609953f708/68747470733a2f2f692e696d6775722e636f6d2f41595a71724b512e706e67" alt=""><figcaption></figcaption></figure>

Tabla con cabecera más grande

A continuación vamos a crear un nuevo servicio Gráfico para decorar mejor la tabla, el propósito de esta clase no sera explicar que hacen estos métodos, vamos a dedicar una clase entera para explicar que hacen estos métodos, por ahora solo lo vamos a implementar.

### Preparando detalles para personalizar la tabla

Vamos a crear un servicio llamado **GraficosAvanzadosService** y lo dejaremos dentro del paquete **ServiceGraphics**

<figure><img src="https://camo.githubusercontent.com/1f6ec1636aa685aa681e0cc946ab181b4d2193797ba35eb0c6a579438ad1e2e0/68747470733a2f2f692e696d6775722e636f6d2f6375397755374c2e706e67" alt=""><figcaption></figcaption></figure>

Creación de servicio GraficosAvanzadosService

Este servicio ademas de la estructura básica de un servicio contiene varios métodos que realizan ciertas acciones las cuales en esta clase no vamos a explicar. Para obtener el código de este servicio usted puede copiarlo de este mismo repositorio entrando a las carpetas **Clase11/src/app/services/servicesGraphics/GraficosAvanzadosService** ahi encontrara el código.

<figure><img src="https://camo.githubusercontent.com/a051554244bf29e31a48904f85fb45cf907fbe534392ff69f501d1f1fc212e30/68747470733a2f2f692e696d6775722e636f6d2f35786a5251626a2e706e67" alt=""><figcaption></figcaption></figure>

Código dentro del servicio GraficosAvanzadosService

Vamos a obtener ese servicio en la clase **AmigosTemplate**

* **Declaración:**

```
private GraficosAvanzadosService sGraficosAvanzados;
```

* **Obtención del servicio:**

```
// Dentro del constructor
this.sGraficosAvanzados = GraficosAvanzadosService.getService();
```

Primero vamos a personalizar la cabecera de la tabla, vamos a añadirle un color de fondo azul y un color de fuente blanco, para eso debemos llamar al método **setDefaultRenderer** de la cabecera:

```
header.setDefaultRenderer();
```

Dentro de este método, como parámetro vamos a tener que crear un objeto **DefaultRender**, pero para esto tenemos un método en el servicio llamado **devolverTablaPersonalizada**, que nos va a pedir varias cosas como parámetro:

* **ColorPrincipal:** Es el color principal que va a tener la tabla.
* **ColorSecundario:** Es el color que complementa al color principal, si se pasan los dos colores la primera fila va a tomar el color primario, la segunda fila el color secundario y asi sucesivamente.
* **ColorSeleccion:** Es el color que se va a dibujar en la tabla una vez se seleccione una fila de la tabla.
* **ColorFuente:** Es el color que va a tener la fuente de la tabla.
* **Fuente:** Es el tipo de fuente que tendrá la tabla.

Para el caso del Header, como este solo representa una fila unicamente vamos a enviar el color principal, el color de fuente y el tipo de fuente:

```
header.setDefaultRenderer(sGraficosAvanzados.devolverTablaPersonalizada(
    sRecursos.getColorPrincipal(), null , null, Color.WHITE, sRecursos.getFontPequeña()
));
```

Vamos a hacer lo mismo para la tabla, pero esta vez vamos a enviar todos los parámetros:

```
tabla.setDefaultRenderer(Object.class, sGraficosAvanzados.devolverTablaPersonalizada(
    Color.WHITE, sRecursos.getColorGrisClaro() , sRecursos.getColorPrincipalOscuro(), 
    sRecursos.getColorGrisOscuro(), sRecursos.getFontPequeña()
));
```

Vamos a ver como se ve la interfaz:

<figure><img src="https://camo.githubusercontent.com/d52cc56934bd7f8f38b5f5bdbade15b57ac178db7708244a7627ad89590c3136/68747470733a2f2f692e696d6775722e636f6d2f63744b4a72344a2e706e67" alt=""><figcaption></figcaption></figure>

Tabla personalizada usando el servicio GraficosAvanzadosService

Ahora vamos a cambiar el Scroll que acompaña a la tabla una vez hay muchos registros, este Scroll por defecto es algo anticuado y no se ve bien con respecto al resto de la interfaz. Para esto le vamos a indicar al PaneScroll **pTabla** que vamos a editar el Scroll vertical, asi que debemos obtenerlo primero:

```
pTabla.getVerticalScrollBar();
```

Luego para darle una personalización debemos llamar al método **setUI** que va a pedir por parámetro un objeto tipo **BasicScrollBarUI** y con ayuda del servicio **GraficosAvanzadosService** y su método **devolverScrollPersonalizado** podemos realizar dicha personalización.

Este método va a pedir por parámetro:

* El Grosor de la barra del Scroll.
* El Radio de las esquinas de la barra del Scroll.
* El color de fondo del ScrollBar.
* El color de la barra.
* El color de la barra una vez se esta arrastrando (moviendo con el botón del mouse oprimido).

```
pTabla.getVerticalScrollBar().setUI(
    sGraficosAvanzados.devolverScrollPersonalizado(
        7, 10, Color.WHITE, Color.GRAY, sRecursos.getColorGrisOscuro()
    )
);
```

La tabla se vera de la siguiente manera:

<figure><img src="https://camo.githubusercontent.com/265337da1924c56e3e0bc2e7ae66fec61baddcd2a9a4d8c306b0bf46a5321aa8/68747470733a2f2f692e696d6775722e636f6d2f794279426973392e706e67" alt=""><figcaption></figcaption></figure>

Personalización del Scroll de la tabla.

Por ultimo podemos notar que en la parte superior izquierda al lado de la cabecera hay un espacio que sobra, este espacio es conocido como el **Corner** del ScrollBar y podemos editarlo para que luzca como si fuera parte de la cabecera. Para esto vamos a usar el panel **pCorner**, lo primero que haremos es ejemplificarlo de forma tradicional:

```
// Dentro del método crearJTable
pCorner = new JPanel();
```

Ahora vamos a indicarle que tenga un color de fondo azul al igual que la cabecera:

```
// Dentro del método crearJTable
pCorner = new JPanel();
pCorner.setBackground(sRecursos.getColorPrincipal());
```

Por ultimo vamos a configurar ese **Corner** al **ScrollPane**, esto mediante el método **setCorner** que va a pedir por parámetros 2 cosas:

* **Ubicación del corner:** Esto debido a que puede existir un espacio sobrante en distintas partes del **JScrollPane**, asi que hay que especificar en que esquina esta ubicado el Corner a editar.
* **Corner:** Es el objeto gráfico que va a cubrir el espacio, en este caso un panel.

```
// Dentro del método crearJTable
pCorner = new JPanel();
pCorner.setBackground(sRecursos.getColorPrincipal());
pTabla.setCorner(JScrollPane.UPPER_RIGHT_CORNER, pCorner);
```

Finalmente la tabla se ve asi:

<figure><img src="https://camo.githubusercontent.com/2f5430f12a3de2f7c44d27cc80d0b3ed4c43c25cf74cc88506b383988746f7ed/68747470733a2f2f692e696d6775722e636f6d2f4b384a5968716d2e706e67" alt=""><figcaption></figcaption></figure>

Personalización total de la tabla.

## Resultado

Si has llegado hasta aquí **!Felicidades!** has aprendido las partes para construir tablas, como gestionar información a traves de Tablas, como dar cierta interactividad a estas y ademas has aprendido como personalizarlas. En la siguiente clase vamos a ver animaciones para darle ese toque final de interactividad al proyecto.

## Actividad

Hacer uso de tablas dentro de sus respectivos proyectos para la gestión de la información y realizar personalización de estas con ayuda del nuevo servicio gráfico.

Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 12

### Objetivos

* Reconocer la forma para realizar animaciónes de movimiento dentro de nuestro proyecto para adicionar interactividad a las interfaces de usuario o mostrar información adicional que el usuario requiera.
* Identificar algunos factores importantes que intervienen cuando se realizan animaciónes como los objetos y eventos que intervienen.
* Explicar algunas particularidades clave a la hora de usar animaciones que son importantes para el buen funcionamiento.
* Explorar varios enfoques para realizar una misma animación pero en distintas formas.

## Antes de Comenzar

Para continuar con el ejercicio deberá actualizar la carpeta **resources/img** ya que se han agregado nuevas imágenes. Estas las puede descargar en este mismo repositorio entrando a la carpeta **Clase12** seguido de **resources/img**.

Recordando un poco nuestro recorrido en la clase anterior revisamos el uso de tablas para gestionar información, entre otras cosas se mostró **Las principales partes para la creación de una tabla**, **Los métodos de gestión de información dentro de tablas**, **Personalización de tablas**.

<figure><img src="https://camo.githubusercontent.com/2f5430f12a3de2f7c44d27cc80d0b3ed4c43c25cf74cc88506b383988746f7ed/68747470733a2f2f692e696d6775722e636f6d2f4b384a5968716d2e706e67" alt=""><figcaption></figcaption></figure>

Resultado de la clase anterior con el uso de tablas.

## Uso de animaciones

Esta sesión tratará el tema de animaciones de movimiento sobre nuestras interfaces y para la explicación e implementación de estas se verán 4 items:

* **Animaciones para Interactividad.**
  * **Particularidades con las animaciones.**
* **Animaciones para muestra de información.**
  * **Enfoques de animación.**

## Animaciones para Interactividad

En muchos casos nos interesa crear animaciones para darle un toque extra de interactividad a nuestras interfaces de usuario, las animaciones pueden capturar la atención de nuestros usuario y hacen de la visibilidad una experiencia bastante agradable. Para crear animaciones dentro de nuestro proyecto vamos a enfocarnos una vez mas en nuestro **Login** y vamos a darle uso a los tres botones que tiene nuestro login en su parte izquierda:

<figure><img src="https://camo.githubusercontent.com/1ebb7dc7684fe06e34dcdbb34d6b999c4aaf7b07eb9460041fc43e124164243e/68747470733a2f2f692e696d6775722e636f6d2f4f3031565569692e706e67" alt=""><figcaption></figcaption></figure>

Botones de opción dentro de nuestro Login

Lo que queremos es que una vez se oprima alguno de estos botones se muestre una nueva imagen en el Login:

<figure><img src="https://camo.githubusercontent.com/de6df79cd70614c1c8768738197bc5c162c1fb571c0637aedb167eb4a77e55a7/68747470733a2f2f692e696d6775722e636f6d2f664748486667332e706e67" alt=""><figcaption></figcaption></figure>

Imagen dentro del login que quiere ser cambiada

Pero para no hacer que esta desaparezca de golpe una vez se muestre la siguiente imágen podemos utilizar **Animaciones**, de esta forma podemos hacer que se mueva a la izquierda la imagén actual y asi la nueva imagen pueda verse en pantalla. Para realizar esto antes debemos hacer algunos preparativos.

#### **Preparativos para realizar la animación**.

Como vamos a añadir otras dos imágenes (para la segunda y tercera opción) vamos a crear los objetos **ImageIcon** de estas dentro de nuestra clase **LoginTemplate**. También vamos a añadir una nueva imagen para los botones de las opciones la cual representará cual de las 3 opciones esta siendo seleccionada.

* **Declaración:**

```
private ImageIcon iPunto2, iSvg2, iSvg3;
```

* **Ejemplificación**:

```
// Dentro del método crearObjetosDecoradores
iSvg2 = new ImageIcon("Clase12/resources/img/imagen2.png");
iSvg3 = new ImageIcon("Clase12/resources/img/imagen3.png");
iPunto2 = new ImageIcon("Clase12/resources/img/punto2.png");
```

Para que las nuevas imágenes puedan ser vistas vamos a declarar por ahora los **Labels** correspondientes que contendrán estas imágenes:

* **Declaración:**

```
private JLabel lSvg2, lSvg3;
```

Como queremos que haya un movimiento de las tres imágenes una vez se oprima alguno de los tres botones, debemos hallar una forma optimizada de mover las 3 imágenes al tiempo, ya que tendría mas esfuerzo y código codificar el movimiento de cada una de las imágenes cada vez que se oprima alguno de los 3 botónes. Para esto vamos a crear un panel que contendrá estas imágenes y asi realizaremos el movimiento hacia el panel haciendo el efecto de que se moverán las 3 imágenes al tiempo.

**Declaración:**

```
private JPanel pSvg;
```

**Construcción y adición:**

```
// Dentro del método crearJPanels
pSvg = sObjGraficos.construirJPanel(
    100, 100, 1700, 345, new Color(0, 0, 0, 0), null
);
pIzquierda.add(pSvg);
```

Note algo importante, el color de fondo que le hemos configurado es un color **rgba o transparente** ya que tiene 4 argumentos, todos en 0, esto quiere decir que el color sera "negro" pero totalmente transparente, ya que el ultimo argumento **Alfa** esta en 0 (transparencia total), caso contrario es un color solido el cual debería tener 255 en ese argumento. También podemos notar que el panel no se esta agregando directamente a la ventana sino al panel **pIzquierda**. Además hay que recalcar su tamaño, ya que su ancho es bastante grande, esto para contener las 3 imágenes, sin embargo solo será visible una parte de este en pantalla.

Allí vamos a dejar nuestros Labels que contienen las imágenes **Svg** así que eso realizaremos:

```
// Dentro del método crearJLabels

//LABEL SVG-----------------------------------------------------------------------------
iDimAux = new ImageIcon(
    iSvg.getImage().getScaledInstance(500, 345, Image.SCALE_AREA_AVERAGING)
);
lSvg= sObjGraficos.construirJLabel(null, 0, 0, 500, 345, iDimAux, null, null, null, "c");
pSvg.add(lSvg);

//LABEL SVG 2-----------------------------------------------------------------------------
iDimAux = new ImageIcon(
    iSvg2.getImage().getScaledInstance(500, 345, Image.SCALE_AREA_AVERAGING)
);
lSvg2= sObjGraficos.construirJLabel(null, 600, 0, 500, 345, iDimAux, null, null, null, "c");
pSvg.add(lSvg2);

//LABEL SVG 3-----------------------------------------------------------------------------
iDimAux = new ImageIcon(
    iSvg3.getImage().getScaledInstance(500, 345, Image.SCALE_AREA_AVERAGING)
);
lSvg3= sObjGraficos.construirJLabel(null, 1200, 0, 500, 345, iDimAux, null, null, null, "c");
pSvg.add(lSvg3);
```

Para el Label **lSvg** se agrego ahora al nuevo panel **pSvg** y ya no directamente al panel **pDerecha**, también se cambio las coordenadas de posición, los otros dos label se agregaron al mismo panel.

Vamos ahora a cambiar la imagen del primer botón por la imágen que indica que esta opción esta seleccionada ya que por defecto la primera opción ya esta seleccionada (La primera imagen ya se esta mostrando). Para los demás botones dejaremos la imagen que tenían originalmente pero le agregaremos la escucha de eventos **ActionListener** ya que esta solo la tenía el primer botón.

```
// Dentro del método crearJButtons
iDimAux = new ImageIcon(
    iPunto2.getImage().getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
);

//BOTÓN OPCIÓN 1-----------------------------------------------------------------------------
bOpcion1 = sObjGraficos.construirJButton(
    null, 10, 220, 30, 20, sRecursos.getCMano(), iDimAux, null,
    null, null, null, "c", false
);
bOpcion1.addActionListener(loginComponent);
pIzquierda.add(bOpcion1);

iDimAux = new ImageIcon(
    iPunto.getImage().getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
);

//BOTÓN OPCIÓN 2-----------------------------------------------------------------------------
bOpcion2 = sObjGraficos.construirJButton(
    null, 10, 250, 30, 20, sRecursos.getCMano(), iDimAux, null,
    null, null, null, "c", false
);
bOpcion2.addActionListener(loginComponent);
pIzquierda.add(bOpcion2);

//BOTÓN OPCIÓN 3-----------------------------------------------------------------------------
bOpcion3 = sObjGraficos.construirJButton(
    null, 10, 280, 30, 20, sRecursos.getCMano(), iDimAux, null,
    null, null, null, "c", false
);
bOpcion3.addActionListener(loginComponent);
pIzquierda.add(bOpcion3);
```

Nuestra aplicación se ve de la siguiente manera:

<figure><img src="https://camo.githubusercontent.com/1e80b957a7305c101e89df64d3b9752211b5dda695f1789f80086cc8803989bf/68747470733a2f2f692e696d6775722e636f6d2f45756730475a722e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario con las modificaciones realizadas hasta el momento

Por ahora el único cambio visible esta en el primer botón de opciones ya que resalta en naranja. Las otras imágenes ya están añadidas al panel **pSvg** pero como comentamos solo se esta viendo una parte de este panel.

Ahora vamos a crear algunos métodos **get**.

Como vamos a manipular la posición del panel **pSvg** vamos a necesitar obtenerlo desde la clase **loginComponent**:

```
public JPanel getPSvg(){
    return this.pSvg;
}
```

Como vamos a cambiar la imagen dentro de cada botón una vez se seleccione y poner la imagen original en los botones que no están seleccionados vamos a necesitar estas dos imágenes en la clase **Component**, para que no ocurran problemas con las dimensiones de estas las vamos a retornar rescaldas de una vez:

```
public ImageIcon getIPunto(){
    iDimAux = new ImageIcon(
        iPunto.getImage().getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
    );
    return iDimAux;
}

public ImageIcon getIPunto2(){
    iDimAux = new ImageIcon(
        iPunto2.getImage().getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
    );
    return iDimAux;
}
```

Ahora vamos a devolver los 3 botones de las opciones, ya habíamos creado el **get** del primero, para no realizar un método para cada uno y por motivos de la codificación posterior vamos a modificar el método que ya teníamos de tal forma que reciba como parámetro un entero que representara cual botón requiere y mediante if vamos a retornar el que necesitemos:

```
public JButton getBOpcion(int boton){
    if(boton == 1)
        return this.bOpcion1;
    if(boton == 2)
        return this.bOpcion2;
    if(boton == 3)
        return this.bOpcion3;
    return null;
}
```

Por ultimo vamos a prevenir un futuro conflicto que tiene que ver con **el eje Z** y es que si recordamos un poco el panel que contiene las imágenes se agrego dentro del método **crearJPanels** y por otro lado los botónes de opciones se agregaron dentro del método **crearJButtons**. La creación de los paneles se llama dentro del constructor antes de la creación de los botones, esto inicialmente no crea ningún conflicto ya que el panel **pSvg** esta en la posición **100px** de nuestro panel **pIzquierda** mientras que los botones **bOpcion** están en la posición **10px** del mismo, pero una vez se mueva el panel **pSvg** hacia la izquierda para crear la animación este va a situarse por encima de los botones haciendo que las imágenes los tapen mientras pasan sobre ellos y ademas no se podrán seleccionar mas ya que estarán detrás del panel. Para arreglar esta situación vamos a sacar la agregación de este ultimo panel (**pSvg**) del método de crearJPanels y lo vamos añadir dentro del constructor justo después de la creación de los botones pero justo antes de la creación de los labels:

<figure><img src="https://camo.githubusercontent.com/65fee69e911119059d79e8d4b696bd0d404fa6e330838cbe7420aae9a3194213/68747470733a2f2f692e696d6775722e636f6d2f77533031306f682e706e67" alt=""><figcaption></figcaption></figure>

Resolución de conflictos en el eje Z

#### **Creando la animación.**

Vamos a concentrarnos en la clase **LoginComponent** lo primero que vamos a hacer es declarar tes atributos que nos serán útiles para realizar la animación:

```
private int estado = 1, estadoAnterior = 0, direccion = -1;
```

* **estado:** El estado nos va a indicar cual es el botón que actualmente ha sido seleccionado y asi podremos cambiar la imagen por el aspecto naranja al botón que se selecciono y ademas que imágen debe mostrar, por defecto esta en 1 ya que el primer boton esta seleccionado y la primera imagen se esta mostrando una vez inicia la aplicación.
* **estadoAnterior:** El estado anterior nos va a indicar cual era el anterior botón que se selecciono previamente y asi poder dejarlo en su estado original.
* **Dirección:** Esta nos sera util cuando queramos ver la imagen del medio (la segunda opción) ya que esta puede ser vista desde la primera imágen donde se tendrá que correr el panel a la izquierda (de forma negativa) o desde la tercera imagen donde se tendrá que correr el panel a la derecha (de forma positiva). Como el estado inicial esta en la primera opción, la dirección por defecto va con -1 para que el panel se corra a la izquierda.

Ahora vamos a crear el objeto encargado de gestionar la animación, este es de tipo **Timer** y en el momento de su ejemplificación este debe recibir dos parámetros:

* **Delay:** Que es un numero entero y representa el tiempo en milisegundos donde creara un retraso en el movimiento y de esa forma se pueda apreciar la animación, sin este el objeto se movería de un lado al otro de golpe.
* **ActionListener:** Un Objeto Timer debe recibir un Objeto tipo ActionListener o en su defecto una clase que implemente esta interfaz, esto ya que la animación se realiza exclusivamente dentro de eventos **ActionListener**.
* **Declaración:**

```
private Timer timer;
```

* **Ejemplificación:**

```
// Dentro del constructor
this.timer=new Timer(1, this);
```

Como delay vamos a dejar 1, este es el numero que mas se suele dejar y que deja ver la animación de forma fluida, lo siguiente que nos pide es un objeto **ActionListener** como nuestra clase **LoginComponent** implementa esta interfaz insertamos esta clase por medio el **this**.

_**Nota:** Por precaución es mejor realizar la ejemplificación de este objeto antes de la inyección con la clase template, esto para que el timer este listo antes de la creación de la interfaz y pueda funcionar correctamente. También se debe aclarar que en Java existen varios tipos de Objetos "Timer" pero el que estamos usando es específicamente de la librería Swing._

```
import javax.swing.Timer;
```

Como el Timer esta estrictamente relacionado con los eventos **ActionListener** vamos a tener que hacer algunos cambios, ya que la acción de entrar, registrarse o cerrar no tienen nada que ver con la animación y si se dejan dentro del **ActionListener** creara conflictos asi que vamos a pasar estas acciones al **MouseListener** específicamente al evento **MouseClicked**.

<figure><img src="https://camo.githubusercontent.com/878709c4fd7486700ee758f7a5c094a216c6d40f61a5ae4ebdb1e633dd6f76db/68747470733a2f2f692e696d6775722e636f6d2f6b72523575464d2e706e67" alt=""><figcaption></figcaption></figure>

Traslado de métodos de botones hacia MouseListener

Para su buen funcionamiento recuerde agregar la escucha de eventos **MouseListener** al botón **bCerrar** y quitar la escucha de los eventos **ActionListener** a los botones **bCerrar, bEntrar y bRegistrarse**.

* **bCerrar.addMouseListener(loginComponent);**
* ~~bCerrar.addActionListener(loginComponent);~~
* ~~bEntrar.addActionListener(loginComponent);~~
* ~~bRegistrarse.addActionListener(loginComponent);~~

Ahora nuestro método **ActionPerformed** esta con una sola condición:

```
if (e.getSource() == loginTemplate.getBOpcion1())
    JOptionPane.showMessageDialog(null, "Boton Opcion", "Advertencia", 1);
```

Pero este nos esta sacando error, primero por que hemos cambiado el nombre del método para obtener los botones de opción, ahora se llama **getBOpcion** y ademas este debe exigir que se envié como argumento un numero que indica cual de los 3 botones queremos.

* **1:** Devolverá el botón **bOpcion1**.
* **2:** Devolverá el botón **bOpcion2**.
* **3:** Devolverá el botón **bOpcion3**.

Vamos a arreglar esto, ademas vamos a agregar los if correspondientes a los otros botones y vamos a dejar vaciá cada opción.

```
@Override
public void actionPerformed(ActionEvent e) {
    if (e.getSource() == loginTemplate.getBOpcion(1))

    if (e.getSource() == loginTemplate.getBOpcion(2))

    if (e.getSource() == loginTemplate.getBOpcion(3))
}
```

En cada opción vamos a cambiar el estado para indicar que botón ha sido seleccionado.

```
@Override
public void actionPerformed(ActionEvent e) {
    if (e.getSource() == loginTemplate.getBOpcion(1)){
        this.estado = 1;
    if (e.getSource() == loginTemplate.getBOpcion(2))
        this.estado = 2;
    if (e.getSource() == loginTemplate.getBOpcion(3))
        this.estado = 3;
}
```

Antes de cambiar el estado debemos guardar cual era el estado anterior, esto para volver al estado inicial al botón que antes estaba seleccionado.

```
 @Override
public void actionPerformed(ActionEvent e) {
    this.estadoAnterior = estado;
    if (e.getSource() == loginTemplate.getBOpcion(1))
        this.estado = 1;
    if (e.getSource() == loginTemplate.getBOpcion(2))
        this.estado = 2;
    if (e.getSource() == loginTemplate.getBOpcion(3))
        this.estado = 3;
}
```

También podemos cambiar el estado del botón antes seleccionado para que vuelva a su estado original antes de cambiar el nuevo estado:

```
@Override
public void actionPerformed(ActionEvent e) {
    this.estadoAnterior = estado;
    loginTemplate.getBOpcion(estadoAnterior).setIcon(loginTemplate.getIPunto());
    if (e.getSource() == loginTemplate.getBOpcion(1))
        this.estado = 1;
    if (e.getSource() == loginTemplate.getBOpcion(2))
        this.estado = 2;
    if (e.getSource() == loginTemplate.getBOpcion(3))
        this.estado = 3;
}
```

Una vez se cambio el estado del nuevo botón vamos a cambiar el icono al botón que se acabo de seleccionar:

```
@Override
public void actionPerformed(ActionEvent e) {
    this.estadoAnterior = estado;
    loginTemplate.getBOpcion(estadoAnterior).setIcon(loginTemplate.getIPunto());
    if (e.getSource() == loginTemplate.getBOpcion(1))
        this.estado = 1;
    if (e.getSource() == loginTemplate.getBOpcion(2))
        this.estado = 2;
    if (e.getSource() == loginTemplate.getBOpcion(3))
        this.estado = 3;
    loginTemplate.getBOpcion(estado).setIcon(loginTemplate.getIPunto2());
}
```

Finalmente para iniciar la animación vamos a indicarle a nuestro **Timer** que empiece la animación esto con el método **start()**.

```
@Override
public void actionPerformed(ActionEvent e) {
    this.estadoAnterior = estado;
    loginTemplate.getBOpcion(estadoAnterior).setIcon(loginTemplate.getIPunto());
    if (e.getSource() == loginTemplate.getBOpcion(1))
        this.estado = 1;
    if (e.getSource() == loginTemplate.getBOpcion(2))
        this.estado = 2;
    if (e.getSource() == loginTemplate.getBOpcion(3))
        this.estado = 3;
    loginTemplate.getBOpcion(estado).setIcon(loginTemplate.getIPunto2());
    timer.start();
}
```

Ahora vamos a crear el método que se encargará de darle movimiento a las imágenes, la llamaremos **moverImagenes**:

```
private void moverImagenes(){
}
```

Lo primero que haremos es un **Switch / Case** que se realizara por medio del estado seleccionado:

```
private void moverImagenes(){
    switch(estado){
        case 1:

            break;
        case 2:
            
            break;
        case 3:
            
            break;
    }
}
```

La animación consiste en mover horizontalmente el panel que contiene las imágenes, en este caso **pSgv**, lo primero que vamos a codificar es el **Punto de freno** el cual va a parar la animación:

```
private void moverImagenes(){
    switch(estado){
        case 1:
            if(loginTemplate.getPSvg().getX() == 100)
                timer.stop();
            else

            break;
        case 2:
            if(loginTemplate.getPSvg().getX() == -500)
                timer.stop();
            else

            break;
        case 3:
            if(loginTemplate.getPSvg().getX() == -1100)
                timer.stop();
            else

            break;
    }
}
```

Vamos a explicar un poco lo que realizamos:

* Para el primer caso nuestra referencia será la posición inicial del Panel, este empieza en la posición **100px** con respecto al eje X. Entonces este sera nuestro punto de freno ya que cuando se oprima la primera opción el panel debería estar posicionado como estaba originalmente.
* Para el segundo caso queremos que el panel se mueva hacia la izquierda si empezamos desde la primera opción o hacia la derecha si empezamos desde la tercera opción, hasta el punto en que la segunda imagen pueda ser vista, como la posición inicial del panel es **100px** para que se vea la segunda imágen sea visible, el panel deberá tomar valores negativos en el eje X respecto a toda la ventana, cada imágen tiene un ancho de **500px** y cada una de estas están separadas por **100px** asi que calculamos que debe parar una vez haya recorrido un total de **600px** a la izquierda o derecha, es decir en la posición **-500px (100px - 600px o -1100px + 600px)**.
* Para el tercer caso queremos que el panel se mueva a la izquierda y asi pueda ser mostrada la tercera imagen, nuevamente vamos a recorrer un tramo de **600px**, en este caso desde la perspectiva de la posición inicial, debe ser el doble que la anterior recorriendo **1200px** desde la primera imagen asi que el punto de freno estará cuando el panel se ubique en la posición **-1100px (100px - 1200px o -500px - 600px)**.

Ahora en el caso contrario, cuando no vamos a estar en el **punto de freno** vamos a cambiar la posición del panel por lo que vamos a obtener el panel a traves de la clase compañera **loginTemplate** y le vamos a indicar que vamos a modificar su locación con el método **setLocation**.

```
private void moverImagenes(){
    switch(estado){
        case 1:
            if(loginTemplate.getPSvg().getX() == 100)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation();
            break;
        case 2:
            if(loginTemplate.getPSvg().getX() == -500)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation();
            break;
        case 3:
            if(loginTemplate.getPSvg().getX() == -1100)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation();
            break;
    }
}
```

Para los tres casos el movimiento sera unicamente horizontal por lo que el eje Y no se alterará, así que vamos a dejar esa configuración en los tres casos igual y dejaremos el espació para el eje X que si cambiara para cada caso, para obtener su posición en el eje Y basta con llamar al método **getY**:

```
private void moverImagenes(){
    switch(estado){
        case 1:
            if(loginTemplate.getPSvg().getX() == 100)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation( 
                    , loginTemplate.getPSvg().getY()
                );
            break;
        case 2:
            if(loginTemplate.getPSvg().getX() == -500)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation( 
                    , loginTemplate.getPSvg().getY()
                );
            break;
        case 3:
            if(loginTemplate.getPSvg().getX() == -1100)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation( 
                    , loginTemplate.getPSvg().getY()
                );
            break;
    }
}
```

Ahora vamos a configurar la animación para cada caso.

* En el primero (Cuando se oprima el botón **bOpcion1**) suponemos que el Panel ya se ha movido previamente a la izquierda para mostrar alguna de las imágenes restantes, así que para volver a mostrar la primer imágen debemos volver a correr el panel hacia la derecha en este caso sumándole un 1. Para esto debemos obtener primero la posición actual en el eje X del panel con el método **getX** y se le sumara un 1:

```
private void moverImagenes(){
    switch(estado){
        case 1:
            if(loginTemplate.getPSvg().getX() == 100)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation( 
                    loginTemplate.getPSvg().getX() + 1, loginTemplate.getPSvg().getY()
                );
            break;
        case 2:
            if(loginTemplate.getPSvg().getX() == -500)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation( 
                    , loginTemplate.getPSvg().getY()
                );
            break;
        case 3:
            if(loginTemplate.getPSvg().getX() == -1100)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation( 
                    , loginTemplate.getPSvg().getY()
                );
            break;
    }
}
```

* En el tercer caso (Cuando se oprima el botón **bOpcion3**) suponemos que el Panel debe moverse hacia la izquierda para mostrar la tercera imágen sin importar si se ha mostrado la primera o segunda imágen, en este caso para correr el panel a la izquierda le restamos un 1 a la posición actual. Para esto debemos obtener primero la posición actual en el eje X del panel con el método **getX** y se le restará un 1:

```
private void moverImagenes(){
    switch(estado){
        case 1:
            if(loginTemplate.getPSvg().getX() == 100)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation( 
                    loginTemplate.getPSvg().getX() + 1, loginTemplate.getPSvg().getY()
                );
            break;
        case 2:
            if(loginTemplate.getPSvg().getX() == -500)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation( 
                    , loginTemplate.getPSvg().getY()
                );
            break;
        case 3:
            if(loginTemplate.getPSvg().getX() == -1100)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation( 
                    loginTemplate.getPSvg().getX() - 1, loginTemplate.getPSvg().getY()
                );
            break;
    }
}
```

* En el segundo caso (Cuando se oprima el botón **bOpcion2**) dependemos de una dirección ya que pueden haber dos casos, si se esta mostrando la imagen 1, para mostrar la segunda imágen se debe correr el panel hacia la izquierda (es decir restarle un 1 a la posición actual), por otro lado si se está mostrando la imágen 3, para mostrar la segunda imagén se debe recorrer el panel hacia la derecha (es decir sumarle un 1 a la posición actual).

Para esto vamos a realizar una configuración adicional dentro del **ActionPerformed** en los botones **bOpcion1 y bOpcion3** y sera configurar la dirección.

```
@Override
public void actionPerformed(ActionEvent e) {
    this.estadoAnterior = estado;
    loginTemplate.getBOpcion(estadoAnterior).setIcon(loginTemplate.getIPunto());
    if (e.getSource() == loginTemplate.getBOpcion(1)){
        this.estado = 1;
        this.direccion = -1;
    }
    if (e.getSource() == loginTemplate.getBOpcion(2))
        this.estado = 2;
    if (e.getSource() == loginTemplate.getBOpcion(3)){
        this.estado = 3;
        this.direccion = 1;
    }
    loginTemplate.getBOpcion(estado).setIcon(loginTemplate.getIPunto2());
    timer.start();
}
```

Ahora en el caso 2 simplemente le vamos a sumar la **dirección** a la posición Actual del panel.

```
private void moverImagenes(){
    switch(estado){
        case 1:
            if(loginTemplate.getPSvg().getX() == 100)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation( 
                    loginTemplate.getPSvg().getX() + 1, loginTemplate.getPSvg().getY()
                );
            break;
        case 2:
            if(loginTemplate.getPSvg().getX() == -500)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation( 
                    loginTemplate.getPSvg().getX() + direccion, loginTemplate.getPSvg().getY()
                );
            break;
        case 3:
            if(loginTemplate.getPSvg().getX() == -1100)
                timer.stop();
            else
                loginTemplate.getPSvg().setLocation( 
                    loginTemplate.getPSvg().getX() - 1, loginTemplate.getPSvg().getY()
                );
            break;
    }
}
```

Nuestro método esta listo, ahora vamos a llamar este método al final del **ActionPerformed** justo después de iniciar el **Timer**:

```
@Override
public void actionPerformed(ActionEvent e) {
    this.estadoAnterior = estado;
    loginTemplate.getBOpcion(estadoAnterior).setIcon(loginTemplate.getIPunto());
    if (e.getSource() == loginTemplate.getBOpcion(1)){
        this.estado = 1;
        this.direccion = -1;
    }
    if (e.getSource() == loginTemplate.getBOpcion(2))
        this.estado = 2;
    if (e.getSource() == loginTemplate.getBOpcion(3)){
        this.estado = 3;
        this.direccion = 1;
    }
    loginTemplate.getBOpcion(estado).setIcon(loginTemplate.getIPunto2());
    timer.start();
    moverImagenes();
}
```

Si corremos nuestra aplicación veremos algo como esto:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase12/raw/master/gifs/Animacion1.gif" alt=""><figcaption></figcaption></figure>

Primer prueba de animación

Se puede apreciar la animación y el cambio del estado del botón, sin embargo se puede observar algunos detalles con la animación que no están muy bien, en la siguiente sección vamos a hablar de algunas particularidades para entender como funciona una animación a traves de un **Timer** y como resolver algunos conflictos que son visibles y algunos otros no.

### Particularidades con las animaciones

Como pudimos ver en la anterior demostración hay ciertos conflictos al realizar la animación ya que se ven rastros de las imágenes a medida que se van moviendo, ademas de este existen otras particularidades que debemos revisar.

Para empezar un **Timer** funciona como si fuera un Hilo a traves del método **ActionPerformed** asi que lo que hace es crear un ciclo que recorre todas las instrucciones que hay dentro de este evento hasta que llegue a un **Punto de freno**. Esta situación se cumple salvo ciertas situaciones, ya que si dentro del método **ActionPerformed** hay alguna estructura condicional (if) las instrucciones dentro de este condicional se realizaran una sola vez como si de la activación regular del evento se tratara, en cambio con las instrucciones que están directamente en el método sin estar contenido bajo alguna condición se repetirán hasta que se llegue al **Punto de freno**. A continuación podemos ver cuales se repetirán y cuales no.

<figure><img src="https://camo.githubusercontent.com/f2c07b9703e07600880bc7ec32d659371252374a53c8aec8862fae65ebcb2e31/68747470733a2f2f692e696d6775722e636f6d2f36455031564e372e706e67" alt=""><figcaption></figcaption></figure>

Acciones que se repiten y no dentro del ActionPerformed

Para comprobar esto vamos a realizar una prueba metiendo en cada condición el comienzo del **Timer** y la llamada del método **moverImagenes**.

```
@Override
public void actionPerformed(ActionEvent e) {
    this.estadoAnterior = estado;
    loginTemplate.getBOpcion(estadoAnterior).setIcon(loginTemplate.getIPunto());
    if (e.getSource() == loginTemplate.getBOpcion(1)){
        this.estado = 1;
        this.direccion = -1;
        timer.start();
        moverImagenes();
    }
    if (e.getSource() == loginTemplate.getBOpcion(2)){
        this.estado = 2;
        timer.start();
        moverImagenes();
    }
    if (e.getSource() == loginTemplate.getBOpcion(3)){
        this.estado = 3;
        this.direccion = 1;
        timer.start();
        moverImagenes();
    }
    loginTemplate.getBOpcion(estado).setIcon(loginTemplate.getIPunto2());
}
```

Si ejecutamos nuestra aplicación notaremos algo como esto:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase12/raw/master/gifs/Animacion2.gif" alt=""><figcaption></figcaption></figure>

Noten que a medida que se da click la imagen se moverá pero solo una vez, asi que es necesario dar varios clicks sobre el botón **bOpcion2** para que la imagen se vaya moviendo más. Ahora bien volviendo a como teníamos el método anteriormente notamos que hay varios problemas aquí, por ejemplo acciones como:

* El cambio del estadoAnterior.
* El Cambio de imagen del botón anteriormente seleccionado.
* El Cambio de imagen del botón que se selecciono.
* El inicio del Timer.

Son acciones que no queremos que se repitan, por que cada vez que el panel se esta moviendo un pixel se están repitiendo estas acciónes y de hecho la única acción que queremos que se repita es la llamada al método **moverImagenes** para que la animación se vea fluida, las anteriores instrucciones aunque no consumen mucho rendimiento dentro de muchas iteraciones como es el caso de una animación empieza a cobrar factura con el rendimiento de nuestra aplicación.

Tenemos varias opciones aquí, podríamos méter todas estas instrucciones en cada una de las opciones, aunque esto hará que repitamos ese código 3 veces, asi que una mejor opción es envolver todas las instrucciones anteriores a la llamadá del método **moverImagenes** en un If que haga una discriminación de clases por ejemplo así:

```
@Override
public void actionPerformed(ActionEvent e) {
    if(e.getSource() instanceof JButton){
        this.estadoAnterior = estado;
        loginTemplate.getBOpcion(estadoAnterior).setIcon(loginTemplate.getIPunto());
        if (e.getSource() == loginTemplate.getBOpcion(1)){
            this.estado = 1;
            this.direccion = -1;
        }
        if (e.getSource() == loginTemplate.getBOpcion(2))
            this.estado = 2;
        if (e.getSource() == loginTemplate.getBOpcion(3)){
            this.estado = 3;
            this.direccion = 1;
        }
        loginTemplate.getBOpcion(estado).setIcon(loginTemplate.getIPunto2());
        timer.start();
    }
    moverImagenes();
}
```

De esta forma la única instrucción que esta directamente en el **ActionPerformed** sera la llamada del método **moverImagenes** y las otras instrucciones solo se realizaran una vez. Usted puede comprobar la veracidad de esto colocando un mensaje en consola con la instrucción **System.out.println(estadoAnterior);** en ambos casos, y vera que con el código anterior este mensaje se mostrara muchas veces hasta que pare la animación y con el código actual solo se mostrara una vez.

Por otro lado cuando hay movimientos es normal que nuestra interfaz no pueda reaccionar adecuadamente por lo que hay que ayudarle un poco, la forma de hacerlo es diciendole que se debe actualizar por cada iteración que se realice y asi no se vean los rastros de las imágenes mientras se están moviendo. Recordamos que para actualizar la ventana debemos llamar al método **repaint**, en este caso vamos a poner esta instrucción al final del método **moverImagenes** aunque también se podría colocar al final del **ActionPerformed**, en ambos casos el efecto sera igual:

<figure><img src="https://camo.githubusercontent.com/e0f0121be1afd04bc5234b4720a64f7425567d6db710d191e3f07b4a115e61de/68747470733a2f2f692e696d6775722e636f6d2f76334842784a4e2e706e67" alt=""><figcaption></figcaption></figure>

Actualización de la ventana por cada iteración dentro de la animación.

Si ejecutamos nuestra aplicación se verá así:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase12/raw/master/gifs/Animacion3.gif" alt=""><figcaption></figcaption></figure>

Animación mejorada

Podemos observar que hemos realizado nuestra animación y funciona perfectamente.

## Animaciones para muestra de información.

Las animaciones además de darle interactividad a nuestras interfaces gráficas también pueden ser nuestras aliadas para mostrar información adicional que posiblemente no podamos ubicar dentro de las dimensiones de nuestra interfaz. Para ilustrar este ejemplo vamos a enfocarnos en nuestra vista principal y especialmente en el componente **inicio**. Como recordaremos en la parte superior de nuestro componente **Inicio** tenemos una serie de tarjetas que hablan acerca de la organización.

![](https://camo.githubusercontent.com/f4ac7e2fe681e0a4f86ead34e4595207b75b673a4a1091eccfc2584d34bb711a/68747470733a2f2f692e696d6775722e636f6d2f485155684a66682e706e67)

Vista Principal mostrando el componente Inicio

Ahora supongamos que la organización quiere mostrar más aspectos sobre ellos en esas tarjetas, podemos comprobar claramente que no tenemos espacio para colocarlas en nuestra interfaz, bien pues podemos posicionarlas más allá de los limites de las dimensiones de nuestra ventana y a traves de dos botones mostrar estas nuevas tarjetas. Vamos a hacerlo.

#### **Preparativos para crear la animación.**

Para empezar vamos a agregar 3 nuevas tarjetas a nuestro componente **Inicio** asi que vamos a nuestra clase **InicioTemplate** y vamos a declarar tres nuevos paneles, ya que recordemos que el enfoque de reutilización usado para las tarjetas era de incorporación.

* **Declaración:**

```
private JPanel pUsuarios, pDesarrollo, pGrupo;
```

Ahora bien la animación estará enfocada en las tarjetas, sin embargo son 6 tarjetas que tendremos que animar y configurar la animación para cada una resultara muy tedioso, es por eso que al igual que en el login vamos a crear un Panel que contenga estas tarjetas y de esta forma animar un único panel:

* **Declaración:**

```
private JPanel pTarjetas;
```

Ahora vamos a terminar la creación de los paneles que acabamos de declarar y ademas vamos a cambiar la agregación de los paneles que anteriormente habíamos agregado directamente al componente (**pMision, pVision, pNosotros**) ahora se agregaran al panel **pTarjetas** también.

```
public void crearJPanels(){

    this.pTarjetas = sObjGraficos.construirJPanel(0, 0, 2000, 245, new Color(0, 0, 0, 0), null);
    this.add(pTarjetas);

    this.pMision = sObjGraficos.construirJPanel(20, 15, 256, 230, Color.WHITE, null);
    pTarjetas.add(pMision);

    this.pVision = sObjGraficos.construirJPanel(296, 15, 256, 230, Color.WHITE, null);
    pTarjetas.add(pVision);
    
    this.pNosotros = sObjGraficos.construirJPanel(572, 15, 256, 230, Color.WHITE, null);
    pTarjetas.add(pNosotros);
    
    this.pUsuarios = sObjGraficos.construirJPanel(848, 15, 256, 230, Color.WHITE, null);
    pTarjetas.add(pUsuarios);
    
    this.pDesarrollo = sObjGraficos.construirJPanel(1124, 15, 256, 230, Color.WHITE, null);
    pTarjetas.add(pDesarrollo);
    
    this.pGrupo = sObjGraficos.construirJPanel(1400, 15, 256, 230, Color.WHITE, null);
    pTarjetas.add(pGrupo);

    ...
    ...
}
```

Noten que nuestro panel **pTarjetas** tienen un ancho de **2000px** lo cual es muy ancho y solo una parte de este se vera en pantalla, los demás paneles se agregan y se distribuyen sobre este de manera horizontal y uniforme, también tiene un color de fondo transparente.

Ahora recordemos que cada una de estas tarjetas tienen ciertas imágenes asi que las vamos a crearlas dentro del componente, también vamos a necesitar dos imágenes mas para dos botones que crearemos y que nos ayudaran con la animación:

* **Declaración:**

```
private ImageIcon iTarjeta4, iTarjeta5, iTarjeta6, iDerecha, iIzquierda, iDimAux;
```

* **Ejemplificación:**

```
// Dentro del método crearObjetosDecoradores
this.iTarjeta4 = new ImageIcon("Clase12/resources/img/tarjeta4.jpg");
this.iTarjeta5 = new ImageIcon("Clase12/resources/img/tarjeta5.jpg");
this.iTarjeta6 = new ImageIcon("Clase12/resources/img/tarjeta6.jpg");
this.iDerecha = new ImageIcon("Clase12/resources/img/derecha.png");
this.iIzquierda = new ImageIcon("Clase12/resources/img/izquierda.png");
```

Ahora vamos a crear los dos botones antes mencionados:

* **Declaración:**

```
private JButton bDerecha, bIzquierda;
```

* **Método crearJButtons:**

```
public void crearJButtons(){
    iDimAux = new ImageIcon(
        iIzquierda.getImage().getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
    );

    bIzquierda = sObjGraficos.construirJButton(
        null, 0, 125, 20, 20, sRecursos.getCMano(), iDimAux, null, null, null, null, "c", false
    );
    bIzquierda.addActionListener(inicioComponent);
    this.add(bIzquierda);

    iDimAux = new ImageIcon(
        iDerecha.getImage().getScaledInstance(20, 20, Image.SCALE_AREA_AVERAGING)
    );

    bDerecha = sObjGraficos.construirJButton(
        null, 830, 125, 20, 20, sRecursos.getCMano(), iDimAux, null, null, null, null, "c", false
    );
    bDerecha.addActionListener(inicioComponent);
    this.add(bDerecha);
}
```

Podemos notar que estos Botones se están agregando directamente al componente y no a otro panel creado en el, también notamos que se esta agregando de una vez la escucha a eventos **ActionListener** sin embargo nuestra clase **InicioComponent** aun no ha implementado esta interfaz, esto provocará un error asi que por ahora podemos dejar comentada esas dos lineas de código y en la siguiente sección corregiremos el error.

* **Llamada del método dentro del constructor:**

Para evitar conflictos en el eje Z y para que los botones permanezcan siempre encima de las tarjetas vamos a llamar este método dentro del constructor antes de la construcción de los paneles.

```
public InicioTemplate(InicioComponent inicioComponent){
    ...
    ...
    this.crearObjetosDecoradores();
    this.crearJButtons();
    this.crearJPanels();
    this.crearContenidoPMision();
    this.crearContenidoPVision();
    this.crearContenidoPNosotros();
    ...
    ...
}
```

Se van a crear las otras 3 tarjetas de la misma manera que hicimos con las 3 anteriores, así que se va a crear un método por cada una, podríamos realizar la automatización de estas a traves del uso de servicios pero para no hacer mas larga la sesión continuaremos con el modelo que tenia la aplicación:

* **Tarjeta Usuarios:**

```
public void crearContenidoPUsuarios(){
    this.pUsuarios.add(
        new TarjetaComponent(
            "Nuestros Usuarios", 
            iTarjeta4, 
            "Creamos experiencias de aprendizaje acordes a nuestros usuarios."
        ).getTarjetaTemplate()
    );
}
```

* **Tarjeta Desarrollo:**

```
public void crearContenidoPDesarrollo(){
    this.pDesarrollo.add(
        new TarjetaComponent(
            "Desarrollo", 
            iTarjeta5, 
            "Nuestro Enfoque principal esta en la creación de Software."
        ).getTarjetaTemplate()
    );
}
```

* **Tarjeta Grupo:**

```
public void crearContenidoPGrupo(){
    this.pGrupo.add(
        new TarjetaComponent(
            "El grupo", 
            iTarjeta6, 
            "Nuestra comunidad y el aspecto social es lo mas importante."
        ).getTarjetaTemplate()
    );
}
```

* **Llamada de los métodos en el constructor:**

```
// Dentro del constructor
this.crearContenidoPUsuarios();
this.crearContenidoPDesarrollo();
this.crearContenidoPGrupo();
this.crearContenidoPAcciones();
```

Nuestra aplicación al ejecutarla se verá asi:

<figure><img src="https://camo.githubusercontent.com/36cf180e88ba7660248005915ffc5ad549d6b9a51571c54ceb79072bd2186727/68747470733a2f2f692e696d6775722e636f6d2f46454569414e612e706e67" alt=""><figcaption></figcaption></figure>

Componente inicio después de los cambios realizados

Hasta el momento no hay un mayor cambio evidente salvo los dos botones a los costados de nuestro componente sin embargo sabemos que nuestras tarjetas están ubicadas después de los limites de nuestra ventana.

Por ultimo vamos a crear los métodos **get** a los dos botones y al panel que contiene las tarjetas:

```
public JButton getBDerecha(){
    return bDerecha;
}

public JButton getBIzquierda(){
    return bIzquierda;
}

public JPanel getPTarjetas(){
    return pTarjetas;
}
```

#### **Realizando la animación**

Ahora vamos a concentrarnos en la clase **InicioComponent**, lo primero que haremos es implementar la interfaz **ActionListener** y su respectivo método:

```
public class InicioComponent implements ActionListener {
    ...
    ...
}
```

```
@Override
public void actionPerformed(ActionEvent e) {
}
```

Esto nos debe quitar el error que teníamos en la clase **InicioTemplate** con la adición de la escucha de estos eventos en los botones asi que podemos descomentarlos.

Ahora vamos a crear el objeto **Timer** que es el encargado de gestionar la animación.

* **Declaración:**

```
private Timer timer;
```

* **Ejemplificación:**

```
// Dentro del constructor
timer = new Timer(1, this);
```

Recordemos que por prevención ejemplificamos este objeto antes de crear la inyección con la clase **InicioTemplate**.

Vamos a declarar por ultimo dos atributos enteros que nos ayudaran con el propósito de la animación:

```
private int direccion, posicionInicial;
```

* La dirección nos va indicar hacia que lado se va a mover el panel **pTarjetas**.
* La posición inicial nos indicara la posición exacta del panel **pTarjetas** una vez inicia la animación.

Ahora dentro del método implementado **ActionPerformed** vamos a realizar una discriminación de objetos con nuestros botones:

```
@Override
public void actionPerformed(ActionEvent e) {
    if(e.getSource() == inicioTemplate.getBIzquierda())

    if(e.getSource() == inicioTemplate.getBDerecha())
}
```

Dentro de cada condicional vamos a configurar la direccion pero hay que tener algo de cuidado ya que el movimiento que queremos hacer esta cruzado, es decir:

* Cuando oprimamos el boton **bDerecha** queremos ver las tarjetas que están más a la derecha esto quiere decir que debemos correr el panel a la izquierda (-1).
* Cuando oprimamos el boton **bIzquierda** queremos ver las tarjetas que están más a la izquierda esto quiere decir que debemos correr el panel a la derecha (1).

```
@Override
public void actionPerformed(ActionEvent e) {
    if(e.getSource() == inicioTemplate.getBIzquierda())
        this.direccion = 1;
    if(e.getSource() == inicioTemplate.getBDerecha())
        this.direccion = -1;
}
```

Ahora antes de que empiece la animación queremos en ambos casos capturar la posición inicial de donde se encuentra el panel **pTarjeta** asi que lo pondremos debajo de los condicionales. Recordemos que para capturar la posición en el eje X (nuevamente es el único eje que nos interesa por que solo habrá movimiento sobre este) debemos llamar al método **getX**.

```
@Override
public void actionPerformed(ActionEvent e) {
    if(e.getSource() == inicioTemplate.getBIzquierda())
        this.direccion = 1;
    if(e.getSource() == inicioTemplate.getBDerecha())
        this.direccion = -1;
    posicionInicial = inicioTemplate.getPTarjetas().getX();
}
```

Ahora esta todo listo para que inicie la animación por lo que vamos a activar al Timer:

```
@Override
public void actionPerformed(ActionEvent e) {
    if(e.getSource() == inicioTemplate.getBIzquierda())
        this.direccion = 1;
    if(e.getSource() == inicioTemplate.getBDerecha())
        this.direccion = -1;
    posicionInicial = inicioTemplate.getPTarjetas().getX();
    this.timer.start();
}
```

Como se explico previamente debemos tener cuidado con las instrucciones que no están bajo una condición dentro del **ActionPerformed** y que no queremos que se repitan, este es el caso de las dos ultimas instrucciones ya que solo necesitamos capturar la **posición inicial** una vez o de lo contrario esta se actualizara todo el tiempo, también queremos activar el timer una sola vez cada que se oprime cualquiera de los botones. Para esto los envolveremos en una discriminación de clases.

```
@Override
public void actionPerformed(ActionEvent e) {
    if(e.getSource() instanceof JButton){
        if(e.getSource() == inicioTemplate.getBIzquierda())
            this.direccion = 1;
        if(e.getSource() == inicioTemplate.getBDerecha())
            this.direccion = -1;
        posicionInicial = inicioTemplate.getPTarjetas().getX();
        this.timer.start();
    }
}
```

Es hora de crear el método que se encargara de la animación pero vamos a crear dos enfoques que serán explicados en la siguiente sección.

### Enfoques de animación.

A continuación vamos a realizar dos enfoques de animaciónes:

* El primero mostrará las otras 3 tarjetas una vez se oprima el boton de la derecha y volverá a mostrar las 3 tarjetas anteriores una vez se oprima el botón de la izquierda, es decir que solo habrá un movimiento para mostrar las 3 primeras tarjetas o las 3 ultimas.
* El segundo ira recorriendo las tarjetas pero moviendo en tramos cortos ya sea a la izquierda o derecha, esto quiere decir que para mostrar completamente las tarjetas que están de ultimas se deberá oprimir varias veces el boton de la derecha, igualmente en el caso contrario.

Para esto vamos a crear dos métodos:

```
public void moverTarjetas1(){

}

public void moverTarjetas2(){

}
```

#### **Enfoque #1**

Vamos a concentrarnos primero en el método **moverTarjeta1** y vamos a definir primero los **puntos de freno** para eso realizamos un if:

```
public void moverTarjetas1(){
    if(/*Condición para que la animación se detenga*/)
        timer.stop();
    else
}
```

En este caso tenemos 2 **Puntos de Freno**:

* Cuando las primeras 3 tarjetas se están mostrando completamente (como en el estado inicial) y se quiera oprimir el botón **bIzquierda** no debería poder correr el panel más a la derecha ya que no hay mas tarjetas a la izquierda por mostrar. Es decir que cuando el panel esta posicionado en **0px** con respecto al eje X y se quiera oprimir el boton de la izquierda (**1 en dirección**) la animación se va a detener:

```
public void moverTarjetas1(){
    if(
        inicioTemplate.getPTarjetas().getX() == 0 && direccion == 1
    )
        timer.stop();
    else
}
```

* Cuando las ultimas 3 tarjetas se están mostrando completamente y se quiera oprimir el botón **bDerecha** no debería poder correr el panel más a la izquierda ya que no hay mas tarjetas a la derecha por mostrar. Es decir que cuando el panel esta posicionado en **-830px** con respecto al eje X y se quiera oprimir el boton de la derecha (**-1 en dirección**) la animación se va a detener:

```
public void moverTarjetas1(){
    if(
        inicioTemplate.getPTarjetas().getX() == 0 && direccion == 1 ||
        inicioTemplate.getPTarjetas().getX() == -830 && direccion == -1
    )
        timer.stop();
    else
}
```

Ahora en el caso contrario simplemente vamos a indicarle al panel que se mueva sumándole la dirección configurada previamente en el **ActionPerformed**, con el método **setLocation**. Como lo hicimos en el login, la posicion en Y la dejaremos intacta asi que vamos a dejarla con un **getY** mientras que en la posición X se realizara el proceso antes mencionado:

```
public void moverTarjetas1(){
    if(
        inicioTemplate.getPTarjetas().getX() == 0 && direccion == 1 ||
        inicioTemplate.getPTarjetas().getX() == -830 && direccion == -1
    )
        timer.stop();
    else
        inicioTemplate.getPTarjetas().setLocation(
            inicioTemplate.getPTarjetas().getX() + direccion, inicioTemplate.getPTarjetas().getY()
        );
}
```

Finalmente y para que la animación pueda verse fluidamente y sin conflictos de rastros en el movimiento vamos a actualizar la ventana por cada iteración en la animación:

```
public void moverTarjetas1(){
    if(
        inicioTemplate.getPTarjetas().getX() == 0 && direccion == 1 ||
        inicioTemplate.getPTarjetas().getX() == -830 && direccion == -1
    )
        timer.stop();
    else
        inicioTemplate.getPTarjetas().setLocation(
            inicioTemplate.getPTarjetas().getX() + direccion, inicioTemplate.getPTarjetas().getY()
        );
    inicioTemplate.repaint();
}
```

Vamos a llamar al método justo al final del **ActionPerformed** y como queremos que este método se repita en cada iteración de la animación hasta que se detenga la vamos a dejar afuera del condicional:

<figure><img src="https://camo.githubusercontent.com/6ff857ab0da1a3a09b46bb911a15581ee90c4469b2cafc11f44d972ba122fe11/68747470733a2f2f692e696d6775722e636f6d2f535452476972612e706e67" alt=""><figcaption></figcaption></figure>

Llamada del método moverTarjetas1 en ActionPerformed

Una vez corramos nuestra aplicación veremos algo como esto:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase12/raw/master/gifs/Animacion4.gif" alt=""><figcaption></figcaption></figure>

Primer Enfoque de animación implementado

#### **Enfoque #2**

Ahora nos concentraremos en el método **moverTarjetas2**, recordemos que en este no queremos mostrar las otras tarjetas en una sola animación sino que vamos a recorrer todo el panel **pTarjetas** en tramos.

Podemos guiarnos del anterior método implementado que usaba los **Puntos de frenos** ya que los limites serán los mismos para ambos casos sin embargo para este caso este no sera nuestros **Puntos de freno** son solo los limites, asi que en lugar de parar la animación vamos a indicarle al programa que en esos casos no realice nada, esto con la instrucción **assert true**:

```
public void moverTarjetas2(){
    if(
        inicioTemplate.getPTarjetas().getX() == 0 && direccion == 1 ||
        inicioTemplate.getPTarjetas().getX() == -830 && direccion == -1
    )
        assert true;
    else

}
```

Ahora para el caso contrario vamos a tener que configurar nuestros **puntos de freno** reales:

```
public void moverTarjetas2(){
    if(
        inicioTemplate.getPTarjetas().getX() == 0 && direccion == 1 ||
        inicioTemplate.getPTarjetas().getX() == -830 && direccion == -1
    )
        assert true;
    else{
        if(/*Condición para que la animación se detenga*/)

        else
    }
}
```

En este caso queremos que cada vez que oprimamos el botón **bDerecha o bIzquierda** el panel tenga un movimiento horizontal de **200px** ya sea a la izquierda o derecha. Asi que nuestros **Puntos de freno** serán cuando el panel **pTarjetas** haya recorrido esta cantidad de pixeles. Para poder reconocer si el panel recorrió esta cantidad necesitamos de nuestro atributo **posicionInicial** que se configuro previamente en el **ActionPerformed**:

```
public void moverTarjetas2(){
    if(
        inicioTemplate.getPTarjetas().getX() == 0 && direccion == 1 ||
        inicioTemplate.getPTarjetas().getX() == -830 && direccion == -1
    )
        assert true;
    else{
        if( 
            inicioTemplate.getPTarjetas().getX() == posicionInicial + 200 ||
            inicioTemplate.getPTarjetas().getX() == posicionInicial - 200 
        )
            timer.stop();
        else
        
    }
}
```

Ahora falta configurar nuestra animación que será la misma para en este caso, mover el panel sumandole la **dirección** que fue configurada anteriormente en el **ActionPerformed**:

```
public void moverTarjetas2(){
    if(
        inicioTemplate.getPTarjetas().getX() == 0 && direccion == 1 ||
        inicioTemplate.getPTarjetas().getX() == -830 && direccion == -1
    )
        assert true;
    else{
        if( 
            inicioTemplate.getPTarjetas().getX() == posicionInicial + 200 ||
            inicioTemplate.getPTarjetas().getX() == posicionInicial - 200 
        )
            timer.stop();
        else
            inicioTemplate.getPTarjetas().setLocation(
                inicioTemplate.getPTarjetas().getX() + direccion, inicioTemplate.getPTarjetas().getY()
            );
    }
}
```

Para terminar con el método vamos a actualizar la ventana por cada iteración de la animación:

```
public void moverTarjetas2(){
    if(
        inicioTemplate.getPTarjetas().getX() == 0 && direccion == 1 ||
        inicioTemplate.getPTarjetas().getX() == -830 && direccion == -1
    )
        assert true;
    else{
        if( 
            inicioTemplate.getPTarjetas().getX() == posicionInicial + 200 ||
            inicioTemplate.getPTarjetas().getX() == posicionInicial - 200 
        )
            timer.stop();
        else
            inicioTemplate.getPTarjetas().setLocation(
                inicioTemplate.getPTarjetas().getX() + direccion, inicioTemplate.getPTarjetas().getY()
            );
    }
    inicioTemplate.repaint();
}
```

Finalmente para probar este enfoque vamos a llamar ahora a este método, quitando la llamada del anterior en el **ActionPerformed**:

<figure><img src="https://camo.githubusercontent.com/9fa3e909046ae929ccbd287b73bf50889d44005e3b8093fd8ec2629ea11fc17e/68747470733a2f2f692e696d6775722e636f6d2f6c4f335776516b2e706e67" alt=""><figcaption></figcaption></figure>

Llamada del método moverTarjetas2 en el ActionPerformed

Nuestra animación se vera así:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase12/raw/master/gifs/Animacion5.gif" alt=""><figcaption></figcaption></figure>

Implementación de segundo enfoque.

## Resultado

Si llegaste hasta aquí **!Felicidades!** has aprendido a crear animaciones con ayuda del objeto **Timer**, ademas aprendiste algunas particularidades sobre el uso de este para crear animaciones. Vimos varios usos de las animaciónes y revisamos finalmente varios enfoques para realizar una misma animación. Ahora es turno de que implementes estos conocimientos, la imaginación es el limite.

En la siguiente sesión vamos a ver como dibujar formas, textos, imágenes y demás a traves de un lienzo conocido como **Canvas**.

## Actividad

Implementar las animaciones en tu proyecto para añadirle más interactividad a tus interfaces gráficas.

Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 13

### Objetivos

* Reconocer la forma de utilizar Canvas para pintar diferentes elementos en pantalla e identificar que objetos intervienen en este proceso.
* Identificar las particularidades que tiene cada elemento para pintarse en pantalla y su forma de crearse.
* Explicar el funcionamiento de las aréas en canvas para realizar distintas acciónes entre elementos que pintemos en pantalla.
* Hacer uso introductorio de Eventos del Mouse para pintar objetos en pantalla con una interacción del usuario.

## Antes de Comenzar

Para continuar con el ejercicio deberá actualizar la carpeta **resources/img** ya que se han agregado nuevas imágenes. Estas las puede descargar en este mismo repositorio entrando a la carpeta **Clase13** seguido de **resources/img**.

Recordando un poco nuestro recorrido en la clase anterior revisamos el uso de animaciones a traves del objeto **Timer**, dentro de la exploración de las animación, se vieron temas como **Animaciónes para interactividad, Animaciones para muestra de información, Particularidades de animaciónes y diferentes enfoques de animaciones**

[![](https://github.com/CrissUD/InterfazGraficaJavaClase13/raw/master/gifs/Animacion1.gif)](https://github.com/CrissUD/InterfazGraficaJavaClase13/blob/master/gifs/Animacion1.gif)

## Uso de Canvas para pintar en Interfaces Gráficas

En esta sesión vamos a ver el uso de **Canvas** para pintar varias cosas dentro de nuestras interfaces gráficas de una manera introductoria, para explorar a fondo este tema se verán varios items como:

* **Preparativos para crear el Canvas**.
* **Pintando sobre el Canvas (Figuras / Texto / Imágenes)**.
* **Uso de Areas dentro de Canvas**.
* **Uso de EventosMouseListener sobre Canvas**.

## Preparativos para crear el Canvas.

**Canvas** es un elemento característico de la librería **awt** de Java y es fundamental para la creación de figuras, animaciónes, imágenes y demás formas que no se podrían construir con los objetos gráficos comunes, hasta el momento los objetos gráficos que hemos manejado hacen parte de la librería **Swing** de Java, existen diversas opiniones con el uso combinado de estas dos librerías pero no hay de que preocuparse, al fin de cuentas **Swing** esta totalmente basada en la librería **awt** por lo que esta pensada desde el inicio a convivir con su antecesora.

El uso de canvas es importante en la creación de **Juegos2D** ya que este elemento proporciona muchas libertades para plasmar en pantalla y ademas una gran optimización para animaciónes e interacciones con el usuario. También es usado para la representación de gráficas como diagramas de barras, diagrama pastel, lineas temporales, diagramas de Gantt etc. Canvas no es exclusivo de Java, otros lenguajes como **JavaScript** usan el mismo modelo y tienen los mismos principios para pintar en pantalla.

Vamos a crear un nuevo componente al cual llamaremos **Lienzo** dentro del paquete **components** como este será un nuevo componente se creara con sus respectivas clases.

[![](https://camo.githubusercontent.com/5d26b1b6aaaf6fb4f5ffb895c4d7988a33ffec04c109ff1b7b601638d050f41d/68747470733a2f2f692e696d6775722e636f6d2f626f7335754c532e706e67)](https://camo.githubusercontent.com/5d26b1b6aaaf6fb4f5ffb895c4d7988a33ffec04c109ff1b7b601638d050f41d/68747470733a2f2f692e696d6775722e636f6d2f626f7335754c532e706e67)

Creación del componente Lienzo

Vamos a realizar la estructura básica del componentes, empezamos con la clase **LienzoComponent** y como se ha repetido muchas veces, se realizara, la inyección junto al método get correspondiente de su clase compañera.

* **Declaración clase Template:**

```
// Dentro de la clase LienzoComponent
private LienzoTemplate lienzoTemplate;
```

* **Creación de inyección:**

```
// Dentro del constructor
lienzoTemplate = new LienzoTemplate(this);
```

* **Método get de la clase template:**

```
public LienzoTemplate getLienzoTemplate(){
    return lienzoTemplate;
}
```

Ahora vamos con la clase **LienzoTemplate**, vamos a extender de un objeto tipo **Canvas**, como este es un objeto gráfico es posible realizar la extensión hacia este tipo de objeto, se debe importar la librería para soportar este tipo de objetos:

```
import java.awt.Canvas;
```

```
public class LienzoTemplate extends Canvas{

}
```

Vamos a terminar de cellar la inyección:

* **Declaración de clase Component:**

```
// Dentro de la clase LienzoTemplate
private LienzoComponent lienzoComponent;
```

* **Terminando de crear la inyección:**

```
public LienzoTemplate(LienzoComponent lienzoComponent){
    this.lienzoComponent = lienzoComponent;
}
```

También vamos a necesitar del servició **RecursosService** para obtener varios colores y fuentes:

* **Declaración servicio:**

```
private RecursosService sRecursos;
```

* **Obtención servicio:**

```
// Dentro del constructor
this.sRecursos = RecursosService.getService();
```

Como este componente esta heredando de un **Canvas**, es necesario implementar un método especial típico de un canvas el cual es un **paint**, como estamos heredando y no implementando este método se debe implementar de forma manual y es importante que tenga el decorador **@Override** o de lo contrario para Java este método será otro método cualquiera:

```
@Override
public void paint(Graphics g){

}
```

El decorador **@Override** indica que es un método implementado, como hemos visto con el uso de los eventos, esté método **Paint** es un método especial que se ejecuta automáticamente una vez se llama a la clase **Template**, esto hace parte del ciclo de vida de un canvas y se ejecuta estrictamente después de que se ejecuten las instrucciones del constructor. Si no tiene el decorador mencionado el método será tomado como cualquier otro y se deberá ejecutar manualmente (llamando al método). Por otro lado este método recibe un parámetro de tipo **Graphics**, este es el objeto que se encargará de pintar en pantalla.

Ahora vamos a configurar las características físicas del componente:

```
// Detro del constructor
this.setBounds(2, 2, 496, 566);
this.setBackground(Color.WHITE);
this.setVisible(true);
```

Se puede notar que las coordenadas del componente no están estrictamente al comienzo, están en la posición 2 tanto en X como en Y, esto es por que este lienzo será incorporado dentro del componente **Configuraciones** específicamente dentro de su panel **pDibujo**, recordando un poco este panel cuenta con un borde gris de 2 pixeles de grosor, es por esto que el canvas se posicionara desde este punto y ademas se le restaran 4 pixeles de tamaño con respecto al panel contenedor por este motivo, si se dejara desde la posición inicial y al mismo tamaño del panel **pDibujo** este borde quedaría tapado:

<figure><img src="https://camo.githubusercontent.com/ec52e9ff03000a62a988fbe333c4e936dfc496b3fe15b0f0223b1c544d7a0749/68747470733a2f2f692e696d6775722e636f6d2f5a4957564942372e706e67" alt=""><figcaption></figcaption></figure>

Componente Configuraciones

vamos a incorporar el nuevo componente **Lienzo** al componente **Configuraciones**, para esto nos ubicamos en la clase **ConfiguracionesTemplate** y dentro de está realizaremos la declaración, ejemplificación e incorporación:

* **Declaración:**

```
private LienzoComponent lienzoComponent;
```

* **Ejemplificación:**

```
// Dentro del constructor
this.lienzoComponent = new LienzoComponent();
```

* **Incorporación:**

```
// Dentro del constructor después de la creación de los paneles
this.pDibujo.add(lienzoComponent.getLienzoTemplate());
```

Ahora podemos comprobar la incorporación de nuestro componente, sin embargo, pasa algo curioso, cuando pasamos encima del canvas, como este esta posicionado encima del panel **pDibujos** ya no se están escuchando los **eventos del Mouse**, tenemos varias opciones para solucionar este conflicto. Por ejemplo podemos pasar el código de los eventos del mouse en el hijo, sin embargo esto requiere una modificación del código que ya hemos implementado, para no realizar esta modificación podemos pasar la escucha de los mismos eventos desde el padre contenedor hacia el componente hijo.

Dentro de la clase **LienzoComponent** vamos a pedir como parámetro al panelContenedor, al mismo tiempo se lo vamos a pasar como argumento a la clase **Template**:

```
public LienzoComponent(JPanel pPadre){
    lienzoTemplate = new LienzoTemplate(this, pPadre);
}
```

Esto implica que una vez se ejemplifique el componente dentro de la clase **ConfiguracionesTemplate** se debe pasar el panel que lo contiene:

```
this.lienzoComponent = new LienzoComponent(pDibujo);
```

Ahora en la clase **LienzoTemplate** vamos a recibir como parámetro al panelPadre:

```
public LienzoTemplate(LienzoComponent lienzoComponent, JPanel pPadre){
    ...
    ...
}
```

Vamos a agregar la escucha de cada uno de los eventos del Mouse al componente, para esto llamaremos los métodos correspondientes para la escucha de este tipo de eventos:

```
// Dentro del constructor
this.addMouseListener();
this.addMouseMotionListener();
this.addMouseWheelListener();
```

Ahora vamos a obtener los eventos del mouse que esta escuchando actualmente el padre contenedor, esto lo haremos con los métodos:

* **getMouseListeners**.
* **getMouseMotionListeners**.
* **getMouseWheelListeners**.

Correspondientemente:

```
// Dentro del constructor
this.addMouseListener(pPadre.getMouseListeners());
this.addMouseMotionListener(pPadre.getMouseMotionListeners());
this.addMouseWheelListener(pPadre.getMouseWheelListeners());
```

Ahora seguramente el editor de código nos este marcando un error y esto es por que los métodos anteriormente usados, no van a retornar un evento especifico sino un arreglo de eventos por cada categoría, ya que un objeto perfectamente podría escuchar a dos eventos tipo **MouseListener** por dar un ejemplo. Sin embargo sabemos que el panel **pDibujo** esta escuchando solo un evento de cada tipo asi que en los 3 casos vamos a necesitar el evento ubicado en la posición 0:

```
// Dentro del constructor
this.addMouseListener(pPadre.getMouseListeners()[0]);
this.addMouseMotionListener(pPadre.getMouseMotionListeners()[0]);
this.addMouseWheelListener(pPadre.getMouseWheelListeners()[0]);
```

Ahora una vez abramos nuestra aplicación podemos comprobar que efectivamente ahora el canvas también es capaz de escuchar los eventos del mouse que habíamos configurado para el panel contenedor. Nuestro canvas esta listo para usarse, en la siguiente sección vamos a explicar la forma en como pintar diferentes elementos en pantalla.

<figure><img src="https://camo.githubusercontent.com/ec52e9ff03000a62a988fbe333c4e936dfc496b3fe15b0f0223b1c544d7a0749/68747470733a2f2f692e696d6775722e636f6d2f5a4957564942372e706e67" alt=""><figcaption></figcaption></figure>

Componente Lienzo con la escucha de eventos del Mouse de su componente Padre.

## Pintando sobre el Canvas.

Vamos a explicar a continuación como pintar una serie de figuras, ademas se explicará una serie de particularidades en los momentos pertinentes.

### Pintando Textos / Strings

Vamos a ubicarnos dentro del método **paint** y vamos a usar el objeto **Graphics: g**, este objeto tiene una serie de métodos que nos proporcionara herramientas para pintar sobre el canvas. Para pintar un **Texto** vamos a utilizar el método **drawString**. Este método recibe varias cosas por parámetro:

* **String:** Texto que se va a pintar:
* **Posición X:** Posición del texto en el eje X dentro del canvas.
* **Posición Y:** Posición del texto en el eje Y dentro del canvas.

```
@Override
public void paint(Graphics g){
    g.drawString("Rectangulos", (this.getWidth() / 2) - 50, 15);
}
```

Podemos comprobar que se ha pintado este texto dentro del canvas:

<figure><img src="https://camo.githubusercontent.com/27b5f76580a51b104ba2a37cb0999960de75c60c2aa334717c5f9a8d5c351dfa/68747470733a2f2f692e696d6775722e636f6d2f57776f5733576f2e706e67" alt=""><figcaption></figcaption></figure>

Texto pintado dentro del String

Ademas de pintar un texto podemos proporcionar algunos elementos para decorarlo, por ejemplo podemos darle un color y un tipo de fuente, para esto usaremos al servicio **sRecursos**:

```
@Override
public void paint(Graphics g){
    g.setColor(sRecursos.getColorAzul());
    g.setFont(sRecursos.getFontTitulo());
    g.drawString("Rectangulos", (this.getWidth() / 2) - 50, 15);
}
```

Es importante que los métodos **setColor y setFont** vayan antes de pintar el String o cualquier figura, una vez cambiamos el color le estamos indicando al canvas que todo lo que se vaya a pintar de ahí en adelante tendrá ese color, si quisiéramos pintar mas adelante una figura con otro color se debe llamar nuevamente el método **setColor** y configurarle el color que se usará. Lo mismo pasaría en caso de querer cambiar la fuente:

<figure><img src="https://camo.githubusercontent.com/51e95013d2aae237c49ad565e699271620612ccb5bebd0223d66b5df90fe6be7/68747470733a2f2f692e696d6775722e636f6d2f505938524d55462e706e67" alt=""><figcaption></figcaption></figure>

String pintado con un color y fuente configurada.

Vamos a pintar a continuación otros Strings dentro del canvas, pero para realizar una **Modularización de código** vamos a crear un nuevo método llamado **pintarStrings** que va a recibir como parámetro a un objeto tipo **Graphics** y vamos a llamarlo desde el método paint:

* **Método pintarStrings:**

```
public void pintarStrings(Graphics g){
    g.setColor(sRecursos.getColorAzul());
    g.setFont(sRecursos.getFontTitulo());
    g.drawString("Rectangulos", (this.getWidth() / 2) - 50, 15);
    g.drawString("Arcos", (this.getWidth() / 2) - 23, 165);
    g.drawString("Óvalos y Polígonos", (this.getWidth() / 2) - 65, 315);
    g.drawString("Imágenes", (this.getWidth() / 2) - 35, 465);
}
```

**Llamada del método:**

```
@Override
public void paint(Graphics g){
    this.pintarStrings(g);
}
```

<figure><img src="https://camo.githubusercontent.com/f1ba573ca8bdfa2b15a33d8d7f5c45ba606f6fc87c16d2be433a0ed5cef47eab/68747470733a2f2f692e696d6775722e636f6d2f534563474173412e706e67" alt=""><figcaption></figcaption></figure>

Strings pintados dentro del canvas.

### Pintando Rectángulos

Para pintar rectángulos y figuras en general dentro del canvas el objeto **g** proporcionan dos tipos de métodos:

* **draw**: Dibuja la figura sin un relleno, es decir solo pintara el contorno de la figura.
* **fill**: Dibuja la figura con relleno.

En ambos casos pintara la figura con el color que se ha configurado previamente.

Vamos a crear un método llamado **pintarRectangulos** de igual forma recibirá el objeto **Graphics** para poder pintarlos:

```
public void pintarRectangulos(Graphics g){
    
}
```

Por precaución vamos a configurar el color, esto ya que posiblemente en algún otro punto se podría cambiar la configuración del color en el canvas:

```
public void pintarRectangulos(Graphics g){
    g.setColor(sRecursos.getColorMorado());
}
```

Primero vamos a pintar un rectángulo con relleno para esto usaremos el método **fillRect** que recibe por parámetros:

* **Posición en X**.
* **Posición en Y**.
* **Ancho del rectángulo**.
* **Alto del rectángulo**.

```
public void pintarRectangulos(Graphics g){
    g.setColor(sRecursos.getColorMorado());
    g.fillRect(160, 0, 200, 30);
}
```

Llamamos el método desde el método **paint**:

```
// Dentro de Paint
this.pintarRectangulos(g);
```

<figure><img src="https://camo.githubusercontent.com/8380c8785502c4bfdcf98547f7e60e81c9d2ffd0e9c0c90ac98caf22b2e74abc/68747470733a2f2f692e696d6775722e636f6d2f6c7a766f5a51322e706e67" alt=""><figcaption></figcaption></figure>

Rectángulo pintado dentro del canvas

Se puede observar que el rectángulo se pinto de forma correcta y este tiene relleno, sin embargo este esta tapando al String que previamente habíamos pintado. Esto se hizo a propósito para revisar las particularidades con el **eje Z** y es que a diferencia de los objetos gráficos de **Swing** en el canvas a medida que vamos pintando un elemento, este se va a posicionar más al frente que los elementos previos, asi que hay que tener un cuidado especial con el eje Z en estos casos, vamos a cambiar de lugar y tamaño del rectángulo, ademas vamos a cambiar el color a azul nuevamente:

```
public void pintarRectangulos(Graphics g){
    g.setColor(sRecursos.getColorAzul());
    g.fillRect(15, 65, 100, 50);
}
```

<figure><img src="https://camo.githubusercontent.com/9cda65ce6beadf25f071567b4dab77244302b729cf046a5dc68bf0710015417b/68747470733a2f2f692e696d6775722e636f6d2f6c6653565a6f6d2e706e67" alt=""><figcaption></figcaption></figure>

Rectángulo con relleno pintado.

Vamos a pintar un rectángulo esta vez sin relleno, para eso utilizaremos el método **drawRect** este recibe los mismos parámetros que el anterior método usados:

```
public void pintarRectangulos(Graphics g){
    g.setColor(sRecursos.getColorAzul());
    g.fillRect(15, 65, 100, 50);
    g.drawRect(135, 40, 100, 100);
}
```

<figure><img src="https://camo.githubusercontent.com/27d50000cd7f504b1f90ed6e3f0fe31fcfa1464af6d76b5e4bd3f9c24422262e/68747470733a2f2f692e696d6775722e636f6d2f737432755a41572e706e67" alt=""><figcaption></figcaption></figure>

Rectángulo sin relleno

También podemos pintar rectángulos con la particularidad de tener los bordes redondeados, para hacer esto podemos usar los métodos **fillRoundRect o drawRoundRect** ambos van a pedir por parámetros:

* **Posición en X**.
* **Posición en Y**.
* **Ancho del rectángulo**.
* **Alto del rectángulo**.
* **Ancho del borde redondeado**.
* **Alto del borde redondeado**.

Por lo general se suele dejar el ancho y alto del borde del mismo tamaño y entre mas alto es el numero mas redondeado se vera el borde relativo al tamaño del rectángulo.

```
public void pintarRectangulos(Graphics g){
    g.setColor(sRecursos.getColorAzul());
    g.fillRect(15, 65, 100, 50);
    g.drawRect(135, 40, 100, 100);
    g.fillRoundRect(255, 40, 100, 100, 20, 20);
    g.drawRoundRect(400, 40, 50, 100, 20, 20);
}
```

<figure><img src="https://camo.githubusercontent.com/0fb4c186f73d4db737c2437827813c481f58c9269c061d4375fbb3c72d2d2e77/68747470733a2f2f692e696d6775722e636f6d2f49464b65646d462e706e67" alt=""><figcaption></figcaption></figure>

Rectángulos con bordes redondeados pintados.

### Pintando Lineas

Para dibujar lineas necesitamos el método **drawLine** que recibe como parámetros.

* **Coordenada en X del punto inicial**.
* **Coordenada en Y del punto inicial**.
* **Coordenada en X del punto final**.
* **Coordenada en Y del punto final**.

Vamos a crear el método **pintarLineas** que nuevamente recibirá el objeto **graphics**.

```
public void pintarLineas(Graphics g){
}
```

Dentro del método vamos a configurar el color:

```
public void pintarLineas(Graphics g){
    g.setColor(sRecursos.getColorMorado());
}
```

Vamos a pintar nuestra primera linea:

```
public void pintarLineas(Graphics g){
    g.setColor(sRecursos.getColorMorado());
    g.drawLine(0, 150, 496, 150);
}
```

En este caso el punto inicial esta en las coordenadas **(0 , 150)** mientras su punto final esta en las coordenadas **(496 , 150)**. Se puede observar que en el punto inicial e final la coordenada en Y es la misma, esto quiere decir que sera una linea totalmente horizontal, sin embargo se pueden pintar lineas verticales y diagonales si se quiere.

<figure><img src="https://camo.githubusercontent.com/50c6d622ac663552dacf813707eaeda33691070c93031ed61264d8b52d76b6ba/68747470733a2f2f692e696d6775722e636f6d2f7a57744b475a672e706e67" alt=""><figcaption></figcaption></figure>

Linea pintada en el canvas

Pintaremos un par de lineas mas:

```
public void pintarLineas(Graphics g){
    g.setColor(sRecursos.getColorMorado());
    g.drawLine(0, 150, 496, 150);
    g.drawLine(0, 300, 496, 300);
    g.drawLine(0, 450, 496, 450);
}
```

<figure><img src="https://camo.githubusercontent.com/c61e2446bae9bbddb392a919cae9e4401ad5504cba9bc8815982d9677d90ee5d/68747470733a2f2f692e696d6775722e636f6d2f77524c30696e6b2e706e67" alt=""><figcaption></figcaption></figure>

Lineas pintadas en el Canvas

### Pintando Arcos

Los arcos son figuras curvas que se pintan de acuerdo al posicionamiento basado en grados (°), estos pueden ser meramente curvas o una circunferencia entera en caso de pintar la figura sin relleno, pero en caso de pintar la figura con relleno va a mostrarse partes de un ovalo o circulo o en dado caso un ovalo o circulo completo.

Para dibujar esta figura podemos usar los métodos **fillArc y drawArc** que reciben por parámetros:

* **Posición en X**.
* **Posición en Y**.
* **Ancho de la figura**.
* **Alto de la figura**.
* **Posición en grados donde comienza el arco**.
* **Cantidad de grados que ocupa el arco**.

Vamos a dibujar algunos de estos arcos para comprender un poco el concepto, creamos primero el método **pintarArcos**:

```
public void pintarArcos(Graphics g){
}
```

Vamos a configurar el color del canvas:

```
public void pintarArcos(Graphics g){
    g.setColor(sRecursos.getColorAzul());
}
```

Ahora vamos a pintar un arco con relleno, en este caso solo queremos dibujar una cuarta parte de un circulo, para este caso se debe tener en cuenta varias cosas como:

* Al ser un circulo el ancho y el alto de la figura deben ser iguales.
* Como se quiere representar solo una cuarta parte de un circulo el grado inicial será 0° mientras que la cantidad de grados que ocupa el arco serán 90° (todo un circulo ocupa 360°).

```
public void pintarArcos(Graphics g){
    g.setColor(sRecursos.getColorAzul());

    g.fillArc(15, 190, 100, 100, 0, 90);
}
```

Vamos a llamar este método dentro del **paint**:

```
// Dentro del método paint
this.pintarArcos(g);
```

Nuestra interfaz se vera así:

<figure><img src="https://camo.githubusercontent.com/24e9f15a5a52923728033a919ad601e1ef2342aff0a9d5e754f26f2c300824de/68747470733a2f2f692e696d6775722e636f6d2f50476e79716e652e706e67" alt=""><figcaption></figcaption></figure>

Pintando el primer arco

Ahora queremos pintar su contra parte o espejo, es decir queremos pintar la otra cuarta parte del circulo que estaría ubicada en ela parte inferior izquierda, para lograr esto la figura debe tener el mismo tamaño y las mismas coordenadas de posición, pero deben cambiar su grado de inicio, este ahora debería iniciar en el grado 180°, en cuanto a los grados que ocupa, como sera de nuevo una cuarta parte ocupará los mismos 90°.

```
public void pintarArcos(Graphics g){
    g.setColor(sRecursos.getColorAzul());

    g.fillArc(15, 190, 100, 100, 0, 90);
    g.fillArc(15, 190, 100, 100, 180, 90);
}
```

<figure><img src="https://camo.githubusercontent.com/744ddf1effebaa0680b388ec3859a32f3e94f7393ba1d11784756ee6a58de61e/68747470733a2f2f692e696d6775722e636f6d2f414854683572622e706e67" alt=""><figcaption></figcaption></figure>

Segundo arco pintado

Dibujando arcos como este podemos pintar diagramas pastel para representar datos de forma estadística por dar un ejemplo practico de este tipo de figuras. Para terminar de pintar las otras 2 cuartas partes del circulo vamos a cambiar el color del canvas y los dibujaremos usando la misma lógica.

```
public void pintarArcos(Graphics g){
    g.setColor(sRecursos.getColorAzul());

    g.fillArc(15, 190, 100, 100, 0, 90);
    g.fillArc(15, 190, 100, 100, 180, 90);
    g.setColor(Color.ORANGE);
    g.fillArc(15, 190, 100, 100, 90, 90);
    g.fillArc(15, 190, 100, 100, 270, 90);
}
```

<figure><img src="https://camo.githubusercontent.com/28b8fdea9de5c2bf1d65c01967d543c353ac6d576b8777af0bd3ac2b5eafbb5f/68747470733a2f2f692e696d6775722e636f6d2f4f52594e38654c2e706e67" alt=""><figcaption></figcaption></figure>

Dibujando el resto del circulo.

Vamos a dibujar otro circulo con la misma lógica, pero esta vez sin relleno para crear solo el contorno de la circunferencia:

```
// Dentro del método pintarArcos
g.setColor(sRecursos.getColorAzul());
g.drawArc(135, 190, 100, 100, 0, 90);
g.drawArc(135, 190, 100, 100, 180, 90);
g.setColor(Color.ORANGE);
g.drawArc(135, 190, 100, 100, 90, 90);
g.drawArc(135, 190, 100, 100, 270, 90);
```

<figure><img src="https://camo.githubusercontent.com/014aba0a67e8d69220b36f7f41e7dcff6b61c6a3d4a4d99a4179b39361499f8f/68747470733a2f2f692e696d6775722e636f6d2f585437593856582e706e67" alt=""><figcaption></figcaption></figure>

Dibujando arcos sin relleno

Vamos a dejar otros ejemplos de arcos:

```
// Dentro del método pintarArcos
g.setColor(sRecursos.getColorAzul());
g.fillArc(255, 190, 100, 100, 0, 180);

g.drawArc(375, 190, 100, 100, -15, 90);
g.setColor(Color.ORANGE);
g.drawArc(375, 190, 100, 100, 105, 90);
g.setColor(sRecursos.getColorMorado());
g.drawArc(375, 190, 100, 100, 225, 90);
```

<figure><img src="https://camo.githubusercontent.com/4a69b313273915157cbe9db88540deacaa858d37ffa9d88ac94935bd25dda95a/68747470733a2f2f692e696d6775722e636f6d2f51346a6f686f772e706e67" alt=""><figcaption></figcaption></figure>

Otros arcos dibujados

Antes de continuar dibujando otras figuras podemos darnos cuenta que algunas figuras tienen un aspecto "pixeleado", esto se nota sobre todo en las curvas, como en los arcos o en los bordes redondeados de los recuadros, realmente no queremos que nuestras figuras se vean de esta manera. Podemos ayudarnos de un objeto derivado de Graphics que contiene métodos encargados de la mejora en la calidad del pintado, este objeto es **Graphics2D**. Vamos a crear este objeto para mejorar el aspecto, primero vamos a declarar este objeto:

* **Declaración:**

```
private Graphics2D g2d;
```

Ahora vamos a ejemplificar este objeto, pero como mencionamos este se deriva del objeto **Graphics** por lo que este se creara con el método **create**. También se puede derivar de otros objetos como **Images**, esta ejemplificación la vamos a realizar al comienzo del método **paint** antes de llamar a los métodos de pintado:

```
// Dentro del método paint al comienzo
g2d = (Graphics2D) g.create();
```

Ya tenemos nuestro objeto **Graphics2D** ejemplificado y listo para usar, este objeto cuenta con varios algoritmos de renderizado para mejorar la calidad de lo que se esta pintando en pantalla, para invocar algunos de estos debemos llamar al método **setRenderingHint** y usar al objeto especial de **awt RenderingHints** quien es el objeto que proporciona estos algoritmos, vamos a usar dos de ellos:

```
// Dentro del método paint
g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
g2d.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
```

* **KEY\_ANTIALIASING**: Proporciona un difuminado sutil para que el usuario no persiva una pixelizacion en lo que se esta pintando. Para activarlo debemos llamar al parámetro **VALUE\_ANTIALIAS\_ON**.
* **KEY\_STROKE\_CONTROL**: Es un algoritmo de control que se encarga de activar o desactivar el anterior método **KEY\_ANTIALIASING** solo en caso de ser necesario, por ejemplo para lineas rectas el uso de este algoritmo no será necesario, asi que esto reduce el consumo de recursos innecesarios, se activa con el parámetro **VALUE\_STROKE\_NORMALIZE**.

Ahora vamos a pintar todas nuestras figuras con este objeto por lo que vamos a cambiar el parámetro que reciben nuestros métodos de pintado:

```
 public void pintarStrings(Graphics2D g2d){
     ...
 }
 public void pintarRectangulos(Graphics2D g2d){
     ...
 }
 public void pintarLineas(Graphics2D g2d){
     ...
 }
 public void pintarArcos(Graphics2D g2d){

 }
```

Dentro de cada método de pintado en vez de usar el objeto g (Graphics) para pintar ahora usaremos el objeto g2d (Graphics2D).

<figure><img src="https://camo.githubusercontent.com/fa0ccbe7be197a0365e8b2e7d4a8b5c9bcdf0afa3f2f6b4b003e28bf67c1a12b/68747470733a2f2f692e696d6775722e636f6d2f6c624b575a31422e706e67" alt=""><figcaption></figcaption></figure>

Usando el objeto Graphics2D

Para finalizar, una vez se llamen cada uno de los métodos de pintado vamos a enviar como argumento al objeto Graphics2D:

```
this.pintarStrings(g2d);
this.pintarRectangulos(g2d);
this.pintarLineas(g2d);
this.pintarArcos(g2d);
```

Veamos como luce nuestro canvas ahora:

<figure><img src="https://camo.githubusercontent.com/07f8940a9076e828f2c92a6fa94cce0032127828a9378ba5c94d72c3357f8ece/68747470733a2f2f692e696d6775722e636f6d2f683073327032522e706e67" alt=""><figcaption></figcaption></figure>

Figuras pintadas con una mejor calidad.

Noten que las figuras mejoraron su calidad significativamente y no solo estas, los Strings también tienen una mejor definición de pintado.

### Pintando Óvalos

Los óvalos son circunferencias que se pintan de forma similar a los rectángulos, esto debido a que recibe parámetros similares:

* **Posición en X**.
* **Posición en Y**.
* **Ancho del ovalo**.
* **Alto del ovalo**.

Y también pueden ser pintados mediante los métodos **draw o fill**.

Creamos el método **pintarOvalos**, de una vez vamos a pintarlo con el objeto **Graphics2D**:

```
public void pintarOvalos(Graphics2D g2d){

}
```

Configuramos el color al canvas:

```
public void pintarOvalos(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
}
```

Vamos a dibujar un circulo primero es decir un óvalo con mismas dimensiones de ancho y alto, ademas vamos a dibujarlo con relleno:

```
public void pintarOvalos(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillOval(15, 340, 100, 100);
}
```

Vamos a llamar al método desde **paint** pasandole como argumento el objeto **Graphics2D**:

```
// Dentro del método paint
this.pintarOvalos(g2d);
```

<figure><img src="https://camo.githubusercontent.com/94517ab64dcfee0ec0daff84aa7325adc2048cfc950edf93a76846e64893d7f9/68747470733a2f2f692e696d6775722e636f6d2f536549374335672e706e67" alt=""><figcaption></figcaption></figure>

Dibujando el primer ovalo

Ahora vamos a dibujar dos óvalos con solo su contorno, para esto usaremos el método draw:

```
// Dentro del método pintarOvalos
g2d.drawOval(160, 340, 50, 100);
g2d.drawOval(135, 365, 100, 50);
```

<figure><img src="https://camo.githubusercontent.com/db1e35a7f5f0dc42e1564e361af79b3dcf7a774cd4aca7f30a3bdeb398891109/68747470733a2f2f692e696d6775722e636f6d2f647352727554542e706e67" alt=""><figcaption></figcaption></figure>

Dibujando dos óvalos

### Pintando Polígonos

Los polígonos son figuras abstractas que podemos crear de acuerdo a un sistema de puntos, nosotros podemos indicar cuantos puntos tendrá y las coordenadas de cada uno de estos puntos, el sistema se encargará de unir todos los puntos para crear la figura. Esto quiere decir que para dibujar un polígono se usara los métodos **fillPolygon o drawPolygon** y va a recibir por parámetros:

* **Array de enteros int\[]:** Arreglo que representa las coordenadas de cada uno de los puntos de la figura en el eje X.
* **Array de enteros int\[]:** Arreglo que representa las coordenadas de cada uno de los puntos de la figura en el eje Y.
* **Cantidad de puntos:** El numero de puntos que tiene la figura.

De esta forma la coordenada en X que esta ubicada en la posición \[0] de su arreglo se complementará con la coordenada en Y que esta ubicada en la posición \[0] en su respectivo arreglo.

Vamos a crear el método pintarPoligonos y de una vez vamos a configurar el color al canvas:

```
public void pintarPoligonos(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
}
```

Vamos a crear nuestro primer polígono y en este caso crearemos un **Triangulo**, este tendrá entonces 3 puntos, lo pintaremos con relleno asi que primero llamamos al método **fillPolygon**:

```
public void pintarPoligonos(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillPolygon();
}
```

Vamos a configurar los parámetros necesarios, que son los dos arreglos para las coordenadas en cada eje y el numero de puntos que tiene la figura:

```
public void pintarPoligonos(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillPolygon(
        new int[]{}, new int[]{}, 3
    );
}
```

Ya le pasamos los parámetros necesarios pero ahora en cada uno de los arreglos debemos configurar las coordenadas de cada uno de los 3 puntos, empezamos con el punto de arriba y este será nuestra guiá para configurar las coordenadas de los otros 2 puntos.

```
public void pintarPoligonos(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillPolygon(
        new int[]{305}, new int[]{340}, 3
    );
}
```

En el anterior código estamos indicando que las coordenadas del primer punto son (305 en x, 340 en y). De acuerdo a estas coordenadas iniciales vamos a realizar los otros dos puntos, teniendo en cuenta que este punto es el que estará en la parte superior central del triangulo podríamos configurar el punto que esta mas a la izquierda y en la parte inferior.

```
public void pintarPoligonos(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillPolygon(
        new int[]{305, 255}, new int[]{340, 440}, 3
    );
}
```

Aquí configuramos el segundo punto que esta en las coordenadas (255 en x, 440 en y) y si se dan cuenta restamos pixeles en el eje X por lo que estará 50px mas a la izquierda, por otro lado en el eje Y le sumamos pixeles, esto quiere decir que estará abajo por 100px más. Ahora solo falta configurar el siguiente punto:

```
public void pintarPoligonos(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillPolygon(
        new int[]{305, 255, 355}, new int[]{340, 440, 440}, 3
    );
}
```

Aquí configuramos el tercer punto que esta en las coordenadas (355 en x, 440 en y) y si se dan cuenta sumamos pixeles en el eje X por lo que estará 50px mas a la derecha con respecto al punto del medio, mientras que en el eje Y lo dejamos igual que el anterior punto. Para ver la figura vamos a llamar al método desde **paint**:

```
// Dentro del método paint
this.pintarPoligonos(g2d);
```

<figure><img src="https://camo.githubusercontent.com/afddd73c5b744766284f41534a2382a6574a66a56f38833287dafecbcc5269c7/68747470733a2f2f692e696d6775722e636f6d2f646856793969692e706e67" alt=""><figcaption></figcaption></figure>

Pintando el primer polígono: triangulo

A continuación vamos a realizar un Octágono con la misma lógica antes explicada pero con la diferencia de que no tendrá relleno:

```
// Dentro del método pintarPoligono
g2d.drawPolygon(
    new int[]{400, 450, 475, 475, 450, 400, 375, 375}, 
    new int[]{340, 340, 365, 415, 440, 440, 415, 365}, 
    8
);
```

<figure><img src="https://camo.githubusercontent.com/dcc731721a7593117060f41e974d80816782cc113b16e4cd8b84048696a8d77c/68747470733a2f2f692e696d6775722e636f6d2f715143504a62662e706e67" alt=""><figcaption></figcaption></figure>

Octágono dibujado en el canvas

### Pintando Imágenes

En el canvas también podemos dibujar imágenes, para esto debemos hacer uso del método **drawImage**. Aunque podemos pintar una imagen con el propósito de mostrarla como se haría comúnmente con los Labels, usualmente en canvas y en el desarrollo de videojuegos se toma otro enfoque, ya que se suelen usar **Sprites**, primero explicaremos la forma de pintar una imagen normalmente y luego entraremos a mas detalle con el otro enfoque. Primero creamos el método **pintarImagenes**:

```
public void pintarImagenes(Graphics2D g2d){
    
}
```

Lo primero que vamos a hacer es traernos la imagen a traves de un **ImageIcon**, asi que vamos a declarar un objeto de este tipo y de una vez lo vamos a ejemplificar:

```
// Al inicio de la clase LienzoTemplate
private ImageIcon imagen = new ImageIcon("Clase13/resources/img/sonic.png");
```

Dentro del método **pintarImagenes** vamos a pintar la imagen con el método **drawImagen**, este puede recibir multiples parámetros, pero en esta ocasión vamos a usar el que recibe los parámetros básicos:

* **Imagen**: Esta debe ser de tipo **Image** es decir que es necesario decirle a nuestro objeto **ImageIcon** que queremos obtener su imagen con el método **getImage()**.
* **Posición en X**.
* **Posición en Y**.
* **Ancho de la Imagen**.
* **Alto de la Imagen**.
* **Observable:** Es un objeto que notifica de algún modo en caso de que exista una modificación de una imágen, se suele utilizar en animaciónes asi que por ahora se va a dejar en null.

```
public void pintarImagenes(Graphics2D g2d){
    g2d.drawImage(imagen.getImage(), 230, 480, 40, 80, null);
}
```

Llamamos al método desde **paint**:

```
// Dentro del método paint
this.pintarImagenes(g2d);
```

<figure><img src="https://camo.githubusercontent.com/281def9cf8b4af7b6c694f4923debf26e5fa95475554feb0a9489aa340c467dd/68747470733a2f2f692e696d6775722e636f6d2f6b4e49617278512e706e67" alt=""><figcaption></figcaption></figure>

Pintando una imagén

Sin embargo como hemos mencionado muchas veces pintar imágenes dentro del Canvas implica que se querrá realizar una animación y para esto los desarrolladores se basan en **Sprites**, vamos a mostrar la imagén que queremos pintar para explicar mejor el concepto:

<figure><img src="https://camo.githubusercontent.com/ed13acaffd500e05bd97b64daffe80c3b511cb08a5467db5ad116748f5d795a5/68747470733a2f2f692e696d6775722e636f6d2f647444526c614a2e706e67" alt=""><figcaption></figcaption></figure>

Sprite de Sonic

Como se dan cuenta un **Sprite** consiste en una secuencia que da paso a una animación, en este caso no nos vamos a enfocar en animaciones dentro del canvas pero si a la metodología que se utiliza con el pintado de este tipo de imágenes, por lo general en este tipo de casos no se busca pintar toda la imágen de una vez, mas bien se busca recorrer de alguna forma la imagen para ir mostrando cada parte de la animación.

Para pintar solo un tramo de la imágen general podemos utilizar el método **drawImage** nuevamente pero esta vez vamos a necesitar mas parámetros:

* **Posición inicial en X**.
* **Posición inicial en Y**.
* **Posición final en X**.
* **Posición final en Y**.
* **Posición en X inicial sobre la imagen General**.
* **Posición en Y inicial sobre la imagen General**.
* **Posición en X final sobre la imagen General**.
* **Posición en Y final sobre la imagen General**.
* **Observable:** Por ahora se va a dejar en null.

Noten que ahora se tienen 4 parámetros nuevos y también algunos de ellos han cambiado. Por ejemplo ya no vamos a manejar el ancho y alto de la imagen, vamos a jugar con la posición inicial y final de la imagen dentro del canvas, siendo la posición inicial la coordenada de la **parte superior izquierda**, mientras que la posición final será la de la parte **inferior derecha** de la imágen.

Por otra parte, con los 4 parámetros nuevos que estamos añadiendo es como si estuviéramos creando un cuadro imaginario dentro de la imágen general y solo pintará lo que esta dentro de ese cuadro:

<figure><img src="https://camo.githubusercontent.com/9fc1f82ca59f16f4e049a1c662bfb23380ace04ea0044efce3f669dbc46d757d/68747470733a2f2f692e696d6775722e636f6d2f7169735a724f452e706e67" alt=""><figcaption></figcaption></figure>

Analogía de lo que sucede con los nuevos parámetros

vamos a pintar nuestra primer imágen usando este enfoque, primero debemos obtener la imágen que contiene el **Sprite** asi que declararemos y ejemplificaremos un **ImageIcon** para obtener la imagen:

```
// Al inicio de la clase LienzoTemplate
private ImageIcon sprites = new ImageIcon("Clase13/resources/img/sprites.png");
```

_**Nota:** El otro ImageIcon ya no se usara mas asi que se puede borrar su declaración y ejemplificación._

Vamos a dejar nuevamente vació el método pintarImagenes:

```
public void pintarImagenes(Graphics2D g2d){
}
```

Ahora vamos a pintar nuestra primer imágen con el enfoque mencionado:

```
public void pintarImagenes(Graphics2D g2d){
    g2d.drawImage(
        sprites.getImage(), 90, 490, 135, 550, 0, 0, 45, 60,  null
    );
}
```

En el anterior código estamos indicando:

* La imágen se ubicara en la posición (90 en x, 490 en y) del Canvas.
* La imagen tendrá una posición final en las coordenadas (135 en x, 550 en y) del Canvas.
* Lo anterior quiere decir que la imágen tendrá un ancho de **45px** y un alto de **60px** (135 - 90, 550 - 490).
* Sobre la imagen general se creará un cuadro imaginario que estará ubicado inicialmente en las coordenadas (0, 0) de la imágen.
* Este cuadro imaginario terminará en las coordenadas (45, 60) de la imágen.
* Esto quiere decir que el recuadro tendrá el mismo ancho que la imágen que se mostrará en el canvas.

Vamos a mostrar que sucede:

<figure><img src="https://camo.githubusercontent.com/ebb58bb43c455c9ad57bd31ea4e1a28a465c891f22b91f24e5f2446a22f17aae/68747470733a2f2f692e696d6775722e636f6d2f695434463772482e706e67" alt=""><figcaption></figcaption></figure>

Pintando primera parte del Sprite.

Vamos a pintar la segunda parte de la imágen:

```
public void pintarImagenes(Graphics2D g2d){
    g2d.drawImage(
        sprites.getImage(), 90, 490, 135, 550, 0, 0, 45, 60,  null
    );
    g2d.drawImage(
        sprites.getImage(), 135, 490, 180, 550, 45, 0, 90, 60,  null
    );
}
```

<figure><img src="https://camo.githubusercontent.com/a3af3307914fbe2fa19122a7327ee67412b0a0624bb06ddf9c4f14b7c03a7184/68747470733a2f2f692e696d6775722e636f6d2f533651453745552e706e67" alt=""><figcaption></figcaption></figure>

Pintando segunda parte del Sprite

Ahora para no estar pintando cada parte por separado podemos encontrar un patron entre las dos imágenes que pintamos para hacer la automatización del dibujo de las imágenes sobre la pantalla.

Podemos notar que el patron va en aumento en **45px** sobre todas las coordenadas que involucran el eje X tanto para la posición en el canvas de la imágen como en la posición del recuadro dentro de la imágen general:

<figure><img src="https://camo.githubusercontent.com/b6b1e4deeae65be2ec102cb469c5c33428d121805668ef3fee3965bada771cec/68747470733a2f2f692e696d6775722e636f6d2f51334139636c372e706e67" alt=""><figcaption></figcaption></figure>

Patron identificado.

Vamos a borrar las anteriores imágenes pintadas y vamos a crear un ciclo for para automatizar el dibujo de todas las imágenes, como en el **Sprite** hay contenidas 7 imágenes el ciclo empezara desde 0 y terminara en 7-1:

```
public void pintarImagenes(Graphics2D g2d){
    for(int i = 0; i < 7; i++){
    }
}
```

Dentro del ciclo y por cada iteración vamos a dibujar las imágenes:

```
public void pintarImagenes(Graphics2D g2d){
    for(int i = 0; i < 7; i++){
        g2d.drawImage();
    }
}
```

Como el patron consiste en sumar 45 a medida que incrementan las imágenes, y nos podemos guiar de la primera imágen, sabemos que esta:

* Inicia en la posición 90px sobre el eje X del canvas.
* Termina en la posición 135px del eje X del canvas.
* Inicia en la posición 0px sobre el eje X de la imágen.
* Termina en la posición 45px del eje X de la imágen.

Asi que basta con sumarle a esas coordenadas (45 \* i) de tal forma que para la primera imágen se le sumara 0 ya que el i inicia en 0:

```
public void pintarImagenes(Graphics2D g2d){
    for(int i = 0; i < 7; i++){
        g2d.drawImage(
            sprites.getImage(), 
            90 + (45 * i), 490, 135 + (45 * i), 550, 
            0 + (45 * i), 0, 45 + (45 * i), 60,  
            null
        );
    }
}
```

De esta forma se verán pintadas nuestras imágenes:

<figure><img src="https://camo.githubusercontent.com/39fd54b97f077bcaef22a0c27da4de36925db007262cd4c0eb62f635a3f752bb/68747470733a2f2f692e696d6775722e636f6d2f58346d337530372e706e67" alt=""><figcaption></figcaption></figure>

Imágenes pintadas en el Canvas.

## Uso de Areas dentro de Canvas

Las **areas y objetos gráficos especiales de figuras** son también una parte importante del canvas, gracias a estos podríamos realizar una manipulación de las figuras pintadas dentro del canvas, por ejemplo podríamos seleccionar algún circulo y mover la posición de esto (con el uso de eventos claro). Con las Areas también se pueden realizar operaciones como la **sustracción o combinación** de figuras, esto es importante y realizaremos un ejemplo de esto.

Por ahora vamos a comentar la llamada de todos los otros métodos de pintura para dejar vació el canvas:

```
@Override
public void paint(Graphics g){
    g2d = (Graphics2D) g.create();
    g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
    g2d.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
    // this.pintarStrings(g2d);
    // this.pintarRectangulos(g2d);
    // this.pintarLineas(g2d);
    // this.pintarArcos(g2d);
    // this.pintarOvalos(g2d);
    // this.pintarPoligonos(g2d);
    // this.pintarImagenes(g2d);
}
```

Vamos a crear un método nuevo llamado **pintarAreas**:

```
public void pintarAreas(Graphics2D g2d){

}
```

Para realizar el ejemplo de combinación y sustracción vamos a dibujar primero un rectángulo y vamos a suponer que este podría ser un panel cualquiera con un contenido que sera un texto:

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
}
```

<figure><img src="https://camo.githubusercontent.com/df9bcf52c257034ab0b18125c214cb9a1baf60bb335e1fc48da60d5bee47954c/68747470733a2f2f692e696d6775722e636f6d2f49627861564a4d2e706e67" alt=""><figcaption></figcaption></figure>

Simulando la creación de un panel dentro del canvas

Ya tenemos nuestro panel simulado ahora supongamos que queremos que nuestro panel tenga un borde redondeado, sabemos que con los bordes que nos proporciona **Swing** no es posible realizar este tipos de bordes, asi que podríamos crear nuestro propio borde redondeado pintándolo.

Para realizar esto NO basta con pintar un recuadro redondeado encima, de echo este tapara lo que esta contenido en el panel, debemos crear Areas para manipulación de estas figuras. Para trabajar con areas no podemos pintar las figuras como lo trabajamos anteriormente, debemos crear **ObjetosGráficos especiales de Figuras**. A modo de identificación, las figuras que creemos de ahora en adelante las pintaremos de otro color, pero cuando se trabaja con areas la forma de cambiar el color es con el método **setPaint**.

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
    
    g2d.setPaint(Color.ORANGE);
}
```

Vamos a crear un nuevo rectángulo redondeado en forma de objeto para esto necesitamos ejemplificarlo con la clase **RoundRectangle2D**:

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
    
    g2d.setPaint(Color.ORANGE);
    RoundRectangle2D rectanguloRedondeado = new RoundRectangle2D.Double();
}
```

Para ejemplificar este objeto necesitamos importar su respectiva librería:

```
import java.awt.geom.RoundRectangle2D;
```

Ya ejemplificamos nuestro objeto, ahora es necesarió indicarle sus propiedades gráficas mediante el método **setRoundRect**, recordando que sus propiedades gráficas son:

* **Posición en X**.
* **Posición en Y**.
* **Ancho**.
* **Alto**.
* **Ancho Borde redondeado**.
* **Alto Borde redondeado**.

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
    
    g2d.setPaint(Color.ORANGE);
    RoundRectangle2D rectanguloRedondeado = new RoundRectangle2D.Double();
    rectanguloRedondeado.setRoundRect(80, 30, 340, 340, 100, 100);
}
```

Ya ejemplificamos nuestro objeto y le dimos sus propiedades gráficas, ahora debemos añadirlo al canvas. En ves de pintarlo directamente vamos a crear un **Area** que recibe por parámetro al recuadro, de esta forma vamos a poder manipular el area:

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
    
    g2d.setPaint(Color.ORANGE);
    RoundRectangle2D rectanguloRedondeado = new RoundRectangle2D.Double();
    rectanguloRedondeado.setRoundRect(80, 30, 340, 340, 100, 100);

    Area area = new Area(rectanguloRedondeado);
}
```

Ahora vamos a pintar el area con el método **draw** del objeto **graphics2D**:

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
    
    g2d.setPaint(Color.ORANGE);
    RoundRectangle2D rectanguloRedondeado = new RoundRectangle2D.Double();
    rectanguloRedondeado.setRoundRect(80, 30, 340, 340, 100, 100);

    Area area = new Area(rectanguloRedondeado);
    g2d.draw(area);
}
```

<figure><img src="https://camo.githubusercontent.com/526db28bbf8424aa8ac49a88f09df53083e3a839dc4858cc3c139ff71a70dbc9/68747470733a2f2f692e696d6775722e636f6d2f536c32466932582e706e67" alt=""><figcaption></figcaption></figure>

Objeto de rectangulo redondeado pintado

Ya tenemos pintado el contorno del borde que queremos crearle a nuestro panel, lo que queremos hacer es que se borre los espacios azules que sobran en cada esquina, ahora vamos a crear otro objeto, este será un rectangulo que ocupara el espacio total del panel esto mediante la ejemplificación de un objeto tipo **Rectangle**:

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
    
    g2d.setPaint(Color.ORANGE);
    RoundRectangle2D rectanguloRedondeado = new RoundRectangle2D.Double();
    rectanguloRedondeado.setRoundRect(80, 30, 340, 340, 100, 100);

    Area area = new Area(rectanguloRedondeado);

    Rectangle rectangulo = new Rectangle(80, 30, 340, 340);

    g2d.draw(area);
}
```

Vamos a añadir este rectangulo a una nueva area, que en este caso llamaremos **areaFueraBorde**:

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
    
    g2d.setPaint(Color.ORANGE);
    RoundRectangle2D rectanguloRedondeado = new RoundRectangle2D.Double();
    rectanguloRedondeado.setRoundRect(80, 30, 340, 340, 100, 100);

    Area area = new Area(rectanguloRedondeado);

    Rectangle rectangulo = new Rectangle(80, 30, 340, 340);
    Area areaFueraBorde = new Area(rectangulo);

    g2d.draw(area);
}
```

Ahora vamos a hacer el acto de **sustracción**, con ambas Areas, la Sustracción hará que el area de sustracción (**areaFueraBorde**) se transforme por la parte que le sobra con respecto al área que esta sustrayendo (**area**), esto quiere decir que el area **areaFueraBorde** representará ahora las partes sobrantes en cada esquina:

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
    
    g2d.setPaint(Color.ORANGE);
    RoundRectangle2D rectanguloRedondeado = new RoundRectangle2D.Double();
    rectanguloRedondeado.setRoundRect(80, 30, 340, 340, 100, 100);

    Area area = new Area(rectanguloRedondeado);

    Rectangle rectangulo = new Rectangle(80, 30, 340, 340);
    Area areaFueraBorde = new Area(rectangulo);
    areaFueraBorde.subtract(area);
    
    g2d.draw(area);
}
```

Si corremos la aplicación no se notara ningún cambio pero internamente sabemos que ahora el area **areaFueraBorde** representa las esquinas sobrantes:

<figure><img src="https://camo.githubusercontent.com/d4e2a8ca6d3445a02a678465a8da166ceaadd907fff8cc029ec6b2f5a94fcf0b/68747470733a2f2f692e696d6775722e636f6d2f76454d58364f362e706e67" alt=""><figcaption></figcaption></figure>

AreaFueraBorde antes y después de la sustracción

Ahora queremos que esa area no sea visible. Para esto vamos a configurar el canvas dándole un contexto, esto quiere decir que se le indicara al canvas que lo que se pinte de ahora en adelante se pintara unicamente sobre el contexto indicado, para hacer esto necesitamos llamar al método **setClip**:

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
    
    g2d.setPaint(Color.ORANGE);
    RoundRectangle2D rectanguloRedondeado = new RoundRectangle2D.Double();
    rectanguloRedondeado.setRoundRect(80, 30, 340, 340, 100, 100);

    Area area = new Area(rectanguloRedondeado);

    Rectangle rectangulo = new Rectangle(80, 30, 340, 340);
    Area areaFueraBorde = new Area(rectangulo);
    areaFueraBorde.subtract(area);
    g2d.setClip(areaFueraBorde);

    g2d.draw(area);
}
```

Con lo anterior estamos indicando que lo que se pinte de ahi en adelante solo se vera afectado en el area **areaFueraBorde**, vamos a pintar un recuadro de color blanco que ocupe todo el tamaño del panel:

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
    
    g2d.setPaint(Color.ORANGE);
    RoundRectangle2D rectanguloRedondeado = new RoundRectangle2D.Double();
    rectanguloRedondeado.setRoundRect(80, 30, 340, 340, 100, 100);

    Area area = new Area(rectanguloRedondeado);

    Rectangle rectangulo = new Rectangle(80, 30, 340, 340);
    Area areaFueraBorde = new Area(rectangulo);
    areaFueraBorde.subtract(area);
    g2d.setClip(areaFueraBorde);

    g2d.setColor(Color.WHITE);
    g2d.fillRect(80, 30, 340, 340);

    g2d.draw(area);
}
```

Como mencionamos al proporcionar de contexto al canvas este solo se vera reflejado en el area proporcionada (**areaFueraBorde**).

<figure><img src="https://camo.githubusercontent.com/c456fa0ebe39870d51921567eeb86a8dfd0aba65eb08b0cdab32100da2504e8a/68747470733a2f2f692e696d6775722e636f6d2f5a3633534145462e706e67" alt=""><figcaption></figcaption></figure>

Pintando recuadro blanco afectando solo area de contexto.

Ya le proporcionamos los bordes redondeados a nuestro panel ficticio de forma satisfactoria, sin embargo los bordes se ven algo pixeleados y es que el efecto de **setClip** hace que la sustracción se vea borrosa. Para arreglar esto y para poder dibujar mas cosas sobre el canvas sin problemas debemos dejar el contexto nulo de nuevo:

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
    
    g2d.setPaint(Color.ORANGE);
    RoundRectangle2D rectanguloRedondeado = new RoundRectangle2D.Double();
    rectanguloRedondeado.setRoundRect(80, 30, 340, 340, 100, 100);

    Area area = new Area(rectanguloRedondeado);

    Rectangle rectangulo = new Rectangle(80, 30, 340, 340);
    Area areaFueraBorde = new Area(rectangulo);
    areaFueraBorde.subtract(area);
    g2d.setClip(areaFueraBorde);

    g2d.setColor(Color.WHITE);
    g2d.fillRect(80, 30, 340, 340);

    g2d.setClip(null);
    g2d.draw(area);
}
```

<figure><img src="https://camo.githubusercontent.com/e62493829c48e761735b7660f8e9790f626ee2bb8378a671baea35f90245afa2/68747470733a2f2f692e696d6775722e636f6d2f58646c73394c532e706e67" alt=""><figcaption></figcaption></figure>

Bordes implementados

Lo que acabamos de ver es la base para crear bordes redondeados reales en objetos Gráficos **Swing** como botones, labels, paneles etc. No solo podríamos realizarlo con recuadros bordeados podemos hacerlo con óvalos, polígonos etc. A continuación podríamos cambiar el objeto del recuadro redondeado por un circulo por ejemplo:

```
public void pintarAreas(Graphics2D g2d){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.fillRect(80, 30, 340, 340);

    g2d.setColor(Color.WHITE);
    g2d.setFont(sRecursos.getFontTitulo());
    g2d.drawString("Soy un Panel", 200, 200);
    
    g2d.setPaint(Color.ORANGE);
    // RoundRectangle2D rectanguloRedondeado = new RoundRectangle2D.Double();
    // rectanguloRedondeado.setRoundRect(80, 30, 340, 340, 100, 100);
    
    Ellipse2D circulo = new Ellipse2D.Double();
    circulo.setFrameFromCenter((80 + 340 / 2), (30 + 340 / 2), 340 + 80, 340 + 30);
        
    Area area = new Area(circulo);
    
    Rectangle rectangulo = new Rectangle(80, 30, 340, 340);
    Area areaFueraBorde = new Area(rectangulo);
    areaFueraBorde.subtract(area);
    g2d.setClip(areaFueraBorde);

    g2d.setColor(Color.WHITE);
    g2d.fillRect(80, 30, 340, 340);

    g2d.setClip(null);
    g2d.draw(area);
}
```

<figure><img src="https://camo.githubusercontent.com/7698fd1564888fbe3c64b0e6ae2d64a34005b4e792fbd50dca02be4cd1daad15/68747470733a2f2f692e696d6775722e636f6d2f526a6f4e4f6d792e706e67" alt=""><figcaption></figcaption></figure>

Borde implementando un circulo.

## Uso de EventosMouseListener sobre Canvas

Ya hemos usado antes los eventos del mouse para proporcionar interactividad a distintas partes de nuestro proyecto, a este punto ya dominamos las funcionalidades de los eventos del Mouse, en este caso podríamos aprovechar el manejo de eventos para dibujar figuras de manera interactiva con el usuario. Lo que queremos realizar específicamente es que una vez el usuario oprima el botón del mouse dentro del canvas, lo mantenga oprimido y arrastre el mouse, este pueda dibujar una figura en tiempo real. En este caso vamos a dibujar un rectangulo.

Lo primero que vamos a realizar es dejar vació el canvas y para eso vamos a comentar la llamada del método **pintarAreas** dentro del método **paint**:

```
@Override
public void paint(Graphics g){
    g2d = (Graphics2D) g.create();
    g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
    g2d.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
    // this.pintarStrings(g2d);
    // this.pintarRectangulos(g2d);
    // this.pintarLineas(g2d);
    // this.pintarArcos(g2d);
    // this.pintarOvalos(g2d);
    // this.pintarPoligonos(g2d);
    // this.pintarImagenes(g2d);
    // this.pintarAreas(g2d);
}
```

Ahora vamos a concentrarnos en la clase **LienzoComponent**, vamos a implementar las interfaces **MouseListener y MouseMotionListener**.

```
public class LienzoComponent implements MouseListener, MouseMotionListener{

}
```

También vamos a implementar sus respectivos métodos:

```
@Override
public void mouseClicked(MouseEvent e) {}

@Override
public void mousePressed(MouseEvent e) {}

@Override
public void mouseReleased(MouseEvent e) {}

@Override
public void mouseEntered(MouseEvent e) {}

@Override
public void mouseExited(MouseEvent e) {}

@Override
public void mouseDragged(MouseEvent e) {}

@Override
public void mouseMoved(MouseEvent e) {}
```

Vamos a posicionarnos de nuevo en la clase **LienzoTemplate** y lo primero que vamos a realizar es añadirle la escucha de estos eventos del mouse al canvas, como se menciono antes, una clase puede escuchar diferentes eventos del mismo tipo asi que aunque el Canvas ya esta escuchando eventos del Mouse de su panel Contenedor, aun así no habrá ningún problema:

```
// Dentro del Constructor
this.addMouseListener(this.lienzoComponent);
this.addMouseMotionListener(this.lienzoComponent);
```

Vamos a crear un método al cual llamaremos **pintarRectanguloTiempoReal**, este será el encargado de dibujar la figura en tiempo real a traves de los eventos del Mouse:

```
public void pintarRectanguloTiempoReal(){
}
```

Nos pasamos a nuestra clase **LienzoComponent** y vamos a necesitar capturar la posición inicial una vez se oprima el botón del mouse, este enfoque se asemeja al usado para mover la ventana a traves de la barra del título, para eso creamos dos variables que van a capturar esta posición inicial.

* **Declaración:**

```
private int posicionInicialX, posicionInicialY;
```

* **Captura de posición inicial:** Para capturar esto nos vamos a basar del principio de arrastre que usamos con la ventana y vamos a usar en este caso el **MousePressed**:

```
@Override
public void mousePressed(MouseEvent e) {
    this.posicionInicialX = e.getX();
    this.posicionInicialY = e.getY();
}
```

En este caso como el contexto es el canvas nada mas solo usaremos las posiciónes con respecto a este (**getX, getY**).

Ahora como realizaremos una acción mientras el usuario mantiene oprimido el botón del mouse y se esta arrastrado vamos a configurar el evento **mouseDragged**. Allí vamos a llamar al método que se encargará de pintar la figura:

```
@Override
public void mouseDragged(MouseEvent e) {
    this.lienzoTemplate.pintarRectanguloTiempoReal();
}
```

Para poder dibujar la figura vamos a necesitar enviarle 3 argumentos al método:

* **Posición inicial en X**.
* **Posición inicial en Y**.
* **El objeto del evento para capturar la posición de arrastre**.

```
@Override
public void mouseDragged(MouseEvent e) {
    this.lienzoTemplate.pintarRectanguloTiempoReal(posicionInicialX, posicionInicialY, e);
}
```

Así mismo se debe recibir estos elementos como parámetros dentro del método en la clase **LienzoTemplate**:

```
public void pintarRectanguloTiempoReal(int x, int y, MouseEvent e){

}
```

Vamos a configurar el color del canvas para que el rectángulo pueda ser visualizado:

```
public void pintarRectanguloTiempoReal(int x, int y, MouseEvent e){
    g2d.setColor(sRecursos.getColorAzul());
}
```

Dentro del método debemos pintar el rectángulo, para esto llamaremos al método **drawRect**:

```
public void pintarRectanguloTiempoReal(int x, int y, MouseEvent e){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.drawRect();
}
```

La posición inicial del rectángulo la estamos recibiendo por parámetro, así que lo vamos a colocar:

```
public void pintarRectanguloTiempoReal(int x, int y, MouseEvent e){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.drawRect(x, y);
}
```

Ahora debemos configurar el ancho y alto del rectángulo, para esto basta con capturar la posición del mouse a traves del evento que se activa a medida que el mouse se esta arrastrando. Le debemos restar ademas la posicion inicial, en ambos casos:

```
public void pintarRectanguloTiempoReal(int x, int y, MouseEvent e){
    g2d.setColor(sRecursos.getColorAzul());
    g2d.drawRect(x, y, e.getX() - x , e.getY() - y);
}
```

Si probamos nuestros eventos veremos algo como esto:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase13/raw/master/gifs/Canvas1.gif" alt=""><figcaption></figcaption></figure>

Intento de dibujo dentro de canvas

Al parecer nuestro intento de pintar tiene algo extraño, y esto es debido a que a medida que se mueve el mouse mientras se tiene oprimido el botón izquierdo, se esta pintando un rectángulo nuevo, es decir que por cada pixel que mueve el mouse se esta pintando un nuevo rectángulo, debemos hallar la forma en que solo se vea el rectángulo actual y se borren los rectángulos anteriores, hay muchas formas de hacer esto, vamos hacer una forma rápida de hacerlo, no es la mejor forma pero por practicidad y facilidad se realizará así.

Vamos a hacer que por cada vez que se active el evento, se pinte primero un rectángulo blanco que ocupe todo el canvas, esto hará un efecto de borrar cualquier rectangulo anterior que se haya dibujado a parte del actual:

```
public void pintarRectanguloTiempoReal(int x, int y, MouseEvent e){
    g2d.setColor(Color.WHITE);
    g2d.fillRect(0, 0, this.getWidth(), this.getHeight());
    g2d.setColor(sRecursos.getColorAzul());
    g2d.drawRect(x, y, e.getX() - x , e.getY() - y);
}
```

Vamos a ver que ocurre una vez probamos nuestro método:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase13/raw/master/gifs/Canvas2.gif" alt=""><figcaption></figcaption></figure>

Segundo intento de pintar rectángulos.

Efectivamente podemos pintar rectángulos en tiempo real y se esta viendo unicamente el rectángulo actual acorde al movimiento del mouse. Sin embargo hay 2 problemas:

* Si se ha terminado de pintar un rectángulo, es decir el usuario ha soltado el mouse y luego quiere pintar otro el anterior será borrado y esto es debido al enfoque de pintar un rectángulo blanco en el canvas, este problema se dejará asi por esta sesión y mas adelante se podrá discutir.
* El programa unicamente pinta el rectángulo hacia una dirección, si se intenta pintar un rectángulo hacia arriba o a la izquierda con respecto al punto inicial este no se pintara, este problema si lo vamos a resolver.

Para esto debemos realizar una condición para los 4 casos:

* En caso de pintar un rectángulo con dirección **inferior derecha** con respecto al punto inicial.
* En caso de pintar un rectángulo con dirección **superior derecha** con respecto al punto inicial.
* En caso de pintar un rectángulo con dirección **inferior izquierda** con respecto al punto inicial.
* En caso de pintar un rectángulo con dirección **superior izquierda** con respecto al punto inicial.

```
public void pintarRectanguloTiempoReal(int x, int y, MouseEvent e){
    g2d.setColor(Color.WHITE);
    g2d.fillRect(0, 0, this.getWidth(), this.getHeight());
    g2d.setColor(sRecursos.getColorAzul());
    // Dirección Inferior Izquierda
    if(e.getX() - x < 0 && e.getY() - y > 0)

    // Dirección Superior Izquierda
    if(e.getX() - x < 0 && e.getY() - y < 0)

    // Dirección Superior Derecha
    if(e.getX() - x > 0 && e.getY() - y < 0)

    // Dirección Inferior Derecha
    if(e.getX() - x > 0 && e.getY() - y > 0)
        g2d.drawRect(x, y, e.getX() - x , e.getY() - y);
}
```

Ya se crearon los 4 casos y solo el último es el que ya está configurado (el que esta por defecto).

Para el caso en que se dibuje el recuadro con dirección **Inferior Izquierda**:

* El punto inicial en X ahora será la coordenada que ira moviendo el usuario
* El punto inicial en Y permanece estático.
* El ancho del rectangulo sera la posición estática en X menos la posición que va actualizando con cada arrastre (para que quede positivo).
* El alto sera igual a la posición que se va actualizando con el arrastre menos la posición estática en Y.

```
public void pintarRectanguloTiempoReal(int x, int y, MouseEvent e){
    g2d.setColor(Color.WHITE);
    g2d.fillRect(0, 0, this.getWidth(), this.getHeight());
    g2d.setColor(sRecursos.getColorAzul());
    // Dirección Inferior Izquierda
    if(e.getX() - x < 0 && e.getY() - y > 0)
        g2d.drawRect(e.getX(), y, x - e.getX(), e.getY() - y);
    // Dirección Superior Izquierda
    if(e.getX() - x < 0 && e.getY() - y < 0)

    // Dirección Superior Derecha
    if(e.getX() - x > 0 && e.getY() - y < 0)

    // Dirección Inferior Derecha
    if(e.getX() - x > 0 && e.getY() - y > 0)
        g2d.drawRect(x, y, e.getX() - x , e.getY() - y);
}
```

Para el caso en que se dibuje el recuadro con dirección **Superior Izquierda**:

* El punto inicial en X ahora será la coordenada que ira moviendo el usuario.
* El punto inicial en Y ahora será la coordenada que ira moviendo el usuario.
* El ancho del rectangulo sera la posición estática en X menos la posición que va actualizando con cada arrastre (para que quede positivo).
* El alto del rectangulo sera la posición estática en Y menos la posición que va actualizando con cada arrastre (para que quede positivo).

```
public void pintarRectanguloTiempoReal(int x, int y, MouseEvent e){
    g2d.setColor(Color.WHITE);
    g2d.fillRect(0, 0, this.getWidth(), this.getHeight());
    g2d.setColor(sRecursos.getColorAzul());
    // Dirección Inferior Izquierda
    if(e.getX() - x < 0 && e.getY() - y > 0)
        g2d.drawRect(e.getX(), y, x - e.getX(), e.getY() - y);
    // Dirección Superior Izquierda
    if(e.getX() - x < 0 && e.getY() - y < 0)
        g2d.drawRect(e.getX(), e.getY(), x - e.getX(), y - e.getY());
    // Dirección Superior Derecha
    if(e.getX() - x > 0 && e.getY() - y < 0)

    // Dirección Inferior Derecha
    if(e.getX() - x > 0 && e.getY() - y > 0)
        g2d.drawRect(x, y, e.getX() - x , e.getY() - y);
}
```

Para el caso en que se dibuje el recuadro con dirección **Superior Derecha**:

* El punto inicial en X será la coordenada estática.
* El punto inicial en Y ahora será la coordenada que ira moviendo el usuario.
* El ancho sera igual a la posición que se va actualizando con el arrastre menos la posición estática en X.
* El alto del rectangulo sera la posición estática en Y menos la posición que va actualizando con cada arrastre (para que quede positivo).

```
public void pintarRectanguloTiempoReal(int x, int y, MouseEvent e){
    g2d.setColor(Color.WHITE);
    g2d.fillRect(0, 0, this.getWidth(), this.getHeight());
    g2d.setColor(sRecursos.getColorAzul());
    // Dirección Inferior Izquierda
    if(e.getX() - x < 0 && e.getY() - y > 0)
        g2d.drawRect(e.getX(), y, x - e.getX(), e.getY() - y);
    // Dirección Superior Izquierda
    if(e.getX() - x < 0 && e.getY() - y < 0)
        g2d.drawRect(e.getX(), e.getY(), x - e.getX(), y - e.getY());
    // Dirección Superior Derecha
    if(e.getX() - x > 0 && e.getY() - y < 0)
        g2d.drawRect(x, e.getY(), e.getX() - x, y - e.getY()); 
    // Dirección Inferior Derecha
    if(e.getX() - x > 0 && e.getY() - y > 0)
        g2d.drawRect(x, y, e.getX() - x , e.getY() - y);
}
```

Una vez ejecutamos nuestra aplicación vemos algo como esto:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase13/raw/master/gifs/Canvas3.gif" alt=""><figcaption></figcaption></figure>

Pintando rectángulos en tiempo real sobre el canvas.

Para terminar con broche de oro, vamos a arreglar las coordenadas de **Valor Lado X y Valor Lado Y**, Actualmente solo muestra la coordenada actual del mouse mientras se tiene oprimido el botón izquierdo, pero sería bueno que nos indique el valor de los lados del cuadrado.

Vamos a la clase **ConfiguraciónesComponent** y vamos a declarar dos atributos para capturar las coordenadas iniciales:

```
// Al inicio de la clase ConfiguraciónesComponent
private int posicionInicialX, posicionInicialY;
```

Esto lo hacemos para poder realizar el calculo de la resta y asi obtener efectivamente el valor de los lados del recuadro que se esta pintando.

Vamos a capturar las coordenadas iniciales dentro del método **MousePressed**:

```
@Override
public void mousePressed(MouseEvent e) {
    ...
    this.posicionInicialX = e.getX();
    this.posicionInicialY = e.getY();
}
```

Finalmente dentro del método **MouseDragged** en vez de proporcionar solamente las coordenadas directamente (getX, getY) vamos a restarle los valores de la coordenada inicial (similar a como hicimos en la configuración del MouseDragged del componente Lienzo) la única diferencia es que vamos a envolver la resta dentro de un valor absoluto para que el valor siempre sea positivo.

```
@Override
public void mouseDragged(MouseEvent e) {
    this.configuracionesTemplate.getLLadoXValor().setText(Math.abs((e.getX() - posicionInicialX)) + "");
    this.configuracionesTemplate.getLLadoYValor().setText(Math.abs((e.getY() - posicionInicialY)) + "");
}
```

## Resultado

Si has llegado hasta aquí **!Felicidades!** has aprendido acerca del uso del **Canvas** y entre varias cosas como pintar figuras básicas como Strings, Lineas, Rectángulos, Arcos, Ovalos, Poligonos e Imagenes. Aprendiste sobre el uso de las Areas y como realizar operaciones entre ellas. Finalmente aprendiste a dibujar en tiempo real figuras proporcionando una gran interactividad a traves de los eventos del Mouse. En la siguiente clase no vamos a enfocar a revisar el Servicio Gráfico **GraficosAvanzadosServices** y como el Canvas tiene un papel fundamental en la mayoría del código que se encuentra allí.

## Actividad

Estudiar el uso de canvas y como pintar sus figuras básicas.

Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 14

### Objetivos

* Reconocer la forma de utilizar el servicio Gráficos avanzados para realizar decoraciones especiales en los objetos gráficos dentro de nuestro proyecto.
* Determinar el proceso interno de cada uno de los métodos contenidos en del servicio Gráficos avanzados reconociendo cual es propósito de cada uno de ellos.
* Identificar que elementos gráficos intervienen para cumplir con las acciones de cada uno de los métodos contenidos en el servicio Gráficos avanzados.
* Mostrar ejemplos adicionales para brindar una mayor explicación de ciertas particularidades contenidas en algunos de los métodos.

## Antes de Comenzar

Recordando un poco nuestro recorrido en la sesión anterior implementamos el uso de **Canvas** y entre otras cosas aprendimos como **pintar figuras (strings, rectángulos, lineas, arcos, óvalos, polígonos e imágenes)**. Vimos un ejemplo del uso de **Areas para hacer acciones como combinación o sustracción con estas**, finalmente utilizamos los eventos del Mouse para **pintar un rectángulo en tiempo real**.

<figure><img src="https://camo.githubusercontent.com/39fd54b97f077bcaef22a0c27da4de36925db007262cd4c0eb62f635a3f752bb/68747470733a2f2f692e696d6775722e636f6d2f58346d337530372e706e67" alt=""><figcaption></figcaption></figure>

Pintando figuras sobre el Canvas

<figure><img src="https://camo.githubusercontent.com/e62493829c48e761735b7660f8e9790f626ee2bb8378a671baea35f90245afa2/68747470733a2f2f692e696d6775722e636f6d2f58646c73394c532e706e67" alt=""><figcaption></figcaption></figure>

Simulación de bordes redondeados con uso de Areas.

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase14/raw/master/gifs/Canvas1.gif" alt=""><figcaption></figcaption></figure>

Dibujando rectángulos usando Mouse Events.

#### **Aclaración:**

En esta sesión se mencionara mucho la palabra **Component** pero en esta ocasión no nos estaremos refiriendo a componentes gráficos o a la clase **Component** de algún componente. **Component** es también una clase en Java de la cual heredan todos los objetos gráficos que hemos manipulado, como los botones, labels, textField etc. Es valida la aclaración entonces por que al coincidir el nombre puede confundir un poco, sin embargo cuando se hable de la palabrá **Component** en esta sesión hablaremos de esta clase particular de Java, a menos que se nombre explícitamente algún componente gráfico que hemos creado antes.

## Servicio Gráficos Avanzados

En esta sesión vamos a explicar cada uno de los métodos contenidos en este servicio, para explorar este servicio se verán los siguientes items:

* **Decoración de una Tabla**.
* **Personalización de un SrollBar**.
* **Creación de Bordes Difuminados**.
* **Creación de Bordes Redondeados**.
* **Creación de Bordes Circulares**.

## Decoración de una Tabla

En la sesión 11 vimos brevemente que podíamos decorar nuestra tabla usando nuestro nuevo servicio **GraficosAvanzadosService**, esto nos dio la posibilidad de intercalar el color de las filas de la tabla, cambiar el color de fuente, escoger el tipo de fuente, personalizar la cabecera e incluso proporcionar un color en caso de seleccionar alguna de las filas.

<figure><img src="https://camo.githubusercontent.com/2f5430f12a3de2f7c44d27cc80d0b3ed4c43c25cf74cc88506b383988746f7ed/68747470733a2f2f692e696d6775722e636f6d2f4b384a5968716d2e706e67" alt=""><figcaption></figcaption></figure>

Tabla personalizada.

Sin embargo se explico poco o nada de como se lograron todas estas cosas. Para empezar el método que se uso para personalizar la tabla fue **setDefaultRenderer()** este puede recibir por parámetro:

* **ColumnClass**: Debe recibir una clase que representa las columnas que tendrá la tabla, este parámetro por lo general no representa una vital importancia ya que no influye en la personalización y por esto se suele colocar como argumento **Object.class** representando que se enviara una clase cualquiera.
* **TableCellRenderer**: Es una interfaz que contiene ciertos métodos dispuesto para la personalización de una tabla.

_**Nota:** El parámetro ColumnClass solo es necesario para el objeto JTable, para el JTableHeader solo se pide el segundo parámetro._

<figure><img src="https://camo.githubusercontent.com/7a956cd7a4dcfe04aeee8e1c482b8b35e718e2e2d89a122498af2a91503891a7/68747470733a2f2f692e696d6775722e636f6d2f506579586e42792e706e67" alt=""><figcaption></figcaption></figure>

Método para personalizar las tablas.

Lo primero que vamos a ver es la definición del método del servicio **GraficosAvanzadosService** que nos ayuda con la personalización de la tabla.

```
public DefaultTableCellRenderer devolverTablaPersonalizada(
        Color colorPrincipal, Color colorSecundario, Color colorSeleccion, Color colorFuente, Font fuente
){
    ...
    ...
}
```

Podemos observar lo siguiente:

* El método retorna un objeto de tipo **DefaultTableCellRender** este objeto cumple un papel crucial ya que esta clase es la que implementa a la interfaz **TableCellRenderer**, otra particularidad importante es que este objeto se puede tratar como un **JLabel**, si entramos al código Java podemos confirmar esto.

<figure><img src="https://camo.githubusercontent.com/f170aadd88a24252eaa505edc8e031fdc5310ba7489ef04f4121aee463dcc15a/68747470733a2f2f692e696d6775722e636f6d2f42597533416f5a2e706e67" alt=""><figcaption></figcaption></figure>

Clase de Java que ya implementa la interfaz que necesitamos y hereda de un JLabel.

* El método recibe por parámetro:
  * **colorPrincipal**: En nuestro caso el color principal representa el color de fondo de las filas impares.
  * **colorSecundario**: En nuestro caso el color secundario representa el color de fondo de las filas pares.
  * **colorSeleccion**: En nuestro caso el color de selección representa el color de fondo que tendrá una fila una vez se seleccione a traves de un click con el mouse.
  * **colorFuente:** Representa el color de fuente que tendrá toda la tabla.
  * **Fuente:** Representa la fuente que tendrá el contenido de toda la tabla.

_**Nota:** Cabe aclarar que se recalca la frase **en nuestro caso** ya que mas adelante nos podemos dar cuenta que podemos personalizar una tabla de varias maneras y esta solo es una de ellas._

Como ya hemos visto a lo largo del curso para poder obtener **interfaces** es necesario una clase que la implemente, como es el caso de los eventos, la clase que implementa las interfaces de los eventos cuando hablamos de un componente gráfico es la clase **Component** y a traves de esta, la clase **Template** puede indicarle a sus objetos gráficos que podrán escuchar esos eventos. Este es un caso igual, para poder obtener el parámetro/interfaz **TableCellRenderer** debemos usar una clase que implemente a esta interfaz y retornar un objeto de dicha clase. Como acabamos de ver la clase de Java **DefaultTableCellRender** cumple con este criterio asi que vamos a crear una **ejemplificación anónima** de esta clase y de una vez vamos a indicarle al método que vamos a retornar este objeto anónimo que acabamos de ejemplificar.

```
public DefaultTableCellRenderer devolverTablaPersonalizada(
        Color colorPrincipal, Color colorSecundario, Color colorSeleccion, Color colorFuente, Font fuente
){
    return new DefaultTableCellRenderer();
}
```

Hasta el momento nuestro código está bien y no nos notifica ningún error, sin embargo queremos hacer unas configuraciónes sobre este objeto, es por eso que una vez terminan los paréntesis de la ejemplificación y antes del punto y coma vamos a abrir unas llaves **"{}"** para realizar una configuración adicional:

```
devolverTablaPersonalizada(
        Color colorPrincipal, Color colorSecundario, Color colorSeleccion, Color colorFuente, Font fuente
){
    return new DefaultTableCellRenderer(){

    };
}
```

Para los JDK 10 en adelante el compilador va a sugerir crear un identificador de la clase, de hecho en el código se han venido creando seriales en las clases para hacer caso a esta sugerencia, este serial lo realiza el propio compilador cuando se observa la sugerencia y no es mas que un atributo de tipo **long**, así que esta al ser una clase anónima lo pide de igual forma como una sugerencia, esto no es obligatorio solo es una pequeña recomendación del compilador:

```
public DefaultTableCellRenderer devolverTablaPersonalizada(
    Color colorPrincipal, Color colorSecundario, Color colorSeleccion, Color colorFuente, Font fuente
){
    return new DefaultTableCellRenderer(){
        private static final long serialVersionUID = -8946942932242371111L;
    };
}
```

Ahora para realizar la personalización de la tabla debemos implementar un método de la interfaz **TableCellRenderer**, este método es **getTableCellRendererComponent** recordemos que para denotar que estamos implementando un método desde una interfaz es necesario colocar el decorador **@Override** o de lo contrario Java interpretará ese método como cualquier otro que hayamos creado y no funcionará como esperamos.

```
public DefaultTableCellRenderer devolverTablaPersonalizada(
    Color colorPrincipal, Color colorSecundario, Color colorSeleccion, Color colorFuente, Font fuente
){
    return new DefaultTableCellRenderer(){
        private static final long serialVersionUID = -8946942932242371111L;

        @Override
        public Component getTableCellRendererComponent(
            JTable table, Object value, boolean isSelected, boolean hasFocus, int row, int column
        ){
            
        }
    };
}
```

Este método retorna un tipo de objeto **Component** pero debemos aclarar de una vez que en realidad lo que estamos retornando aquí es cada una de las celdas que tiene la tabla. Este método entonces se encarga de tomar las celdas dentro de la tabla una por una y tratar cada celda como si fuera un **JLabel** para que nosotros podamos personalizar dicha celda como queramos.

Ademas este método recibe varios parámetros como:

* **JTable: tabla**: Nos indica la tabla donde esta contenida la celda que vamos a personalizar.
* **Object: value**: Nos indica el contenido que tiene dicha celda (el texto en nuestro caso, cabe aclarar que una celda puede contener una imágen un botón un textfield etc).
* **boolean isSelected**: Nos sirve para comprobar si la fila donde esta la celda dentro de la tabla se ha seleccionado.
* **boolean hasFocus**: Nos sirve para verificar si la celda en particular se seleccionó.
* **int row**: Nos indica la fila donde la celda esta posicionada.
* **int column**: Nos indica la columna donde la celda esa seleccionada.

_**Nota:** Como este método se esta implementando desde una interfaz estos parámetros los pasa automáticamente el compilador, nosotros no debemos preocuparnos por pasar estos datos, un caso similar ocurre con los eventos, donde los parámetros **ActionEvent**, **MouseEvent** etc, son pasados a traves del compilador y nosotros hacemos uso de estos sin necesidad de pasar este parámetro de forma manual. También ocurre con el objeto **Graphics** del canvas. Esto se cumple siempre y cuando se utilice el decorador **@Override** de lo contrario el compilador no sabrá que este es un método implementado y nos pedirá enviar estos parámetros de forma manual._

En este punto el compilador nos esta sacando un error ya que el método no esta retornando nada, bueno para esto vamos a crear un JLabel que representara la celda y será el objeto que retornemos:

```
public DefaultTableCellRenderer devolverTablaPersonalizada(
    Color colorPrincipal, Color colorSecundario, Color colorSeleccion, Color colorFuente, Font fuente
){
    return new DefaultTableCellRenderer(){
        private static final long serialVersionUID = -8946942932242371111L;

        @Override
        public Component getTableCellRendererComponent(
            JTable table, Object value, boolean isSelected, boolean hasFocus, int row, int column
        ){
            JLabel celda;

            return celda;
        }
    };
}
```

Debemos ejemplificar el JLabel pero para indicar que este JLabel es la celda actual en la tabla vamos a tener que obtener la celda a traves de una **llamada recursiva** al mismo método pero esta vez a traves del objeto **super**, esto denota que la interfaz misma será la encargada de darnos la celda actual, como se llamará al mismo método le debemos pasar como argumentos los parámetros que recibimos. Ademas como explicamos el método **getTableCellRendererComponent** nos retorna un objeto tipo **Component** y para tratarlo como JLabel debemos hacer un **Cast de objeto**.

```
public DefaultTableCellRenderer devolverTablaPersonalizada(
    Color colorPrincipal, Color colorSecundario, Color colorSeleccion, Color colorFuente, Font fuente
){
    return new DefaultTableCellRenderer(){
        private static final long serialVersionUID = -8946942932242371111L;

        @Override
        public Component getTableCellRendererComponent(
            JTable table, Object value, boolean isSelected, boolean hasFocus, int row, int column
        ){
            JLabel celda = (JLabel) super.getTableCellRendererComponent (table, value, isSelected, hasFocus, row, column);

            return celda;
        }
    };
}
```

Cabe aclarar que este paso no es obligatorio, podemos trabajar la celda a traves de la palabra clave **this**, pero esto querrá decir que vamos a tratar la celda como un tipo de objeto **Component** y no como un **JLabel**, las dos formas son compatibles, al fin y al cabo un **JLabel** hereda de un **Component**. Sin embargo tratar a la celda como un **JLabel** nos da mas posibilidades, por ejemplo cambiar el color o la fuente de la letra no se podría realizar si trabajamos la celda como un **Component**.

Con esto ya tenemos nuestra celda en forma de Label y podemos manipularla:

* Queremos que nuestros label tengan color de fondo, estos por defecto son transparente asi que para indicarle que si tendrá color llamarémos al método **setOpaque** y le pasaremos un true.
* Vamos a indicar que el label tendrá la fuente que pasamos como parámetro.
* Vamos a indicar que el color de la letra del label sera la que pasamos como parámetro.
* Ademas para nuestro caso vamos a indicar que el contenido del JLabel lo queremos de forma centrada.

```
public DefaultTableCellRenderer devolverTablaPersonalizada(
    Color colorPrincipal, Color colorSecundario, Color colorSeleccion, Color colorFuente, Font fuente
){
    return new DefaultTableCellRenderer(){
        private static final long serialVersionUID = -8946942932242371111L;

        @Override
        public Component getTableCellRendererComponent(
            JTable table, Object value, boolean isSelected, boolean hasFocus, int row, int column
        ){
            JLabel celda = (JLabel) super.getTableCellRendererComponent (table, value, isSelected, hasFocus, row, column);
            celda.setOpaque(true);
            celda.setFont(fuente);
            celda.setForeground(colorFuente);
            celda.setHorizontalAlignment(SwingConstants.CENTER);
            return celda;
        }
    };
}
```

Por el momento no hemos realizado ninguna restricción, esto quiere decir que todas las celdas de la tabla van a cumplir con el hecho de tener **color de fondo, tener la fuente y el color de fuente que le pasamos y ademas estar centradas**. Ahora queremos empezar a realizar restricciones para personalizar la tabla como queremos y aquí viene la aclaración y es que a traves de estas restricciones el desarrollador podrá personalizar la tabla a su antojo, en nuestro caso lo haremos de cierta forma pero se sabe de antemano que se podría realizar de otras maneras.

Nosotros queremos que las filas dentro de nuestra tabla tengan un color de fondo intercalado, es decir que si las filas impares tendrán cierto color, las pares otro. Para eso podemos tomar el parámetro que nos indica en que fila esta nuestra celda y preguntar si es una fila par o impar, esto se hace con el **modulo** que en caso de devolvernos un 0 se sabe que es par, de lo contrario será impar:

```
public DefaultTableCellRenderer devolverTablaPersonalizada(
    Color colorPrincipal, Color colorSecundario, Color colorSeleccion, Color colorFuente, Font fuente
){
    return new DefaultTableCellRenderer(){
        private static final long serialVersionUID = -8946942932242371111L;

        @Override
        public Component getTableCellRendererComponent(
            JTable table, Object value, boolean isSelected, boolean hasFocus, int row, int column
        ){
            JLabel celda = (JLabel) super.getTableCellRendererComponent (table, value, isSelected, hasFocus, row, column);
            celda.setOpaque(true);
            celda.setFont(fuente);
            celda.setForeground(colorFuente);
            celda.setHorizontalAlignment(SwingConstants.CENTER);
            if (row % 2 != 0)
                // Configuración filas impares
            else
                // Configuración filas pares
            return celda;
        }
    };
}
```

Ahora solo basta con configurar el color de fondo de la celda por cada condición:

```
public DefaultTableCellRenderer devolverTablaPersonalizada(
    Color colorPrincipal, Color colorSecundario, Color colorSeleccion, Color colorFuente, Font fuente
){
    return new DefaultTableCellRenderer(){
        private static final long serialVersionUID = -8946942932242371111L;

        @Override
        public Component getTableCellRendererComponent(
            JTable table, Object value, boolean isSelected, boolean hasFocus, int row, int column
        ){
            JLabel celda = (JLabel) super.getTableCellRendererComponent (table, value, isSelected, hasFocus, row, column);
            celda.setOpaque(true);
            celda.setFont(fuente);
            celda.setForeground(colorFuente);
            celda.setHorizontalAlignment(SwingConstants.CENTER);
            if (row % 2 != 0)
                celda.setBackground(colorPrincipal);
            else
                celda.setBackground(colorSecundario);
            return celda;
        }
    };
}
```

Para finalizar con la personalización queremos que una vez se seleccióne una celda, cambie de color toda la fila donde esta se encuentra, para esto podemos tomar el parámetro **isSelected** que nos retornara un booleano el cual nos indicará si la fila donde está la celda se seleccionó, si se quisiera ser mas especifico y solo se quisiera cambiar el color de fondo de esa única celda en ese caso utilizaríamos el parámetro **hasfocus**.

```
public DefaultTableCellRenderer devolverTablaPersonalizada(
    Color colorPrincipal, Color colorSecundario, Color colorSeleccion, Color colorFuente, Font fuente
){
    return new DefaultTableCellRenderer(){
        private static final long serialVersionUID = -8946942932242371111L;

        @Override
        public Component getTableCellRendererComponent(
            JTable table, Object value, boolean isSelected, boolean hasFocus, int row, int column
        ){
            JLabel celda = (JLabel) super.getTableCellRendererComponent (table, value, isSelected, hasFocus, row, column);
            celda.setOpaque(true);
            celda.setFont(fuente);
            celda.setForeground(colorFuente);
            celda.setHorizontalAlignment(SwingConstants.CENTER);
            if (row % 2 != 0)
                celda.setBackground(colorPrincipal);
            else
                celda.setBackground(colorSecundario);
            if(isSelected){
            }
            return celda;
        }
    };
}
```

Dentro de este condicional haremos dos cosas, primero cambiaremos el color de fondo de la fila, luego cambiaremos el color de fuente, y esto debido a que suponemos que en la mayoría de los casos cuando se seleccione una fila se querrá mostrar un color fuerte que resalte, asi que esto podría hacer que la letra dentro de la celda se opaque un poco y para evitar esto cambiaremos el color de fuente a blanco para que la letra pueda resaltar aun mas.

```
public DefaultTableCellRenderer devolverTablaPersonalizada(
    Color colorPrincipal, Color colorSecundario, Color colorSeleccion, Color colorFuente, Font fuente
){
    return new DefaultTableCellRenderer(){
        private static final long serialVersionUID = -8946942932242371111L;

        @Override
        public Component getTableCellRendererComponent(
            JTable table, Object value, boolean isSelected, boolean hasFocus, int row, int column
        ){
            JLabel celda = (JLabel) super.getTableCellRendererComponent (table, value, isSelected, hasFocus, row, column);
            celda.setOpaque(true);
            celda.setFont(fuente);
            celda.setForeground(colorFuente);
            celda.setHorizontalAlignment(SwingConstants.CENTER);
            if (row % 2 != 0)
                celda.setBackground(colorPrincipal);
            else
                celda.setBackground(colorSecundario);
            if(isSelected){
                celda.setBackground(colorSeleccion);
                celda.setForeground(Color.WHITE);
            }
            return celda;
        }
    };
}
```

De esta forma ha quedado listo nuestro método para personalizar la tabla.

## Personalización de un SrollBar

Cuando creamos la tabla en la sesión 11 también se realizo la personalización del ScrollBar vertical del **JScrollPane** esto debido a que el ScrollBar que viene por defecto se ve algo antiguo y no concuerda muchas veces con el resto de nuestra interfaz, para personalizar este objeto usamos el método **getVerticalScrollBar** de nuestro **JScrollPane** que nos devolvía el objeto del **ScrollBar** vertical y seguido a eso llamamos al método **setUI** este es el encargado de configurar una personalización al ScrollBar.

<figure><img src="https://camo.githubusercontent.com/54be6320bde58b0635706fb02f98274692e0c3d0fb43b0416f109eb6d7f4da79/68747470733a2f2f692e696d6775722e636f6d2f474774753750692e706e67" alt=""><figcaption></figcaption></figure>

Uso de métodos para personalizar el ScrollBar vertical.

El método **SetUI** debe recibir por parámetro un objeto de tipo **ScrollBarUI**, este objeto será el responsable de la personalización del ScrollBar.

Antes de continuar debemos ver las partes que conforman un **ScrollBar** y de esta forma comprenderemos mejor el código que se explicará a continuación:

<figure><img src="https://camo.githubusercontent.com/3d192540b832484b2d0f2fa234ba292f74e5fa6b193088af6f9c7c93381c9545/68747470733a2f2f692e696d6775722e636f6d2f4d5a614e5359772e706e67" alt=""><figcaption></figcaption></figure>

Partes de un ScrollBar.

Podemos observar que un ScrollBar contiene 3 partes principales:

* **Track:** Es el recuadro de fondo que contiene los demás elementos y por el cual podrá moverse el Thumb.
* **Thumb:** Es el recuadro o barra que se moverá a traves del Track y por el cual nosotros podremos navegar en la pantalla.
* **Buttons:** Son los botones que están en cada esquina del track y con los cuales también podremos navegar y mover el Thumb.

Notamos que para obtener este ScrollBar personalizado llamamos al método **devolverScrollPersonalizado** del servicio **GraficosAvanzadosService**. vamos a ver que realizamos en este método, para empezar veamos su definición:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    ...
    ...
}
```

Podemos notar que este método retorna un objeto de tipo **BasicScrollBarUI** y podemos verificar que este objeto es compatible con un **ScrollBarUI** ya que el primero mencionado hereda de este ultimo, podemos verificarlo si entramos a la definición de esta clase:

<figure><img src="https://camo.githubusercontent.com/199d333eceb0f255fc9cc4a9e36d83dff8d510b88b6e35e40ac039d0fc3bfeb9/68747470733a2f2f692e696d6775722e636f6d2f576779526a32642e706e67" alt=""><figcaption></figcaption></figure>

Definición de la clase BasicScrollBarUI.

También podemos notar que el método recibe por parámetros varias cosas:

* **Grosor**: Representa el grosor de la barra de navegación dentro del ScrollBar (Thumb).
* **Radio**: Representa el radio de los bordes de la barra de navegación (Thumb) Para hacer que esta sea un rectángulo con bordes redondeados o un rectángulo recto.
* **ColorFondo**: Representa el color del recuadro donde se encuentra la barra (color del track).
* **ColorBarraNormal**: Representa el color de la barra mientras esta quieta.
* **ColorBarraArrastrada**: Representa el color de la barra mientras se esta oprimiendo con el Mouse y se arrastra.

Como definimos que el método retorna un objeto de este tipo vamos a crear un objeto a traves de una ejemplificación anónima de esta clase y de una vez vamos a indicar que retornaremos este objeto anónimo:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI();
}
```

Nuevamente como queremos una personalización de este objeto vamos a abrir corchetes después de los paréntesis de la ejemplificación:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        
    };
}
```

Para personalizar completamente nuestro ScrollBar debemos implementar algunos métodos de su clase padre para asi poder decorar cada parte:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        @Override
        protected JButton createDecreaseButton(int orientation) {
        }
    
        @Override
        protected JButton createIncreaseButton(int orientation) {
        }
    
        @Override
        protected void paintTrack(Graphics g, JComponent c, Rectangle r) {

        }
    
        @Override
        protected void paintThumb(Graphics g, JComponent c, Rectangle r) {
        }
    };
}
```

* Los dos primeros métodos **createDecreaseButton** representan la personalización de ambos botones del ScrollBar.
* El método **paintTrack** se encarga de la personalización del track o recuadro de fondo del ScrollBar.
* El método **paintThumb** se encarga de la personalización del Thumb o barra de navegación del ScrollBar.

Vamos a empezar con la configuración de los botones, el método **createDecreaseButton** nos exige retornar un botón asi que crearemos un botón para luego retornarlo.

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        @Override
        protected JButton createDecreaseButton(int orientation) {
            JButton boton = new JButton();
            return boton;
        }
    
        @Override
        protected JButton createIncreaseButton(int orientation) {
            JButton boton = new JButton();
            return boton;
        }
    
        ...
        ...
    };
}
```

Con los botónes podemos crearlos a nuestro antojo, podemos incluso llamar a nuestro otro servicio **sObjGraficosService** para construirlos.

Otra posibilidad es no crear ningún botón es decir que no vamos a manejar estos métodos y podemos borrarlos de nuestro código, en este caso se generarán unos botónes que Java trae por defecto:

<figure><img src="https://camo.githubusercontent.com/09c2b55628056b99ac172ce8e51e45844163078e7d7bfab8dc4ea5f34735fc0b/68747470733a2f2f692e696d6775722e636f6d2f363568497337702e706e67" alt=""><figcaption></figcaption></figure>

ScrollBar con botones por defecto.

También se puede retornar un botón como lo estamos haciendo en este momento es decir solo ejemplificarlo y luego retornarlo, esto hará que se creen dos botones vacíos pero con su funcionamiento correcto.

<figure><img src="https://camo.githubusercontent.com/acbe3afc374447d62e85b5ae0c81d8e1b3d3d21bc75312a0c4f095843a0849c0/68747470733a2f2f692e696d6775722e636f6d2f305544324371472e706e67" alt=""><figcaption></figcaption></figure>

ScrollBar con botones vacíos.

En nuestro caso queremos que en nuestro ScrollBar los botónes no sean visibles, para esto podríamos indicarle a nuestros botónes que tengan un tamaño de 0 en x y 0 en y llamando al método **setSize**, sin embargo esto no funcionará, el compilador volverá a crear un botón vació como en la anterior imágen. En este caso vamos a necesitar el método **setPreferredSize** que nos pide como parámetro un objeto dimensión, primero vamos a crear una variable de tipo dimensión dentro de la configuración del objeto **BasicScrollBar** :

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        private Dimension d = new Dimension();
        ...
        ...
    }
}
```

Al ejemplificar el objeto dimensión y dejar el constructor vacío () se esta especificando que esta dimensión no ocupara ningún espacio, ahora le vamos a dar esta dimensión a nuestros botones:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        @Override
        protected JButton createDecreaseButton(int orientation) {
            JButton boton = new JButton();
            boton.setPreferredSize(d);
            return boton;
        }
    
        @Override
        protected JButton createIncreaseButton(int orientation) {
            JButton boton = new JButton();
            boton.setPreferredSize(d);
            return boton;
        }

        ...
        ...
    };
}
```

De esta forma nuestros botones no serán visibles dentro del ScrollBar. Ahora vamos a ocuparnos del **track** para este caso vamos a pintar un rectángulo que ocupara el total de las dimensiones del ScrollBar, y se pintara con el color de fondo que se proporcionó por parámetros:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        ...
        ...
    
        @Override
        protected void paintTrack(Graphics g, JComponent c, Rectangle r) {
            g.setColor(colorFondo);
            g.fillRect(r.x, r.y, r.width, r.height);
        }
    
        ...
        ...
    };
}
```

Para pintar el rectángulo usamos el parámetro **Graphics** que tiene el método implementado, para hallar las dimensiones del ScrollBar como la posición y el tamaño usamos el objeto **Rectangle**.

Es hora de pintar el **Thumb** o barra de navegación, en este caso queremos pintar un rectángulo con bordes redondeados, como el rectángulo tendrá curvas, sería bueno pintarlo con un objeto **Graphics2D** asi que vamos a crear este objeto a traves del padre **Graphics** que obtenemos desde los parámetros, de una vez configuraremos los algoritmos para una mejor calidad de renderizado:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        ...
        ...
    
        @Override
        protected void paintThumb(Graphics g, JComponent c, Rectangle r) {
            Graphics2D g2 = (Graphics2D) g.create();
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
        }
    };
}
```

Crearemos ahora un objeto tipo **JScrollBar** esto para verificar algunas condiciones, podemos obtenerlo a traves del parámetro **Component** y vamos a hacer el **Cast** correspondiente:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        ...
        ...
    
        @Override
        protected void paintThumb(Graphics g, JComponent c, Rectangle r) {
            Graphics2D g2 = (Graphics2D) g.create();
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            JScrollBar sb = (JScrollBar) c;
        }
    };
}
```

Ahora vamos a crear una condición y es que en los casos en que un objeto gráfico no ocupe un tamaño mayor a las dimensiones del **JScrollPane** no necesitamos mostrar los **ScrollBarr**, esto lo haremos preguntando si el ScrollBar esta habilitado o no, en caso de estar deshabilitado no retornaremos nada:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        ...
        ...
    
        @Override
        protected void paintThumb(Graphics g, JComponent c, Rectangle r) {
            Graphics2D g2 = (Graphics2D) g.create();
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            JScrollBar sb = (JScrollBar) c;
            if (!sb.isEnabled())
                return;
        }
    };
}
```

Ahora en el caso en que si este habilitado vamos a crear una segunda condición, preguntando si el usuario esta arrastrando la barra a traves del mouse, en ese caso vamos a configurar el color cuando se esta arrastrando que pasamos por el parámetro:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        ...
        ...
    
        @Override
        protected void paintThumb(Graphics g, JComponent c, Rectangle r) {
            Graphics2D g2 = (Graphics2D) g.create();
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            JScrollBar sb = (JScrollBar) c;
            if (!sb.isEnabled())
                return;
            else if (isDragging)
                g2.setPaint(colorBarraArrastrada);
        }
    };
}
```

Crearemos una tercera condición, donde vamos a preguntar si el usuario esta moviendo el ScrollBar a traves del Wheel o rueda del Mouse, para este caso nosotros optamos configurarle el color normal de la barra pasado por parámetro pero el desarrollador podrá elegir si dejar este color o cambiarlo por otro:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        ...
        ...
    
        @Override
        protected void paintThumb(Graphics g, JComponent c, Rectangle r) {
            Graphics2D g2 = (Graphics2D) g.create();
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            JScrollBar sb = (JScrollBar) c;
            if (!sb.isEnabled())
                return;
            else if (isDragging)
                g2.setPaint(colorBarraArrastrada);
            else if (isThumbRollover())
                g2.setPaint(colorBarraNormal);
        }
    };
}
```

Finalmente para el caso por defecto (Cuando la barra esta habilitada) pero no se esta moviendo vamos a configurar el color de la barra normal recibido por parámetro:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        ...
        ...
    
        @Override
        protected void paintThumb(Graphics g, JComponent c, Rectangle r) {
            Graphics2D g2 = (Graphics2D) g.create();
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            JScrollBar sb = (JScrollBar) c;
            if (!sb.isEnabled())
                return;
            else if (isDragging)
                g2.setPaint(colorBarraArrastrada);
            else if (isThumbRollover())
                g2.setPaint(colorBarraNormal);
            else
                g2.setPaint(colorBarraNormal);
        }
    };
}
```

Ahora se crea un condicional aparte, este será para preguntar si se va a pintar un **ScrollBar Horizontal o Vertical**, esto es importante ya que en muchos casos se podrían usar cualquiera de los dos y debemos tener presente esto, para saber esto basta con tomar las dimensiones del ScrollBar y preguntar cual dimensión es mas grande, el ancho o el alto:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        ...
        ...
    
        @Override
        protected void paintThumb(Graphics g, JComponent c, Rectangle r) {
            Graphics2D g2 = (Graphics2D) g.create();
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            JScrollBar sb = (JScrollBar) c;
            if (!sb.isEnabled())
                return;
            else if (isDragging)
                g2.setPaint(colorBarraArrastrada);
            else if (isThumbRollover())
                g2.setPaint(colorBarraNormal);
            else
                g2.setPaint(colorBarraNormal);
            
            if(r.width < r.height)
                //ScrollBar Vertical
            else
                //ScrollBar Horizontal
        }
    };
}
```

Ahora vamos a pintar el **Rectángulo con bordes redondeados**.

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        ...
        ...
    
        @Override
        protected void paintThumb(Graphics g, JComponent c, Rectangle r) {
            Graphics2D g2 = (Graphics2D) g.create();
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            JScrollBar sb = (JScrollBar) c;
            if (!sb.isEnabled())
                return;
            else if (isDragging)
                g2.setPaint(colorBarraArrastrada);
            else if (isThumbRollover())
                g2.setPaint(colorBarraNormal);
            else
                g2.setPaint(colorBarraNormal);
            
            if(r.width < r.height)
                g2.fillRoundRect();
            else
                g2.fillRoundRect();
        }
    };
}
```

recordemos que para dibujar este tipo de rectángulos debemos pasar como argumento la posición, el tamaño del recuadro y el tamaño de los bordes redondeados. Para ambos casos queremos que nuestro **Thumb** quede en el medio para esto vamos a realizar la operación de restar las mitades entre el grosor del **Track** y el **Thumb** como hemos explorado con anterioridad:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        ...
        ...
    
        @Override
        protected void paintThumb(Graphics g, JComponent c, Rectangle r) {
            Graphics2D g2 = (Graphics2D) g.create();
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            JScrollBar sb = (JScrollBar) c;
            if (!sb.isEnabled())
                return;
            else if (isDragging)
                g2.setPaint(colorBarraArrastrada);
            else if (isThumbRollover())
                g2.setPaint(colorBarraNormal);
            else
                g2.setPaint(colorBarraNormal);
            
            if(r.width < r.height)
                g2.fillRoundRect((r.width - grosor) / 2, r.y);
            else
                g2.fillRoundRect(r.x, (r.height - grosor) / 2);
        }
    };
}
```

Para el primer caso al ser vertical restaremos la mitad de los anchos, mientras que en el segundo caso al ser horizontal restaremos la mitad de los altos. Ahora vamos a configurar el tamaño del **Thumb**:

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        ...
        ...
    
        @Override
        protected void paintThumb(Graphics g, JComponent c, Rectangle r) {
            Graphics2D g2 = (Graphics2D) g.create();
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            JScrollBar sb = (JScrollBar) c;
            if (!sb.isEnabled())
                return;
            else if (isDragging)
                g2.setPaint(colorBarraArrastrada);
            else if (isThumbRollover())
                g2.setPaint(colorBarraNormal);
            else
                g2.setPaint(colorBarraNormal);
            
            if(r.width < r.height)
                g2.fillRoundRect((r.width - grosor) / 2, r.y, grosor, r.height);
            else
                g2.fillRoundRect(r.x, (r.height - grosor) / 2, r.width, grosor);
        }
    };
}
```

Para el primer caso al ser un **ScrollBar Vertical** se dejara un ancho igual al grosor proporcionado por parámetro y la altura que por defecto se da para el Thumb, para el segundo caso al ser un **ScrollBar Horizontal** se dejara un ancho por defecto que se da para el Thumb y la altura igual al grosor que se proporciono por parámetro. Esto hará que las barras de navegación sean tan delgadas o gruesas como el desarrollador elija.

Finalmente vamos a configurar los bordes, para este caso se proporciona el radio que se paso por parámetro, de esta forma la barra podrá quedar con bordes redondeados o como un rectángulo con esquinas rectas, depende de como configure el desarrollador.

```
public BasicScrollBarUI devolverScrollPersonalizado(
    int grosor, int radio, Color colorFondo, Color colorBarraNormal, Color colorBarraArrastrada
){
    return new BasicScrollBarUI(){
        ...
        ...
    
        @Override
        protected void paintThumb(Graphics g, JComponent c, Rectangle r) {
            Graphics2D g2 = (Graphics2D) g.create();
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            JScrollBar sb = (JScrollBar) c;
            if (!sb.isEnabled())
                return;
            else if (isDragging)
                g2.setPaint(colorBarraArrastrada);
            else if (isThumbRollover())
                g2.setPaint(colorBarraNormal);
            else
                g2.setPaint(colorBarraNormal);
            
            if(r.width < r.height)
                g2.fillRoundRect((r.width - grosor) / 2, r.y, grosor, r.height, radio, radio);
            else
                g2.fillRoundRect(r.x, (r.height - grosor) / 2, r.width, grosor, radio, radio);
        }
    };
}
```

Para el caso de la tabla no se personalizo el ScrollBar Horizontal ya que las columnas no ocupabán mas del ancho del panel, sin embargo en dado caso también podría realizarse. A continuación se muestra un ejemplo del uso de los dos ScrollBar en una interfaz de ejemplo:

<figure><img src="https://camo.githubusercontent.com/4f6f8b0fa3363e92b1a2dbdab0cb62221035a94f853193c0a67e048a50334566/68747470733a2f2f692e696d6775722e636f6d2f317334763244582e706e67" alt=""><figcaption></figcaption></figure>

Ejemplo de la personalización de ScrollBar Vertical y Horizontal

## Creación de Bordes Difuminados.

Vamos a ver un ejemplo de la creación de bordes difuminados, este método es solo un prototipo y por el momento solo funciona para algunos casos especiales, funciona perfectamente con colores grises claros (a partir de 210 de color) u otros colores muy claros también, ademas el fondo debe ser blanco. Aun asi se puede proporcionar cualquier color y no habrá ningún error, sin embargo no se vera tan bien el efecto. Para realizar esta técnica nos vamos a basar el 3 cosas importantes:

* Creación de bordes lineales a través del borde tipo **LineBorder**.
* Creación de bordes combinados (union entre dos bordes) de forma acumulada a través del borde **CompoundBorder**.
* Aumento de color en las tres lineas (Rojo, Verde, Azul) a traves de la descomposición del color.

Primero vamos a ver la definición del método:

```
public Border devolverBordeDifuminado(Color colorBase, int grosor){
}
```

Podemos notar que el método retorna un objeto tipo **Border** y recibe como parámetros:

* **ColorBase**: Es el color con el que inicia el borde y al cual se va a difuminar.
* **Grosor**: Es un entero que representa que tan grueso se quiere construir el borde, este por lo general no debe tener mucho grosor.

A continuación vamos a crear un borde que será el borde final y el cual vamos a retornar:

```
public Border devolverBordeDifuminado(Color colorBase, int grosor){
    Border bordeFinal = null;
    return bordeFinal;
}
```

Vamos a crear a continuación el borde inicial, este tendrá el color base y será un borde Lineal:

```
public Border devolverBordeDifuminado(Color colorBase, int grosor){
    Border bordeFinal = null;
    Border bordeInicial =  BorderFactory.createLineBorder(colorBase, 1, true);
    return bordeFinal;
}
```

Ahora vamos a crear un nuevo color que será derivado del color base, este tendrá las mismas coordenadas de color pero aumentada con 5 unidades. Para esto debemos descomponer el color base en sus 3 lineas principales (RGB) esto se puede realizar tomando al color en cuestión y llamando sus métodos **getRed(), getGreen(), getBlue()**:

```
public Border devolverBordeDifuminado(Color colorBase, int grosor){
    Border bordeFinal = null;
    Border bordeInicial =  BorderFactory.createLineBorder(colorBase, 1, true);  
    Color siguienteColor = new Color(colorBase.getRed() + 5, colorBase.getGreen() + 5, colorBase.getBlue() + 5);
    return bordeFinal;
}
```

Ahora vamos a crear una variable que nos servirá como contador y será clave para determinar el grosor del borde.

```
public Border devolverBordeDifuminado(Color colorBase, int grosor){
    Border bordeFinal = null;
    Border bordeInicial =  BorderFactory.createLineBorder(colorBase, 1, true);  
    Color siguienteColor = new Color(colorBase.getRed() + 5, colorBase.getGreen() + 5, colorBase.getBlue() + 5);
    int contador = 0;
    return bordeFinal;
}
```

A partir de aquí vamos a iterar sobre un ciclo, primero vamos a crear la condición para que el ciclo pueda seguir iterando, para empezar el máximo valor posible cuando se habla de colores es 255, y como notaron vamos a ir aumentando el color de 5 en 5, esto quiere decir que si en algún punto el color en cualquiera de sus 3 lineas (RGB) supera el valor de 200, ya no podrá entrar mas al ciclo, de los contrario se le va a sumar 5 y esto nos dará un valor superior a 255 y generará un error. Por otro lado debemos verificar que el borde no pase del grosor dado por parámetro.

```
public Border devolverBordeDifuminado(Color colorBase, int grosor){
    Border bordeFinal = null;
    Border bordeInicial =  BorderFactory.createLineBorder(colorBase, 1, true);  
    Color siguienteColor = new Color(colorBase.getRed() + 5, colorBase.getGreen() + 5, colorBase.getBlue() + 5);
    int contador = 0;
    while(
        siguienteColor.getRed() < 251 && siguienteColor.getGreen() < 251 && 
        siguienteColor.getBlue() < 251 && contador < grosor
    ){
    }
    return bordeFinal;
}
```

Ahora bien si estas condiciones son cumplidas vamos a empezar a construir nuestro borde compuesto, para empezar debemos construir la siguiente parte del borde compuesto, este será otro borde lineal pero esta vez tendrá el siguiente color (que es un poco mas claro) es decir que será el borde externo:

```
public Border devolverBordeDifuminado(Color colorBase, int grosor){
    Border bordeFinal = null;
    Border bordeInicial =  BorderFactory.createLineBorder(colorBase, 1, true);  
    Color siguienteColor = new Color(colorBase.getRed() + 5, colorBase.getGreen() + 5, colorBase.getBlue() + 5);
    int contador = 0;
    while(
        siguienteColor.getRed() < 251 && siguienteColor.getGreen() < 251 && 
        siguienteColor.getBlue() < 251 && contador < grosor
    ){
        Border bordeExterno =  BorderFactory.createLineBorder(siguienteColor, 1, true);
    }
    return bordeFinal;
}
```

Ahora podemos realizar un borde Compuesto y recordando un poco la **Clase 3** de nuestro curso, un borde compuesto se compone por 2 bordes asi que como parámetros recibe 2 bordes: **El borde externo como primer parámetro y el El borde interno como segundo parámetro**, para realizar el borde compuesto debemos crear una condición y esto es debido a que la primera vez que se pase por el ciclo el borde compuesto estará conformado por **el borde externo y el borde inicial**. Pero después de esto como el borde ya tendrá dos bordes integrados el borde se conformará por **el borde externo y así mismo**, de esta forma podemos acumular varios bordes en uno solo:

```
public Border devolverBordeDifuminado(Color colorBase, int grosor){
    Border bordeFinal = null;
    Border bordeInicial =  BorderFactory.createLineBorder(colorBase, 1, true);  
    Color siguienteColor = new Color(colorBase.getRed() + 5, colorBase.getGreen() + 5, colorBase.getBlue() + 5);
    int contador = 0;
    while(
        siguienteColor.getRed() < 251 && siguienteColor.getGreen() < 251 && 
        siguienteColor.getBlue() < 251 && contador < grosor
    ){
        Border bordeExterno =  BorderFactory.createLineBorder(siguienteColor, 1, true);
        if(contador == 0)
                bordeFinal = BorderFactory.createCompoundBorder(bordeExterno, bordeInicial);
            else
                bordeFinal = BorderFactory.createCompoundBorder(bordeExterno, bordeFinal);
    }
    return bordeFinal;
}
```

Por ultimo vamos a tener que actualizar el **Siguiente Color** y el **Contador**, con el siguiente color vamos a sumarle 5 unidades al color actual (sumarle a si mismo) y con el contador sumaremos una unidad nada mas:

```
public Border devolverBordeDifuminado(Color colorBase, int grosor){
    Border bordeFinal = null;
    Border bordeInicial =  BorderFactory.createLineBorder(colorBase, 1, true);  
    Color siguienteColor = new Color(colorBase.getRed() + 5, colorBase.getGreen() + 5, colorBase.getBlue() + 5);
    int contador = 0;
    while(
        siguienteColor.getRed() < 251 && siguienteColor.getGreen() < 251 && 
        siguienteColor.getBlue() < 251 && contador < grosor
    ){
        Border bordeExterno =  BorderFactory.createLineBorder(siguienteColor, 1, true);
        if(contador == 0)
            bordeFinal = BorderFactory.createCompoundBorder(bordeExterno, bordeInicial);
        else
            bordeFinal = BorderFactory.createCompoundBorder(bordeExterno, bordeFinal);
        siguienteColor = new Color(
            siguienteColor.getRed() + 5, siguienteColor.getGreen() + 5, siguienteColor.getBlue() + 5
        );
        contador ++;
    }
    return bordeFinal;
}
```

Nuestro método esta listo para usarse, vamos a usarlo a traves del otro servicio **RecursosService** para tener el borde guardado y dispuesto para las partes de nuestro proyecto que lo requieran. En nuestro Servicio **RecursosService** vamos a declarar una referencia hacia el otro servicio y luego lo vamos a obtener:

* **Declaración:**

```
// Dentro del servicio RecursosService
private GraficosAvanzadosService sGraficosAvanzados;
```

* **Obtención del servicio:**

```
// Dentro del constructor
sGraficosAvanzados = GraficosAvanzadosService.getService();
```

Ahora vamos a declarar un borde llamado **bordeDifuminado** y lo crearemos con ayuda de nuestro servicio **GraficosAvanzadosService:**

* **Declaración:**

```
private Border bordeDifuminado;
```

* **Ejemplificación:**

```
// Dentro del constructor
devolverBordeDifuminado(new Color(215, 215, 215), 8);
```

* **Método get**:

```
public Border getBordeDifuminado(){
    return bordeDifuminado;
}
```

Es hora de usar nuestro borde, para este caso vamos a usarlos en nuestro componente **Accion** cambiando el borde gris que tenía por el nuevo borde gris difuminado:

```
// Dentro del constructor de la clase AccionTemplate
this.setBorder(sRecursos.getBordeDifuminado());
```

Vamos a realizar unos pequeños ajustes de posicionamiento bajando 10px en el eje Y de la imágen, título y párrafo:

<figure><img src="https://camo.githubusercontent.com/0b46ccc1116eee03a9e90d31d6846fc0a145cc9d5034ff452388b4009bcc1d21/68747470733a2f2f692e696d6775722e636f6d2f3451476b4d4b522e706e67" alt=""><figcaption></figcaption></figure>

Ajuste de posiciones

Nuestro borde difuminado se ve así:

<figure><img src="https://camo.githubusercontent.com/14e5db3d9863f703692d3568948bc212f63f088183a6651dea61cc17c32d9c2a/68747470733a2f2f692e696d6775722e636f6d2f4b4c665a4551552e706e67" alt=""><figcaption></figcaption></figure>

Implementación de bordes difuminados.

## Creación de Bordes Redondeados

Como hemos comprobado antes, no es posible que alguno de nuestros objetos gráficos tengan un borde redondeado, en la clase anterior a traves del canvas realizamos una simulación de como podríamos crear un borde de este estilo, es hora de implementarlo. Primero vamos a ver la definición del método:

```
public Border DibujarBordeRedondeado (Color color, int radio, boolean esLineal, Image imagen) {
}
```

Podemos observar que el método retorna un objeto tipo **Border** y recibe por parámetros:

* **Color de borde:** Muchas veces se va querer construir este tipo de bordes con un contorno de algún color, para estos casos enviaremos un color.
* **Radio:** Representa el ancho y alto que tendrán los bordes redondeados del rectángulo, entre mas alto mas se notarán estos bordes.
* **esLineal**: Es un booleano que nos sirve para verificar si queremos que solo se vea el contorno del borde o vamos a crear un borde redondeado sin una linea que denote el borde.
* **Imágen**: Este parámetro se utilizara en casos especiales en donde el objeto gráfico al cual se le va a aplicar el borde redondeado está encima de una imágen o fondo.

Con lo anterior podemos darnos cuenta que existen 3 casos para querer usar estos bordes:

* Borde redondeado con un contorno (una linea que denota el borde).
* Borde redondeado sin contorno.
* Borde redondeado para un elemento que esta encima de una imagén de fondo.

Para el proyecto se usara el segundo caso pero se mostrarán ejemplos de los otros dos casos para que se entienda el propósito de esos casos. Lo primero que vamos a hacer es crear un objeto tipo **Border** y retornarlo ya que es lo que nos exige el método:

```
public Border DibujarBordeRedondeado (Color color, int radio, boolean esLineal, Image imagen) {
    Border bordeRedondeado = new Border();
    return bordeRedondeado;
}
```

Ahora seguramente el compilador nos arroja un error y es que un **Border** en realidad es una interfaz y al ser de este tipo nos va a exigir que implementemos ciertos métodos que trae por defecto:

```
public Border DibujarBordeRedondeado (Color color, int radio, boolean esLineal, Image imagen) {
    Border bordeRedondeado = new Border(){

        @Override
        public void paintBorder(Component c, Graphics g, int x, int y, int width, int height) {
        }

        @Override
        public Insets getBorderInsets(Component c) {
            return null;
        }

        @Override
        public boolean isBorderOpaque() {
            return false;
        }  
    };
    return bordeRedondeado;
}
```

Vamos a empezar con los dos últimos métodos ya que son los mas cortos, un borde exige crear un **insert** o **Padding** esto significa un espacio entre el borde y el contenido del objeto gráfico, para esto vamos a crear un objeto tipo **Inserts** que exige en su constructor 4 parámetros estos son 4 enteros que representan:

* **Espacio entre borde superior y contenido.**
* **Espacio entre borde izquierdo y contenido.**
* **Espacio entre borde inferior y contenido.**
* **Espacio entre borde derecho y contenido.**

Para hacerlo general vamos a crear un Padding pequeño de 2px, este objeto se crea dentro del método **getBorderInserts**. Por otro lado con el método **isBorderOpaque** vamos a retornar un **true** para habilitar los casos en que se dibujará el contorno del borde y en caso de no, nosotros lo gestionaremos:

```
public Border DibujarBordeRedondeado (Color color, int radio, boolean esLineal, Image imagen) {
    Border bordeRedondeado = new Border(){
        ...

        @Override
        public Insets getBorderInsets(Component c) {
            return new Insets(2, 2, 2, 2);
        }

        @Override
        public boolean isBorderOpaque() {
            return true;
        }
    };
    return bordeRedondeado;
}
```

Ahora nos concentraremos unicamente en el método **paintBorder**, pueden notar que recibe como parámetros:

* **Componente**: Objeto Gráfico al que se le añadirá el borde.
* **Graphics**: Objeto con el cual se pintará el borde redondeado.
* **Coordenadas:** Las coordenadas donde esta el objeto gráfico al cual se le añadirá el borde redondeado.
* **Tamaño:** El tamaño del objeto gráfico al cual se le añadirá el borde redondeado.

Recordemos que al ser un método implementado estos parámetros los pasa el compilador de forma automática. También podemos cambiar el nombre de la variable y no habrá ningún problema, en este caso cambiaremos los dos últimos al español.

Como vamos a pintar un borde con curvas vamos a necesitar crear un objeto **Graphics2D** y de una vez implementar los algoritmos de calidad de renderizado:

```
public Border DibujarBordeRedondeado (Color color, int radio, boolean esLineal, Image imagen) {
    Border bordeRedondeado = new Border(){

        @Override
        public void paintBorder(Component c, Graphics g, int x, int y, int ancho, int alto) {
            Graphics2D g2= (Graphics2D) g;
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
        }

        ...
    };
    return bordeRedondeado;
}
```

En la clase anterior vimos que para crear un borde necesitábamos el uso de **Areas** ya que necesitamos realizar operaciónes de sustracción y ademas no queremos tapar el contenido del objeto gráfico que tenga este borde, vamos a declarar el area principal, por otro lado necesitamos obtener el **objeto gráfico padre** esto quiere decir el objeto gráfico que lo contiene, por ejemplo un botón puede estar contenido dentro de un panel, este ultimo será entonces el padre del botón, y necesitamos obtener al padre para obtener su color de fondo y asi pintar las esquinas sobrantes del borde de dicho color. Esto se hace con el método **getParent**.

```
public Border DibujarBordeRedondeado (Color color, int radio, boolean esLineal, Image imagen) {
    Border bordeRedondeado = new Border(){

        @Override
        public void paintBorder(Component c, Graphics g, int x, int y, int ancho, int alto) {
            Graphics2D g2= (Graphics2D) g;
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            Area area;
            Component padreContenedor  = c.getParent();
        }

        ...
    };
    return bordeRedondeado;
}
```

Vamos a crear nuestro rectángulo redondeado como un **objeto gráfico 2D** y le pasaremos sus dimensiónes de una vez con ayuda de los parámetros recibidos.

```
public Border DibujarBordeRedondeado (Color color, int radio, boolean esLineal, Image imagen) {
    Border bordeRedondeado = new Border(){

        @Override
        public void paintBorder(Component c, Graphics g, int x, int y, int ancho, int alto) {
            Graphics2D g2= (Graphics2D) g;
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            Area area;
            Component padreContenedor  = c.getParent();
            RoundRectangle2D rectanguloBordeado = new RoundRectangle2D.Double();
            rectanguloBordeado.setRoundRect(x, y, ancho - 1, alto - 1, radio, radio);
        }

        ...
    };
    return bordeRedondeado;
}
```

Noten que el ancho y alto se deja con un pixel menos esto para que se pueda ver el contorno en caso de que el usuario quiera mostrarlo, por otro lado el radio de los bordes lo obtenemos de los parámetros globales del método **DibujarBordeRedondeado**. Ahora vamos a realizar una condicional que es quizás la parte mas importante del método, aquí se preguntará si el borde que se quiere dibujar será lineal o por el contrario sera un borde sin contorno:

```
public Border DibujarBordeRedondeado (Color color, int radio, boolean esLineal, Image imagen) {
    Border bordeRedondeado = new Border(){

        @Override
        public void paintBorder(Component c, Graphics g, int x, int y, int ancho, int alto) {
            Graphics2D g2= (Graphics2D) g;
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            Area area;
            Component padreContenedor  = c.getParent();
            RoundRectangle2D rectanguloBordeado = new RoundRectangle2D.Double();
            rectanguloBordeado.setRoundRect(x, y, ancho - 1, alto - 1, radio, radio);
            if(esLineal){
            }
            else{
            }
        }

        ...
    };
    return bordeRedondeado;
}
```

Esto se hace principalmente por que si se quiere dibujar un borde con contorno primero se tendrá que dibujar el fondo que se usa para borrar las partes sobrantes del borde y luego si pintar dicho borde, de lo contrario el fondo no dejara ver la linea del borde.

Por otro lado si se quiere dibujar un borde sin contorno se tendrá que primero dibujar el borde y luego dibujar el fondo o de lo contrario el fondo va a tapar el contenido del objeto gráfico. Nótese que como vamos a dibujar sobre **Contextos** el orden de las cosas tiene una gran importancia para cada caso.

Para el caso que es lineal entonces vamos a llamar a dos métodos auxiliares con su respectivo orden **dibujarFondo** y **dibujarBorde**, estos métodos se explicaran en breve, por ahora es bueno notar que el método **DibujarBorde** retorna un Area y la vamos a igualara a la que nosotros declaramos. Para el caso de pintar un borde sin contorno se va a llamar con un orden contrario los dos métodos:

```
public Border DibujarBordeRedondeado (Color color, int radio, boolean esLineal, Image imagen) {
    Border bordeRedondeado = new Border(){

        @Override
        public void paintBorder(Component c, Graphics g, int x, int y, int ancho, int alto) {
            Graphics2D g2= (Graphics2D) g;
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            Area area;
            Component padreContenedor  = c.getParent();
            RoundRectangle2D rectanguloBordeado = new RoundRectangle2D.Double();
            rectanguloBordeado.setRoundRect(x, y, ancho - 1, alto - 1, radio, radio);
            if(esLineal){
                dibujarFondo(c, padreContenedor, imagen, g2, ancho, alto);
                area = dibujarBorde(c, g2, color, x, y, ancho, alto, rectanguloBordeado);
            }
            else{
}
```

Finalmente para este método vamos a cambiar el contexto a nulo y pintar el area final, esto ultimo para evitar errores de pintado en futuros componentes y ademas para evitar el efecto pixeleado que se crea al poner un contexto distinto.

```
public Border DibujarBordeRedondeado (Color color, int radio, boolean esLineal, Image imagen) {
    Border bordeRedondeado = new Border(){

        @Override
        public void paintBorder(Component c, Graphics g, int x, int y, int ancho, int alto) {
            Graphics2D g2= (Graphics2D) g;
            g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
            g2.setRenderingHint(RenderingHints.KEY_STROKE_CONTROL, RenderingHints.VALUE_STROKE_NORMALIZE);
            Area area;
            Component padreContenedor  = c.getParent();
            RoundRectangle2D rectanguloBordeado = new RoundRectangle2D.Double();
            rectanguloBordeado.setRoundRect(x, y, ancho - 1, alto - 1, radio, radio);
            if(esLineal){
                dibujarFondo(c, padreContenedor, imagen, g2, ancho, alto);
                area = dibujarBorde(c, g2, color, x, y, ancho, alto, rectanguloBordeado);
            }
            else{
                area = dibujarBorde(c, g2, color, x, y, ancho, alto, rectanguloBordeado);
                dibujarFondo(c, padreContenedor, imagen, g2, ancho, alto);
            }
            g2.setClip(null);
            g2.draw(area);
        }
        ...
    };
    return bordeRedondeado;
}
```

Ahora se explicarán los dos métodos auxiliares que usamos, vamos a ver la definición del método **DibujarFondo**:

```
public void dibujarFondo(Component c, Component padreContenedor, Image imagen, Graphics2D g2, int ancho, int alto){
}
```

Los parámetros que pide son:

* **Objeto Gráfico**: Al cual se le aplicará el borde.
* **Objeto Gráfico**: Que contiene al objeto que se le aplicará el borde.
* **Imágen**: En caso de que el objeto este encima de una imágen de fondo se pedirá esta.
* **Graphics2D**: El cual pintara el fondo.
* **Ancho y Alto**: Tamaño del Objeto Gráfico.

Lo primero que haremos es preguntar si se ha enviado una imágen, para ese caso se sabe que se tiene un fondo y se deberá pintar para simular una transparencia.

```
public void dibujarFondo(Component c, Component padreContenedor, Image imagen, Graphics2D g2, int ancho, int alto){
    if(imagen != null)
        g2.drawImage(
            imagen, 
            0, 0, imagen.getWidth(null), imagen.getHeight(null),
            c.getX(), c.getY(), imagen.getWidth(null) + c.getX(), imagen.getHeight(null) + c.getY(),
            c
        );
    else{
    }
}
```

En este caso se dibuja una imágen usando el enfoque que se uso para pintar **Sprites**, lo que se hace es recortar la imágen original justo en la parte donde debería estar el objeto gráfico esto es para que en las esquinas que sobran del borde se vea pintada la imágen y de esa forma simule una transparencia. A continuación se muestra un ejemplo de lo que se quiere explicar con un Login.

<figure><img src="https://camo.githubusercontent.com/190b02f5923303c8727a7ef91d6d6e43e22fa05fa9b0091604a729f4c1cae3d3/68747470733a2f2f692e696d6775722e636f6d2f505155676164532e706e67" alt=""><figcaption></figcaption></figure>

Bordes redondeados sin imágen.

En este caso se quería implementar los bordes redondeados en el panel, sin embargo no se envió la imágen, incluso si se pintan los bordes restantes de transparente no hará efecto.

<figure><img src="https://camo.githubusercontent.com/d21b36781e86492fa24423a2748a363a1e2795ff45b738f1ea9bcce01b7fbd82/68747470733a2f2f692e696d6775722e636f6d2f523978677a74362e706e67" alt=""><figcaption></figcaption></figure>

Bordes redondeados con imágen.

Para este caso se pinto la imágen justo en los bordes creando un efecto de transparencia. El método esta implementado de tal forma que el desarrollador no tiene que preocuparse mas que por enviar la imágen, eso si con las mismas dimensiónes que tiene la imágen en el fondo.

Volviendo con nuestro método, en caso contrarió cuando no hay una imágen de fondo se pintará simplemente un rectangulo que tendrá el color de fondo del contenedor padre.

```
public void dibujarFondo(Component c, Component padreContenedor, Image imagen, Graphics2D g2, int ancho, int alto){
    if(imagen != null)
        g2.drawImage(
            imagen, 
            0, 0, imagen.getWidth(null), imagen.getHeight(null),
            c.getX(), c.getY(), imagen.getWidth(null) + c.getX(), imagen.getHeight(null) + c.getY(),
            c
        );
    else{
        g2.setColor(padreContenedor.getBackground());
        g2.fillRect(0, 0, ancho, alto);
    }
}
```

Ahora nos vamos a concentrar en el método **dibujarBorde**, primero veamos su definición:

```
public Area dibujarBorde(
    Component c, Graphics2D g2, Color color, int x, int y, int ancho, int alto, RectangularShape figura
){
}
```

Este método retorna un objeto tipo **Area** y recibe por parámetros:

* **Objeto Gráfico**: Objeto que tendrá el borde redondeado.
* **Graphics 2D**: El objeto por el cual se pintará el borde.
* **Posición Objeto Gráfico**.
* **Tamaño Objeto Gráfico**.
* **Figura**: Recibe la figura que tendrá el borde ya que este método será llamado por otros métodos.

Lo primero que haremos es configurar el color del contorno del borde, en caso de ser nulo se pintará con el color de fondo del objeto gráfico para que no se vea, en caso contrario obtendrá el color que se paso por parámetro:

```
public Area dibujarBorde(
    Component c, Graphics2D g2, Color color, int x, int y, int ancho, int alto, RectangularShape figura
){
    if(color == null)
        g2.setPaint(c.getBackground());
    else
        g2.setPaint(color);
}
```

Ahora crearemos el borde por medió de la operación entre areas, primero crearemos el area principal con la figura pasada por parámetro:

```
public Area dibujarBorde(
    Component c, Graphics2D g2, Color color, int x, int y, int ancho, int alto, RectangularShape figura
){
    if(color == null)
        g2.setPaint(c.getBackground());
    else
        g2.setPaint(color);
    Area area = new Area(figura);
}
```

Se crea ahora el area que representará los bordes sobrantes de la figura:

```
public Area dibujarBorde(
    Component c, Graphics2D g2, Color color, int x, int y, int ancho, int alto, RectangularShape figura
){
    if(color == null)
        g2.setPaint(c.getBackground());
    else
        g2.setPaint(color);
    Area area = new Area(figura);
    Rectangle rectangulo = new Rectangle(0,0,ancho, alto);
    Area regionBorde = new Area(rectangulo);
}
```

Ahora realizaremos una **sustracción** entre areas para que el area **regionBorde** represente justamente las partes sobrantes del borde:

```
public Area dibujarBorde(
    Component c, Graphics2D g2, Color color, int x, int y, int ancho, int alto, RectangularShape figura
){
    if(color == null)
        g2.setPaint(c.getBackground());
    else
        g2.setPaint(color);
    Area area = new Area(figura);
    Rectangle rectangulo = new Rectangle(0,0,ancho, alto);
    Area regionBorde = new Area(rectangulo);
    regionBorde.subtract(area);
}
```

Finalmente vamos a cambiar el contexto hacia esta area para que sea la única afectada cuando se pinte un fondo o en caso de que se haya pintado previamente el fondo, para que el contenido dentro del borde no sea tapado por el fondo, ademas se retorna esta area para poder ser pintada en los métodos principales en que se llamen.

```
public Area dibujarBorde(
    Component c, Graphics2D g2, Color color, int x, int y, int ancho, int alto, RectangularShape figura
){
    if(color == null)
        g2.setPaint(c.getBackground());
    else
        g2.setPaint(color);
    Area area = new Area(figura);
    Rectangle rectangulo = new Rectangle(0,0,ancho, alto);
    Area regionBorde = new Area(rectangulo);
    regionBorde.subtract(area);
    g2.setClip(regionBorde);
    return area;
}
```

Ya tenemos listo nuestro método para pintar bordes redondeados, vamos a crear un borde redondeado sin contorno desde nuestro servicio **sRecursos**:

* **Declaración:**

```
// Dentro del servicio RecursosService
private Border bordeRedondeado;
```

* **Ejemplificación:**

```
// Dentro del constructor
bordeRedondeado = sGraficosAvanzados.DibujarBordeRedondeado(null, 40, false, null);
```

* **Método get:**

```
public Border getBordeRedondeado(){
    return bordeRedondeado;
}
```

El borde ya esta listo para ser usado, en este caso se va a incorporar en los botones **bEntrar y bRegistrar** de nuestro **Login**.

<figure><img src="https://camo.githubusercontent.com/21ed2133121cad35c7c46a4478084b52c53a8e5e12b037cae57d89942d862dd9/68747470733a2f2f692e696d6775722e636f6d2f594437333668752e706e67" alt=""><figcaption></figcaption></figure>

Incorporando el borde redondeado.

Nuestro login se ve así:

<figure><img src="https://camo.githubusercontent.com/cdcca14ed7659dc7d36ae4d14d988baaf14a09c9bcba2106a6009010c5e4783c/68747470733a2f2f692e696d6775722e636f6d2f74476e724c484b2e706e67" alt=""><figcaption></figcaption></figure>

Bordes redondeados incorporados.

A continuación mostraremos otra versión de este mismo login donde se implementan **bordes redondeados con contorno** para el area de los JTextField.

<figure><img src="https://camo.githubusercontent.com/d85c713cbb9c157f8d9e7018753ce99712fc58d60087c3e9add7a2132f80b13c/68747470733a2f2f692e696d6775722e636f6d2f48744431774f4d2e706e67" alt=""><figcaption></figcaption></figure>

Login de usuario con bordes redondeados con contorno incorporado.

## Creación de Bordes Circulares

El caso de dibujar bordes circulares es bastante similar al anterior salvo algunas particularidades que explicaremos a continuación:

* **Definición del método**: En este caso se va a retornar un tipo de objeto **AbstractBorder** a diferencia del anterior donde devolvía un objeto tipo **Border**, este tipo de objeto actuá mejor para figuras diferentes a rectángulos. Como parámetros recibe:
  * **Color**: Color de contorno de la circunferencia.
  * **Boolean**: Nos indica si se quiere dibujar o no el contorno.
  * **Image**: Imágen en caso de que el objeto gráfico que incorporará el borde este encima de una imágen de fondo.

```
public AbstractBorder DibujarBordeCircular(Color color, boolean esLineal, Image imagen) {
    ...
}
```

* **Tipo AbstractBorder**: Como vamos a retornar un tipo de objeto distinto este tiene otras particularidades:
* Nos pedirá a modo de sugerencia un serial de clase
* Solo será necesario implementar el método **paintBorder**, los métodos **getBorderInsets e isBorderOpaque** ya no serán necesarios.

```
public AbstractBorder DibujarBordeCircular(Color color, boolean esLineal, Image imagen) {
    AbstractBorder bordeCircular = new AbstractBorder() {
        private static final long serialVersionUID = 2009875951859777681L;

        @Override
        public void paintBorder(Component c, Graphics g, int x, int y, int ancho, int alto) {
            ...
            ...
        }
    };
    return bordeCircular;
}
```

* **Figura:** Dentro del método **paintBorder** el procedimiento realizado para crear el borde Redondeado va a ser exactamente el mismo a excepción de la figura que se creará, en este caso crearemos un elipse:

<figure><img src="https://camo.githubusercontent.com/c65bce96302ff53dc967a9ee493fe9b33ab257d8227853065e53d9cf34c742f8/68747470733a2f2f692e696d6775722e636f6d2f546970563531382e706e67" alt=""><figcaption></figcaption></figure>

Creación de figura circular.

Note que dentro de este método también se llaman los métodos **dibujarFondo y DibujarBorde**. De esta manera el método para dibujar bordes circulares esta listo para usarse.

Vamos a crear un borde circular sin contorno en nuestro servicio **sRecursos** para incorporarlo:

* **Declaración:**

```
// Dentro del servicio RecursosService
private Border bordeCircular;
```

* **Ejemplificación:**

```
// Dentro del constructor
bordeCircular = sGraficosAvanzados.DibujarBordeCircular(null, false, null);
```

* **Método get:**

```
public Border getBordeCircular(){
    return bordeCircular;
}
```

Ahora podemos incorporar el borde circular, en este caso lo incorporaremos en la imágen del usuario que se encuentra en el componente gráfico **Navegación de usuario**.

<figure><img src="https://camo.githubusercontent.com/d8117c1925e523893d647ce91461c530e2a45609c47bf614c1fd008c349a0abf/68747470733a2f2f692e696d6775722e636f6d2f486b5a557a35422e706e67" alt=""><figcaption></figcaption></figure>

Incorporando bode circular.

Nuestra interfaz gráfica se ve así:

<figure><img src="https://camo.githubusercontent.com/ca9b7288eee1be58e005d5ee91ab8fba8a14d68dd6f8b58344118261bbb54686/68747470733a2f2f692e696d6775722e636f6d2f724a56335246742e706e67" alt=""><figcaption></figcaption></figure>

Borde Circular incorporado en nuestro proyecto.

## Resultado

Si has llegado hasta aquí **!Felicidades!** ahora sabes como funcionan cada uno de los métodos del servicio **GraficosAvanzadosService** y entre todas las particularidades vistas aprendiste **Como decorar una tabla, como personalizar un ScrollBarr, como realizar bordes difuminados, bordes redondeados y bordes circulares.**. En la siguiente clase vamos a introducirnos en el posicionamiento gestionado por **LayoutsManager**.

## Actividad

Usa el Servicio **GraficosAvanzadosService** para personalizar de forma avanzada los objetos gráficos de tu proyecto, ademas como reto puedes crear un nuevo método que se encargue de la personalización de un **JComboBox**. En internet puedes encontrar varias formas de hacerlo pero procura mantenerlo bajo un método de este servicio.

Interfaz Gráfica en Java

Curso propuesto por el grupo de trabajo Semana de Ingenio y Diseño (**SID**) de la Universidad Distrital Francisco Jose de Caldas.

### Monitor

**Cristian Felipe Patiño Cáceres** - Estudiante de Ingeniería de Sistemas de la Universidad Distrital Francisco Jose de Caldas

## Clase 15

### Objetivos

* Reconocer el modo de gestionar el posicionamiento y tamaño de objetos gráficos a traves de LayoutManager y mostrar las ventajas de utilizar este enfoque.
* Identificar alguno de los principales tipos de Layout para gestionar el posicionamiento y tamaño de objetos gráficos.
* Realizar uso del GridBadLayout dentro de nuestro proyecto y reconocer cada uno de los procesos que intervienen en su construcción.
* Explicar particularidades en torno al uso de GridBadLayout para entender a detalle como funciona este LayoutManager.

## Antes de Comenzar

Antes de iniciar con la clase de hoy vamos a realizar una actualización en la carpeta **images** de nuestro proyecto, en este caso vamos a agregar nuevas imágenes sobre productos que están contenidas en una carpeta internas llamada **productos**, usted puede descargar estas imágenes dentro del mismo repositorio entrando a la carpeta **Clase15/resources/images/productos**:

<figure><img src="https://camo.githubusercontent.com/c187d55d34ec21a30387b0332195caa5856eb18ce6842855bad81be11927821e/68747470733a2f2f692e696d6775722e636f6d2f65526d3155616b2e706e67" alt=""><figcaption></figcaption></figure>

Imágenes sobre productos.

_**Nota: Estas imágenes fueron tomadas de la página**_ [_**ed.team**_](https://ed.team/) _**son ellos los creadores y dueños de estas imágenes, aquí daremos uso a estas imágenes con motivos académicos basándonos un poco en el diseño de su página web. Por favor utilizar estas imágenes con responsabilidad en caso de ser descargadas.**_

Vamos a crear algunos nuevos objetos decoradores dentro de nuestro servicio **RecursosService**, que vamos a necesitar para la construcción de la interfaz en esta sesión, primero vamos a crear dos nuevos colores de tipo azul:

* **Declaración:**

```
// Dentro del servicio RecursosService
private Color colorAzulClaro, colorAzulMarino;
```

* **Ejemplificación**

```
// Dentro del constructor
colorAzulClaro = new Color(231, 244, 253);
colorAzulMarino = new Color(17, 146, 238);
```

* **Métodos get:**

```
public Color getColorAzulClaro(){
    return colorAzulClaro;
}

public Color getColorAzulMarino(){
    return colorAzulMarino;
}
```

También vamos a crear una fuente que usaremos en los productos que se verán a lo largo de esta clase:

* **Declaración:**

```
private Font fontTProducto;
```

* **Ejemplificación:**

```
fontTProducto = new Font("LuzSans-Book", Font.BOLD, 28);
```

* **Método Get:**

```
public Font getFontTProducto(){
    return fontTProducto;
}
```

Recordando un poco nuestro recorrido, en la clase anterior vimos el funcionamiento de cada método contenido en el servicio **GraficosAvanzadosService** para personalizar nuestros objetos gráficos de forma especial.

<figure><img src="https://camo.githubusercontent.com/ca9b7288eee1be58e005d5ee91ab8fba8a14d68dd6f8b58344118261bbb54686/68747470733a2f2f692e696d6775722e636f6d2f724a56335246742e706e67" alt=""><figcaption></figcaption></figure>

Uso del servicio Gráficos Avanzados para dar un borde circular y bordes difuminados

## Posicionamiento y tamaño de elementos con LayoutManager

En esta sesión se explicara el uso de **LayoutManager** para el posicionamiento y tamaño de objetos gráficos en la interfaz y para una explicación completa veremos los siguientes items:

* **Definición de LayoutManager**.
* **Tipos de LayoutManager**.
* **Preparación de proyecto para uso de GridBadLayout**.
* **Implementación de GridBadLayout**.

## Definición de LayoutManager

Los **LayoutManager** son objetos en Java encargados de posiciónar los objetos gráficos dentro de nuestras interfaces gráficas además de darles un tamaño de forma automática, para esto se deben tener en cuenta ciertos criterios, existen por ejemplo, varios tipos de **LayoutManagers** con distintas configuraciones pero en general, todos ofrecen el servicio de posicionar y dar tamaño a los elementos en pantalla de forma adecuada.

Hasta el momento no hemos utilizado ningún **LayoutManager** y esto es por que son complejos de utilizar y aprender, pero el tiempo que nos ahorramos aprendiendo el uso de estos **Layouts** lo gastamos en el calculo de cada posición y tamaño de cada objeto gráfico en pantalla y muchas veces haciendo multiples pruebas para comprobar que nuestros elementos en pantalla están como queremos. Aunque esto trae cierta ventaja ya que nosotros somos los que controlamos este aspecto y podemos posicionar nuestros elementos como queremos, si es verdad que el tiempo invertido para la gestión de posicionamiento y tamaña en cada objeto se vuelve bastante largo.

El uso de **LayoutManager** ademas de ahorrarnos tiempos de cálculos para posicionar nuestros elementos y darles un tamaño adecuado, tiene un serie de ventajas que valen la pena recalcar.

### Reactividad

Esta es quizás la ventaja que mas resalta en el uso de **LayoutManager** a comparación del uso de **posicionamiento por pixeles**, cuando usamos el segundo enfoque estamos dando un **tamaño y posición fija** a nuestros elementos y esto quiere decir que si la ventana se va a cambiar de tamaño en algún punto estos objetos no van a reaccionar al cambio de la pantalla y se quedaran estáticos con la posición y tamaño dado. Por el contrario cuando utilizamos **LayoutManager** nuestros objetos gráficos van a tener un **tamaño y posición dinámica** que va a depender del tamaño de la ventana y se va a reactivar cada vez que la ventana cambie este aspecto, avisando internamente que el tamaño y posición del objeto gráfico va a cambiar para que sea proporcional al nuevo tamaño de la ventana.

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase15/raw/master/gifs/sinLayout.gif" alt=""><figcaption></figcaption></figure>

Prueba de cambio de tamaño de ventana sin LayoutManager

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase15/raw/master/gifs/conLayout.gif" alt=""><figcaption></figcaption></figure>

Prueba de cambio de tamaño de ventana utilizando LayoutManager

En los ejemplos anteriores tenemos un botón que queremos que este ubicado en el medio de nuestra ventana siempre, sin embargo cuando cambiamos el tamaño de la ventana este no reacciona a menos que usemos un **LayoutManager**.

Esto se podría realizar también con un enfoque derivado del **Posicionamiento por pixeles** que es el **Posicionamiento por porcentajes**, pero de todos modos nosotros internamente tendríamos que crear métodos que de forma manual cambiaran el tamaño y posición de nuestros elementos una vez la ventana cambia de tamaño lo cual requiere más lineas de código mientras que el uso de **LayoutManager** hace que este proceso se realice de forma automática.

### Tamaño real a nuestros objetos gráficos

Esto es un problema que muchos desarrolladores no pueden solucionar cuando utilizan **Posicionamiento por pixeles** y es que cuando se quiere utilizar un **JScrollPane** debido a que lo elementos dentro de la ventana van a ocupar un tamaño mayor a esta, tenemos que utilizar **ScrollBar** para poder navegar dentro de la pantalla y asi ver todos los elementos.

El problema aquí radica en que si utilizamos el enfoque que hemos venido utilizando el **JScrollPane** no va a reconocer un tamaño real en nuestros elementos y por esta razón no va a activar los **ScrollBar** para navegar. Esto quiere decir que si por ejemplo tenemos un botón que ocupa de ancho mas de lo que la ventana puede mostrar nuestro **JScrollPane** no nos activara estas barras y no podremos ver el objeto gráfico completo. A esto le llamamos un **Tamaño Falso** por que aunque le configuremos este tamaño a nuestro botón y podamos ver el tamaño en pantalla internamente Java no lo esta reconociendo y por eso no activará barras de navegación.

Por otro lado usando **LayoutManager** el compilador es quien se encarga de dar un tamaño y por esto los tamaños serán **reales** para el programa y activará las barras de navegación.

<figure><img src="https://camo.githubusercontent.com/705324d0f605246f9771b0d881bd2249ffc8f6cec81fa19f629be6d60b0ebfb2/68747470733a2f2f692e696d6775722e636f6d2f69515a516163482e706e67" alt=""><figcaption></figcaption></figure>

Botón con un tamaño mayor sin LayoutManager

<figure><img src="https://camo.githubusercontent.com/c55543ce4ad126ec006c735797df7cbf99e2d0a77b30c1dee91cc5ac13f9e2db/68747470733a2f2f692e696d6775722e636f6d2f706c6151776b432e706e67" alt=""><figcaption></figcaption></figure>

Botón con un tamaño mayor usando LayoutManager

Este problema se puede solucionar mediante el uso del método **setPreferredSize** y el uso de objetos **Dimension** y asi Java podrá reconocer el **Tamaño Real** de nuestros objetos Gráficos y activar las barras de navegación en un **JScrollPane** cuando usemos **Posicionamiento por pixeles**. Sin embargo esto implica crear un objeto **Dimension** nuevo en memoria por cada objeto gráfico en nuestra interfaz lo cual llenará mas la memoria y habrá mas consumos de recursos.

### Tamaño dinámico de la ventana

Cuando utilizamos **posicionamiento por pixeles** siempre debemos estar pendiente del tamaño ideal de nuestra ventana mientras realizamos su contenido, sin embargo esto queda de lado usando **LayoutManager**, una vez nuestros objetos están creados y agregados, solo basta con utilizar el método **Pack()** de la ventana y esta ajustara su tamaño para que todos los elementos en pantalla puedan verse de manera adecuada.

***

Los **LayoutManager** posiciónan los elementos bajo ciertos criterios y depende del **Layout** que vamos a manejar en la siguiente sección se explicaran las características generales de los **LayoutManager** mas importantes.

## Tipos de LayoutManager

### BorderLayout

Este **LayoutManager** es el que viene por defecto en la mayoría de objetos encargados de contener otro objetos tales como **Frames, Paneles, ScrollPane** etc. Divide la ventana en 5 partes: **centro, arriba, abajo, derecha e izquierda** y esto implica cierta estructura:

* Los objetos que se ubiquen en la parte superior o inferior va a ocupar siempre todo el ancho de la ventana.
* Los objetos que se ubiquen en los laterales ocuparan siempre todo el alto de la ventana.
* El objeto ubicado en el centro tratará siempre de expandirse en ambas dimensiones, de esta forma si hay un único elemento central ocupara toda la ventana, de lo contrario se extenderá hasta el limite con sus objetos compañeros.

El **BorderLayout** es ideal para posicionar elementos generales en las ventanas ya que tiene una estructura básica de una aplicación de escritorio. Es común que los JFrames utilicen este **LayoutManager** para dar la estructura principal de la aplicación y cada elemento en especifico use sus propios layouts.

A continuación veremos un ejemplo sencillo:

<figure><img src="https://camo.githubusercontent.com/6491aad6fda59bbeb41ee2f6faedbb9a372218b53228b36e2c690b9b421b9fd2/68747470733a2f2f692e696d6775722e636f6d2f454131416b764c2e706e67" alt=""><figcaption></figcaption></figure>

Implementación BorderLayout

<figure><img src="https://camo.githubusercontent.com/e24dca8a7b5fd63d8a67f9def2b4805f493d2e5aa437736a58fd68fbce553fb2/68747470733a2f2f692e696d6775722e636f6d2f786871314238472e706e67" alt=""><figcaption></figcaption></figure>

Resultado implementación BorderLayout

Podemos ver algunas particularidades:

* **Construcción Layout**: Basta con ejemplificarlos y agregarlo mediante el método **setLayout**, en este caso al ser una ventana este paso esta de mas ya que por defecto tiene este layout, pero se coloco para mostrar su construcción.
* **Dirección de Objetos Gráficos**: Para indicarle a nuestra aplicación debemos indicar la dirección del objeto una vez se agrega a la ventana mediante el objeto **BorderLayout** y sus opciones **North, South, West, East, Center**.
* **Tamaño de objetos gráficos:** Podemos notar que cuando construimos los paneles, le pasamos como argumentos 0, ya que nosotros no nos encargaremos de dar la posición o tamaño como lo hacíamos antes, ahora es el LayoutManager.
* **Tamaño de Paneles:** Por defecto el compilador ira agrandando o reduciendo la ventana a medida que cada panel ubicado va agregando objetos, en este caso solo se crearon paneles vacíos, asi que para representar que ocuparan un tamaño usamos el método **setPreferredSize**, pero esto no será necesario una vez cada panel tenga elementos internos.
* **Tamaño de la ventana**: No es necesario indicarle un tamaño fijo a la ventana, mediante el método **pack()** la ventana encontrará el menor tamaño para que los objetos gráficos quepan en ella.

Como desventaja esta el hecho de que este **LayoutManager** impone una sola estructura para crear aplicaciónes, si queremos dar otra forma a nuestra aplicación no será posible.

### FlowLayout

Este **LayoutManager** coloca los objetos gráficos de forma horizontal, creando una fila dentro de la ventana. De esta forma el layout posicióna los elementos de igual forma a lo largo del eje X. Ademas trae ciertas características, por ejemplo si la ventana tiene un ancho muy grande y sobra espacio tratara siempre de ubicar los elementos de forma centrada. Por otro lado si la ventana no ocupa el ancho suficiente para colocar todos los elementos el **LayoutManager** automáticamente crea una fila debajo para poder ubicar los objetos gráficos sobrantes y siempre tratando de centrar estos elementos.

Es ideal para usarse por ejemplo en barras de herramientas, barras de títulos, menus horizontales etc.

A continuación se muestra un ejemplo simple de como usar este **FlowLayout**:

<figure><img src="https://camo.githubusercontent.com/b1ac2ff746e16435b3dd0e71e662e59b8369c3c1a2b45fc5dff1fbb9073941dd/68747470733a2f2f692e696d6775722e636f6d2f585471397a447a2e706e67" alt=""><figcaption></figcaption></figure>

Implementación de FlowLayout

<figure><img src="https://camo.githubusercontent.com/18c4afd940a71f8b016397c54302c39a80d33fd7906c94aabe9db82da4b71869/68747470733a2f2f692e696d6775722e636f6d2f6c3065535863762e706e67" alt=""><figcaption></figcaption></figure>

Resultado del código

En este caso se creo una barra de titulo o **Header** bastante sencillo a partir del uso de **FlowLayout**. Noten que al crear objetos gráficos no estamos proporcionando ningún tamaño ni posición ya que de eso se va a encargar automáticamente el **LayoutManager** el resto del proceso de construcción es igual al que hemos manejado.

Aunque es un Layout simple e ideal para este tipo de casos, tiene ciertas desventajas:

* **Posicionamiento Horizontal:** Solo funciona para posicionar de manera horizontal, no podemos controlar la posición de forma vertical.
* **Espacio entre objetos gráficos:** Este layout por defecto junta todos los elementos y los tratará de centrar, si queremos simular espaciado entre objetos gráficos debemos realizar algunas configuraciones adicionales como usar **bordes vacíos**.
* **Alineación Vertical Automática:** No es posible realizar una alineación vertical entre elementos de forma manual, si un elemento es mas alto que el resto, el **FlowLayout** tratara siempre de centrarlos de forma vertical pero si queremos que alguno de esos este en la parte superior o inferior de la fila no será posible.

### BoxLayout

Este **LayoutManager** esta creado dentro de la librería **Swing** y cubre la necesidad de poder posicionar elementos de forma vertical, pero al igual que su antecesor si se decea, se puede posicionar elementos de forma horizontal lo cual hace de este **LayoutManager** un objeto mas completo para posicionar elementos. Sin embargo no se puede posicionar sobre las dos dimensiones a la vez, el desarrollador debe elegir sobre cual eje se posicionarán los elementos.

Puede usarse para menus verticales, menus horizontales, combinaciones entre posiciones, barras títulos, barras de herramientas etc.

A continuación se muestra un ejemplo de uso:

<figure><img src="https://camo.githubusercontent.com/043518d897c5138bdae69d635f3c978150379b685b9807ef44ca831ff1c8242d/68747470733a2f2f692e696d6775722e636f6d2f776f4b46634b4b2e706e67" alt=""><figcaption></figcaption></figure>

Implementación BoxLayout

<figure><img src="https://camo.githubusercontent.com/c06a7fd72be67919939c1728adce7b123cde2e70d4b0123058a560d5ece11179/68747470733a2f2f692e696d6775722e636f6d2f564a6a4c3241732e706e67" alt=""><figcaption></figcaption></figure>

Resultado de código

Del anterior ejemplo se pueden notar varias cosas:

* **Creación BoxLayout**: Para crear este **LayoutManager** se debe pasar por parámetro le objeto gráfico que contendrá el Layout y ademas la orientación siento:
  * **X\_AXIS**: para posicionar elementos de forma Horizontal
  * **Y\_AXIS**: para posicionar elementos de forma Vertical.
  * **LINE\_AXIS o PAGE\_AXIS**: Le da la responsabilidad a cada objeto gráfico de indicar si se posicionará deforma horizontal o vertical de acuerdo al anterior objeto agregado.
* **Espacio entre elementos**: El **BoxLayout** maneja unos elementos especiales para realizar la separación entre elementos siendo:
  * **RigidArea**: Un elemento que ocupa un espacio con una dimensión que nosotros le damos y que se encarga de separar los elementos.
  * **HorizontalGlue**: Crea la separación maxima entre elementos de forma horizontal, es util cuando se quiere dos elementos en cada esquina horizontal.
  * **VerticalGlue**: Crea la separación maxima entre elementos de forma Vertical, es util cuando se quiere dos elementos en cada esquina Vertical.
  * **Filler**: Este elemento crea 3 dimensiones por defecto para denotar cual sera la menor distancia, la distancia por defecto y la mayor distancia entre elementos en ambos ejes. Es el mas util para configurar espacios dinámicos a medida que el tamaño de la ventana cambie.
* **Alineación:** A diferencia de su antecesor los objetos gráficos dentro del panel con el **BoxLayout** pueden alinearse a nuestro antojo ya sea de forma vertical u horizontal. Esto quiere decir que si por ejemplo estamos posicionando de forma vertical ciertos elementos pero queremos que algunos estén en la parte izquierda, otros en la derecha y otros en el centro, podamos realizar esta alineación. Debemos llamar al objeto **Component** de java y proporcionar la alineación que queremos. Sin embargo esta siempre suele dar problemas.
* **Combinación de Layouts**: Por supuesto se puede usar varios **Layouts** para distintos objetos gráficos por ejemplo en este caso la ventana no maneja ningún Layout, mientras que el panel **pContenido** si tiene el **BoxLayout**.

### GridLayout

Este **LayoutManger** permite colocar elementos dentro de una matriz lo cual nos da la posibilidad de posicionar objetos gráficos de manera horizontal y vertical al mismo tiempo. Con este Layout puedes proporcionar el numero de filas y columnas donde estarán contenidos los elementos. Muchas veces se suele usar **GridLayout** para mostrar una colección de elementos del mismo tipo y bajo unas mismas condiciones.

Puede ser usado para crear teclados virtuales, crear sudokus, sopas de leras, crear tarjetas con muestra de productos etc. A continuación se muestra un ejemplo:

<figure><img src="https://camo.githubusercontent.com/90bb6d629cf3420891077eef093ea2ae83d206b71d3b8532a968bb30143996b2/68747470733a2f2f692e696d6775722e636f6d2f30424f567a365a2e706e67" alt=""><figcaption></figcaption></figure>

Implementación GridLayout

<figure><img src="https://camo.githubusercontent.com/a17e9233988d758a469dd18c2fba6bd3cf9531d308ecd4a5ee90c203ddce1e0e/68747470733a2f2f692e696d6775722e636f6d2f57446c626d50762e706e67" alt=""><figcaption></figcaption></figure>

Resultado código GridLayout

En el anterior ejemplo se representó una sopa de letras con ayuda de un **GridBagLayout**, podemos notar varias particularidades:

* **Construcción Layout**: para construir un GridLayout podemos pasar 4 parámetros.
  * Numero Filas.
  * Numero Columnas.
  * Espacio horizontal entre objetos gráficos.
  * Espacio vertical entre objetos gráficos.
* **Arreglo de Objetos Gráficos**: Como podemos ver es posible crear arreglos de tipo de algún objeto gráfico y de hecho esta es la forma mas común para agregar elementos a un **GridLayout**.

El uso de este Layout aunque nos da varias posibilidades para posicionar en ambas dimensiones tiene ciertas desventajas:

* **Mismo tamaño de elementos:** Cuando usamos **GridLayout** los elementos dentro de este van a ocupar todos el mismo tamaño, no es posible cambiar e tamaño de un solo elemento dentro del Grid.
* **Ocupación:** Cada elemento estrictamente ocupará una celda dentro del Grid, si quisiéramos que un elemento ocupe toda una fila o columna esto no será posible. Tampoco podemos hacer que un objeto ocupe dos o mas celdas.

### GridBadLayout

Este **LayoutManager** es el mas sofisticado y pretende cubrir todas las falencias de los demás Layouts, para empezar con este podemos posicionar elementos en ambas dimensiones (de forma vertical y horizontal), podemos realizar ademas una serie de configuraciones como:

* Establecer posición de un elemento dentro del grid de forma individual.
* Establecer cuantas celdas puede ocupar un elemento o dar su propio espacio destinado dentro del Grid.
* Establecer si un elemento va a ocupar todo el espacio dentro de su espacio destinado.
* Establecer la posición interna dentro de su espacio destinado.
* Establecer el el espaciado entre objetos de forma individual y hacia cualquier dirección también conocido como margin.
* Establecer el el espaciado interno de cada objeto de forma individual también conocido como padding.
* Establecer si una fila o columna va a tener mayor tamaño que las demás.
* Crear filas y columnas de formas dinámicas, no es necesario establecer un tamaño fijo del Grid

Estas características serán explicadas una a una mas adelante en esta sesión. Otra característica es que si el **GridBagLayout** solo mantiene un objeto, independientemente de las configuraciónes dadas con las restricciones, colocará ese único elemento en el centro tanto de forma horizontal como vertical.

Esto da muchas posibilidades para crear interfaces como nosotros queremos y con distintas formas que con los anteriores Layout no es posible. En la siguiente sección vamos a implementar este **LayoutManager** en nuestro proyecto asi que no vamos a mostrar un pequeño ejemplo. Pero antes vamos a construir rápidamente los preparativos para usar nuestro **GridBadLayout**.

## Preparación de proyecto para uso de GridBadLayout

Queremos mostrar una seríe de productos en nuestra interfaz gráfica, en este caso los productos a mostrar serán una serie de cursos que nuestra empresa inventada dicta en linea, bueno esta información acerca de cada curso podría obtenerse de forma externa así que vamos a crear en esta sección todo lo necesario para que la aplicación pueda obtener, gestionar y mostrar esta información.

Para empezar vamos a simular el contenido de la información mediante un archivo plano asi que sería bueno revisar la estructura de nuestro archivo, en este caso llamado **productos.txt** ubicado en nuestro paquete **archives**:

<figure><img src="https://camo.githubusercontent.com/56862ce7e6ac14466338d2d474f4e9a9cd21193599e7498cd327987e8abf9e25/68747470733a2f2f692e696d6775722e636f6d2f764a75665842532e706e67" alt=""><figcaption></figcaption></figure>

Archivo plano creado

Lo primero será entonces identificar de que se compone nuestro archivo plano:

<figure><img src="https://camo.githubusercontent.com/6d1c289561cbeac17a7e8ce099da23b0a46e32b188a2db1dc98d1e958f427a7c/68747470733a2f2f692e696d6775722e636f6d2f43526a4e6f42582e706e67" alt=""><figcaption></figcaption></figure>

Contenido en archivo plano productos.txt

Podemos observar mediante este archivo plano que un curso se compone de:

* **id de Curso**.
* **Nombre de Curso**.
* **Descripción de Curso**.
* **Area de conocimiento de Curso**.
* **Puntuación de Curso**.
* **Dirección imágen de Curso**.

Ahora crearemos una **Clase Modelo** que encapsule toda esta información y de esta forma poder manejar los datos a traves de objetos:

<figure><img src="https://camo.githubusercontent.com/6561621245adf868ad3ed3cf26a154a802445d09d973508b45e19e7e7600646c/68747470733a2f2f692e696d6775722e636f6d2f4c644e67494f522e706e67" alt=""><figcaption></figcaption></figure>

Clase modelo que representa un producto

Vamos a declarar sus correspondientes atributos junto a sus métodos **get y set**:

```
public class Producto {
    private int id;
    private String nombreProducto, descripcion, campo, puntuacion;
    private ImageIcon imagen;

    public int getId(){
        return id;
    }

    public String getNombreProducto(){
        return  nombreProducto;
    }

    public String getDescripcion(){
        return  descripcion;
    }

    public String getCampo(){
        return  campo;
    }

    public String getPuntuacion(){
        return puntuacion;
    }

    public ImageIcon getImagen(){
        return imagen;
    }

    public void setId(int id){
        this.id = id;
    }

    public void setNombreProducto(String nombreProducto){
        this.nombreProducto = nombreProducto;
    }

    public void setDescripcion(String descripcion){
        this.descripcion = descripcion;
    }

    public void setCampo(String campo){
        this.campo = campo;
    }

    public void setPuntuacion(String puntuacion){
        this.puntuacion = puntuacion;
    }

    public void setImagen(ImageIcon imagen){
        this.imagen = imagen;
    }
}
```

Ahora vamos a crear un **Controlador externo** que simulara la gestión y obtención directa de la información de forma foránea:

<figure><img src="https://camo.githubusercontent.com/7914bf4232f8402b07df08371b93292be734471d0fa73727076f455368558cf5/68747470733a2f2f692e696d6775722e636f6d2f4776486c4d395a2e706e67" alt=""><figcaption></figcaption></figure>

Creación Controlador de productos

Vamos a declarar y ejemplificar nuestro arrayList que será la lista de los productos:

* **Declaración:**

```
// Dentro del controlador ControlProductos
private ArrayList<Producto> productos;
```

* **Ejemplificación:**

```
public ControlProductos(){
    productos = new ArrayList<Producto>();
}
```

Ahora vamos a crear el método encargado de cargar la información externa para ser contenida en la lista:

```
public void cargarDatos(){
    File archivo = null;
    FileReader fr = null;
    BufferedReader br = null;
    try {
        archivo = new File ("Clase15/src/archives/productos.txt");
        fr = new FileReader(archivo);
        br = new BufferedReader(fr);
        String linea;
        while((linea=br.readLine())!=null){
            String[] atributos = linea.split(",");
            Producto producto = new Producto();
            producto.setId(Integer.parseInt(atributos[0]));
            producto.setNombreProducto(atributos[1]);
            producto.setDescripcion(atributos[2]);
            producto.setCampo(atributos[3]);
            producto.setPuntuacion(atributos[4]);
            producto.setImagen(new ImageIcon(atributos[5]));
            productos.add(producto);
        }
        fr.close(); 
    }
    catch(Exception e){
        e.printStackTrace();
    }
}
```

Finalmente vamos a devolver la lista de los productos para que sea el servicio quien gestione la información:

```
public ArrayList<Producto> getProductos(){
    return productos;
}
```

Nuestro controlador esta listo, ahora vamos adentrarnos en nuestra aplicación frontend y vamos a crear un **Servicio** encargado de tomar esta información para ser gestionada:

<figure><img src="https://camo.githubusercontent.com/79f736e254b23f4156293aff3a5eb24212af32ff64dcd4392bef270f4aae4d08/68747470733a2f2f692e696d6775722e636f6d2f53774f645544352e706e67" alt=""><figcaption></figcaption></figure>

Servicio ProductoService Creado.

Primero crearemos la estructura básica del servicio:

* **Referencia estática a si mismo**

```
private static ProductoService servicio;
```

* **Método para obtención única del servicio:**

```
public static ProductoService getService(){
    if(servicio == null)
        servicio = new ProductoService();
    return servicio;
}
```

* **Método constructor**:

```
public ProductoService(){
}
```

Ahora vamos a declarar y ejemplificar una referencia al controlador para obtener la información externa, adicionalmente vamos a declarar un arrayList para apuntar a la lista contenida en el controlador:

* **Declaración:**

```
// Dentro del servicio ProductoService
private ControlProductos cProductos;
private ArrayList<Producto> productos;
```

* **Ejemplificación y obtención de información:**

```
public ProductoService(){
    cProductos = new ControlProductos();
    productos = cProductos.getProductos();
}
```

Vamos a crear un método que nos retorne un producto de acuerdo a la posición que le enviemos:

```
public Producto devolverProducto(int posicion){
    try{
        return productos.get(posicion);
    }
    catch(Exception e){
        return null;
    }
}
```

Ya tenemos todo listo en cuanto a la gestión de la información externa, ahora podemos concentrarnos en el componente **Productos**. Dentro de este componente vamos a realizar una **Reutilización de componentes** y para esto crearemos otro componente al cual llamaremos **Producto** y este se encargará de encapsular la estructura básica de cada uno de los cursos, por ahora solo vamos a crearlo y a realizar su código básico:

<figure><img src="https://camo.githubusercontent.com/c55bbf96fa7f2f7d4bcb0518cc1e09f0232339c9f35102c8f69304055c5380ca/68747470733a2f2f692e696d6775722e636f6d2f716931537665412e706e67" alt=""><figcaption></figcaption></figure>

Creación del componente producto

Vamos a crear el código base de la clase **ProductoComponent**:

* **Declaración de clase Template:**

```
// Dentro de la clase ProductoComponent
private ProductoTemplate productoTemplate;
```

* **Creación de inyección:**

```
public ProductoComponent(){
    productoTemplate = new ProductoTemplate(this);
}
```

* **Método get de clase Template:**

```
public ProductoTemplate getProductoTemplate(){
    return productoTemplate;
}
```

Ahora en la clase **ProductoTemplate** vamos a extender de un JPanel, cerraremos la inyección y llamaremos a los servicios gráficos que podamos necesitar:

* **Declaraciones:**

```
// Declaración Servicios y dependencias
private ProductoComponent productoComponent;
private ObjGraficosService sObjGraficos;
private RecursosService sRecursos;
```

* **Cerrando Inyección y obteniendo servicios:**

```
public ProductoTemplate(ProductoComponent productoComponent){

    this.productoComponent = productoComponent;
    this.productoComponent.getClass();
    this.sObjGraficos = ObjGraficosService.getService();
    this.sRecursos = RecursosService.getService();
}
```

Para acabar y como sabemos que este componente se usara de forma recursiva vamos a pedir por parámetro esta vez un objeto tipo **Producto** para poder obtener la información de cada uno de ellos:

* **Clase ProductoComponent:**

```
public ProductoComponent(Producto producto){
    productoTemplate = new ProductoTemplate(this, producto);
}
```

* **Clase ProductoTemplate:**

```
public ProductoTemplate(ProductoComponent productoComponent, Producto producto){
    ...
    ...
}
```

Dentro de la case **ProductoTemplate** vamos a igualar el parámetro recibido con un atributo que declaremos global ya que es probable que lo necesitemos en otras partes distintas al constructor:

```
private Producto producto;

public ProductoTemplate(ProductoComponent productoComponent, Producto producto){
    this.producto = producto;
    ...
    ...
}
```

Con esto estamos listos para empezar a construir nuestros componentes a traves del **GridBagLayout**, en la siguiente sección vamos a ver a profundidad como utilizar este **LayoutManager** al tempo que vamos construyendo nuestro componente gráfico.

## Implementación de GridBadLayout

Vamos a configurar primero el componente padre en este caso **Productos** y en su clase **ProductosComponent** lo primero por hacer es obtener el servicio **ProductosService** para traer la información de los productos una vez se pidan:

* **Declaración:**

```
// Dentro de la clase ProductosComponent
private ProductoService sProducto;
```

* **Obtención del servicio:**

```
public ProductosComponent(){
    sProducto = ProductoService.getService();
    productosTemplate = new ProductosTemplate(this);
}
```

_**Nota:** Es importante que la obtención del servicio se posicione antes de la inyección con la parte gráfica ya que necesitamos tener lista la información antes de mostrar en pantalla_.

Vamos a crear un método que nos será útil una vez estemos en la clase template:

* Método para devolver un producto:

```
public Producto devolverProducto(int posicion){
    return this.sProducto.devolverProducto(posicion);
}
```

Ahora nos concentraremos en la clase **ProductosTemplate**, primero vamos a realizar tres cosas importantes en las configuraciones generales del componente, vamos a cambiar el color de fondo por un gris claro, vamos a retirar la configuración que dejaba nulo el **LayoutManager** y también borraremos la configuración del tamaño del componente:

```
this.setBackground(sRecursos.getColorGrisClaro());
***this.setLayout(null);*** // Se borra esta linea
***this.setSize(850, 600);*** // Se borra esta linea
```

Vamos a llamar a los servicios gráficos necesarios para ayudarnos con la creación de objetos gráficos:

* **Declaración:**

```
private ObjGraficosService sObjGraficos;
private RecursosService sRecursos;
```

* **Obtención de servicios:**

```
// Dentro del constructor
this.sRecursos = RecursosService.getService();
this.sObjGraficos = ObjGraficosService.getService();
```

Vamos a crear dos elementos que serán muy importantes para posicionar y colocar nuestros objetos gráficos:

* **Layout Manager tipo GridBadLayout**: Es el layout y quien se encargará de asignar el tamaño y posición y elementos dentro del componente.
* **Objeto de configuraciones GridBagConstraints**: Es el objeto encargado de configurar ciertas restricciones que nos ayudarán a indicarle al Layout como estará posicionado y que tamaño tendrá cada objeto gráfico.
* **Declaración:**

```
private GridBagLayout lGrid;
private GridBagConstraints gbc;
```

* **Ejemplificación:**

```
// Dentro del constructor
lGrid = new GridBagLayout();
gbc = new GridBagConstraints();
```

Ya teniendo listo el Layout, podemos establecer este **LayoutManager** en nuestro componente:

```
// Dentro del constructor
this.setLayout(lGrid);
```

Antes de siquiera crear algún elemento en nuestro componente, conviene explicar de que se tratan cada una de estas restricciones que le indicarán al **GridBagLayout** como estarán posicionado nuestros elementos.

### Restricciones

#### **Posición de objeto dentro del Grid**:

Recordemos que un GridBagLayout crea una matriz imaginaria donde nosotros vamos a posicionar nuestros elementos de forma vertical y horizontal. Bien pues debemos siempre indicar en que fila y columna dentro del grid va comenzar algún elemento, esto lo haremos configurando el objeto **GridBagConstraints** y usando los atributos **gridx y gridy**.

La fila y columna inicial es la numero 0 y este es el numero por defecto si no se configura el elemento, pero es recomendable siempre configurar este aspecto.

* **Ejemplo:**

Aquí estamos indicando que un elemento se posicionará en la fila 0 y columna 0 dentro del **GridBagLayout**.

```
gbc.gridx = 0;
gbc.gridy = 0;
```

Aquí estamos indicando que un elemento se posicionará en la fila 3 y columna 2 dentro del **GridBagLayout**.

```
gbc.gridx = 2;
gbc.gridy = 3;
```

#### **Espacio destinado**:

Como habíamos mencionado en la descripción de este **LayoutManager**, a diferencia de un **GridLayout** en este si tenemos la posibilidad de indicar si vamos a destinar mas de una celda en nuestra matriz o grid para un elemento en especifico. Para este caso podemos usar los atributos:

* **gridwidth**: que nos indicará cuantas columnas van a estar destinadas para nuestro elemento dentro del Grid.
* **gridheight**: que nos indicará cuantas filas van a estar destinadas para nuestro elemento dentro del Grid.

Por defecto un elemento tendrá un **gridwidth y gridheight** de 1 es decir que ocupan una celda como espacio.

* **Ejemplo:**

Aquí nuestro elemento a posicionar tendrá destinado tres columnas y una fila dentro del Grid.

```
gbc.gridwidth = 3;
gbc.gridheight = 1;
```

#### **Estiramiento de objeto dentro de su espacio destinado**:

Independientemente de si un elemento tiene destinada una celda o pueda tener varias filas o columnas, puede que este objeto si requiera ocupar todo este espacio, o en caso contrario solo queremos que ocupe un espacio mínimo dentro de su espacio destinado y queremos intencionalmente que exista un campo sobrante (vació) dentro de su espacio destinado.

Otro caso podría ser un elemento el cual queremos que ocupe todo el ancho de su espacio pero el alto no lo queremos ocupar del todo, o viceversa.

Por defecto un elemento solo va a ocupar su tamaño justo, por ejemplo un botón con un texto solo ocupará lo suficiente para que el texto pueda leerse dentro del botón pero si queremos hacer que el botón se estire y ocupe todo su espacio podemos llamar al atributo **fill** y darle como valores:

* **NONE == 0:** Para que no se estire en ningún sentido, es la opción por defecto.
* **BOTH == 1:** Para que se estire en ambas dimensiones.
* **HORIZONTAL == 2:** Para que se estire sólo en horizontal.
* **VERTICAL == 3:** Para que se estire sólo en vertical.

Se puede usar el numero o la configuración explicita, como el desarrollador prefiera.

* **Ejemplo:**

```
// Objeto sin estiramiento (por defecto)
gbc.fill = 0;
gbc.fill = GridBagConstraints.NONE;

// Objeto sin estiramiento de ambas dimensiones
gbc.fill = 1;
gbc.fill = GridBagConstraints.BOTH;

// Objeto sin estiramiento de forma horizontal
gbc.fill = 2;
gbc.fill = GridBagConstraints.HORIZONTAL;

// Objeto sin estiramiento de forma Vertical
gbc.fill = 3;
gbc.fill = GridBagConstraints.VERTICAL;
```

#### **Posición dentro del espacio destinado:**

Para los objetos que no ocuparán todas las dimensiones de su espacio destinado, podemos configurar en que posición interna va a colocarse, para esto tenemos el atributo **anchor** y le podemos pasar como valor:

* **CENTER == 10:** Para que se posicione en el centro de la celda, Es la opción por defecto.
* **NORTH == 11:** Para que se posicione en a la parte superior y centrado en el eje horizontal.
* **NORTHEAST == 12:** Para que se posicione en la esquina superior derecha.
* **EAST == 13:** Para que se posicione en el lado derecho y centrado en el eje vertical.
* **SOUTHEAST == 14:** Para que se posicione en la esquina inferior derecha.
* **SOUTH == 15:** Para que se posicione en el lado inferior y centrado en el eje horizontal.
* **SOUTHWEST == 16:** Para que se posicione en la esquina inferior izquierda.
* **WEST == 17:** Para que se posicione en el lado izquierdo y centrado en el eje vertical.
* **NORTHWEST == 18:** Para que se posicione en la esquina superior izquierda.

Se puede usar el numero o la configuración explicita, como el desarrollador prefiera.

* **Ejemplo:**

```
// Objeto gráfico posicionado en el centro
gbc.anchor = 10;
gbc.anchor = GridBagConstraints.CENTER;

// Objeto gráfico posicionado en la esquina superior derecha
gbc.anchor = 12;
gbc.anchor = GridBagConstraints.NORTHEAST;

// Objeto gráfico posicionado en el lado izquierdo
gbc.anchor = 17;
gbc.anchor = GridBagConstraints.WEST;
```

#### **Margin de un objeto:**

El Margin de un objeto es el espacio que tendrá en pixeles con respecto al exterior, esto quiere decir el espacio entre el borde y los elementos que estén al rededor del objeto gráfico, puede ser hacia otro elemento que este arriba, abajo o a los lados, en caso de no haber algún elemento entonces será el espaciado contra la esquina de la ventana, panel u objeto que lo contenga. Para poder indicar cuanto espacio exterior tendrá el objeto actual en sus lados llamamos al atributo **insets** seguido de la opción:

* **top:** Margin hacia la parte superior.
* **right:** Margin hacia la parte derecha.
* **bottom:** Margin hacia la parte inferior.
* **left:** Margin hacia la parte izquierda.

Por defecto el margin es de 0px.

* **Ejemplo:**

En este ejemplo el elemento tiene un margin de 10px para arriba y abajo y un margin de 5px para la derecha e izquierda.

```
gbc.insets.top = 10;
gbc.insets.right = 5;
gbc.insets.bottom = 10;
gbc.insets.left = 5;
```

#### **Padding de un objeto:**

El Padding de un objeto es el espacio que tendrá en pixeles con respecto al interior, esto quiere decir cuanto espacio habrá entre el borde del objeto y los elementos internos de este. Es una buena forma para darle un poco mas de tamaño a nuestros elementos sin tener que estirar totalmente el objeto. Para poder indicar cuanto espacio interior tendrá el objeto actual en sus lados llamamos al atributo **ipadx** para el padding en el eje x o **ipady** para el padding en el eje y.

Por defecto el padding es de 0px.

**Ejemplo:**

En el siguiente ejemplo un elemento tiene un padding de 5px para el eje x y un padding de 10px para el eje y.

```
gbc.ipadx = 5;
gbc.ipady = 10;
```

#### **Estiramiento de filas o columnas**

Por defecto el grid que vamos a ir construyendo hará que todas las filas y columnas ocupen el ancho y alto de acuerdo al elemento que tenga mas altos valores en sus dimensiones, pero quizás pueden haber casos en los que queremos que una fila en especifico ocupe un ancho mayor al resto o quizás una columna, para estos casos podemos usar los atributos: **weightx** para estirar una columna, o **weighty** para estirar una fila.

Por defecto el valor de estiramiento es de 0, para indicar que una fila será estirada se debe colocar el valor de 1. El estiramiento se realizara hasta lo permitido respecto a cuantos mas elementos habrá en el grid.

**Ejemplo:**

En este caso la primera columna se estirará con respecto a las demás, mientras que la primera fila estará con el alto por defecto.

```
gbc.weightx = 1;
gbc.weighty = 0;
```

### Ajustando nuestra Ventana Principal

Como vamos a mostrar varios productos en nuestra ventana, es muy probable que estos ocupen mas dimensiones que tiene la ventana, es por esto que debemos hallar una forma para poder navegar dentro de esta ventana, para eso vamos a utilizar un **JScrollPane** el cual nos brinda **JScrollBars** para que el usuario pueda navegar dentro de una ventana de dimensiones fijas como es nuestro caso.

Vamos a ir a nuestra clase **VentanaPrincipalTemplate**, allí lo primero que vamos a hacer es declarar un objeto tipo **JScrollPane**:

```
private JScrollPane psProductos;
```

Vamos a crear un método dentro de esta clase en la cual vamos a crear el JScrollPane, pero como vimos en la sesión de tablas, cuando creamos un JScrollPane debemos pasarle de inmediato el componente que este va a contener, es por eso que el método va a recibir como parámetro el panel que será contenido, en este caso el panel de productos:

```
public void crearContenidoProductos(JPanel pProductos){

}
```

Vamos a construir nuestro ScrollPane pasando como componente al panel que recibimos por parámetro:

```
public void crearContenidoProductos(JPanel pProductos){
    this.psProductos = sObjGraficos.construirPanelBarra(pProductos, 0, 0, 850, 600, null, null);
}
```

Vamos a personalizar el scroll vertical ya que será el único que necesitamos activar:

```
public void crearContenidoProductos(JPanel pProductos){
    this.psProductos = sObjGraficos.construirPanelBarra(pProductos, 0, 0, 850, 600, null, null);
    this.psProductos.getVerticalScrollBar().setUI(sGraficosAvanzados.devolverScrollPersonalizado(
        7, 10, sRecursos.getColorGrisClaro(), sRecursos.getColorAzul(), sRecursos.getColorAzulOscuro())
    );
}
```

Ya tenemos listo el ScrollPane, ahora vamos a agregarlo en nuestro al panel principal de la ventana:

```
public void crearContenidoProductos(JPanel pProductos){
    this.psProductos = sObjGraficos.construirPanelBarra(pProductos, 0, 0, 850, 600, null, null);
    this.psProductos.getVerticalScrollBar().setUI(sGraficosAvanzados.devolverScrollPersonalizado(
        7, 10, sRecursos.getColorGrisClaro(), sRecursos.getColorAzul(), sRecursos.getColorAzulOscuro())
    );
    this.pPrincipal.add(psProductos);
}
```

Finalmente y esto se hace para que el contenido del ScrollPane se vea sin problemas, ya que muchas veces mostrar contenido dentro de un ScrollPane puede generar problemas de visualización, vamos a usar el método **revalidate** que actualiza todo el contenido que este dentro del ScrollPane, si por ejemplo usáramos el método **repaint** no funcionaría y no se verían los elementos hasta hacer scroll con el mouse.

```
public void crearContenidoProductos(JPanel pProductos){
    this.psProductos = sObjGraficos.construirPanelBarra(pProductos, 0, 0, 850, 600, null, null);
    this.psProductos.getVerticalScrollBar().setUI(sGraficosAvanzados.devolverScrollPersonalizado(
        7, 10, sRecursos.getColorGrisClaro(), sRecursos.getColorAzul(), sRecursos.getColorAzulOscuro())
    );
    this.pPrincipal.add(psProductos);
    this.psProductos.revalidate();
}
```

Nuestro método esta listo, pero no lo hemos llamado, ¿Donde llamaremos a este método?, justo en el código que reacciona cuando el usuario oprime click en el botón de la navegación **Productos**, recordemos esa configuración esta dentro de la clase **VistaPrincipalComponent**, lo único que debemos hacer es cambiar la agregación directa del componente **Productos** al panel principal, por el paso al método que creamos:

<figure><img src="https://camo.githubusercontent.com/6f39bb3c251af7c45013a1cf4e4adfd2307002ab84456c43d3a4a0ee2b57691f/68747470733a2f2f692e696d6775722e636f6d2f5976536e61594a2e706e67" alt=""><figcaption></figcaption></figure>

### Creando nuestro componente padre

Siempre es bueno que antes de empezar a crear elementos y posicionarlos, hagamos un esquema general de como se van a distribuir los elementos dentro del GridBagLayout, a continuación mostramos el esquema de como se quiere construir el componente **Productos**:

<figure><img src="https://camo.githubusercontent.com/7b1432b021405e91d89832fbe8dadf310c0f0ae3e0fcc163908e5a13c9ec9010/68747470733a2f2f692e696d6775722e636f6d2f694a64726d464b2e706e67" alt=""><figcaption></figcaption></figure>

Esquema de distribución dentro del Grid

En este caso podemos ver las siguientes particularidades:

* La primera fila va a ocupar 3 columnas.
* Las demás filas estarán divididas en 3 columnas.
* No se aprecia en la imágen pero pueden haber muchas filas, dependiendo del numero de productos que coloquemos, mientras que el numero máximo de columnas va a ser siempre 3.

Vamos a crear nuestro primer elemento dentro de nuestro componente y a posicionarlo mediante las restricciones que acabamos de ver, en este caso queremos dar un titulo principal que nos indique que los productos mostrados serán cursos en linea, como será un único JLabel vamos a crearlo dentro del constructor:

* **Declaración:**

```
private JLabel lTitulo;
```

* **Creación:**

```
// Dentro del constructor
lTitulo = sObjGraficos.construirJLabel(
    "Cursos en Linea", 0, 0, 0, 0, null, sRecursos.getColorAzul(), null, sRecursos.getFontTProducto(), "c"
);
lTitulo.setBorder(sRecursos.getBorderInferiorAzul());
```

Noten que dentro de la creación de nuestro JLabel hemos dado una posición y tamaño de 0 ya que la posición por pixeles queda de lado y será el **GridBagLayout** se encargará de esto.

Ahora vamos a configurar las restricciones para posicionar nuestro elemento, no es necesario configurar todas las restricciones, solo las necesarias. Para empezar como nuestro titulo estará en la parte superior debemos indicar que nuestro titulo va a posicionarse en la columna y fila 0:

```
// Dentro del constructor
lTitulo = sObjGraficos.construirJLabel(
    "Cursos en Linea", 0, 0, 0, 0, null, sRecursos.getColorAzul(), null, sRecursos.getFontTProducto(), "c"
);
lTitulo.setBorder(sRecursos.getBorderInferiorAzul());

gbc.gridx = 0;
gbc.gridy = 0;
```

Ahora vamos a indicar que queremos que nuestro label tenga un espacio exterior (Margin) de 15px para todos sus lados:

```
// Dentro del constructor
lTitulo = sObjGraficos.construirJLabel(
    "Cursos en Linea", 0, 0, 0, 0, null, sRecursos.getColorAzul(), null, sRecursos.getFontTProducto(), "c"
);
lTitulo.setBorder(sRecursos.getBorderInferiorAzul());

gbc.gridx = 0;
gbc.gridy = 0;
gbc.insets.top = 15;
gbc.insets.bottom = 15;
gbc.insets.left = 15;
gbc.insets.right = 15;
```

Ahora basándonos en el esquema podemos darnos cuenta, la primera fila va a ocupar 3 columnas asi que debemos indicar esto a nuestras restricciones:

```
// Dentro del constructor
lTitulo = sObjGraficos.construirJLabel(
    "Cursos en Linea", 0, 0, 0, 0, null, sRecursos.getColorAzul(), null, sRecursos.getFontTProducto(), "c"
);
lTitulo.setBorder(sRecursos.getBorderInferiorAzul());

gbc.gridx = 0;
gbc.gridy = 0;
gbc.insets.top = 15;
gbc.insets.bottom = 15;
gbc.insets.left = 15;
gbc.insets.right = 15;
gbc.gridwidth = 3;
```

Por ultimo, queremos que nuestro label ocupe todo el ancho horizontal de las 3 columnas asi que vamos a estirar el objeto en este sentido:

```
// Dentro del constructor
lTitulo = sObjGraficos.construirJLabel(
    "Cursos en Linea", 0, 0, 0, 0, null, sRecursos.getColorAzul(), null, sRecursos.getFontTProducto(), "c"
);
lTitulo.setBorder(sRecursos.getBorderInferiorAzul());

gbc.gridx = 0;
gbc.gridy = 0;
gbc.insets.top = 15;
gbc.insets.bottom = 15;
gbc.insets.left = 15;
gbc.insets.right = 15;
gbc.gridwidth = 3;
gbc.fill = GridBagConstraints.HORIZONTAL;
```

Ya terminamos con todas las restricciones, ahora le debemos indicar al **GridBagLayout** que el elemento actual (JLabel) ,tendrá las restricciones actuales, esto con el método **setConstraints** que recibe como parámetros:

* **El objeto gráfico que se añadirá**.
* **El objeto de configuración de restricciones.**

```
// restricciones
...
...

lGrid.setConstraints(lTitulo, gbc);
```

Ahora simplemente agregamos el elemento al componente:

```
// restricciones
...
...

lGrid.setConstraints(lTitulo, gbc);
this.add(lTitulo);
```

_**Nota1:** Muy seguramente si ejecutamos la aplicación se verá nuestro titulo en la mitad y sin las propiedades que hemos indicado, esto eso por que es el único elemento por el momento y en estos casos el GridBagLayout coloca esos únicos elementos en el medio._

<figure><img src="https://camo.githubusercontent.com/34bb54aa1439e10573efb4ad4dd264f2761ec81d47eae86ad8a721ef10260ca7/68747470733a2f2f692e696d6775722e636f6d2f774d4d745956392e706e67" alt=""><figcaption></figcaption></figure>

_**Nota2:** Debemos tener cuidado con las restricciones que vamos configurando ya que estas quedan así a menos que se vuelan a cambiar, por ejemplo ya indicamos que el titulo ocupará 3 columnas, pero esto no será asi para los demás elementos que coloquemos así que debemos modificarlo de nuevo para cambiar su valor. Debemos tener cuidado de volver a configurar las restricciones o puede que por alguna de estas que no se haya actualizado y como consecuencia todo nuestro esquema quede mal._

Es hora de crear a los productos, para esto vamos a crear un método llamado **crearProductos**:

```
public void crearProductos(){
}
```

Lo primero que haremos es declarar dos variables enteras que nos ayudaran para el posicionamiento de nuestros productos y ademas para obtenerlos:

* **numProducto:** Nos servirá para consultar los productos desde el ArrayList y ademas para cuestiones de posicionamiento con las columnas.
* **fila**: Nos servirá para ubicar los productos en la fila correspondiente y empieza en 1 por que la fila 0 ya la ocupa el Label del titulo.

```
public void crearProductos(){
    int numProducto = 0, fila = 1;
}
```

Ahora vamos a empezar a llamar los productos, en este caso se llamará al primero a traves del método de la clase **Component** que ya configuramos:

```
public void crearProductos(){
    int numProducto = 0, fila = 1;
    Producto producto = productosComponent.devolverProducto(numProducto);
}
```

El paso siguiente es muy importante y es que como indicamos hay restricciones que ya se configuraron para colocar el titulo pero alguna de estas no las queremos asi que debemos volver a colocarlas en su valor por defecto, en este caso para cada producto **NO** queremos:

* Que cada panel de un producto se estire en el eje horizontal, queremos que ocupe su tamaño justo.
* Que cada producto ocupe tres columnas, solo queremos que ocupe una columna.
* Que tenga un margin a la derecha de 15, si queremos un margin de 15 para los demás lados pero para la derecha no será necesario.

```
public void crearProductos(){
    int numProducto = 0, fila = 1;
    Producto producto = productosComponent.devolverProducto(numProducto);
    gbc.fill = GridBagConstraints.NONE;
    gbc.gridwidth = 1;
    gbc.insets.right = 0;
}
```

Crearemos un ciclo while y la condición para que este continue es que el objeto de producto no sea nulo, o en otras palabras el ciclo se mantendrá hasta que acabemos de recorrer la lista de productos:

```
public void crearProductos(){
    int numProducto = 0, fila = 1;
    Producto producto = productosComponent.devolverProducto(numProducto);
    gbc.fill = GridBagConstraints.NONE;
    gbc.gridwidth = 1;
    gbc.insets.right = 0;
    while(producto != null){
    }
}
```

Dentro del While vamos a realizar **Reutilización de componentes con enfoque de posicionamiento**, es decir que dentro del while vamos a llamar al componente hijo **Producto**, recordemos que debemos llamar a su parte lógica para poder realizar una comunicación pero necesitamos obtener su parte gráfica:

```
public void crearProductos(){
    int numProducto = 0, fila = 1;
    Producto producto = productosComponent.devolverProducto(numProducto);
    gbc.fill = GridBagConstraints.NONE;
    gbc.gridwidth = 1;
    gbc.insets.right = 0;
    while(producto != null){
        ProductoTemplate pProducto = new ProductoComponent().getProductoTemplate();
    }
}
```

Ahora para que el componente hijo **Producto** pueda mostrar la información de cada curso debemos pasarle como argumento los datos de cada curso en este caso y con el propósito de no mandar tantos argumentos, el componente hijo nos pide directamente el objeto del producto:

```
public void crearProductos(){
    int numProducto = 0, fila = 1;
    Producto producto = productosComponent.devolverProducto(numProducto);
    gbc.fill = GridBagConstraints.NONE;
    gbc.gridwidth = 1;
    gbc.insets.right = 0;
    while(producto != null){
        ProductoTemplate pProducto = new ProductoComponent(producto).getProductoTemplate();
    }
}
```

Por ahora la parte template del componente hijo no tiene nada, esto se configurará en breve, vamos a seguir con el componente padre. Una vez obtenido el objeto gráfico del componete hijo debemos empezar a configurar su posicion, debemos indicar en que fila y columna se va a posicionar cada uno de los productos:

* Para las columnas nos ayudaremos de la operación modulo con 3 y el numero del producto que tenemos actualmente, asi:
  * si estamos con el producto numero 0 el modulo con 3 dará 0.
  * si estamos con el producto numero 1 el modulo con 3 dará 1.
  * si estamos con el producto numero 2 el modulo con 3 dará 2.
  * si estamos con el producto numero 3 el modulo con 3 dará 0.

Así podemos darnos cuenta que gracias al modulo el valor de las columnas va a oscilar entre 0 a 2 que es justamente lo que queremos.

* Para las filas vamos a ayudarnos con la variable **fila** y pueden notar que la inicializamos con 1 por que recordemos que la primera fila ya esta ocupada por el título.

```
public void crearProductos(){
    int numProducto = 0, fila = 1;
    Producto producto = productosComponent.devolverProducto(numProducto);
    gbc.fill = GridBagConstraints.NONE;
    gbc.gridwidth = 1;
    gbc.insets.right = 0;
    while(producto != null){
        ProductoTemplate pProducto = new ProductoComponent(producto).getProductoTemplate();
        gbc.gridx = numProducto % 3;
        gbc.gridy = fila;
    }
}
```

Estas son todas las restricciones que configuraremos asi que ahora debemos añadir las configuraciones actualizadas y añadir nuestro producto:

```
public void crearProductos(){
    int numProducto = 0, fila = 1;
    Producto producto = productosComponent.devolverProducto(numProducto);
    gbc.fill = GridBagConstraints.NONE;
    gbc.gridwidth = 1;
    gbc.insets.right = 0;
    while(producto != null){
        ProductoTemplate pProducto = new ProductoComponent(producto).getProductoTemplate();
        gbc.gridx = numProducto % 3;
        gbc.gridy = fila;
        lGrid.setConstraints(pProducto, gbc);
        this.add(pProducto);
    }
}
```

Ahora debemos actualizar los valores de cada iteración para que el ciclo recorra todos los productos y no quede intermitente, primero debemos actualizar el valor de la fila y es que si ya hay 3 productos ocupando la fila es hora de sumarle el valor a la fila:

```
public void crearProductos(){
    int numProducto = 0, fila = 1;
    Producto producto = productosComponent.devolverProducto(numProducto);
    gbc.fill = GridBagConstraints.NONE;
    gbc.gridwidth = 1;
    gbc.insets.right = 0;
    while(producto != null){
        ProductoTemplate pProducto = new ProductoComponent(producto).getProductoTemplate();
        gbc.gridx = numProducto % 3;
        gbc.gridy = fila;
        lGrid.setConstraints(pProducto, gbc);
        this.add(pProducto);
        if(numProducto % 3 == 2)
            fila ++;
    }
}
```

Ahora debemos actualizar el numero del producto y asi mismo debemos llamar al siguiente producto en la lista:

```
public void crearProductos(){
    int numProducto = 0, fila = 1;
    Producto producto = productosComponent.devolverProducto(numProducto);
    gbc.fill = GridBagConstraints.NONE;
    gbc.gridwidth = 1;
    gbc.insets.right = 0;
    while(producto != null){
        ProductoTemplate pProducto = new ProductoComponent(producto).getProductoTemplate();
        gbc.gridx = numProducto % 3;
        gbc.gridy = fila;
        lGrid.setConstraints(pProducto, gbc);
        this.add(pProducto);
        if(numProducto % 3 == 2)
            fila ++;
        numProducto ++;
        producto = productosComponent.devolverProducto(numProducto);
    }
}
```

Finalmente y para que mas adelante podamos ver la estructura, debemos llamar el método dentro del constructor:

```
// Dentro del constructor
this.crearProductos();
```

En teoría ya tenemos configurada la estructura básica de nuestro componente padre, pero como nuestro componente hijo aun no tiene un contenido, no se notará aun esta estructura, en la siguiente sección vamos a crear el contenido de cada producto para poder ver por fin como quedá nuestro componente gráfico:

### Creando nuestro componente hijo

Dentro de la clase **ProductoTemplate** vamos a crear la estructura básica de un producto y como dijimos antes es bueno realizar un esquema general de como queremos que se vea un producto:

<figure><img src="https://camo.githubusercontent.com/8b436ed08af0cfac9367586dcc77cae8caf425d49254eeb56348a57aa2a4b630/68747470733a2f2f692e696d6775722e636f6d2f4f374e6d5a364c2e706e67" alt=""><figcaption></figcaption></figure>

Esquema general de un producto

vamos a dar las características generales al componente:

* Primero vamos a darle un color de fondo blanco
* Vamos a darle un borde redondeado a nuestro producto
* Vamos a decirle que sea visible

```
// Dentro del constructor
this.setBackground(Color.WHITE);
this.setBorder(sRecursos.getBordeRedondeado());
this.setVisible(true);
```

Ahora queremos que cada producto tenga en este caso un tamaño fijo, para eso vamos a dar una dimensión fija a nuestro componente:

```
// Dentro del constructor
this.setPreferredSize(new Dimension(262, 330));
```

Ahora podemos ver que la estructura del componente padre **Productos** funciona:

<figure><img src="https://camo.githubusercontent.com/a7f0e35481a1c469a06986f7c1639893cead5ff9b491a2a11cc029779529ccbf/68747470733a2f2f692e696d6775722e636f6d2f724d6e513763362e706e67" alt=""><figcaption></figcaption></figure>

Estructura del componente padre

Vamos a declarar nuestros objetos que estarán a cargo del posicionamiento y tamaño de los objetos gráficos que serán contenidos:

* **Declaración:**

```
// Declaración LayoutManager
private GridBagLayout lGrid;
private GridBagConstraints gbc;
```

* **Ejemplificación:**

```
lGrid = new GridBagLayout();
gbc = new GridBagConstraints();
```

Ahora podemos indicarle al componente que su LayoutManager será este **GridBagLayout**.

```
lGrid = new GridBagLayout();
gbc = new GridBagConstraints();
this.setLayout(lGrid);
```

A continuación se declaran los objetos gráficos y decoradores que vamos a crear dentro del componente gráfico:

```
// Declaración Objetos Gráficos
private JLabel lTitulo, lImagen, lParrafo, lEstrella, lPuntuacion, lCampo;

// Declaración Objetos Decoradores
private ImageIcon iEstrella, iDimAux;
```

Podemos notar que en este caso serán todos JLabels, pero serán varios asi que nos conviene crear un método para la creación de estos:

```
public void crearJLabels(){
}
```

Como sera una cantidad considerable de labels los que vamos a crear, es probable que modificar algunas restricciones y luego tener encuentra cuales deben ser modificadas para el siguiente objeto será una tarea tediosa y ademas puede que ocupe bastantes lineas de código, podría ser una mejor solución si creamos un método que se encargue de la actualización de cada una de las restricciones por objeto y de esta forma no solo nos ahorramos lineas de código, también nos aseguramos de actualizar cada restricción y asi no tener problemas de posicionamiento en el futuro:

```
public void modificarGbc(
    int posColumna, int posFila, int numColumnas, int numFilas, int tipoEstirado, int posicionInterna, 
    int marginArriba, int marginDerecha, int marginAbajo, int marginIzquierda, int paddingX, int paddingY,
    int estiramientoColumna, int estiramientoFila
){
    gbc.gridx = posColumna;
    gbc.gridy = posFila;
    gbc.gridwidth = numColumnas;
    gbc.gridheight = numFilas;
    gbc.fill = tipoEstirado;
    gbc.anchor = posicionInterna;
    gbc.insets.top = marginArriba;
    gbc.insets.right = marginDerecha;
    gbc.insets.bottom = marginAbajo;
    gbc.insets.left = marginIzquierda;
    gbc.ipadx = paddingX;
    gbc.ipady = paddingY;
    gbc.weightx = estiramientoColumna;
    gbc.weighty = estiramientoFila;
}
```

Dentro de este método están contenidas todas las restricciones que puedan tener, nuestro objeto **GridBagConstraints** y aunque no en todos los casos vamos a necesitar configurar todas las restricciones las podemos dejar con su valor por defecto y ademas nos vamos a ahorrar muchas lineas de código.

Dentro del método **crearLabels** vamos a construir nuestro primer Label que será el titulo o nombre del producto:

```
public void crearJLabels(){
    lTitulo = sObjGraficos.construirJLabel(
        producto.getNombreProducto(), 0, 0, 0, 0, null, sRecursos.getColorAzul(),
        null, sRecursos.getFontTitulo(), "l"
    );
}
```

Ahora vamos a configurar todas sus restricciones llamando al método que creamos para esto y explicaremos que representan cada uno de estos números, ademas vamos a agregarlo de una vez al componente:

```
public void crearJLabels(){
    lTitulo = sObjGraficos.construirJLabel(
        producto.getNombreProducto(), 0, 0, 0, 0, null, sRecursos.getColorAzul(),
        null, sRecursos.getFontTitulo(), "l"
    );
    modificarGbc(0, 0, 3, 1, 0, 10, 10, 0, 0, 0, 0, 0, 0, 0);
    this.add(lTitulo, gbc);
}
```

_**Nota:** Noten que podemos agregar un elemento directamente con sus respectivas configuraciones **GridBagConstraints** pero para que esto funcione nuestro componente debe ya tener configurado el **LayoutManager**, esto quiere decir que la linea de código **setLayoutManager(lGrid)**, debe estar antes de llamar este método (crearLabels) o de lo contrario no funcionara, en cambio cuando usamos el otro enfoque (como lo hicimos en la clase **ProductosTemplate**) no es necesario que la configuración del layout esté antes de la configuración de las posiciones de los elementos, esa es la diferencia de por que en la clase **ProductosTemplate** esta al final mientras que en la clase **ProductoTemplate** esta al comienzo._

Ahora para el caso del titulo estamos diciendo que el objeto gráfico:

* Va a posicionarse en la columna y fila 0 (la primera en cada caso).
* Va a ocupar 3 columnas y 1 fila.
* No se va a estirar el objeto (se deja valor en defecto 0).
* Se quiere que el titulo quede en el medio (se deja valor por defecto 10).
* Se deja un margin de 10px con el espacio de arriba, con los otros lados serán de 0px.
* Se deja un padding de 0px para ambas dimensiones.
* No se quiere estirar la fila ni la columna (se deja en 0).

Vamos ahora con nuestro siguiente Label que en este caso será la imágen del producto:

```
// Dentro del método crearLabels
iDimAux = new ImageIcon(producto.getImagen().getImage().getScaledInstance(250, 148, Image.SCALE_AREA_AVERAGING));

lImagen = sObjGraficos.construirJLabel(null, 0, 0, 0, 0, iDimAux, null, null, null, "c");
lImagen.setBorder(sRecursos.getBordeRedondeado());
modificarGbc(0, 1, 3, 1, 2, 10, 10, 3, 10, 3, 0, 0, 0, 0);
this.add(lImagen, gbc);
```

Para este caso debemos tener en cuenta que la resolución de la imágen y esta es la que dará el tamaño al label, en cuanto a sus restricciones tenemos que el Label:

* Va a posicionarse en la columna 0 y en la fila 1.
* Va a ocupar 3 columnas y 1 fila.
* Se va a estirar la imagen de forma horizontal asi que se deja un numero 2.
* Se quiere que la imágen quede en el medio (se deja valor por defecto 10).
* Se deja un margin de 10px con el espacio de arriba y abajo, con los lados laterales serán de 3px.
* Se deja un padding de 0px para ambas dimensiones.
* No se quiere estirar la fila ni la columna (se deja en 0).

El siguiente elemento será el párrafo de descripción del producto:

```
// Dentro del método crearLabels
lParrafo = sObjGraficos.construirJLabel(
    "<html><div align='justify'>" + producto.getDescripcion() + "</div></html>", 0, 0, 0, 0, 
    null, sRecursos.getColorGrisOscuro(), null, sRecursos.getFontPequeña(), "l"
);
modificarGbc(0, 2, 3, 1, 2, 10, 10, 15, 10, 15, 0, 0, 0, 0);
this.add(lParrafo, gbc);
```

Para este caso en cuanto a sus restricciones tenemos que el objeto gráfico:

* Va a posicionarse en la columna 0 y en la fila 2.
* Va a ocupar 3 columnas y 1 fila.
* Se va a estirar el párrafo de forma horizontal asi que se deja un numero 2.
* Se quiere que la imágen quede en el medio (se deja valor por defecto 10).
* Se deja un margin de 10px con el espacio de arriba y abajo, con los lados laterales serán de 15px.
* Se deja un padding de 0px para ambas dimensiones.
* No se quiere estirar la fila ni la columna (se deja en 0).

Ahora vamos a crear el label del campo o area del curso:

```
// Dentro del método crearLabels
lCampo = sObjGraficos.construirJLabel(
    producto.getCampo(), 0, 0, 0, 0, null, sRecursos.getColorAzulMarino(), sRecursos.getColorAzulClaro(), sRecursos.getFontBotones(), "c"
);
modificarGbc(0, 3, 1, 1, 0, 10, 10, 5, 15, 5, 10, 10, 0, 0);
this.add(lCampo, gbc);
```

Para este caso en cuanto a sus restricciones tenemos que el objeto gráfico:

* Va a posicionarse en la columna 0 y en la fila 3.
* Va a ocupar 1 columna y 1 fila.
* No se quiere estirar el objeto (se deja valor por defecto 0).
* Se quiere que la imágen quede en el medio (se deja valor por defecto 10).
* Se deja un margin de 10px con el espacio de arriba, 15px con respecto al espacio de abajo, con los lados laterales serán de 5px.
* Se deja un padding de 10px para ambas dimensiones.
* No se quiere estirar la fila ni la columna (se deja en 0).

Ahora vamos a crear el label que representa la imagén de una estrella:

```
// Dentro del método crearLabels
iEstrella = new ImageIcon("Clase15/resources/img/estrella.png");
iDimAux = new ImageIcon(iEstrella.getImage().getScaledInstance(25, 25, Image.SCALE_AREA_AVERAGING));

lEstrella = sObjGraficos.construirJLabel(null, 0, 0, 0, 0, iDimAux, null, null, null, "c");
modificarGbc(1, 3, 1, 1, 0, 13, 10, 5, 15, 5, 0, 0, 1, 0);
this.add(lEstrella, gbc);
```

Para este caso ejemplificamos primero la imágen para obtenerla y luego si la redimensionamos, en cuanto a las restricciones tenemos que el objeto gráfico:

* Va a posicionarse en la columna 1 y en la fila 3.
* Va a ocupar 1 columna y 1 fila.
* No se quiere estirar el objeto (se deja valor por defecto 0).
* Se quiere pegar la imagen con el lado derecho de su espacio destinado asi que se deja el valor de 13.
* Se deja un margin de 10px con el espacio de arriba, 15px con respecto al espacio de abajo, con los lados laterales se dejan 5px.
* Se deja un padding de 0px para ambas dimensiones.
* En este caso se quiere estirar la columna del medio es decir la columna que ocupa este objeto asi que se deja en 1, para el caso de la fila si se deja normal.

Finalmente vamos a agregar el puntaje del curso:

```
// Dentro del método crearLabels
lPuntuacion = sObjGraficos.construirJLabel(
    producto.getPuntuacion() + "/ 5", 0, 0, 0, 0, null, sRecursos.getColorAzulMarino(), 
    null, sRecursos.getFontBotones(), "l"
);
modificarGbc(2, 3, 1, 1, 0, 16, 10, 10, 15, 0, 0, 0, 0, 0);
this.add(lPuntuacion, gbc);
```

Para este caso en cuanto a sus restricciones tenemos que el Label:

* Va a posicionarse en la columna 2 y en la fila 3.
* Va a ocupar 1 columna y 1 fila.
* No se quiere estirar el objeto (se deja valor por defecto 0).
* Se quiere que el label quede posicionado en la parte inferior izquierda, para que quede pegado a la izquierda y este a la misma altura con la imágen de la estrella o de lo contrario se vera un poco mas arriba de ella.
* Se deja un margin de 10px con el espacio de arriba y a la derecha, 15px con respecto al espacio de abajo y 0px para la izquierda.
* Se deja un padding de 10px para ambas dimensiones.
* No se quiere estirar la fila ni la columna (se deja en 0).

Ya esta listo nuestro método, ahora debemos llamar nuestro método en el constructor, recordemos que debemos llamar al método después de configurar el LayoutManager al componente:

```
// Dentro del constructor
lGrid = new GridBagLayout();
gbc = new GridBagConstraints();
this.setLayout(lGrid);

this.crearJLabels();
...
```

Finalmente nuestra interfaz gráfica queda así:

<figure><img src="https://github.com/CrissUD/InterfazGraficaJavaClase15/raw/master/gifs/final.gif" alt=""><figcaption></figcaption></figure>

Resultado final del uso de GridBagLayout

## Resultado

Si llegaste hasta aquí **!felicidades!** aprendiste mucho sobre **LayoutManager** y entre muchas cosas aprendiste **Las características generales de los LayoutManager y que ventajas tiene frente a otros enfoques**, **Los tipos de LayoutManager, como y cuando usar cada tipo**, **Aprendiste a usar el GridBagLayout** que es quizás el mas sofisticado y mostramos finalmente una lista de productos.

## Actividades

Utiliza **GridBagLayout** para posicionar elementos dentro de tu proyecto y trata de situarlos dentro de un JScrollPane.\


####

\
