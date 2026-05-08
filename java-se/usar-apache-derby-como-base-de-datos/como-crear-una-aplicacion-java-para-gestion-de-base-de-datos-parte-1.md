# Cómo crear una aplicación Java para gestión de base de datos (Parte 1)

Siguiendo los pasos que se muestran a continuación podrás crear una **aplicación Java** que gestione una simple **lista con datos de personas**, almacenada en una **base datos** de manera que persistan los datos de los contactos aunque se cierre la aplicación. Esta aplicación podrá servirte de base para crear otras aplicaciones similares que realicen la gestión de otras bases de datos.

Para la creación completa de la aplicación se usarán distintas **tecnologías** que podrías cambiar por otras si lo estimaras oportuno, pero este tutorial se centrará en las siguientes:

* **Java**, como lenguaje de programación.
* **NetBeans**, como entorno de desarrollo.
* **Java DB** (Derby), como gestor de la base de datos.
* **JPA** (Java Persistence API), como API para el acceso a la base de datos.
* **JavaFX**, como API para el interfaz de usuario.
* **SceneBuilder**, como diseñador del interfaz de usuario.

Inicialmente deberás **crear una aplicación Java estándar**, asignándole el nombre _**AgendaContactos**_, a la que posteriormente se le añadirá un interfaz gráfico más amigable para el usuario:&#x20;

**File > New Project > Java > Java Application**

<img src="https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_21.10.46_7bef4.png" alt="Screen Shot 2017 04 05 at 21.10.46 7bef4" height="167" width="600">

## Base de datos Java DB

### Registro de la base de datos en NetBeans

