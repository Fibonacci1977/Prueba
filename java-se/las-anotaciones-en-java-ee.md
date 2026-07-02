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

## Anotaciones de Yakarta

{% embed url="https://www.youtube.com/playlist?list=PLTd5ehIj0goMhqWg_v2CbIZf_Ed2jqE-r" %}

* [Licencia de especificación de la Fundación Eclipse](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#eclipse-foundation-specification-license)
  * [Descargo de responsabilidad](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#disclaimers)
* [1. Alcance de las especificaciones](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#specification-scope)
* [2. Introducción](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#introduction)
  * [2.1. Objetivos](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#goals)
  * [2.2. No Goles](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#non-goals)
  * [2.3. Compatibilidad](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#compatibility)
  * [2.4. Convenciones](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#conventions)
  * [2.5. Miembros del Grupo de Expertos](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#expert-group-members)
  * [2.6. Agradecimientos](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#acknowledgements)
* [3. Anotaciones](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#annotations)
  * [3.1. Directrices generales para la herencia de anotaciones](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#general-guidelines-for-inheritance-of-annotations)
  * [3.2. jakarta.annotation.Generated](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-generated)
  * [3.3. jakarta.annotation.Resource](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-resource)
    * [3.3.1. Inyección en campo](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#field-based-injection)
    * [3.3.2. Inyección basada en setter](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#setter-based-injection)
  * [3.4. jakarta.annotation.Resources](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-resources)
  * [3.5. jakarta.annotation.PostConstruct](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-postconstruct)
  * [3.6. jakarta.annotation.PreDestroy](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-predestroy)
  * [3.7. jakarta.annotation.Priority](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-priority)
  * [3.8. jakarta.annotation.Nonnull](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-nonnull)
  * [3.9. jakarta.annotation.Nullable](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-nullable)
  * [3.10. jakarta.annotation.security.RunAs](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-security-runas)
  * [3.11. jakarta.annotation.security.RolesAllowed](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-security-rolesallowed)
  * [3.12. jakarta.annotation.security.PermitAll](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-security-permitall)
  * [3.13. jakarta.annotation.security.DenyAll](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-security-denyall)
  * [3.14. Interacciones PermitAll, DenyAll y RolesAllowed](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#permitall-denyall-and-rolesallowed-interactions)
  * [3.15. jakarta.annotation.security.DeclareRoles](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-security-declareroles)
  * [3.16. jakarta.annotation.sql.DataSourceDefinition](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-sql-datasourcedefinition)
  * [3.17. jakarta.annotation.sql.DataSourceDefinitions](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-sql-datasourcedefinitions)
  * [3.18. jakarta.annotation.ManagedBean](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#jakarta-annotation-managedbean)
* [4. Referencias](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#references)

```
Especificación: Anotaciones de Yakarta

Versión: 2.1

Estado: Versión final

Fecha de lanzamiento: 1 de diciembre de 2021
```

Copyright (c) 2021 Fundación Eclipse.

#### Licencia de especificación de la Fundación Eclipse

Al usar y/o copiar este documento, o el documento de la Fundación Eclipse desde el cual se vincula esta declaración, usted (el licenciatario) acepta que ha leído, comprendido y cumplirá con los siguientes términos y condiciones:

Se concede permiso para copiar y distribuir el contenido de este documento, o del documento de la Fundación Eclipse al que está vinculado este comunicado, en cualquier medio, para cualquier propósito y sin cargo ni regalías, siempre que incluya lo siguiente en TODAS las copias del documento, o partes del mismo, que utilice:

* Enlace o URL al documento original de la Fundación Eclipse.
* Todos los avisos de derechos de autor existentes, o si no existe ninguno, un aviso (se prefiere el hipertexto, pero se permite una representación textual) con el siguiente formato: "Copyright (c) \[$fecha-del-documento] Eclipse Foundation, Inc. [\[url a esta licencia\]](https://jakarta.ee/specifications/annotations/2.1/annotations-spec-2.1.html#url%20to%20this%20license) "

Se debe incluir el texto completo de este AVISO. Solicitamos que se mencione la autoría en cualquier software, documento u otro producto que usted cree a partir de la implementación del contenido de este documento, o cualquier parte del mismo.

Esta licencia no otorga ningún derecho a crear modificaciones o obras derivadas de los documentos de la Fundación Eclipse, salvo que cualquier persona pueda preparar y distribuir obras derivadas y partes de este documento en software que implemente la especificación, en materiales de apoyo que acompañen a dicho software y en la documentación del mismo, SIEMPRE QUE dichas obras incluyan el aviso que figura a continuación. SIN EMBARGO, la publicación de obras derivadas de este documento para su uso como especificación técnica está expresamente prohibida.

El aviso es:

"Copyright (c) 2018 Eclipse Foundation. Este software o documento incluye material copiado o derivado de \[título y URI del documento de especificaciones de la Eclipse Foundation]."

**Descargo de responsabilidad**

ESTE DOCUMENTO SE PROPORCIONA "TAL CUAL", Y LOS TITULARES DE LOS DERECHOS DE AUTOR Y LA FUNDACIÓN ECLIPSE NO HACEN DECLARACIONES NI GARANTÍAS, EXPRESAS O IMPLÍCITAS, INCLUIDAS, ENTRE OTRAS, LAS GARANTÍAS DE COMERCIABILIDAD, IDONEIDAD PARA UN PROPÓSITO PARTICULAR, NO INFRACCIÓN O TITULARIDAD; QUE EL CONTENIDO DEL DOCUMENTO SEA ADECUADO PARA CUALQUIER PROPÓSITO; NI QUE LA IMPLEMENTACIÓN DE DICHO CONTENIDO NO INFRINJA PATENTES, DERECHOS DE AUTOR, MARCAS COMERCIALES U OTROS DERECHOS DE TERCEROS.

LOS TITULARES DE LOS DERECHOS DE AUTOR Y LA FUNDACIÓN ECLIPSE NO SERÁN RESPONSABLES DE NINGÚN DAÑO DIRECTO, INDIRECTO, ESPECIAL O CONSECUENTE QUE SURJA DEL USO DEL DOCUMENTO O DEL RENDIMIENTO O LA IMPLEMENTACIÓN DE SU CONTENIDO.

El nombre y las marcas comerciales de los titulares de los derechos de autor o de la Fundación Eclipse NO podrán utilizarse en publicidad ni promoción relacionadas con este documento o su contenido sin autorización previa y por escrito. Los derechos de autor de este documento pertenecerán en todo momento a sus titulares.

### 1. Alcance de las especificaciones

Jakarta Annotations define una colección de anotaciones que representan conceptos semánticos comunes y que permiten un estilo de programación declarativo aplicable a diversas tecnologías Java.

### 2. Introducción

Con la incorporación de JSR 175 (A Metadata Facility for the Java™ Programming Language) a la plataforma Java, prevemos que diversas tecnologías utilizarán anotaciones para habilitar un estilo de programación declarativo. Sería lamentable que cada una de estas tecnologías definiera de forma independiente sus propias anotaciones para conceptos comunes. Sería valioso contar con coherencia dentro de las tecnologías de componentes de Jakarta EE y Java SE, pero también lo será permitir la coherencia entre Jakarta EE y Java SE.

El objetivo de esta especificación es definir un conjunto reducido de anotaciones comunes que estarán disponibles para su uso en otras especificaciones. Se espera que esto ayude a evitar redundancias o duplicaciones innecesarias entre las anotaciones definidas en diferentes especificaciones de Jakarta EE. De esta forma, todas las anotaciones comunes se centralizarán y las tecnologías podrán hacer referencia a esta especificación en lugar de tenerlas definidas en múltiples especificaciones. Así, todas las tecnologías podrán usar la misma versión de las anotaciones y se garantizará la coherencia en las anotaciones utilizadas en todas las plataformas.

#### 2.1. Objetivos

Definición de anotaciones para su uso en Jakarta EE: Esta especificación definirá las anotaciones que se utilizarán dentro de las tecnologías de componentes en Jakarta EE, así como en la plataforma en su conjunto.

#### 2.2. No Goles

Compatibilidad con versiones de Java anteriores a J2SE 5.0

Las anotaciones se introdujeron en J2SE 5.0. No es posible procesar anotaciones en versiones anteriores a J2SE 5.0. El objetivo de esta especificación no es definir un método para procesar anotaciones de ningún tipo en versiones anteriores a J2SE 5.0.

#### 2.3. Compatibilidad

Las anotaciones definidas en esta especificación pueden incluirse individualmente según sea necesario en los productos que las utilicen. Otras especificaciones de Java requerirán compatibilidad con subconjuntos de estas anotaciones. Los productos que sean compatibles con estas especificaciones de Java deben incluir las anotaciones requeridas.

#### 2.4. Convenciones

Las palabras clave 'MUST', 'MUST NOT', 'REQUIRED', 'SHALL', 'SHALL NOT', 'SHOULD', 'SHOULD NOT', 'RECOMMENDED', 'MAY' y 'OPTIONAL' en este documento deben interpretarse como se describe en RFC 2119.

El código Java tiene el formato que se muestra a continuación:

```
package com.wombat.hello;

public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello world");
    }
}
```

#### 2.5. Miembros del Grupo de Expertos

Los siguientes miembros del grupo de expertos participaron en JSR 250:

* Cedric Beust (individual)
* Bill Burke (JBoss)
* Wayne Carr (Intel)
* Robert Clevenger (Oráculo)
* Evan Ireland (Sybase)
* Woo Jin Kim (Tmax Soft)
* Gavin King (JBoss)
* Rajiv Mordani (Oracle Corporation, Responsable de especificaciones)
* Ted Neward (individual)
* Anurag Parashar (tecnologías Pramati)
* Michael Santos (individual)
* Hani Suleiman (Ironflare AB)
* Seth White (BEA)

#### 2.6. Agradecimientos

Además del grupo de expertos mencionado anteriormente, Linda DeMichiel, Ron Monzillo, Lance Andersen y Bill Shannon, todos ellos empleados de Oracle Corporation, han aportado información para esta especificación.

### 3. Anotaciones

Este capítulo describe las anotaciones estándar, algunas pautas para la herencia de anotaciones y el uso de estas anotaciones siempre que sea posible.

#### 3.1. Directrices generales para la herencia de anotaciones

La interacción entre anotaciones y herencia en el lenguaje Java puede resultar compleja para los desarrolladores. Estos se basan en ciertas suposiciones implícitas al intentar comprender cómo se combinan las anotaciones con otras características del lenguaje. Al mismo tiempo, la semántica de las anotaciones se define mediante especificaciones individuales, lo que puede generar inconsistencias. Por ejemplo, consideremos el siguiente caso:

```
public class Base {
    @TransactionAttribute(REQUIRES_NEW)
    public void foo {...}
}

@Stateless
public class Derived extends Base {
    @TransactionAttribute(NEVER)
    public void foo {...}
}
```

De acuerdo con el concepto de sobreescritura de métodos, la mayoría de los desarrolladores asumirán que, en la clase _Derivada_ , la anotación _TransactionAttribute efectiva para el método foo_ es _TransactionAttribute(NEVER)_ . Por otro lado, la especificación que rige la semántica del tipo de anotación _TransactionAttribute podría haber requerido que la TransactionAttribute_ efectiva fuera la más restrictiva en todo el árbol de herencia, es decir, en el ejemplo anterior, _TransactionAttribute(REQUIRES\_NEW)_ . Una posible justificación para esta semántica podría ser que el método _foo_ en la clase _Derivada podría llamar a super.foo()_ , lo que resultaría en la ejecución de algún código que requiere que exista una transacción. Esta elección por parte de la especificación para _TransactionAttribute_ habría contradicho la intuición del desarrollador sobre cómo funciona la sobreescritura de métodos.

Para mantener bajo control la complejidad resultante, a continuación se presentan algunas pautas recomendadas sobre cómo deben interactuar las anotaciones definidas en las diferentes especificaciones con la herencia:

1. Las anotaciones a nivel de clase solo afectan a la clase que anotan y a sus miembros, es decir, a sus métodos y campos. Nunca afectan a un miembro declarado por una superclase, incluso si no está oculto ni sobrescrito por la clase en cuestión.
2. Además de afectar a la clase anotada, las anotaciones a nivel de clase pueden funcionar como una forma abreviada de las anotaciones a nivel de miembro. Si un miembro lleva una anotación específica a nivel de miembro, cualquier anotación del mismo tipo implícita en una anotación a nivel de clase se ignora. En otras palabras, las anotaciones explícitas a nivel de miembro tienen prioridad sobre las anotaciones a nivel de miembro implícitas en una anotación a nivel de clase. Por ejemplo, una anotación _TransactionAttribute(REQUIRED)_ en una clase implica que todos los métodos públicos de la clase a la que se aplica están anotados con _TransactionAttribute(REQUIRED)_ . Sin embargo, si hay una anotación _TransactionAttribute(NEVER)_ en un método en particular, entonces _TransactionAttribute(NEVER)_ se aplica a ese método en particular y no _TransactionAttribute(REQUIRED)_ .
3. Las interfaces implementadas por una clase nunca aportan anotaciones a la clase misma ni a ninguno de sus miembros.
4. Los miembros heredados de una superclase que no estén ocultos ni sobrescritos mantienen las anotaciones que tenían en la clase que los declaró, incluidas las anotaciones a nivel de miembro implícitas en las anotaciones a nivel de clase.
5. Las anotaciones a nivel de miembro en un miembro oculto o sobrescrito siempre se ignoran.

Este conjunto de directrices garantiza que los efectos de una anotación sean locales a la clase en la que aparece. Para encontrar la anotación efectiva de un miembro de clase, el desarrollador debe localizar su última declaración no oculta ni sobrescrita y examinarla. Si no encuentra la anotación buscada, deberá examinar la declaración de la clase que la contiene. Si incluso este paso no proporciona la anotación, no se consultará ningún otro archivo fuente.

A continuación se muestran algunos ejemplos que explican cómo se aplicarán las directrices definidas anteriormente a la anotación _TransactionAttribute ._

```
@TransactionAttribute(REQUIRED)
class Base {
    @TransactionAttribute(NEVER)
    public void foo() {...}

    public void bar() {...}
}

@Stateless
class ABean extends Base {
    public void foo() {...}
}

@Stateless
public class BBean extends Base {
    @TransactionAttribute(REQUIRES_NEW)
    public void foo() {...}
}

@Stateless
@TransactionAttribute(REQUIRES_NEW)
public class CBean extends Base {
    public void foo() {...}
    public void bar() {...}
}

@Stateless
@TransactionAttribute(REQUIRES_NEW)
public class DBean extends Base {
    public void bar() {...}
}

@Stateless
@TransactionAttribute(REQUIRES_NEW)
public class EBean extends Base {
    // ...
}
```

La tabla que aparece a continuación muestra la anotación _TransactionAttribute_ efectiva en cada uno de los casos anteriores, aplicando las directrices especificadas para las anotaciones y la herencia:

| Métodos en clases derivadas | Valor efectivo del atributo de transacción                                                                                            |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| foo() en ABean              | TransactionAttribute(REQUERIDO). (Atributo de transacción predeterminado según lo define la especificación Jakarta Enterprise Beans). |
| bar() en ABean              | Atributo de transacción (OBLIGATORIO)                                                                                                 |
| foo() en BBean              | Atributo de transacción (REQUIERE\_NUEVO)                                                                                             |
| bar() en BBean              | Atributo de transacción (OBLIGATORIO)                                                                                                 |
| foo() en CBean              | Atributo de transacción (REQUIERE\_NUEVO)                                                                                             |
| bar() en CBean              | Atributo de transacción (REQUIERE\_NUEVO)                                                                                             |
| foo() en DBean              | TransactionAttribute(NUNCA) (de la clase base)                                                                                        |
| bar() en DBean              | Atributo de transacción (REQUIERE\_NUEVO)                                                                                             |
| foo() en EBean              | TransactionAttribute(NUNCA) (de la clase base)                                                                                        |
| bar() en EBean              | TransactionAttribute(REQUERIDO) (de la clase Base)                                                                                    |

Para obtener más detalles sobre la anotación _TransactionAttribute_ , consulte la especificación _de contratos principales de Jakarta Enterprise Beans_ .

Todas las anotaciones definidas en esta especificación siguen las directrices definidas anteriormente, a menos que se indique explícitamente lo contrario.

#### 3.2. jakarta.annotation.Generated

La anotación _«Generado»_ se utiliza para marcar el código fuente que se ha generado. Se puede especificar en una clase, método o campo. También se puede usar para diferenciar el código escrito por el usuario del código generado en un mismo archivo.

El elemento _de valor_ DEBE contener el nombre del generador de código. La convención recomendada es utilizar el nombre completo del generador de código. Por ejemplo: _com.company.package.classname_ .

El elemento _de fecha_ se utiliza para indicar la fecha en que se generó el código fuente. El elemento _de fecha_ DEBE cumplir con la norma ISO 8601. Por ejemplo, el elemento _de fecha_ podría tener el siguiente valor:

```
2001-07-04T12:08:56.235-0700
```

lo que representa las 12:08:56 de la hora local del 4 de julio de 2001 en la zona horaria del Pacífico de Estados Unidos.

El elemento _de comentarios_ sirve como marcador de posición para cualquier comentario que el generador de código desee incluir en el código generado.

```
package jakarta.annotation;

import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

@Target({ANNOTATION_TYPE, CONSTRUCTOR, FIELD, LOCAL_VARIABLE, METHOD, PACKAGE, PARAMETER, TYPE})
@Retention(SOURCE)
public @interface Generated {
    String[] value();
    String date() default "";
    String comments() default "";
}
```

| Elemento    | Descripción                                                                                      | Por defecto |
| ----------- | ------------------------------------------------------------------------------------------------ | ----------- |
| valor       | Nombre del generador de código                                                                   |             |
| fecha       | Fuente de datos generada. DEBE cumplir con la norma ISO 8601.                                    | ""          |
| comentarios | Espacio reservado para comentarios que el generador podría querer incluir en el código generado. | ""          |

El siguiente ejemplo muestra el uso de la anotación definida anteriormente:

```
@Generated("com.sun.xml.rpc.AProcessor")
public interface StockQuoteService extends java.rmi.Remote {
    this.context = context;
}
```

#### 3.3. jakarta.annotation.Resource

La anotación _\`Resource\`_ se utiliza para declarar una referencia a un recurso. Puede especificarse en una clase, método o campo. Cuando se aplica a un campo o método, el contenedor inyectará una instancia del recurso solicitado en la aplicación al inicializarla. Si se aplica a una clase, declara un recurso que la aplicación consultará en tiempo de ejecución. Aunque esta anotación no esté marcada como _\`Inherited\`_ , es necesario examinar todas las superclases para descubrir todos sus usos. Todas estas instancias de anotación especifican recursos que la aplicación necesita. Cabe destacar que esta anotación puede aparecer en campos y métodos privados de las superclases. En estos casos, también es necesario inyectar los recursos declarados, incluso si una subclase sobrescribe un método con dicha anotación.

El elemento _\`name\`_ es el nombre JNDI del recurso. Cuando se aplica la anotación _\`Resource\`_ a un campo, el valor predeterminado del elemento _\`name\`_ es el nombre del campo seguido del nombre de la clase. Cuando se aplica a un método, el valor predeterminado es el nombre de la propiedad JavaBeans correspondiente al método, seguido del nombre de la clase. Cuando se aplica a una clase, no hay valor predeterminado y el nombre DEBE especificarse.

El elemento _\`type\`_ define el tipo Java del recurso. Cuando se aplica la anotación _\`Resource\` a un campo, el valor predeterminado del elemento \`type\`_ es el tipo del campo. Cuando se aplica a un método, el valor predeterminado es el tipo de la propiedad \`JavaBeans\`. Cuando se aplica a una clase, no hay valor predeterminado y el tipo DEBE especificarse. Cuando se utiliza, el tipo DEBE ser compatible con la asignación.

El elemento _authenticationType_ se utiliza para indicar el tipo de autenticación que se usará para el recurso. Puede tomar uno de dos valores definidos como _enumeración_ : _CONTAINER_ o _APPLICATION_ . Este elemento se puede especificar para recursos que representan una fábrica de conexiones de cualquier tipo compatible y NO DEBE especificarse para recursos de otros tipos.

El elemento _"compartible_ " se utiliza para indicar si un recurso puede compartirse entre este componente y otros componentes. Este elemento puede especificarse para recursos que representan una fábrica de conexiones de cualquier tipo compatible o instancias de objetos ORB, y NO DEBE especificarse para recursos de otros tipos.

El elemento _\` mappedName\`_ es un nombre específico del producto al que se debe asignar este recurso. Este elemento permite asignar la referencia del recurso especificada por la anotación _\`Resource\`_ al nombre de un recurso conocido por el servidor de aplicaciones. El nombre asignado puede tener cualquier formato. Los servidores de aplicaciones no están obligados a admitir ningún formato o tipo específico de nombre asignado, ni a utilizarlos. El nombre asignado depende del producto y, a menudo, de la instalación. Ningún uso de un nombre asignado es portable.

El elemento _de descripción_ describe el recurso. Se espera que la descripción esté en el idioma predeterminado del sistema donde se implementa la aplicación. Esta descripción puede utilizarse para facilitar la selección del recurso adecuado.

El elemento _de búsqueda_ especifica el nombre JNDI de un recurso al que se vinculará el recurso que se está definiendo. El tipo del recurso referenciado debe ser compatible con el del recurso que se está definiendo.

```
package jakarta.annotation;

import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

@Target({TYPE, METHOD, FIELD})
@Retention(RUNTIME)
@Repeatable(Resources.class)
public @interface Resource {
    public enum AuthenticationType {
        CONTAINER,
        APPLICATION
    }

    String name() default "";

    Class<?> type() default Object.class;

    AuthenticationType authenticationType() default AuthenticationType.CONTAINER;

    boolean shareable() default true;

    String mappedName() default "";

    String description() default "";

    String lookup() default "";
}
```

| Elemento              | Descripción                                                                            | Por defecto  |
| --------------------- | -------------------------------------------------------------------------------------- | ------------ |
| nombre                | El nombre JNDI del recurso                                                             | ""           |
| tipo                  | El tipo Java del recurso                                                               | Objeto.clase |
| tipo de autenticación | El tipo de autenticación que se utilizará para el recurso                              | RECIPIENTE   |
| compartible           | Indica si el recurso se puede compartir.                                               | verdadero    |
| nombre mapeado        | Un nombre específico del producto al que debe corresponder el recurso.                 | ""           |
| descripción           | Descripción del recurso.                                                               | ""           |
| buscar                | el nombre JNDI de un recurso al que estará vinculado el recurso que se está definiendo | ""           |

**3.3.1. Inyección en campo**

Para acceder a un recurso, el desarrollador declara un campo y lo anota como referencia de recurso. Si faltan los elementos de nombre y tipo en la anotación, se inferirán a partir de la declaración del campo. Se produce un error si el tipo especificado por la anotación _de recurso_ y el tipo del campo son incompatibles.

Por ejemplo:

```
@Resource
private DataSource myDB;
```

En el ejemplo anterior, el nombre efectivo es _com.example.class/myDB_ y el tipo efectivo es _javax.sql.DataSource.class_ .

```
@Resource(name="customerDB")
private DataSource myDB;
```

En el ejemplo anterior, el nombre es _customerDB_ y el tipo efectivo es _javax.sql.DataSource.class_ .

**3.3.2. Inyección basada en setter**

Para acceder a un recurso, el desarrollador declara un método setter y lo anota como referencia al recurso. El nombre y el tipo del recurso pueden inferirse examinando la declaración del método, si es necesario. Si el recurso no se declara, el nombre de la propiedad JavaBeans se determina a partir del nombre del método setter. El método setter DEBE seguir la convención estándar de JavaBeans: el nombre comienza con " _set_ ", el tipo de retorno es _void_ y solo tiene un parámetro. Además, el tipo del parámetro DEBE ser compatible con el elemento _type_ de la anotación _Resource_ , si se especifica.

Por ejemplo:

```
@Resource
private void setMyDB(DataSource ds) {
    myDB = ds;
}

private DataSource myDB;
```

En el ejemplo anterior, el nombre efectivo es _com.example.class/myDB_ y el tipo es _javax.sql.DataSource.class_ .

```
@Resource(name="customerDB")
private void setMyDB(DataSource ds) {
    myDB = ds;
}

private DataSource myDB;
```

En el ejemplo anterior, el nombre es _customerDB_ y el tipo es _javax.sql.DataSource.class_ .

La tabla que aparece a continuación muestra la correspondencia entre el tipo de Java y el tipo de recurso equivalente en los descriptores de despliegue de Jakarta EE 9 (y posteriores):

| Tipo Java                                                                  | Tipo de recurso equivalente    |
| -------------------------------------------------------------------------- | ------------------------------ |
| java.lang.String                                                           | entrada de entorno             |
| java.lang.Character                                                        | entrada de entorno             |
| java.lang.Entero                                                           | entrada de entorno             |
| java.lang.Booleano                                                         | entrada de entorno             |
| java.lang.Double                                                           | entrada de entorno             |
| java.lang.Byte                                                             | entrada de entorno             |
| java.lang.Short                                                            | entrada de entorno             |
| java.lang.Long                                                             | entrada de entorno             |
| java.lang.Float                                                            | entrada de entorno             |
| jakarta.xml.ws.Servicio                                                    | referencia de servicio         |
| Servicio web jakarta.jws.                                                  | referencia de servicio         |
| javax.sql.DataSource                                                       | referencia de recurso          |
| Jakarta.jms.Fábrica de conexiones                                          | referencia de recurso          |
| Jakarta.jms.FábricaDeConexionesDeCola                                      | referencia de recurso          |
| Jakarta.jms.Fábrica de conexiones de temas                                 | referencia de recurso          |
| jakarta.mail.Sesión                                                        | referencia de recurso          |
| java.net.URL                                                               | referencia de recurso          |
| Jakarta.resource.cci.ConnectionFactory                                     | referencia de recurso          |
| cualquier otra fábrica de conexiones definida por un adaptador de recursos | referencia de recurso          |
| Jakarta.jms.Cola                                                           | referencia-destino-del-mensaje |
| jakarta.jms.Tema                                                           | referencia-destino-del-mensaje |
| jakarta.resource.cci.InteractionSpec                                       | referencia-entorno-recurso     |
| Jakarta.Transacción.Transacción de usuario                                 | referencia-entorno-recurso     |
| Todo lo demás                                                              | referencia-entorno-recurso     |

#### 3.4. jakarta.annotation.Resources

La anotación _Resource_ se utiliza para declarar una referencia a un recurso. La anotación _Resources_ actúa como un contenedor para múltiples declaraciones de recursos.

```
package jakarta.annotation;

import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

@Target({TYPE})
@Retention(RUNTIME)
public @interface Resources {
    Resource[] value;
}
```

| Elemento | Descripción                                 | Por defecto |
| -------- | ------------------------------------------- | ----------- |
| valor    | Contenedor para definir múltiples recursos. |             |

El siguiente ejemplo muestra el uso de la anotación definida anteriormente:

```
@Resources ({
    @Resource(name="myDB", type=javax.sql.DataSource),
    @Resource(name="myMQ", type=jakarta.jms.ConnectionFactory)
})

public class CalculatorBean {
    // ...
}
```

#### 3.5. jakarta.annotation.PostConstruct

La anotación _PostConstruct_ se utiliza en un método que debe ejecutarse después de la inyección de dependencias para realizar cualquier inicialización. Este método DEBE invocarse antes de que la clase se ponga en servicio. Esta anotación DEBE ser compatible con todas las clases que admiten la inyección de dependencias. El método anotado con _PostConstruct_ DEBE invocarse incluso si la clase no solicita ningún recurso para inyectar. Solo un método en una clase determinada puede estar anotado con esta anotación. El método al que se aplica la anotación _PostConstruct_ DEBE cumplir todos los siguientes requisitos, excepto en los casos en que estos requisitos se hayan flexibilizado en otra especificación. Véase, en particular, la especificación _de Interceptores de Jakarta_ .

* El método NO DEBE tener ningún parámetro.
* El tipo de retorno del método DEBE ser _void_ .
* El método NO DEBE lanzar una excepción verificada.
* El método sobre el que se aplica _PostConstruct_ PUEDE ser _público_ , _protegido_ , privado de paquete o _privado_ .
* El método NO DEBE ser estático excepto para el cliente de la aplicación.
* En general, el método NO DEBE ser definitivo. Sin embargo, se permiten otras especificaciones para flexibilizar este requisito en función de cada componente.
* Si el método lanza una excepción no controlada, la clase NO DEBE ponerse en servicio.

```
package jakarta.annotation;

import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

@Target(METHOD)
@Retention(RUNTIME)
public @interface PostConstruct {

}
```

El siguiente ejemplo muestra el uso de la anotación definida anteriormente:

```
@Resource
private void setMyDB(DataSource ds) {
    myDB = ds;
}

@PostConstruct
private void initialize() {
    // Initialize the connection object from the DataSource
    connection = myDB.getConnection();
}

private DataSource myDB;
private Connection connection;
```

#### 3.6. jakarta.annotation.PreDestroy

La anotación _PreDestroy_ se utiliza en un método como notificación de devolución de llamada para indicar que el contenedor está eliminando la instancia. El método anotado con _PreDestroy_ se usa normalmente para liberar los recursos que la instancia ha estado utilizando. Esta anotación DEBE ser compatible con todos los objetos gestionados por el contenedor que admiten _PostConstruct,_ excepto el cliente de la aplicación. El método al que se aplica la anotación _PreDestroy_ DEBE cumplir todos los requisitos siguientes, excepto en los casos en que otros requisitos los hayan flexibilizado. Véase, en particular, la especificación _de Jakarta Interceptors_ .

* El método NO DEBE tener ningún parámetro.
* El tipo de retorno del método DEBE ser _void_ .
* El método NO DEBE lanzar una excepción verificada.
* El método sobre el que se aplica _PreDestroy_ PUEDE ser _público_ , _protegido_ , privado de paquete o _privado_ .
* El método NO DEBE ser estático.
* En general, el método NO DEBE ser definitivo. Sin embargo, se permiten otras especificaciones para flexibilizar este requisito en función de cada componente.
* Si el método lanza una excepción no controlada, esta se ignora.

```
package jakarta.annotation;

import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

@Target(METHOD)
@Retention(RUNTIME)
public @interface PreDestroy {

}
```

El siguiente ejemplo muestra el uso de la anotación definida anteriormente:

```
@Resource
private void setMyDB(DataSource ds) {
    myDB = ds;
}

@PostConstruct
private void initialize() {
    // Initialize the connection object from the DataSource
    connection = myDB.getConnection();
}

@PreDestroy
private void cleanup() {
    // Close the connection to the DataSource.
    connection.close();
}

private DataSource myDB;
private Connection connection;
```

#### 3.7. jakarta.annotation.Priority

La anotación _Priority_ se puede aplicar a cualquier elemento del programa para indicar el orden en que deben utilizarse. El efecto de usar la anotación _Priority_ en un caso particular viene determinado por otras especificaciones que definen el uso de una clase específica.

Por ejemplo, la especificación _Jakarta Interceptors_ define el uso de prioridades en los interceptores para controlar el orden en que se llaman.

Los valores de prioridad generalmente deben ser no negativos, reservándose los valores negativos para significados especiales como "indefinido" o "no especificado". Una especificación que defina el uso de la anotación _Priority_ puede definir el rango de prioridades permitidas y cualquier valor de prioridad con significado especial.

```
package jakarta.annotation;

import java.lang.annotation.*;
import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

@Retention(RUNTIME)
@Documented
public @interface Priority {
     // The priority value.
     int value();
}
```

#### 3.8. jakarta.annotation.Nonnull

La anotación _Nonnull_ se utiliza para marcar elementos que no pueden ser nulos `null`.

Esta información puede ser utilizada para la validación por IDE, herramientas de análisis estático y en tiempo de ejecución.

La anotación puede estar presente en cualquier objetivo. Esta especificación define el comportamiento en los siguientes objetivos:

* Método: el tipo de retorno nunca será`null`
* Parámetro: el parámetro no debe ser`null`
* Campo: el campo no puede existir `null`después de que se haya completado la construcción del objeto.

```
package jakarta.annotation;

import java.lang.annotation.Documented;
import java.lang.annotation.Retention;

import static java.lang.annotation.RetentionPolicy.RUNTIME;

@Documented
@Retention(RUNTIME)
public @interface Nonnull {
}
```

El siguiente ejemplo muestra el uso de la anotación definida anteriormente:

```
public interface StockQuoteService {
    @Nonnull
    BigDecimal quote(@Nonnull String marker);
}
```

#### 3.9. jakarta.annotation.Nullable

La anotación _Nullable_ se utiliza para marcar elementos que pueden ser nulos `null`.

Esta información puede ser utilizada para la validación por IDE, herramientas de análisis estático y en tiempo de ejecución.

La anotación puede estar presente en cualquier objetivo. Esta especificación define el comportamiento en los siguientes objetivos:

* Método: el tipo de retorno puede ser`null`
* Parámetro: el parámetro puede ser`null`
* Campo - el campo puede ser`null`

```
package jakarta.annotation;

import java.lang.annotation.Documented;
import java.lang.annotation.Retention;

import static java.lang.annotation.RetentionPolicy.RUNTIME;

@Documented
@Retention(RUNTIME)
public @interface Nullable {
}
```

El siguiente ejemplo muestra el uso de la anotación definida anteriormente:

```
public interface StockQuoteService {
    BigDecimal quote(String marker, @Nullable BigDecimal defaultValue);
}
```

#### 3.10. jakarta.annotation.security.RunAs

La anotación _RunAs_ define el rol de seguridad de la aplicación durante su ejecución en un contenedor Jakarta EE. Se puede especificar en una clase. Esto permite a los desarrolladores ejecutar una aplicación bajo un rol específico. El rol DEBE corresponder a la información de usuario/grupo en el dominio de seguridad del contenedor. El _valor_ de la anotación es el nombre del rol de seguridad.

```
package jakarta.annotation.security;

import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

@Target(TYPE)
@Retention(RUNTIME)
public @interface RunAs {
    String value();
}
```

| Elemento | Descripción                                                                             | Por defecto |
| -------- | --------------------------------------------------------------------------------------- | ----------- |
| valor    | Función de seguridad de la aplicación durante su ejecución en un contenedor Jakarta EE. |             |

El siguiente ejemplo muestra el uso de la anotación definida anteriormente:

```
@RunAs("Admin")
public class Calculator {
    // ...
}
```

#### 3.11. jakarta.annotation.security.RolesAllowed

La anotación _RolesAllowed_ especifica los roles de seguridad autorizados para acceder a los métodos de una aplicación. El valor de la anotación _RolesAllowed_ es una lista de nombres de roles de seguridad.

La anotación _RolesAllowed_ se puede especificar en una clase o en uno o varios métodos. Si se especifica en una clase, se aplica a todos los métodos de la clase. Si se especifica en un método, se aplica solo a ese método. Si se aplica tanto a la clase como al método, el valor del método tiene prioridad sobre el de la clase.

```
package jakarta.annotation.security;

import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

@Target({TYPE,METHOD})
@Retention(RUNTIME)
public @interface RolesAllowed {
    String[] value();
}
```

| Elemento | Descripción                                                             | Por defecto |
| -------- | ----------------------------------------------------------------------- | ----------- |
| valor    | Lista de roles autorizados para acceder a los métodos de la aplicación. |             |

El siguiente ejemplo muestra el uso de la anotación definida anteriormente:

```
@RolesAllowed("Users")
public class Calculator {
    @RolesAllowed("Administrator")
    public void setNewRate(int rate) {
        // ...
    }
}
```

#### 3.12. jakarta.annotation.security.PermitAll

La anotación _PermitAll_ especifica que todos los roles de seguridad tienen permiso para invocar el/los método(s) especificado(s), es decir, que dicho(s) método(s) no están sujetos a verificación. Puede especificarse en una clase o en sus métodos. Si se especifica en la clase, se aplica a todos sus métodos. Si se especifica a nivel de método, solo afecta a ese método.

```
package jakarta.annotation.security;

import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

@Target({TYPE,METHOD})
@Retention(RUNTIME)
public @interface PermitAll {

}
```

El siguiente ejemplo muestra el uso de la anotación definida anteriormente:

```
import jakarta.annotation.security.*;

@RolesAllowed("Users")
public class Calculator {
    @RolesAllowed("Administrator")
    public void setNewRate(int rate) {
        // ...
    }

    @PermitAll
    public long convertCurrency(long amount) {
        // ...
    }
}
```

#### 3.13. jakarta.annotation.security.DenyAll

La anotación _DenyAll_ especifica que ningún rol de seguridad tiene permitido invocar el/los método(s) especificado(s), es decir, que el/los método(s) deben excluirse de la ejecución en el contenedor Jakarta EE.

```
package jakarta.annotation.security;

import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

@Target({TYPE, METHOD})
@Retention(RUNTIME)
public @interface DenyAll {

}
```

El siguiente ejemplo muestra el uso de la anotación definida anteriormente:

```
import jakarta.annotation.security.*;

@RolesAllowed("Users")
public class Calculator {
    @RolesAllowed("Administrator")
    public void setNewRate(int rate) {
        // ...
    }

    @DenyAll
    public long convertCurrency(long amount) {
        // ...
    }
}
```

#### 3.14. Interacciones PermitAll, DenyAll y RolesAllowed

Las anotaciones _PermitAll_ , _DenyAll_ y _RolesAllowed_ definen qué roles de seguridad tienen permiso para acceder a los métodos a los que se aplican. Esta sección describe cómo interactúan estas anotaciones y qué usos de las mismas son válidos.

Si las anotaciones _PermitAll_ , _DenyAll_ y _RolesAllowed_ se aplican a los métodos de una clase, entonces las anotaciones a nivel de método tienen prioridad (en los métodos correspondientes) sobre cualquier anotación a nivel de clase de tipo _PermitAll_ , _DenyAll_ y _RolesAllowed_ .

#### 3.15. jakarta.annotation.security.DeclareRoles

La anotación _DeclareRoles_ se utiliza para especificar los roles de seguridad que usa la aplicación. Se puede especificar en una clase. Normalmente, se usa para definir roles que se pueden comprobar (por ejemplo, llamando a _isUserInRole_ ) desde los métodos de la clase anotada. También se puede usar para declarar roles que no se declaran implícitamente como resultado de su uso en una anotación _RolesAllowed_ en la clase o en un método de la clase.

```
package jakarta.annotation.security;

import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

@Target(TYPE)
@Retention(RUNTIME)
public @interface DeclareRoles {
    String[] value();
}
```

| Elemento | Descripción                                                 | Por defecto |
| -------- | ----------------------------------------------------------- | ----------- |
| valor    | Lista de roles de seguridad especificados por la aplicación |             |

El siguiente ejemplo muestra el uso de la anotación definida anteriormente:

```
@DeclareRoles("BusinessAdmin")
public class Calculator {
    public void convertCurrency() {
        if (x.isUserInRole("BusinessAdmin")) {
            // ...
        }
    }

    // ...
}
```

#### 3.16. jakarta.annotation.sql.DataSourceDefinition

La anotación _DataSourceDefinition_ se utiliza para definir un _DataSource_ de contenedor que se registrará con JNDI. El _DataSource_ se puede configurar estableciendo los elementos de anotación para las propiedades _de DataSource_ de uso común . Se pueden especificar propiedades estándar y específicas del proveedor adicionales mediante el elemento _properties_ . El origen de datos se registrará con el nombre especificado en el elemento _name_ . Se puede definir en cualquier espacio de nombres válido de Jakarta EE, lo que determinará la accesibilidad del origen de datos desde otros componentes. Una clase de implementación de controlador JDBC del tipo apropiado, ya sea _DataSource_ , _ConnectionPoolDataSource_ o _XADataSource_ , debe indicarse mediante el elemento _className_ . La clase del controlador no tiene que estar disponible en el despliegue, pero debe estar disponible en tiempo de ejecución antes de cualquier intento de acceder al _DataSource_ .

```
Las propiedades _DataSource_ no deberían ser
especificado más de una vez. Si el elemento de anotación _url_ contiene un
La propiedad _DataSource_ que también se especificó utilizando la correspondiente
elemento de anotación o se especificó en la anotación _properties_
elemento, el orden de precedencia no está definido y depende de la implementación.
```

Los proveedores no están obligados a admitir _propiedades_ que normalmente no se aplican a un tipo de origen de datos específico. Por ejemplo, especificar la propiedad _transaccional_ como _verdadera_ , pero proporcionar un valor para _className_ que implemente una clase de origen de datos distinta de _XADataSource_ , podría no ser compatible.

Las propiedades específicas del proveedor pueden combinarse con las propiedades estándar de la fuente de datos definidas mediante esta anotación, o utilizarse para anularlas.

_Las propiedades de DataSource_ que se especifiquen pero que no sean compatibles con una configuración determinada o que no se puedan asignar a una propiedad de configuración específica del proveedor pueden ignorarse.

Si bien la anotación permite especificar una contraseña, se recomienda no incluir contraseñas en el código de producción. El elemento _de contraseña_ en la anotación se proporciona para facilitar el desarrollo.

```
package jakarta.annotation.sql;

import java.lang.annotation.Target;
import java.lang.annotation.Retention;
import java.lang.annotation.ElementType;
import java.lang.annotation.RetentionPolicy;

@Target({ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Repeatable(DataSourceDefinitions.class)
public @interface DataSourceDefinition {
    String name();
    String className();
    String description() default "";
    String url() default "";
    String user() default "";
    String password() default "";
    String databaseName() default "";
    int portNumber() default -1;
    String serverName() default "localhost";
    int isolationLevel() default -1;
    boolean transactional() default true;
    int initialPoolSize() default -1;
    int maxPoolSize() default -1;
    int minPoolSize() default -1;
    int maxIdleTime() default -1;
    int maxStatements() default -1;
    String[] properties() default \{};
    int loginTimeout() default 0;
}
```

| Elemento                     | Descripción                                                                                                                                                                                                                                                                                                                   | Por defecto                   |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| _nombre_                     | Nombre JNDI con el que se registrará la fuente de datos.                                                                                                                                                                                                                                                                      |                               |
| _nombre de clase_            | Nombre de la clase de implementación de DataSource                                                                                                                                                                                                                                                                            |                               |
| _descripción_                | Descripción de la fuente de datos                                                                                                                                                                                                                                                                                             | ""                            |
| _URL_                        | Una URL JDBC. Si el elemento de anotación url contiene una propiedad DataSource que también se especificó mediante el elemento de anotación correspondiente, el orden de precedencia no está definido y depende de la implementación.                                                                                         | ""                            |
| _usuario_                    | Nombre de usuario para la autenticación de la conexión                                                                                                                                                                                                                                                                        | ""                            |
| _contraseña_                 | Contraseña para la autenticación de la conexión                                                                                                                                                                                                                                                                               | ""                            |
| _nombre de la base de datos_ | Nombre de una base de datos en un servidor                                                                                                                                                                                                                                                                                    | ""                            |
| _número de puerto_           | Número de puerto donde un servidor está escuchando las solicitudes                                                                                                                                                                                                                                                            | ""                            |
| _nombre\_servidor_           | nombre del servidor de base de datos                                                                                                                                                                                                                                                                                          | "localhost"                   |
| _nivel de aislamiento_       | Nivel de aislamiento para las conexiones.                                                                                                                                                                                                                                                                                     | -1 (específico del proveedor) |
| _transaccional_              | Indica si una conexión es transaccional o no.                                                                                                                                                                                                                                                                                 | verdadero                     |
| _tamañoinicialdepiscina_     | Número de conexiones que deben crearse al inicializar un grupo de conexiones.                                                                                                                                                                                                                                                 | -1 (específico del proveedor) |
| _tamañomáximodepiscina_      | Número máximo de conexiones que deben asignarse simultáneamente a un grupo de conexiones.                                                                                                                                                                                                                                     | -1 (específico del proveedor) |
| _Tamaño mínimo de piscina_   | Número mínimo de conexiones que deben asignarse a un grupo de conexiones.                                                                                                                                                                                                                                                     | -1 (específico del proveedor) |
| _maxIdleTime_                | Número de segundos que una conexión física debe permanecer sin usar en el grupo antes de que se cierre la conexión para un grupo de conexiones.                                                                                                                                                                               | -1 (específico del proveedor) |
| _maxDeclaraciones_           | El número total de sentencias que un grupo de conexiones debe mantener abiertas. Un valor de 0 indica que el almacenamiento en caché de sentencias está deshabilitado para un grupo de conexiones.                                                                                                                            | -1 (específico del proveedor) |
| _propiedades_                | _Se utiliza para especificar propiedades específicas del proveedor y propiedades de origen de datos_ menos comunes . Si se especifica una propiedad _de origen de datos_ en el elemento properties y también se especifica el elemento de anotación para dicha propiedad, el valor del elemento de anotación tiene prioridad. | \\{}                          |
| _loginTimeout_               | El tiempo máximo en segundos que esta fuente de datos esperará mientras intenta conectarse a una base de datos. Un valor de 0 especifica que el tiempo de espera es el tiempo de espera predeterminado del sistema, si existe; de ​​lo contrario, especifica que no hay tiempo de espera.                                     | 0                             |

Ejemplos:

```
@DataSourceDefinition(
    name="java:global/MyApp/MyDataSource",
    className="com.foobar.MyDataSource",
    portNumber=6689,
    serverName="myserver.com",
    user="lance",
    password="secret")
```

Usando una URL:

```
@DataSourceDefinition(
    name="java:global/MyApp/MyDataSource",
    className="org.apache.derby.jdbc.ClientDataSource",
    url="jdbc:derby://localhost:1527/myDB",
    user="lance",
    password="secret")
```

#### 3.17. jakarta.annotation.sql.DataSourceDefinitions

La anotación _DataSourceDefinition_ se utiliza para declarar un _DataSource_ contenedor . La anotación _DataSourceDefinitions_ actúa como un contenedor para múltiples declaraciones de fuentes de datos.

```
package jakarta.annotation.sql;

import java.lang.annotation.Target;
import java.lang.annotation.Retention;
import java.lang.annotation.ElementType;
import java.lang.annotation.RetentionPolicy;

@Target({ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
public @interface DataSourceDefinitions {
    DataSourceDefinition[] value ();
}
```

| Elemento | Descripción                                         | Por defecto |
| -------- | --------------------------------------------------- | ----------- |
| valor    | Contenedor para definir múltiples fuentes de datos. |             |

El siguiente ejemplo muestra el uso de la anotación definida anteriormente:

```
@DataSourceDefinitions ({
    @DataSourceDefinition(name="java:global/MyApp/MyDataSource",
        className="com.foobar.MyDataSource",
        portNumber=6689,
        serverName="myserver.com",
        user="lance",
        password="secret"),

    @DataSourceDefinition(name="java:global/MyApp/MyDataSource",
        className="org.apache.derby.jdbc.ClientDataSource",
        url="jdbc:derby://localhost:1527/myDB",
        user="lance",
        password="secret")
})
public class CalculatorBean {
    // ...
}
```

#### 3.18. jakarta.annotation.ManagedBean

La anotación _ManagedBean_ se utiliza para declarar un Jakarta Managed Bean, tal como se especifica en la especificación de _Jakarta Managed Beans_ . Los Jakarta Managed Beans son objetos gestionados por el contenedor que admiten un pequeño conjunto de servicios básicos, como la inyección de recursos, las devoluciones de llamada del ciclo de vida y los interceptores. Un Jakarta Managed Bean puede tener opcionalmente un nombre, una _cadena de texto_ especificada mediante el elemento _value_ .

```
package jakarta.annotation;

import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

@Target(TYPE)
@Retention(RUNTIME)
public @interface ManagedBean {
    boolean value() default "";
}
```

| Elemento | Descripción                     | Por defecto |
| -------- | ------------------------------- | ----------- |
| valor    | Nombre del Jakarta Managed Bean | ""          |

Ejemplos:

```
@ManagedBean("cart")
public class ShoppingCart {
    // ...
}
```

### 4. Referencias

JSR 175: Un sistema de metadatos para el lenguaje de programación Java. [http://jcp.org/en/jsr/detail?id=175](http://jcp.org/en/jsr/detail?id=175)

Plataforma 9 de Yakarta EE (Yakarta EE). [https://jakarta.ee/specifications/platform/9/](https://jakarta.ee/specifications/platform/9/)

Plataforma Java 2, Edición Estándar, v5.0 (J2SE). [https://www.oracle.com/java/technologies/javase/j2se-v50.html](https://www.oracle.com/java/technologies/javase/j2se-v50.html)

Frijoles empresariales de Yakarta, v4.0. [https://jakarta.ee/specifications/enterprise-beans/4.0](https://jakarta.ee/specifications/enterprise-beans/4.0)

Interceptores de Yakarta, 2.0. [https://jakarta.ee/specifications/interceptors/2.0/](https://jakarta.ee/specifications/interceptors/2.0/)

Jakarta Managed Beans. [https://jakarta.ee/specifications/managedbeans/2.0/](https://jakarta.ee/specifications/managedbeans/2.0/)

RFC 2119. [http://www.faqs.org/rfcs/rfc2119.html](http://www.faqs.org/rfcs/rfc2119.html)

## El concepto de Java Annotations y su funcionamiento

Todos usamos en el día a día **Java Annotations** .Sin embargo no siempre entendemos como el lenguaje Java las procesa. Es decir estamos **más que acostumbrados a usar @Ejb o @Entity** para la capa de persistencia o para la gestión de servicios . Ahora bien **¿Cómo son procesadas o cómo son construidas?**. Vamos a ver un ejemplo sencillo de crear una anotación y procesarla con Java. El primer paso es definir la anotación con las propiedades que dispone.

```
```

### Java Annotations y Anotaciones

Lo primero que nos sorprend**e es que las propias anotaciones Java llevan aplicadas anotaciones.** Podemos ver @Target y @Retention. @Target nos indica en que lugares se puede aplicar **esta anotación** . En nuestro caso tanto en clases como en propiedades (Type,Field).La anotacion **Retention  valora si la anotación se chequea en tiempo de ejecucion.**&#x55;na vez definido esto usamos @interface  y le asignamos un nombre. **El último paso es añadir propiedades a la anotación por si permite parametrizaciones.**

<figure><img src="https://www.arquitecturajava.com/wp-content/uploads/javaanotationdeclaracion-300x137.png" alt="" height="137" width="300"><figcaption></figcaption></figure>

En nuestro caso la anotación permite un parámetro de mayusculas true/false. Vamos a ver ahora como se aplica la anotación a una clase normal como es la clase Libro.

```
```

Hemos aplicado la anotación sobre una clase . Nuestra anotación nos informa si tenemos que procesar los objetos e imprimir la información en mayusculas o minúsculas por pantalla. Nos queda construir un programa Java que sea capaz de procesar las anotaciones . Para ello haremos uso del [API de Reflection](https://www.arquitecturajava.com/el-concepto-java-reflection/). Veamos el código:

```
```

El código es complejo de entender pero vamos a ver si podemos explicarlo paso a paso

1. Recorremos la lista de Objetos
2. Por cada Objeto leemos las propiedades (campos) que tiene “getDeclaredFields()”
3. El siguiente paso es comprobar si el campo dispone de la anotaccion Imprimible getAnnotation(Imprimible.class)
4. Si esa anotacion existe , comprobamos si la propiedad mayuscula esta a true o false
5. Imprimimos por consola los datos

Un diagrama lo deja un poco más claro:

<figure><img src="https://www.arquitecturajava.com/wp-content/uploads/javaannotations.png" alt="" height="439" width="738"><figcaption></figcaption></figure>

Por último nos queda ejecutar e imprimir la información en pantalla:

<figure><img src="https://www.arquitecturajava.com/wp-content/uploads/javannotationsresultado.jpeg" alt="" height="109" width="128"><figcaption></figcaption></figure>

Hemos creado nuestras propias Java Annotations. Este tipo de enfoque puede ser útil cuando queremos diseñar nuestros propios frameworks.



{% file src="../.gitbook/assets/Java Override y encapsulación.pdf" %}

{% file src="../.gitbook/assets/Java Generic Repository y JPA.pdf" %}

{% file src="../.gitbook/assets/Java Diamond Operator y Genéricos.pdf" %}
