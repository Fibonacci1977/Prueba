# Page 1

Las anotaciones en Java EE (actualmente evolucionado a Jakarta EE) son metadatos que se añaden directamente al código fuente para configurar el comportamiento de componentes, simplificar el desarrollo declarativo y eliminar la necesidad de extensos archivos XML de configuración. \[[1](https://www.makigas.es/series/fundamentos-de-jakarta-ee/que-diferencia-hay-entre-jakartaee-y-javaee), [2](https://www.ibm.com/docs/en/wasdtfe?topic=annotations-java-ee-overview), [3](https://openxava.org/OpenXavaDoc/docs/annotations_es.html), [4](https://www.aluracursos.com/blog/crear-anotaciones-en-java)]Para tips sobre cómo aplicar anotaciones para inyectar dependencias eficientemente:

{% embed url="https://youtu.be/5yhvVdx2yVA?si=st44V6cULcwm4-m5" %}



[Anotaciones para aplicar inyección de dependencia en ..](https://www.youtube.com/watch?v=5yhvVdx2yVA)Las anotaciones más utilizadas en el ecosistema se agrupan según su función:1. Inyección de Dependencias (CDI)

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