Con el fin de que la aplicación puede ser fácilmente utilizable por cualquier usuario, sin necesidad de que tenga que disponer de un servidor de base datos como MySQL (cuya instalación puede ser compleja para un usuario normal), se va a utilizar como gestor de base de datos el que incorpora Java, de manera que el usuario simplemente necesitará ejecutar la aplicación de la Agenda de Contactos para que pueda utilizarla, sin necesidad de tener otros requisitos para usar una base de datos. Java ofrece dentro de su kit de desarrollo el gestor de **base de datos** [**Java DB**](http://docs.oracle.com/javadb/) **que es una distribución por parte de Oracle de la base de datos** [**Derby de Apache**](https://db.apache.org/derby/). Debes tener en cuenta que el **lenguaje SQL de Java DB tiene ligeras diferencias** con el lenguaje SQL de MySQL, por lo que debes tener en cuenta su [**página de referencia del lenguaje SQL de JavaDB**](http://docs.oracle.com/javadb/10.10.1.2/ref/index.html).

Para que la gestión de la base de datos de _Contactos_ resulte más cómoda, conviene **registrar la base de datos en NetBeans**. Esto puedes hacerlo cómodamente desde la pestaña _**Services**_ seleccionando, desde el menú contextual del elemento _**Databases,**_ la opción _**New Connection**_.

![Screen Shot 2017 04 05 at 21.06.40 a7200](https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_21.06.40_a7200.png)

Selecciona la opción _**Java DB (Embedded)**_ para utilizar el gestor de base de datos que se ha comentado anteriormente, de manera que no se requiera un servidor de base de datos externo a la aplicación que se está desarrollando. Si se prefiere utilizar un servidor de base de datos como MySQL, se deberá seleccionar la opción correspondiente.

![Screen Shot 2017 04 05 at 20.56.22 9d1ba](https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_20.56.22_9d1ba.png)

En la ventana de configuración de la conexión con la base de datos, indica la **ruta a la carpeta** donde has creado el proyecto junto con el **nombre deseado para la base de datos** (en este ejemplo _BDAgendaContactos_), el **nombre de usuario** (indica **APP** que es el usuario por defecto) **y contraseña** (la que quieras) que se desea utilizar para autorizar la conexión (indica los valores que desees), selecciona la opción recordar contraseña (Remember password) para que se almacene y no sea necesario introducirla cada vez que se desee hacer la conexión a la base de datos desde el entorno de NetBeans, y **añade el texto ;create=true a la dirección (URL)** de conexión a la base de datos con el fin de que se **cree la base de datos en caso de que no exista** (que es el caso actualmente, ya que no se ha creado anteriormente dicha base de datos).

![Screen Shot 2017 04 05 at 20.50.38 b7004](https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_20.50.38_b7004.png)

Para JavaDB debes indicar el esquema (_**Schema**_) de la base de datos que va a utilizar las herramientas de NetBeans, por lo que debes dejar el que aparece por defecto: **APP**, que es el utilizado para no indicar un usuario concreto de conexión a la base de datos.

![Screen Shot 2017 04 05 at 20.51.02 2875b](https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_20.51.02_2875b.png)

En la siguiente ventana podrás asignar un **nombre a la conexión** con la base de datos, aunque puedes dejar el que aparece por defecto.

![Screen Shot 2017 04 05 at 20.51.32 71667](https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_20.51.32_71667.png)

Una vez finalizado este proceso de registro de la base de datos en NetBeans, aparecerá su **conexión en el árbol&#x20;**_**Databases**_, y a patir de este momento será más sencillo realizar diversas operaciones con la base de datos desde el propio entorno de desarrollo NetBeans.

<img src="https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_20.52.06_ad515.png" alt="Screen Shot 2017 04 05 at 20.52.06 ad515" height="212" width="600">

Comprueba también que en la carpeta donde has creado el proyecto se ha creado una **nueva carpeta correspondiente a la base de datos**.

<img src="https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_20.35.53_09dc4.png" alt="Screen Shot 2017 04 05 at 20.35.53 09dc4" height="209" width="600">

### Creación de las tablas

Las tablas que van a formar parte de la base de datos se van a crear desde el mismo NetBeans utilizando un archivo SQL que contenga las sentencias SQL correspondientes a la creación de las tablas.

Con el fin de mantener organizado el código fuente de la aplicación, conviene crear un paquete que almacene el código SQL de manera separada del código Java propio de la aplicación Java que se desarrollará posteriormente.

Vuelve a la pestaña _**Projects**_, y utiliza el menú contextual de la carpeta _**Source Packages**_ para seleccionar la opción _**New > Java Package**_ e indica el nombre para el paquete de fuentes que almacenará los archivos SQL. Un buen nombre puede ser el mismo que se ha utilizado para la aplicación, **seguido de&#x20;**_**.sql**_:

<img src="https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_21.12.34_8457b.png" alt="Screen Shot 2017 04 05 at 21.12.34 8457b" height="312" width="600">

Crea dentro de esta carpeta un archivo SQL desde su menú contextual, usando la opción _**New > Other > (Categories) Other > SQL file**_ o _New > SQL File_ si ya has usado anteriormente esta opción. Asigna un nombre al archivo, por ejemplo, _CreacionTablas_. Una vez abierto el archivo, asegúrate de **seleccionar en su parte superior la conexión con la base de datos** que se ha creado anteriormente, para que la ejecución de las sentencias SQL que se escriban se ejecuten sobre la base de datos deseada.

<img src="https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_21.14.32_a1fe9.png" alt="Screen Shot 2017 04 05 at 21.14.32 a1fe9" height="102" width="600">

Como este tutorial no es más que un ejemplo de una posible base de datos, se va a crear una **tabla** para almacenar una serie de datos de **personas**. Los datos que se indicarán no tendrán mucho sentido en algunos casos, pero se intenta crear un ejemplo que utilice **diversos tipos de datos**, y de ahí que haya algunos datos añadidos de manera uno tanto forzada. También con el fin de crear un ejemplo con tablas relacionadas, se va a crear una **segunda tabla con las provincias** españolas que se relacionará con la tabla de personas, para indicar en qué provincia reside cada una.

Para este ejemplo se ha creado el siguiente **script SQL** que se encargará de **crear las tablas**:

```
CREATE TABLE PROVINCIA (
    ID INTEGER NOT NULL GENERATED ALWAYS AS IDENTITY,
    CODIGO CHAR(2),
    NOMBRE VARCHAR(20) NOT NULL,
    CONSTRAINT ID_PROVINCIA_PK PRIMARY KEY (ID)
);

CREATE TABLE PERSONA (
    ID INTEGER NOT NULL GENERATED ALWAYS AS IDENTITY, -- Id autonumérico
    NOMBRE VARCHAR(20) NOT NULL,
    APELLIDOS VARCHAR(40) NOT NULL,
    TELEFONO VARCHAR(15),
    EMAIL VARCHAR(30),
    PROVINCIA INTEGER NOT NULL,
    FECHA_NACIMIENTO DATE,
    NUM_HIJOS SMALLINT,
    ESTADO_CIVIL CHAR(1),
    SALARIO DECIMAL(7,2),
    JUBILADO BOOLEAN,
    FOTO VARCHAR(30),
    CONSTRAINT ID_PERSONA_PK PRIMARY KEY (ID),
    CONSTRAINT PROV_PERSONA_FK FOREIGN KEY (PROVINCIA) REFERENCES PROVINCIA (ID)
);
```

Puedes ver que cada tabla dispone de un campo **ID como identificador** para cada registro, que es **autonumérico** y que se utilizará como **clave primaria** de cada tabla. Ahí puedes ver que la declaración de este tipo autonumérico (GENERATED ALWAYS AS IDENTITY) es diferente a MySQL, por lo que si la base de datos se desea conectar a un servidor MySQL se deben modificar algunos aspectos del lenguaje SQL como ese.

Observa también que no sólo se han creado **columnas de tipo** VARCHAR, sino también algunas de tipo numérico con distintos tamaños (INTEGER, SMALLINT, DECIMAL, etc), así como la columna JUBILADO de tipo BOOLEAN o la fecha de nacimiento de tipo DATE, para poder conocer cómo se pueden gestionar esos otros tipos de datos desde Java. Consulta la documentación de los [tipos de datos de Derby](https://db.apache.org/derby/docs/10.7/ref/crefsqlj31068.html) para conocerlos mejor.

La **relación entre las 2 tablas** se lleva a cabo mediante la clave foránea PROVINCIA de la tabla PERSONA que hará referencia a un valor numérico entero correspondiente a una ID de la tabla PROVINCIA. Consulta la documentación de la cláusula [CONSTRAINT de Derby](https://db.apache.org/derby/docs/10.1/ref/rrefsqlj13590.html) para conocer mejor su uso.

Para **ejecutar el script SQL** anterior, haz clic sobre el **botón&#x20;**_**Run SQL**_ de la barra de herramientas asociada a este archivo.

<img src="https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_21.16.35_513c8.png" alt="Screen Shot 2017 04 05 at 21.16.35 513c8" height="374" width="600">

Como resultado de la ejecución, deberían aparecer, en la pestaña _**Services**_, las tablas que se han creado, y si vas desplegando el contenido de cada una, verás los nombres de las columnas.

![Screen Shot 2017 04 05 at 21.20.33 fe234](https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_21.20.33_fe234.png)

## Más información

* [Working with the Java DB (Derby) Database - NetBeans.org](https://netbeans.org/kb/docs/ide/java-db.html)&#x20;
* [Java DB (oracle.com)](http://www.oracle.com/technetwork/es/java/javadb/overview/index.html)
* [Apache Derby (apache.org)](https://db.apache.org/derby/)

## Continúa ...

### [Cómo crear una aplicación Java para gestión de base de datos (Parte 2)](https://javiergarciaescobedo.es/programacion-en-java/9-bases-de-datos/447-como-crear-una-aplicacion-java-para-gestion-de-base-de-datos-parte-2)

&#x20;

Contenidos anteriores de este tutorial:

* [Cómo crear una aplicación Java para gestión de base de datos (Parte 1)](https://javiergarciaescobedo.es/programacion-en-java/9-bases-de-datos/446-como-crear-una-aplicacion-java-para-gestion-de-base-de-datos-parte-1)

Clases entidad

Para que desde el lenguaje de programación Java se pueda tratar **cada registro o fila de las tablas como un objeto Java**, se debe crear una clase asociada a cada tabla de la base de datos. A ese tipo de clases se las conoce como **Clases Entidad (**_**Entity Classes**_**)**. También se puede acceder a una base de datos desde Java sin la utilización de objetos relacionados con las tablas, pero para este tipo de aplicación que se quiere crear resultará más cómodo el uso de objetos.

Para acceder a las bases de datos sin usar directamente clases asociadas a las tablas se usaría la librería **JDBC (Java Database Connectivity)**, includa en los paquetes _java.sql_, y para este caso que vamos a tratar (usando clases entidad) se usa la librería **JPA (Java Persistence API)** que se encuentra en los paquetes _javax.persistence_.

Las **clases entidad** que se acaban de comentar, se podrían crear manualmente, pero _**NetBeans**_ ofrece una herramienta para **crearlas automáticamente** una vez que se haya establecido la conexión con la base de datos en dicho entorno de desarrollo, como se ha hecho en los pasos anteriores.

Para ello, usa el menú contextual en el proyecto, o sobre el paquete de fuentes donde se deseen crear las clases entidad, y usa la opción _**New > Entity Classes from Database**_. Tras hacerlo, aparecerá una ventana de diáologo donde se deberá indicar la conexión con la base de datos que se quiere utilizar, y en la parte central aparecerán las tablas que contiene.

<img src="https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_21.25.59_ee30b.png" alt="Screen Shot 2017 04 05 at 21.25.59 ee30b" height="416" width="600">

Las **tablas** que se deseen utilizar para crear sus clases entidad correspondientes se deben **añadir a la lista de la derecha**. En este caso se añadirán todas, por lo que puedes usar el **botón&#x20;**_**Add All**_. Comprueba que aparecen las tablas en la parte derecha y usa el **botón&#x20;**_**Next**_ para continuar.

En la siguientes pantallas se pueden concretar algunos detalles sobre las clases entidad que se van a crear, pero puedes dejar las opciones por defecto que aparecen y continuar hasta finalizar este proceso.

<img src="https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_21.27.38_209e6.png" alt="Screen Shot 2017 04 05 at 21.27.38 209e6" height="403" width="600">

<img src="https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_21.28.52_d4c5b.png" alt="Screen Shot 2017 04 05 at 21.28.52 d4c5b" height="403" width="600">

Como resultado, se debe haber creado en los paquetes de fuentes **una clase Java por cada tabla** de la base de datos, así como el archivo _**persistence.xml**_ dentro del paquete _META-INF_, que contiene información sobre la conexión con la base de datos como la ruta donde se encontrará, el usuario y contraseña de acceso, etc.

Si observas en **contenido** de ambas clases entidad que se han creado, podrás comprobar que son muy similares. Se muestra a continuación el contenido de la clase _**Provincia.java**_ al ser más corta que _Persona.java_. A continuación se comentará brevemente los aspectos más importantes para que conozcas su contenido.

```
import java.io.Serializable;
import java.util.Collection;
import javax.persistence.Basic;
import javax.persistence.CascadeType;
import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.NamedQueries;
import javax.persistence.NamedQuery;
import javax.persistence.OneToMany;
import javax.persistence.Table;
import javax.xml.bind.annotation.XmlRootElement;
import javax.xml.bind.annotation.XmlTransient;

@Entity
@Table(name = "PROVINCIA")
@XmlRootElement
@NamedQueries({
    @NamedQuery(name = "Provincia.findAll", query = "SELECT p FROM Provincia p")
    , @NamedQuery(name = "Provincia.findById", query = "SELECT p FROM Provincia p WHERE p.id = :id")
    , @NamedQuery(name = "Provincia.findByCodigo", query = "SELECT p FROM Provincia p WHERE p.codigo = :codigo")
    , @NamedQuery(name = "Provincia.findByNombre", query = "SELECT p FROM Provincia p WHERE p.nombre = :nombre")})
public class Provincia implements Serializable {

    private static final long serialVersionUID = 1L;
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    @Basic(optional = false)
    @Column(name = "ID")
    private Integer id;
    @Column(name = "CODIGO")
    private String codigo;
    @Basic(optional = false)
    @Column(name = "NOMBRE")
    private String nombre;
    @OneToMany(cascade = CascadeType.ALL, mappedBy = "provincia")
    private Collection<Persona> personaCollection;

    public Provincia() {
    }

    public Provincia(Integer id) {
        this.id = id;
    }

    public Provincia(Integer id, String nombre) {
        this.id = id;
        this.nombre = nombre;
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getCodigo() {
        return codigo;
    }

    public void setCodigo(String codigo) {
        this.codigo = codigo;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    @XmlTransient
    public Collection<Persona> getPersonaCollection() {
        return personaCollection;
    }

    public void setPersonaCollection(Collection<Persona> personaCollection) {
        this.personaCollection = personaCollection;
    }

    @Override
    public int hashCode() {
        int hash = 0;
        hash += (id != null ? id.hashCode() : 0);
        return hash;
    }

    @Override
    public boolean equals(Object object) {
        // TODO: Warning - this method won't work in the case the id fields are not set
        if (!(object instanceof Provincia)) {
            return false;
        }
        Provincia other = (Provincia) object;
        if ((this.id == null && other.id != null) || (this.id != null && !this.id.equals(other.id))) {
            return false;
        }
        return true;
    }

    @Override
    public String toString() {
        return "es.javiergarciaescobedo.agendacontactos.Provincia[ id=" + id + " ]";
    }
    
}
```

### Propiedades de la clase

Los elementos más importantes de una clase entidad podrían ser las propiedades de la clase, que como puedes ver en su código fuente, están **relacionadas directamente con cada una de las columna** de la tabla.

Para la tabla _Provincia_ se han generado automáticamente las siquientes propiedades:

```
    private Integer id;
    private String codigo;
    private String nombre;
```

Y para la tabla _Persona,_ estas otras propiedades, que como puedes ver tienen **tipos de datos relacionados con los que se han asignado a la tabla** de la base de datos. Por ejemplo, a la columna _NUM\_HIJOS,_ que se indicó en el script SQL que sería de tipo _SMALLINT_, se le ha asignado el tipo _Short_ de Java a la propiedad _numHijos_. Además, puedes ver que los **guiones bajos** utilizados en los nombres de las columnas de las tablas, se usan para distinguir la separación de palabras para los identificadores en Java, empezando en mayúsculas.

```
    private Integer id;
    private String nombre;
    private String apellidos;
    private String telefono;
    private String email;
    private Date fechaNacimiento;
    private Short numHijos;
    private Character estadoCivil;
    private BigDecimal salario;
    private Boolean jubilado;
    private String foto;
    private Provincia provincia;
```

### Anotaciones JPA

Sobre cada propiedad de las clases entidad puedes encontrar una serie de líneas de código que **comienzan por @**. Esas líneas son [**anotaciones de JPA**](http://www.oracle.com/technetwork/middleware/ias/toplink-jpa-annotations-096251.html) (Java Persistence API) que utilizará para conoce la relación entre dichas propiedades y las columnas de la tabla relacionada.

Por ejemplo, justo antes de la propiedad nombre se encuentra la anotación:

```
@Column(name = "NOMBRE")
private String nombre;
```

De esa manera, JPA sabrá que la propiedad _nombre_ está relacionada con la columna _NOMBRE_.

Algunas propiedades también tienen añadida la anotación:

```
@Basic(optional = false)
```

De esta manera se sabrá que en la tabla de la base de datos, esa columna es de carácter **obligatorio** (se ha indicado NOT NULL en la creación de la tabla), y no se podrá dejar vacío ese dato.

Y a las **claves primarias autonuméricas** que se van a utilizar se les ha añadido:

```
@Id
@GeneratedValue(strategy = GenerationType.IDENTITY)
```

### Claves foráneas

En las propiedades que se utilizan como claves foráneas también se añaden anotaciones. Por ello, en la propiedad provincia de la clase _Persona_ se ha añadido automáticamente las anotaciones:

```
@JoinColumn(name = "PROVINCIA", referencedColumnName = "ID")
@ManyToOne(optional = false)
private Provincia provincia;
```

Es **importante** que observes que la **propiedad&#x20;**_**provincia**_ de la clase _Persona_ no es de tipo numérico, sino que ahora se trata como un **objeto de la clase&#x20;**_**Provincia**_. Recuerda que en el script SQL se declaró la columna como INTEGER, ya que es una clave foránea relacionada con la columna ID (de tipo INTEGER) de la tabla PROVINCIA:

```
PROVINCIA INTEGER NOT NULL
```

En cambio en la clase Java no aparece como _Integer_ sino:

```
private Provincia provincia;
```

Por tanto, la propiedad Java asociada debería ser de tipo _Integer_, pero al ser una clave foránea se convierte directamente al objeto correspondiente. De esta manera será **muy sencillo acceder a cualquier información contenida en el objeto Provincia** (por ejemplo el nombre de la Provincia) al que está asociado un determinado objeto Persona, y no sólo el ID correspondiente a la Provincia.

Por otro lado, en la clase _Provincia_, se ha añadido una propiedad extra (_**personaCollection**_):

```
@OneToMany(cascade = CascadeType.ALL, mappedBy = "provincia")
private Collection<Persona> personaCollection;
```

Se trata de una **propiedad de tipo&#x20;**_**Collection**_, que es uno de los tipos de lista que ofrece Java. En dicha lista podremos encontrar, en este caso, todas las personas (objetos _Persona_) que tienen una determinada Provincia. De esta manera, a partir de un determinado objeto _Provincia_, podremos conocer todos los objetos _Persona_ relacionados.

### Métodos get y set

Como suele ser habitual, las propiedades de la clase son de ambito privado (_private_), por lo que la información que contienen no puede ser consultada ni modificada directamente desde otra clase. Se han generado automáticamente los métodos _get_ y _set_ correspondientes a cada propiedad (_getNombre_, _setNombre_, etc), para poder obtener y modificar el valor de cada propiedad.

```
public String getNombre() {
    return nombre;
}
```

```
public void setNombre(String nombre) {
    this.nombre = nombre;
}
```

### Métodos constructores

También se han generado varios métodos constructores para poder crear objetos de estas clases entidad. Por ejemplo, para la clase _Persona_ se han creado los siguientes métodos constructores:

```
public Persona()
public Persona(Integer id)	
public Persona(Integer id, String nombre, String apellidos) {
```

Es decir, se ha creado un método constructor **sin parámetros**, otro para indicar únicamente un ID (al ser la **clave principal**) y otro con los campos que se han marcado como **obligatorios** (NOT NULL) en la tabla.

### Consultas predefinidas (NamedQuery)

En la parte superior del código fuente de las clases entidad puedes encontrar otro conjunto de anotaciones, dentro de la **sección&#x20;**_**@NamedQueries**_. Ahí se encuentran predefinidas una serie de **consultas a la tabla, a las que se le asigna un nombre**, y que puedes utilizar posteriormente en el código Java sin necesidad de escribir el código SQL, sino únicamente indicando el nombre de la consulta.

Por ejemplo, en la clase entidad _Provincia_ hay consultas como:

```
@NamedQuery(name = "Provincia.findAll", query = "SELECT p FROM Provincia p")
```

Que permitirá **obtener todas las provincias** que se encuentren en la tabla _Provincia_, indicando el nombre de consulta _**Provincia.findAll**_.

O esta otra:

```
@NamedQuery(name = "Provincia.findByCodigo", query = "SELECT p FROM Provincia p WHERE p.codigo = :codigo")
```

Que permitirá obtener las provincias cuyo código corresponda con el que se indique en el parámetro _:codigo_.

## Archivo persistence.xml de configuración de la Unidad de Persistencia

Anteriormente se comentó que ademaś de las clases entidad, el asistente de generación de dichas clases crea además el **archivo&#x20;**_**persistence.xml**_**&#x20;dentro del paquete&#x20;**_**META-INF**_. En ese archivo se encuentra la configuración necesaria para realizar la conexión con la base de datos. Contiene, por ejemplo, el nombre de la base de datos, el usuario y contraseña de conexión, etc.

En la tecnología empleada por JPA se conoce como **Unidad de Persistencia (**_**PersistenceUnit**_**)** y el nombre que se le asigne debes tenerlo en cuenta, ya que se usará posteriormente en el código Java de la aplicación. En este caso se le ha asignado el nombre _**AgendaContactosPU**_.

<img src="https://javiergarciaescobedo.es/images/stories/apuntes/Java/BaseDatos/Screen_Shot_2017-04-05_at_21.30.29_927ae.png" alt="Screen Shot 2017 04 05 at 21.30.29 927ae" height="466" width="600">

Este archivo puede verse en modo visual, como se muestra en la imagen anterior, o en modo **código fuente XML**, usando la pestaña _Source_. En su contenido puedes ver, entre otras cosas, los nombres de las clases entidad que se utilizan, la ruta de conexión con la base de datos, así como el nombre de usuario y contraseña de acceso.

```
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="2.1" xmlns="http://xmlns.jcp.org/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence http://xmlns.jcp.org/xml/ns/persistence/persistence_2_1.xsd">
  <persistence-unit name="AgendaContactosPU" transaction-type="RESOURCE_LOCAL">
    <provider>org.eclipse.persistence.jpa.PersistenceProvider</provider>
    <class>es.javiergarciaescobedo.agendacontactos.Provincia</class>
    <class>es.javiergarciaescobedo.agendacontactos.Persona</class>
    <shared-cache-mode>ENABLE_SELECTIVE</shared-cache-mode>
    <properties>
      <property name="javax.persistence.jdbc.url" value="jdbc:derby:/<<<RUTA_AL_PROYECTO>>>/AgendaContactos/BDAgendaContactos;create=true"/>
      <property name="javax.persistence.jdbc.user" value="root"/>
      <property name="javax.persistence.jdbc.driver" value="org.apache.derby.jdbc.EmbeddedDriver"/>
      <property name="javax.persistence.jdbc.password" value="root"/>
    </properties>
  </persistence-unit>
</persistence> 
```

