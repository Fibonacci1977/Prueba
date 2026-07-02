# Las anotaciones en Java EE

Las anotaciones en Java EE (actualmente evolucionado a Jakarta EE) son metadatos que se añaden directamente al código fuente para configurar el comportamiento de componentes, simplificar el desarrollo declarativo y eliminar la necesidad de extensos archivos XML de configuración. \[[1](https://www.makigas.es/series/fundamentos-de-jakarta-ee/que-diferencia-hay-entre-jakartaee-y-javaee), [2](https://www.ibm.com/docs/en/wasdtfe?topic=annotations-java-ee-overview), [3](https://openxava.org/OpenXavaDoc/docs/annotations_es.html), [4](https://www.aluracursos.com/blog/crear-anotaciones-en-java)]Para tips sobre cómo aplicar anotaciones para inyectar dependencias eficientemente:

{% embed url="https://youtu.be/5yhvVdx2yVA?si=st44V6cULcwm4-m5" %}



Las anotaciones más utilizadas en el ecosistema se agrupan según su función:1. Inyección de Dependencias (CDI)

* **`@Inject`**: Inyecta una dependencia o componente en la clase actual.
* **`@Named`**: Permite exponer un bean para que sea accesible desde páginas web (como JSF).
* **`@PostConstruct`**: Se ejecuta inmediatamente después de que el bean haya sido construido y las dependencias inyectadas.
* **`@PreDestroy`**: Se ejecuta justo antes de que el contenedor destruya el bean.

2\. Enterprise JavaBeans (EJB) y Transacciones

* **`@Stateless`**: Define un EJB sin estado.
* **`@Stateful`**: Define un EJB que mantiene el estado conversacional.
* **`@TransactionAttribute`**: Define el comportamiento de las transacciones (ej. `REQUIRED`, `REQUIRES_NEW`).

3\. Java Persistence API (JPA)

* **`@Entity`**: Indica que la clase representa una tabla en la base de datos.
* **`@Table`**: Especifica el nombre de la tabla (opcional si coincide con la clase).
* **`@Id`**: Indica la clave primaria de la entidad.
* **`@GeneratedValue`**: Define la estrategia de generación automática para la clave primaria.
* **`@Column`**: Asigna un campo a una columna específica.
* **`@ManyToOne`, `@OneToMany`, `@OneToOne`**: Definen relaciones entre diferentes entidades. \[[1](https://desarrollodesoftware.home.blog/2019/03/03/que-es-una-entidad-en-java-ee-y-como-declararla/)]

4\. Nivel Web y RESTful (JAX-RS)

* **`@Path`**: Define la ruta URI para acceder a un recurso REST.
* **`@GET`, `@POST`, `@PUT`, `@DELETE`**: Mapean el método HTTP correspondiente.
* **`@Produces`**: Define el tipo de contenido que devuelve el servicio (ej. `MediaType.APPLICATION_JSON`).
* **`@Consumes`**: Define el tipo de contenido que el servicio acepta.

5\. Configuración y Ámbitos (CDI / JSF)

* **`@RequestScoped`**: El ámbito del bean dura una sola petición HTTP.
* **`@SessionScoped`**: El ámbito dura mientras exista la sesión del usuario.
* **`@ApplicationScoped`**: El ámbito dura toda la vida de la aplicación.
* **`@Named`**: Da nombre a un bean para poder llamarlo desde otros componentes.

¿Estás trabajando con un proyecto de **Java EE tradicional** o estás migrando a **Jakarta EE**? Cuéntame qué tipo de aplicación estás desarrollando para ofrecerte ejemplos prácticos adaptados a tu caso.

## Gestión de Transacciones en Jakarta EE: Lo básico

<img src="https://jugnicaragua.org/wp-content/uploads/2023/12/jakarta-transacciones-en-base-de-datos.png" alt="Jakarta Transacciones en base de datos." height="675" width="1080">

La gestión de transacciones es fundamental e integral en las aplicaciones empresariales para garantizar la preservación de la consistencia e integridad de los datos. Una transacción, desde el punto de vista de una base de datos, representa una unidad lógica de trabajo que abarca una o múltiples operaciones de base datos(insertar, update, borrar).

[**Jakarta EE**](https://tuxtor.shekalug.org/al-final-del-dia-que-es-jakarta-ee/), al igual que su predecesor [**JavaEE**](https://es.wikipedia.org/wiki/Java_EE), ofrece una abstracción integral para gestionar transacciones, ya sea programáticamente a través de las API de JTA o de manera declarativa mediante anotaciones. Esta última es más popular debido a su simplicidad y la capacidad de mantener límites de transacción claros sin abrumar el código lógico del negocio. En este artículo, exploraremos la anotación **`@Transactional`** en Jakarta EE, y veremos  diferentes comportamientos bajo varias configuraciones y algunas mejores prácticas.

### La Anotación @Transactional

La anotación **`@Transactional`** es la que ofrece las capacidades de gestión de transacciones declarativas de Jakarta EE. Básicamente, cuando un método está decorado con **@Transactional**, Jakarta EE se asegura de que se inicie una transacción antes de la ejecución del método y posteriormente se confirme si la ejecución continúa normalmente, o se revierta si se produce una excepción.

Por defecto, la anotación **`@Transactional`** tiene un comportamiento de propagación **REQUERIDO**. Es decir, **Si hay una transacción activa, únase a ella. Si no hay una transacción activa, inicie una nueva.**

Vease:

[https://jakarta.ee/specifications/transactions/2.0/apidocs/jakarta/transaction/transactional](https://jakarta.ee/specifications/transactions/2.0/apidocs/jakarta/transaction/transactional)

Ejemplo:

```
@Stateless
public class MyService {

  @Inject
  private MyRepository repository;
  
  @Transactional
  public void performBusinessOperation() {
    // lógica del negocio
    repository.save(entity);
  }
}
```

Repository Code.

```
@Stateless
public class MyRepository {

  @PersistenceContext
  private EntityManager entityManager;
  
  @Transactional
  public void save(MyEntity entity) {
    entityManager.persist(entity);
  }
}
```

En el ejemplo anterior, invocar **`performBusinessOperation()`** inicializa una nueva transacción. Cuando **`save()`** se llama posteriormente dentro de esa transacción, `save()` se une a la transacción existente en lugar de iniciar una nueva debido a su comportamiento de propagación REQUERIDO por defecto.

Sin embargo, vale la pena señalar que el uso superfluo de anotaciones **`@Transactional`**, especialmente cuando las transacciones ya están definidas en la capa de servicio, puede provocar confusión y comportamientos no anticipados. Por lo tanto, generalmente es una buena práctica definir transacciones a nivel de operaciones comerciales (como en la capa de servicio).

### Manejo de errores (RollBack/Deshacer)

La anotacion @**Transactional** no es magica, hay alcances y caracteristicas que se deben manejar como el asilamiento de la persistencia de datos y el **RollBack**, esto se logra lanzando excpeciones del tipo **Runtime**, si usa una excepcion custom, esta debe heredar o ser del tipo **Runtime**.

### Mejores Prácticas

Los límites de transacción deben reflejar los requisitos comerciales. Por lo general, es recomendable iniciar una nueva transacción para cada operación comercial distinta. Las demarcaciones de transacciones suelen ser mejor ubicadas en la capa de servicio, que se alinea bien con la comprensión de las operaciones comerciales. Por otro lado, anotar cada método a nivel de repositorio puede hacer que cada operación CRUD sea transaccional y, en consecuencia, puede crear una multitud de transacciones breves.

Sin embargo, vale la pena considerar el costo de una transacción. Cuanto más larga sea una transacción, más tiempo persistirán los bloqueos en los datos, limitando las posibilidades de acceso concurrente a los datos.

### Conclusión

Todo lo que es entendible es hackeable: Un sólido entendimiento de las transacciones y **`@Transactional`** es indispensable para diseñar aplicaciones empresariales robustas. Seleccionar límites y configuraciones precisas para sus transacciones es crucial para mantener la integridad de los datos, el rendimiento y la escalabilidad de sus aplicaciones. Si bien **Jakarta EE** simplifica significativamente las complejidades de la gestión con la anotación `@Transactional`, ser consciente de sus comportamientos bajo diferentes configuraciones es crucial.
