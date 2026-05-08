# Internacionalización de Java (i18n): traduzca su aplicación/sitio web Java.

La internacionalización se ha convertido en un [método invaluable](https://lokalise.com/blog/customer-service-language/) para captar la atención de los usuarios y brindarles una experiencia fluida en el mundo globalizado actual. Al adaptar tu aplicación Java para que admita varios idiomas y matices culturales, la haces accesible a usuarios de diferentes regiones, garantizando que se sientan como en casa. En este artículo, exploraremos cómo la internacionalización de Java puede ayudarte a traducir tus aplicaciones o sitios web de manera efectiva y a crear software que sea compatible con audiencias diversas con facilidad.

* [Internacionalización en Java](https://lokalise.com/blog/java-internationalization-learn-the-basics/#internationalization-in-java)
  * [Compatibilidad con la internacionalización de Java](https://lokalise.com/blog/java-internationalization-learn-the-basics/#support-for-java-internationalization)
  * [Reglas a seguir](https://lokalise.com/blog/java-internationalization-learn-the-basics/#rules-to-follow)
    * [Reducción de la lista de ubicaciones](https://lokalise.com/blog/java-internationalization-learn-the-basics/#narrowing-down-locales)
* [Traducciones sencillas en Java](https://lokalise.com/blog/java-internationalization-learn-the-basics/#simple-translations-in-java)
  * [Crear una nueva aplicación Java](https://lokalise.com/blog/java-internationalization-learn-the-basics/#create-a-new-java-application)
  * [Crea un paquete de recursos](https://lokalise.com/blog/java-internationalization-learn-the-basics/#create-a-resource-bundle)
    * [Recursos en formato de archivo de propiedad](https://lokalise.com/blog/java-internationalization-learn-the-basics/#resources-in-property-file-form)
    * [Recursos en formato de clase Java](https://lokalise.com/blog/java-internationalization-learn-the-basics/#resources-in-java-class-form)
  * [Agregar más recursos](https://lokalise.com/blog/java-internationalization-learn-the-basics/#add-more-resources)
  * [Agregue algunos objetos de clase de localización](https://lokalise.com/blog/java-internationalization-learn-the-basics/#add-some-locale-class-objects)
  * [Utilice la clase ResourceBundle.](https://lokalise.com/blog/java-internationalization-learn-the-basics/#use-resourcebundle-class)
    * [Gestión de ubicaciones faltantes](https://lokalise.com/blog/java-internationalization-learn-the-basics/#handling-missing-locales)
* [Cambiar entre ubicaciones](https://lokalise.com/blog/java-internationalization-learn-the-basics/#switching-between-locales)
  * [Requisitos previos](https://lokalise.com/blog/java-internationalization-learn-the-basics/#prerequisites)
  * [Configurar el proyecto](https://lokalise.com/blog/java-internationalization-learn-the-basics/#set-up-the-project)
  * [Agregar componentes de la interfaz gráfica de usuario](https://lokalise.com/blog/java-internationalization-learn-the-basics/#add-gui-components)
  * [Agregar recursos de idioma](https://lokalise.com/blog/java-internationalization-learn-the-basics/#add-language-resources)
  * [Codifique la funcionalidad del botón de interruptor.](https://lokalise.com/blog/java-internationalization-learn-the-basics/#code-the-switch-button-functionality)
* [Algunas otras características de internacionalización de Java](https://lokalise.com/blog/java-internationalization-learn-the-basics/#a-few-other-java-internationalization-features)
  * [Pluralización](https://lokalise.com/blog/java-internationalization-learn-the-basics/#pluralization)
    * [Uso de ChoiceFormat para la pluralización](https://lokalise.com/blog/java-internationalization-learn-the-basics/#using-choiceformat-for-pluralization)
    * [Recuperación de mensajes pluralizados](https://lokalise.com/blog/java-internationalization-learn-the-basics/#retrieving-pluralized-messages)
    * [Consideraciones para otros idiomas](https://lokalise.com/blog/java-internationalization-learn-the-basics/#considerations-for-other-languages)
    * [Uso de ICU MessageFormat para la pluralización avanzada](https://lokalise.com/blog/java-internationalization-learn-the-basics/#using-icu-messageformat-for-advanced-pluralization)
    * [Configurando ICU4J](https://lokalise.com/blog/java-internationalization-learn-the-basics/#setting-up-icu4j)
    * [Uso de ICU MessageFormat para la pluralización](https://lokalise.com/blog/java-internationalization-learn-the-basics/#using-icu-messageformat-for-pluralization)
    * [Agregar pluralización específica del idioma](https://lokalise.com/blog/java-internationalization-learn-the-basics/#adding-language-specific-pluralization)
    * [Por qué la UCI es mejor para la pluralización](https://lokalise.com/blog/java-internationalization-learn-the-basics/#why-icu-is-better-for-pluralization)
  * [Fecha y hora](https://lokalise.com/blog/java-internationalization-learn-the-basics/#date-and-time)
    * [Usando getDateTimeInstance](https://lokalise.com/blog/java-internationalization-learn-the-basics/#using-getdatetimeinstance)
    * [Uso del formateador de fecha y hora](https://lokalise.com/blog/java-internationalization-learn-the-basics/#using-datetimeformatter)
  * [Formato de números y moneda](https://lokalise.com/blog/java-internationalization-learn-the-basics/#formatting-numbers-and-currency)
  * [Errores y soluciones alternativas en la internacionalización de Java.](https://lokalise.com/blog/java-internationalization-learn-the-basics/#errors-and-fallbacks-in-java-internationalization)
    * [Gestión de recursos faltantes](https://lokalise.com/blog/java-internationalization-learn-the-basics/#handling-missing-resources)
    * [Cómo solucionar errores de API](https://lokalise.com/blog/java-internationalization-learn-the-basics/#dealing-with-api-errors)
    * [Buenas prácticas para el manejo de errores y mecanismos de reserva.](https://lokalise.com/blog/java-internationalization-learn-the-basics/#best-practices-for-error-handling-and-fallbacks)
* [Utilice Lokalise para la internacionalización de Java.](https://lokalise.com/blog/java-internationalization-learn-the-basics/#use-lokalise-for-java-internationalization)
  * [¿Por qué Lokalise?](https://lokalise.com/blog/java-internationalization-learn-the-basics/#why-lokalise)
  * [Primeros pasos con Lokalise](https://lokalise.com/blog/java-internationalization-learn-the-basics/#getting-started-with-lokalise)
  * [Más recursos](https://lokalise.com/blog/java-internationalization-learn-the-basics/#more-resources)
* [Conozca la API de traducción en la nube](https://lokalise.com/blog/java-internationalization-learn-the-basics/#meet-cloud-translation-api)
  * [Crear proyecto de Google Cloud](https://lokalise.com/blog/java-internationalization-learn-the-basics/#create-google-cloud-project)
  * [Habilitar la API de traducción de Google Cloud](https://lokalise.com/blog/java-internationalization-learn-the-basics/#enable-google-cloud-translation-api)
  * [Configurar credenciales](https://lokalise.com/blog/java-internationalization-learn-the-basics/#set-up-credentials)
* [Aplicación sencilla con API de traducción en la nube](https://lokalise.com/blog/java-internationalization-learn-the-basics/#simple-app-with-cloud-translation-api)
  * [Crea un proyecto Maven](https://lokalise.com/blog/java-internationalization-learn-the-basics/#create-a-maven-project)
  * [Agregar dependencias al proyecto](https://lokalise.com/blog/java-internationalization-learn-the-basics/#add-dependencies-to-project)
  * [Clase de traductor](https://lokalise.com/blog/java-internationalization-learn-the-basics/#translator-class)
    * [Cómo funciona](https://lokalise.com/blog/java-internationalization-learn-the-basics/#how-it-works)
    * [Producción](https://lokalise.com/blog/java-internationalization-learn-the-basics/#output)
    * [Idiomas compatibles](https://lokalise.com/blog/java-internationalization-learn-the-basics/#supported-languages)
* [Conclusiones sobre la internacionalización de Java](https://lokalise.com/blog/java-internationalization-learn-the-basics/#conclusions-on-java-i18n)
* [Lecturas adicionales](https://lokalise.com/blog/java-internationalization-learn-the-basics/#further-reading)

_Un agradecimiento especial a Anton Malich por sus aportaciones y por revisar el código fuente._

### Internacionalización en Java <a href="#internationalization-in-java" id="internationalization-in-java"></a>

Tienes una idea interesante para una aplicación o sitio web Java, o quizás gestionas una aplicación Java ya consolidada en tu trabajo. Pero, ¿qué ocurre cuando tu aplicación necesita ser compatible con varios idiomas? Debe funcionar a la perfección, no solo en inglés, sino también en otros idiomas para llegar a un público global, posiblemente con la ayuda de una [biblioteca de traducción JavaScript](https://lokalise.com/blog/comparing-libraries-translating-js-apps/) .

Ahí es donde entra en juego la internacionalización de Java.

#### Compatibilidad con la internacionalización de Java <a href="#support-for-java-internationalization" id="support-for-java-internationalization"></a>

En lo que respecta a la localización de software y la compatibilidad con diferentes idiomas en Java, es fundamental comprender tres conceptos clave. Estos elementos permiten adaptar las aplicaciones a diferentes regiones e idiomas de forma eficaz:

1. [**Clase Locale**](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html) : Objetos que representan las regiones geográficas, políticas y culturales específicas a las que planea brindar soporte.
2. **Recursos** : Datos específicos de la configuración regional almacenados en forma de clases o archivos de propiedades.
3. [**Clase ResourceBundle**](https://docs.oracle.com/javase/8/docs/api/java/util/ResourceBundle.html) : Objetos utilizados para obtener datos para las configuraciones regionales relevantes de los recursos apropiados.

Estas clases están integradas en el `java.util`paquete, lo que simplifica la implementación de la internacionalización de Java en su aplicación web o software.

#### Reglas a seguir <a href="#rules-to-follow" id="rules-to-follow"></a>

Al agregar recursos lingüísticos, asegúrese de seguir estas reglas:

* **Ubicación de los archivos de recursos** : Todos los archivos de recursos deben residir en el mismo paquete.
* **Convención de nomenclatura** : Todos los archivos de recursos deben compartir un nombre base común. Este nombre base es fundamental y se utilizará en todo el código. Puedes elegir el nombre que prefieras.

Por ejemplo:

* El recurso predeterminado debe usar solo el nombre base:
  * `bundle.properties`o`Bundle.java`
* Los archivos de propiedades adicionales deben seguir este patrón:
  * `base name _ language suffix`
    * Ejemplo: `bundle_fr.properties`o`Bundle_fr.java`

**Reducción de la lista de ubicaciones**

Si necesita dirigirse a un país específico dentro de un idioma, puede agregar más archivos de recursos utilizando un sufijo de país. Por ejemplo:

* `base name _ language suffix _ country suffix`
  * Ejemplo: `bundle_en_US.properties`o`Bundle_en_US.java`

Para obtener aún más detalles, puede incluir un sufijo de variante:

* `base name _ language suffix _ country suffix _ variant suffix`
  * Ejemplo: `bundle_th_TH_TH.properties`o`Bundle_th_TH_TH.java`

Siguiendo estas convenciones, te aseguras de que tu aplicación Java cumpla con las mejores prácticas de internacionalización, lo que facilita su adaptación a nuevas configuraciones regionales.

### Traducciones sencillas en Java <a href="#simple-translations-in-java" id="simple-translations-in-java"></a>

Para comprender cómo funciona la internacionalización en Java, vamos a crear un [ejemplo básico de localización](https://lokalise.com/blog/localization-examples/) utilizando las características que hemos comentado anteriormente.

#### Crear una nueva aplicación Java <a href="#create-a-new-java-application" id="create-a-new-java-application"></a>

Comience creando una nueva aplicación Java llamada `java-i18n`. Esta servirá como base para demostrar cómo implementar traducciones simples en Java.

#### Crea un paquete de recursos <a href="#create-a-resource-bundle" id="create-a-resource-bundle"></a>

El primer paso en la internacionalización de Java es agregar recursos de idioma. Estos recursos servirán de base para localizar su aplicación a varios idiomas.

**Recursos en formato de archivo de propiedad**

La forma más sencilla de almacenar datos de localización es mediante archivos de propiedades de Java. Estos archivos son gestionados por la `PropertyResourceBundle`clase y son ideales para la localización en Java.

1. **Cree el paquete de recursos** :\
   agregue un nuevo `res`paquete dentro de su paquete principal. Dentro de él, cree un `bundle.properties`archivo.
2. **Defina pares clave-valor** :\
   En el archivo de propiedades, incluya las palabras o frases que se van a internacionalizar en formato clave-valor:

```
hello=Hello
welcome=Welcome to my app
ok=OK
cancel=Cancel
tryagain=Please try again
```

1. Aquí `bundle`está el nombre base para el archivo de recursos.
2. Este `bundle.properties`archivo actúa como archivo de recursos predeterminado y se utiliza cuando no se encuentra ningún archivo específico de la configuración regional.

**Ventajas** :

* La actualización de los archivos de recursos no requiere recompilación, lo que simplifica el mantenimiento.

**Limitaciones** :

* Los valores de los recursos están restringidos a cadenas de texto.

**Recursos en formato de clase Java**

Como alternativa, puedes crear recursos extendiendo la `ListResourceBundle`clase abstracta. Este enfoque te permite usar objetos más complejos como valores de los recursos.

En el `res`paquete, crea una `Bundle`clase que extienda la `ListResourceBundle`clase. Sobrescribe el `getContents`método:

1. &#x20;

```
package res;

import java.util.ListResourceBundle;

public class Bundle extends ListResourceBundle {
    @Override
    protected Object[][] getContents() {
        return new Object[][] {
                {"hello", "Hello"},
                {"ourfeatures", new String[] {
                    "Collaborative Translation", 
                    "Localization Workflow Management", 
                    "Localization Process Automation"
                }}
        };
    }
}
```

**Beneficios** :

* Admite cualquier tipo de objeto como valor de recurso.
* Reduce la sobrecarga y mejora la recolección de basura en comparación con los archivos de propiedades serializados.

#### Agregar más recursos <a href="#add-more-resources" id="add-more-resources"></a>

Para localizar tu aplicación para usuarios de habla italiana, añade otro archivo de propiedades con las mismas claves, pero con las traducciones al italiano como valores.

**Cree un nuevo archivo de propiedades** . Agregue un `bundle_it_IT.properties`archivo en el mismo paquete con el siguiente contenido:

1. &#x20;

```
hello=Ciao
welcome=Benvenuti nella mia app
ok=OK
cancel=Annulla
tryagain=Per favore riprova
```

**Como alternativa, cree una clase de recurso** . También puede usar una `Bundle_it_IT`clase:

```
package res;

import java.util.ListResourceBundle;

public class Bundle_it_IT extends ListResourceBundle {
    @Override
    protected Object[][] getContents() {
        return new Object[][] {
                {"hello", "Ciao"},
                {"ourfeatures", new String[] {"Traduzione Collaborativa", "Gestione del flusso di lavoro di localizzazione", "Automazione del processo di localizzazione"}}
        };
    }
}
```

Estos recursos, en conjunto, forman un **paquete de recursos** , que es esencial para la traducción de Java y la internacionalización [(i18n)](https://lokalise.com/blog/what-is-i18n/) .

#### Agregue algunos objetos de clase de localización <a href="#add-some-locale-class-objects" id="add-some-locale-class-objects"></a>

Para representar regiones geográficas, políticas o culturales específicas, es necesario crear `Locale`objetos. Por ejemplo, en la `main`metodología de su `java-i18n`proyecto, puede definir un objeto `Locale`para los hablantes de italiano en Italia:

```
Locale locale_it_IT = new Locale("it", "IT");
```

Si encuentra advertencias de obsolescencia, utilice el método actualizado:

```
Locale locale_it_IT = Locale.of("it", "IT");
```

Para obtener una lista completa de las configuraciones regionales compatibles con Java 8, [consulte la documentación oficial](https://www.oracle.com/java/technologies/javase/jdk8-jre8-suported-locales.html) .

#### Utilice la clase ResourceBundle. <a href="#use-resourcebundle-class" id="use-resourcebundle-class"></a>

Ahora que hemos creado nuestro paquete de recursos, vamos a obtener datos específicos del idioma utilizando la `ResourceBundle`clase. Para ello, llama al `ResourceBundle.getBundle`método estático, proporcionando como primer parámetro el nombre de clase completo de la clase base.

Por ejemplo, para recuperar datos para la `it-IT`configuración regional italiana ( ):

```
ResourceBundle resourceBundle = ResourceBundle.getBundle("res.bundle", locale_it_IT);

System.out.println(resourceBundle.getString("welcome"));
```

Esto permitirá localizar e imprimir correctamente el valor específico correspondiente al `it-IT`código de país definido en su paquete de recursos.

**Gestión de ubicaciones faltantes**

Pero, ¿qué sucede si solicitas datos para una configuración regional que no está presente en tu paquete de recursos? Por ejemplo:

```
Locale locale_ru_RU = new Locale("ru", "RU");

ResourceBundle resourceBundle = ResourceBundle.getBundle("res.bundle", locale_ru_RU);

System.out.println(resourceBundle.getString("welcome"));
```

En este caso, el programa recurrirá al archivo de recursos predeterminado ( `bundle.properties`) e imprimirá el valor de la `en-US`configuración regional, ya que es el recurso predeterminado. Este comportamiento es coherente con el mecanismo de internacionalización de Java, lo que garantiza que su aplicación siempre proporcione una respuesta, incluso cuando la configuración regional exacta no esté disponible.

### Cambiar entre ubicaciones <a href="#switching-between-locales" id="switching-between-locales"></a>

Vamos a crear una aplicación GUI sencilla para visualizar cómo funciona el cambio de idioma en una aplicación de internacionalización (i18n) de Java. Usando Java Swing, diseñaremos una GUI que utilice los recursos de idioma que creamos anteriormente. La aplicación incluirá un botón "Cambiar" para alternar el idioma de la aplicación cada vez que se pulse.

#### Requisitos previos <a href="#prerequisites" id="prerequisites"></a>

Antes de continuar, asegúrese de tener las siguientes herramientas:

* **Entorno de desarrollo integrado NetBeans** : Utilizaré NetBeans IDE 11.3 para el desarrollo de software con interfaz gráfica de usuario (GUI) en Java.
* **Maven** : Para gestionar las dependencias del proyecto.

#### Configurar el proyecto <a href="#set-up-the-project" id="set-up-the-project"></a>

1. **Crea un nuevo proyecto Maven** :\
   Nombra el proyecto `java-i18n-gui`.
2. **Configurar el paquete GUI** :\
   Añadir un `gui`paquete al proyecto.
3. **Crear un formulario Swing** :\
   Dentro del `gui`paquete, cree un nuevo `JFrame`formulario llamado `SwitchLang`.

#### Agregar componentes de la interfaz gráfica de usuario <a href="#add-gui-components" id="add-gui-components"></a>

Para construir la interfaz de usuario de nuestra aplicación de cambio de idioma, agregaremos los siguientes componentes al `SwitchLang`formulario:

1. **Componentes de JLabel** :
   * `jLabelHello`: Muestra un saludo localizado.
   * `jLabelWelcome`Muestra un mensaje de bienvenida localizado.
2. **Componentes de JButton** :
   * `jButtonOk`: Representa un botón "Aceptar" con texto localizado.
   * `jButtonCancel`: Representa un botón de "Cancelar" con texto localizado
   * `jButtonSwitchLang`: Un botón con la etiqueta “Cambiar” que, al pulsarlo, alterna el idioma de la aplicación.

#### Agregar recursos de idioma <a href="#add-language-resources" id="add-language-resources"></a>

Para sincronizar el `SwitchLang`formulario JFrame con los recursos localizados, siga estos pasos:

1. **Configurar la carpeta de recursos** :
   * Siguiendo [las convenciones de Maven](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html) , haga clic en la pestaña **Archivos** en NetBeans.
   * Crea una `resources`carpeta dentro del `src/main/`directorio de tu proyecto.
   * Maven lo marcará automáticamente `src/main/resources`como un directorio de recursos durante la siguiente compilación.
2. **Cree el archivo de recursos predeterminado** :
   * Dentro de la `resources`carpeta, crea un `bundle.properties`archivo.
   * Este archivo actuará como archivo de recursos predeterminado para su paquete de recursos.
3. **Vincula el archivo de recursos al formulario** :
   * Abra el `SwitchLang`formulario desde la ventana Proyectos y cambie a la pestaña Diseño.
   * En la sección Navegador (esquina inferior izquierda), haga clic en el nodo raíz etiquetado como "Form SwitchLang".
   * En la ventana Propiedades (a la derecha), localice el campo Paquete de propiedades.
     * Busque `src/main/resources`y seleccione el `bundle.properties`archivo.
   * Compruebe la opción de internacionalización automática en la misma ventana.
4. **Defina los valores predeterminados de los recursos** :\
   Abra el `bundle.properties`archivo y reemplace su contenido con lo siguiente:

```
SwitchLang.jLabelHello.text=Hello
SwitchLang.jLabelWelcome.text=Welcome to my app
SwitchLang.jButtonOk.text=OK
SwitchLang.jButtonCancel.text=Cancel
SwitchLang.jButtonSwitchLang.text=Switch
```

Estas claves corresponden a los elementos Swing creados anteriormente y definen su texto predeterminado (en-US).

**Agregar un archivo de configuración regional italiana** :

* Crea un nuevo archivo con el nombre especificado `bundle_it_IT.properties`en la `resources`carpeta.
* Agregue el siguiente contenido:

```
SwitchLang.jLabelHello.text=Ciao
SwitchLang.jLabelWelcome.text=Benvenuti nella mia app
SwitchLang.jButtonOk.text=OK
SwitchLang.jButtonCancel.text=Annulla
SwitchLang.jButtonSwitchLang.text=Interruttore
```

Este archivo define el texto para la `it-IT`configuración regional.

Ahora, el paquete de recursos está sincronizado con los `SwitchLang`elementos del formulario JFrame y la aplicación está lista para mostrar texto específico de la configuración regional.

#### Codifique la funcionalidad del botón de interruptor. <a href="#code-the-switch-button-functionality" id="code-the-switch-button-functionality"></a>

Ahora, vamos a implementar la funcionalidad del `jButtonSwitchLang`botón para permitir al usuario cambiar la configuración regional de la aplicación a italiano.

**Crear el método de acción** :

* Haz doble clic en el `jButtonSwitchLang`botón del **Editor** .
* Esto creará un `jButtonSwitchLangActionPerformed`método donde podrá definir el comportamiento que se activa al presionar el botón.

**Recuperar el paquete de recursos de la configuración regional italiana** :\
Dentro del `jButtonSwitchLangActionPerformed`método, agregue el siguiente código para recuperar el paquete de recursos para la `it-IT`configuración regional:

1. &#x20;

```
Locale locale_it_IT = new Locale("it", "IT");
ResourceBundle resourceBundleIT = ResourceBundle.getBundle("bundle", locale_it_IT);
```

Asegúrese de que se importen las clases necesarias ( `Locale`y `ResourceBundle`) del `java.util`paquete.

**Actualizar el texto de los elementos Swing** :\
Utilice el paquete de recursos para actualizar el texto de sus componentes Swing:

```
jLabelHello.setText(resourceBundleIT.getString("SwitchLang.jLabelHello.text"));
jLabelWelcome.setText(resourceBundleIT.getString("SwitchLang.jLabelWelcome.text"));
jButtonOk.setText(resourceBundleIT.getString("SwitchLang.jButtonOk.text"));
jButtonCancel.setText(resourceBundleIT.getString("SwitchLang.jButtonCancel.text"));
jButtonSwitchLang.setText(resourceBundleIT.getString("SwitchLang.jButtonSwitchLang.text"));
```

Prueba la aplicación:

* Ejecuta la `java-i18n-gui`aplicación.
* Haz clic en el botón **Cambiar** para comprobar que se cambia la configuración regional y que la interfaz de usuario se actualiza para mostrar el texto en italiano.

### Algunas otras características de internacionalización de Java <a href="#a-few-other-java-internationalization-features" id="a-few-other-java-internationalization-features"></a>

Además de los paquetes de recursos y las configuraciones regionales, Java ofrece funciones adicionales para facilitar las tareas de localización. Exploremos algunas de estas funciones.

#### Pluralización <a href="#pluralization" id="pluralization"></a>

El uso correcto del plural es a menudo necesario al tratar con textos internacionalizados. Por ejemplo, consideremos cómo representar el número de manzanas en inglés:

* `0 apples`
* `1 apple`
* `2 apples`

Un método sencillo para manejar esto en Java podría ser el siguiente:

```
public static String getAppleCountMsg(int count) {
    if (count == 1) {
        return "1 apple";
    } else if (count == 0 || count > 1) {
        return count + " apples";
    } else {
        return "You don't count apples in minus numbers! Please input a whole number";
    }
}
```

Si bien este enfoque es funcional, puede volverse rápidamente tedioso y propenso a errores, especialmente al trabajar con varios idiomas.

**Uso de ChoiceFormat para la pluralización**

La clase de Java `ChoiceFormat`simplifica la pluralización al reducir la complejidad y hacer que el código sea más fácil de mantener. Así es como se puede usar:

```
public static ChoiceFormat getAppleCountMsgChoiceFormat() {
    double[] minAppleCount = {0, 1, 2};
    String[] appleCountFormat = {"apples", "apple", "apples"};  
    return new ChoiceFormat(minAppleCount, appleCountFormat);
}
```

Aquí hay un desglose de los parámetros pasados ​​a `ChoiceFormat`:

1. **Intervalos (matriz doble)** :
   * `{0, 1, 2}`define los puntos de partida de los intervalos.
   * El intervalo `[0, 1)`corresponde a `"apples"`.
   * El intervalo `[1, 2)`corresponde a `"apple"`.
   * El intervalo `[2, ∞)`corresponde a `"apples"`.
2. **Cadenas (matriz de cadenas)** :
   * `{"apples", "apple", "apples"}`define para cada intervalo.

**Recuperación de mensajes pluralizados**

Una vez que tenga un `ChoiceFormat`objeto, podrá usarlo para formatear mensajes en función del recuento proporcionado:

```
public static String getAppleCountMsg(ChoiceFormat appleCountChoiceFormat, int count) {
    return count + " " + appleCountChoiceFormat.format(count); 
}
```

Ejemplo de uso:

```
ChoiceFormat appleCountChoiceFormat = getAppleCountMsgChoiceFormat();
System.out.println(getAppleCountMsg(appleCountChoiceFormat, 0)); // Output: "0 apples"
System.out.println(getAppleCountMsg(appleCountChoiceFormat, 1)); // Output: "1 apple"
System.out.println(getAppleCountMsg(appleCountChoiceFormat, 5)); // Output: "5 apples"
```

**Consideraciones para otros idiomas**

Es importante tener en cuenta que las reglas de pluralización varían entre idiomas. Por ejemplo:

* El inglés tiene dos formas plurales: singular y plural.
* Otros idiomas, como el árabe o el ruso, pueden tener reglas de pluralización más complejas.

Para tener en cuenta estas diferencias , deberá crear manualmente `ChoiceFormat`objetos separados para cada idioma compatible con su aplicación internacionalizada.

**Uso de ICU MessageFormat para la pluralización avanzada**

Si bien la `ChoiceFormat`clase en Java ayuda a gestionar la pluralización básica, puede resultar engorrosa al tratar con reglas de pluralización complejas en idiomas con múltiples formas plurales (por ejemplo, árabe, ruso). Para estos casos, la biblioteca [**ICU**](https://lokalise.com/blog/complete-guide-to-icu-message-format/) **MessageFormat** proporciona una solución robusta, compatible con las reglas de pluralización específicas de cada idioma definidas por el Unicode CLDR (Common Locale Data Repository).

**Configurando ICU4J**

Para usar ICU MessageFormat en tu aplicación Java, incluye la biblioteca ICU4J en tu proyecto. Para Maven, agrega la siguiente dependencia:

```
<dependency>
    <groupId>com.ibm.icu</groupId>
    <artifactId>icu4j</artifactId>
    <version>72.1</version>
</dependency>
```

Para Gradle:

```
implementation("com.ibm.icu:icu4j:72.1")
```

**Uso de ICU MessageFormat para la pluralización**

La `MessageFormat`clase ICU permite definir reglas de pluralización de forma dinámica según la configuración regional. Aquí tienes un ejemplo de cómo usarla para gestionar la pluralización en un mensaje sobre manzanas:

```
import com.ibm.icu.text.MessageFormat;
import java.util.Locale;

public class ICUPuralizationExample {
    public static void main(String[] args) {
        // Define the pluralization pattern
        String pattern = "{0, plural, one {# apple} other {# apples}}";

        // Create a MessageFormat instance for a specific locale
        MessageFormat messageFormat = new MessageFormat(pattern, Locale.ENGLISH);

        // Format pluralized messages
        System.out.println(messageFormat.format(new Object[]{1})); // Output: "1 apple"
        System.out.println(messageFormat.format(new Object[]{5})); // Output: "5 apples"
    }
}
```

**Agregar pluralización específica del idioma**

ICU MessageFormat maneja automáticamente las reglas específicas de cada idioma. Por ejemplo, el ruso utiliza formas distintas para 1, 2-4 y 5 o más. Lo mismo `MessageFormat`se puede adaptar para manejar la pluralización en ruso:

```
public class ICULocaleExample {
    public static void main(String[] args) {
        // Define the pluralization pattern
        String pattern = "{0, plural, one {# яблоко} few {# яблока} other {# яблок}}";

        // Create a MessageFormat instance for the Russian locale
        MessageFormat messageFormat = new MessageFormat(pattern, new Locale("ru", "RU"));

        // Format pluralized messages
        System.out.println(messageFormat.format(new Object[]{1})); // Output: "1 яблоко"
        System.out.println(messageFormat.format(new Object[]{3})); // Output: "3 яблока"
        System.out.println(messageFormat.format(new Object[]{5})); // Output: "5 яблок"
    }
}
```

En este ejemplo:

* La `one`regla se aplica a números singulares como `1`.
* La `few`regla se aplica a los números que terminan en `2, 3, or 4`(excluyendo del 12 al 14).
* La `other`regla se aplica a números como `0`, `5`, o cualquier cosa que no esté cubierta por las dos primeras reglas.

**Por qué la UCI es mejor para la pluralización**

1. **Adaptación al idioma** : Se adapta automáticamente a las reglas de pluralidad del idioma especificado.
2. **Facilidad de uso** : Permite definir reglas de pluralización complejas en un único patrón legible.
3. **Flexibilidad** : Admite no solo la pluralización, sino también el género y reglas de selección para una localización avanzada.

#### Fecha y hora <a href="#date-and-time" id="date-and-time"></a>

Gestionar los formatos de fecha y hora localizados es fundamental para la internacionalización de Java, especialmente en aplicaciones destinadas a usuarios de diversas regiones. Java proporciona una `DateFormat`clase que simplifica esta tarea.

**Usando`getDateTimeInstance`**

El `getDateTimeInstance`método de la `DateFormat`clase permite recuperar formatos de fecha y hora específicos de la configuración regional. Por ejemplo, así es como se puede obtener la fecha y hora actuales en formato **CORTO** para una configuración regional determinada:

```
public String getCurrentDateAndTime(Locale locale) {
    DateFormat dateFormat = DateFormat.getDateTimeInstance(DateFormat.SHORT,
                                                           DateFormat.SHORT, 
                                                           locale);
    return dateFormat.format(new Date());
}
```

Ejemplo de uso:

```
Locale locale_us = new Locale("en", "US");
Locale locale_fr = new Locale("fr", "FR");

System.out.println(getCurrentDateAndTime(locale_us)); // Output: 12/23/24, 4:30 PM
System.out.println(getCurrentDateAndTime(locale_fr)); // Output: 23/12/24, 16:30
```

Esto garantiza que la fecha y la hora se muestren con el formato adecuado para las diferentes regiones.

**Usando`DateTimeFormatter`**

Introducida en Java 8, la `DateTimeFormatter`clase del `java.time`paquete ofrece mayor flexibilidad y opciones de formato modernas. Funciona a la perfección `Locale`para crear formatos de fecha y hora específicos para cada configuración regional.

```
public String getLocalizedDateAndTime(Locale locale) {
    DateTimeFormatter formatter = DateTimeFormatter.ofLocalizedDateTime(FormatStyle.SHORT)
                                                    .withLocale(locale);
    return LocalDateTime.now().format(formatter);
}
```

Ejemplo de uso:

```
Locale locale_de = new Locale("de", "DE");
Locale locale_jp = new Locale("ja", "JP");

System.out.println(getLocalizedDateAndTime(locale_de)); // Output: 23.12.24, 16:30
System.out.println(getLocalizedDateAndTime(locale_jp)); // Output: 2024/12/23 16:30
```

#### Formato de números y moneda <a href="#formatting-numbers-and-currency" id="formatting-numbers-and-currency"></a>

Además de fechas y horas, la internacionalización de Java también incluye el formato de números y monedas. La `NumberFormat`clase se puede usar para formatear valores según la configuración regional.

Ejemplo:

```
public String getFormattedCurrency(Locale locale, double amount) {
    NumberFormat currencyFormat = NumberFormat.getCurrencyInstance(locale);
    return currencyFormat.format(amount);
}
```

Ejemplo de uso:

```
Locale locale_uk = new Locale("en", "GB");
Locale locale_in = new Locale("hi", "IN");

System.out.println(getFormattedCurrency(locale_uk, 1234.56)); // Output: £1,234.56
System.out.println(getFormattedCurrency(locale_in, 1234.56)); // Output: ₹1,234.56
```

Gracias a estas características, Java facilita el manejo del formato de fecha, hora y números en aplicaciones internacionalizadas. Estas herramientas son invaluables al localizar aplicaciones web, gestionar `HTTP requests`o desarrollar software para una audiencia global.

#### Errores y soluciones alternativas en la internacionalización de Java. <a href="#errors-and-fallbacks-in-java-internationalization" id="errors-and-fallbacks-in-java-internationalization"></a>

Pueden surgir errores en las aplicaciones internacionalizadas cuando faltan traducciones, no se admiten configuraciones regionales o los servicios externos (como la API de traducción de Google Cloud) no responden. Para garantizar la solidez de su aplicación Java, es fundamental implementar mecanismos de respaldo.

**Gestión de recursos faltantes**

Al usar `ResourceBundle`, la falta de un recurso o configuración regional puede provocar una excepción o un comportamiento indefinido. Para gestionar esto correctamente, Java recurre automáticamente al paquete de recursos predeterminado (por ejemplo, `bundle.properties`). Sin embargo, puede agregar lógica de reserva personalizada para garantizar un comportamiento adecuado.

**Ejemplo** : Agregar un mensaje alternativo para las traducciones faltantes:

```
import java.util.Locale;
import java.util.MissingResourceException;
import java.util.ResourceBundle;

public class TranslationFallbackExample {
    public static void main(String[] args) {
        Locale locale_ru = new Locale("ru", "RU"); // A locale without translations
        String key = "welcome";

        ResourceBundle resourceBundle;
        try {
            resourceBundle = ResourceBundle.getBundle("bundle", locale_ru);
            System.out.println(resourceBundle.getString(key));
        } catch (MissingResourceException e) {
            // Fallback to default message
            System.out.println("Translation not found. Default message: Welcome!");
        }
    }
}
```

Esto garantiza que la aplicación gestione correctamente los escenarios en los que falte o esté incompleto el paquete de recursos de una configuración regional específica.

**Cómo solucionar errores de API**

Al trabajar con API externas como la **API de traducción de Google Cloud** , los problemas de red o las interrupciones del servicio pueden afectar la funcionalidad. Implemente lógica de reintento o recurra a un mecanismo de traducción predeterminado para mantener una experiencia de usuario fluida.

**Ejemplo** : Lógica de reserva ante fallos de la API:

```
import com.google.cloud.translate.Translate;
import com.google.cloud.translate.TranslateOptions;
import com.google.cloud.translate.Translation;

public class ApiFallbackExample {
    public static void main(String[] args) {
        String textToTranslate = "Hello, world!";
        String translatedText;

        try {
            Translate translate = TranslateOptions.getDefaultInstance().getService();
            Translation translation = translate.translate(
                    textToTranslate,
                    Translate.TranslateOption.targetLanguage("es")
            );
            translatedText = translation.getTranslatedText();
        } catch (Exception e) {
            // Log the error and use a default translation
            System.err.println("Translation API failed: " + e.getMessage());
            translatedText = "Hola, mundo!"; // Fallback to a predefined translation
        }

        System.out.println(translatedText);
    }
}
```

**Buenas prácticas para el manejo de errores y mecanismos de reserva.**

1. **Utilice valores predeterminados significativos** :\
   Proporcione siempre un mensaje predeterminado adecuado en caso de que no haya traducciones disponibles. Esto garantiza que los usuarios puedan seguir entendiendo la interfaz de usuario.
2. **Registro de errores** :\
   Realice un seguimiento de las traducciones faltantes o las llamadas a la API fallidas utilizando un marco de registro (por ejemplo, SLF4J o Log4j). Esto ayuda a identificar deficiencias en la localización.
3. **Traducciones en caché** :\
   Almacena en caché el contenido traducido para minimizar la dependencia de las API externas durante problemas o interrupciones de la red.
4. **Validar los paquetes de recursos** :\
   Pruebe sus `ResourceBundle`archivos periódicamente para asegurarse de que existan todas las claves necesarias para cada configuración regional.
5. **Notificar a los usuarios de forma adecuada** :\
   si se utiliza un mecanismo de reserva, considere notificar a los usuarios con un mensaje sutil o un registro con fines de desarrollo.

### Utilice Lokalise para la internacionalización de Java. <a href="#use-lokalise-for-java-internationalization" id="use-lokalise-for-java-internationalization"></a>

Como se demuestra en nuestros ejemplos de traducción e internacionalización de Java, internacionalizar correctamente una aplicación Java puede ser una tarea compleja y que requiere mucho tiempo. Gestionar los paquetes de recursos, manejar la pluralización y formatear los datos localizados suele requerir un esfuerzo considerable. ¿Por qué no simplificar este proceso con un [sistema profesional de gestión de traducciones](https://lokalise.com/blog/translation-management-system/) como Lokalise?

#### ¿Por qué Lokalise? <a href="#why-lokalise" id="why-lokalise"></a>

Lokalise ofrece una plataforma integral para gestionar archivos de traducción y optimizar el flujo de trabajo de localización. Proporciona varias funciones para hacer que la internacionalización sea más eficiente:

* **Traducciones de Google** : Genera traducciones iniciales con facilidad.
* **Traducciones colaborativas** : Permiten que los equipos trabajen juntos en tiempo real.
* **Herramientas de control de calidad** : Asegúrese de que sus traducciones cumplan con altos estándares.
* **Soporte para la integración** : Intégrese sin problemas con diversos servicios y plataformas.
* **Gestión centralizada** : Gestiona todas las traducciones a través de un panel de control intuitivo.

Con Lokalise, podrá ahorrar tiempo y reducir la complejidad de gestionar la internacionalización de Java en sus aplicaciones web o proyectos de software.

#### Primeros pasos con Lokalise <a href="#getting-started-with-lokalise" id="getting-started-with-lokalise"></a>

Sigue estos sencillos pasos para empezar a usar Lokalise:

1. **Regístrate** para una prueba gratuita:\
   Crea una [cuenta gratuita](https://app.lokalise.com/signup) en Lokalise (no se requiere tarjeta de crédito).
2. **Iniciar sesión** :\
   Acceda a su panel de control de Lokalise.
3. **Crear un proyecto** :\
   Inicie un nuevo proyecto y asígnele el nombre que desee.
4. **Sube tus archivos de traducción** :\
   Importa tus archivos de traducción existentes (por ejemplo, `bundle.properties`en otros formatos). Edítalos según sea necesario directamente en Lokalise.
5. **Gestiona e implementa** :\
   utiliza las herramientas de Lokalise para perfeccionar tus traducciones y exportar los archivos actualizados a tu aplicación Java.

#### Más recursos <a href="#more-resources" id="more-resources"></a>

* [**Guía de inicio**](https://docs.lokalise.com/en/collections/652196-getting-started) : Explora tutoriales paso a paso que te ayudarán a comenzar tu experiencia con Lokalise.
* [**Documentación de la API de Lokalise**](https://developers.lokalise.com/reference/lokalise-rest-api#resource-getting-started) : Acceda a una lista completa de comandos REST para integrar y automatizar la gestión de traducciones en sus proyectos.

Al utilizar Lokalise, puede simplificar su flujo de trabajo, garantizar traducciones de alta calidad y centrarse en crear una aplicación Java excepcional para una audiencia global.

### Conozca la API de traducción en la nube <a href="#meet-cloud-translation-api" id="meet-cloud-translation-api"></a>

Como extra, veamos cómo integrar la funcionalidad de Google Translate en tu aplicación Java mediante la [API de traducción de Google Cloud](https://github.com/googleapis/google-api-java-client-services/tree/main/clients/google-api-services-translate/v3) . Esta API, proporcionada por Google Cloud Platform, te permite realizar traducciones de texto básicas con facilidad.

Antes de comenzar, asegúrese de que Maven esté instalado en su computadora, ya que será necesario para la gestión de dependencias.

#### Crear proyecto de Google Cloud <a href="#create-google-cloud-project" id="create-google-cloud-project"></a>

Si ya tienes un proyecto de Google Cloud, puedes omitir este paso y usarlo para tus traducciones. De lo contrario, consulta la [documentación de Google Cloud](https://cloud.google.com/resource-manager/docs/creating-managing-projects) para obtener instrucciones paso a paso sobre cómo crear un nuevo proyecto.

#### Habilitar la API de traducción de Google Cloud <a href="#enable-google-cloud-translation-api" id="enable-google-cloud-translation-api"></a>

Para empezar, habilita la **API de traducción en la nube** para tu proyecto:

1. Navegue a la [página principal de la API de traducción](https://console.cloud.google.com/apis/library/translate.googleapis.com) .
2. Selecciona tu proyecto de Google Cloud en el menú desplegable.
3. Haz clic en **Habilitar** para activar la API.

#### Configurar credenciales <a href="#set-up-credentials" id="set-up-credentials"></a>

Para establecer una comunicación segura entre la **API de Cloud Translation** y tu aplicación, debes configurar las credenciales. Encontrarás instrucciones detalladas en la [sección de Autenticación](https://cloud.google.com/docs/authentication/getting-started) de la documentación de Google Cloud. Sigue los pasos para generar una clave de cuenta de servicio y descargar el archivo de credenciales JSON.

### Aplicación sencilla con API de traducción en la nube <a href="#simple-app-with-cloud-translation-api" id="simple-app-with-cloud-translation-api"></a>

Vamos a crear una aplicación Java básica, llamada aplicación **Traductor** , para demostrar cómo realizar traducciones utilizando la biblioteca cliente Java de la **API de traducción en la nube** .

#### Crea un proyecto Maven <a href="#create-a-maven-project" id="create-a-maven-project"></a>

Comience generando un nuevo proyecto Maven utilizando el siguiente comando:

```
mvn archetype:generate -DgroupId=com.lokalise -DartifactId=translate -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

Esto crea un proyecto con un nombre que `translate`pertenece al `com.lokalise`grupo, siguiendo las convenciones de Maven.

#### Agregar dependencias al proyecto <a href="#add-dependencies-to-project" id="add-dependencies-to-project"></a>

Agregue la siguiente dependencia a su `pom.xml`archivo para incluir la [biblioteca cliente de Java](https://github.com/googleapis/java-translate) para la API de traducción de Google Cloud:

```
<dependency>
    <groupId>com.google.cloud</groupId>
    <artifactId>google-cloud-translate</artifactId>
    <version>2.28.0</version>
</dependency>
```

**Nota** : La versión de la dependencia mencionada anteriormente podría cambiar con el tiempo. Consulta el [repositorio central de Maven](https://mvnrepository.com/artifact/com.google.cloud/google-cloud-translate/) para asegurarte de que estás utilizando la última versión.

Si estás usando Gradle, agrega esta línea a tu `build.gradle`archivo:

```
implementation(“com.google.cloud:google-cloud-translate:2.28.0”)
```

#### Clase de traductor <a href="#translator-class" id="translator-class"></a>

Vamos a implementar la clase **Translator** para realizar traducciones de texto utilizando la API de traducción de Google Cloud. Este sencillo programa Java muestra cómo configurar el servicio de traducción, traducir texto y obtener el resultado traducido.

```
import com.google.cloud.translate.Translate;
import com.google.cloud.translate.TranslateOptions;
import com.google.cloud.translate.Translation;

public class Translator {
    public static void main(String[] args) {
        // Initialize Google Cloud Translation service
        Translate translate = TranslateOptions.getDefaultInstance().getService(); // 1

        // Text to translate
        String textToTranslate = "Localization in Java is fun";

        // Perform translation
        Translation translation = translate.translate(
                textToTranslate,
                Translate.TranslateOption.sourceLanguage("en"), // 2
                Translate.TranslateOption.targetLanguage("it")
        );

        // Retrieve and print the translated text
        String translatedText = translation.getTranslatedText();
        System.out.println(translatedText);
    }
}
```

**Cómo funciona**

1. **Inicialización del servicio de traducción** :\
   Este `TranslateOptions.getDefaultInstance().getService()`método inicializa el cliente de la API de traducción de Google Cloud. Utiliza las credenciales configuradas mediante la `GOOGLE_APPLICATION_CREDENTIALS`variable de entorno. Asegúrese de que esta variable apunte al archivo de clave JSON descargado durante el paso **de configuración de credenciales** .
2. **Especificar opciones de traducción** :
   * El `TranslateOption.sourceLanguage("en")`parámetro especifica el idioma de origen (inglés en este caso).
   * El `TranslateOption.sourceLanguage("it")`parámetro especifica el idioma de destino (italiano).
   * El parámetro de idioma de origen es opcional, ya que la API puede detectar los idiomas automáticamente. Sin embargo, es recomendable especificar el idioma de origen explícitamente para evitar malentendidos.
3. **Realización de la traducción** :\
   Este `translate.translate()`método procesa el texto de entrada y devuelve un `Translation`objeto que contiene el texto traducido.
4. **Recuperación del resultado** :\
   El `getTranslatedText()`método recupera la cadena traducida, que luego se imprime en la consola.

**Producción**

Al ejecutar el programa, se imprimirá la traducción al italiano del texto de entrada ( `textToTranslate`) en la consola. Por ejemplo:

```
La localizzazione in Java è divertente
```

**Idiomas compatibles**

La API de traducción de Google Cloud admite una amplia gama de idiomas. Consulta la [lista de idiomas compatibles](https://cloud.google.com/translate/docs/languages) para encontrar los códigos de idioma que puedes usar en el `TranslateOption.targetLanguage()`parámetro.

### Conclusiones sobre la internacionalización de Java <a href="#conclusions-on-java-i18n" id="conclusions-on-java-i18n"></a>

En este tutorial, exploramos los fundamentos de la internacionalización (i18n) y la localización de Java para tu aplicación o sitio web. Recorrimos el proceso de configuración de la API de traducción de Google Cloud, su integración en un proyecto Maven sencillo y la realización de traducciones de texto básicas mediante su biblioteca cliente de Java.

También profundizamos en la incorporación de soporte multilingüe a las aplicaciones Java, aprovechando las clases integradas de Java `Locale`. `ResourceBundle`Estas herramientas, junto con nuestros ejemplos prácticos, demostraron cómo gestionar las traducciones y crear aplicaciones internacionalizadas de forma eficaz.

Desde la implementación de la pluralización básica hasta la exploración de opciones avanzadas como ICU MessageFormat, ahora dispone de una base sólida para crear aplicaciones que satisfagan las necesidades de una audiencia global.

¡Con esto concluimos esta guía! Esperamos que este artículo te ayude a dar tus primeros pasos en la localización de Java. Hasta la próxima, ¡feliz programación y hasta pronto, colega desarrollador!
