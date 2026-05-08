# Uso de SOAP-to-REST para simplificar la migración e integración

### 1. ¿Qué es un Servicio Web? <a href="#id-1-que-es-un-servicio-web" id="id-1-que-es-un-servicio-web"></a>

Un servicio web es definido por el World Wide Web Consortium (W3C) como un sistema de software diseñado para soportar interacción interoperable entre máquinas a través de una red.

Un servicio web realiza tareas específicas o un conjunto de tareas y es descrito por una representación estándar en XML de un servicio llamada [Lenguaje de Descripción de Servicios Web (WSDL)](https://en.wikipedia.org/wiki/Web_Services_Description_Language). La descripción del servicio proporciona todos los detalles necesarios para interactuar con el servicio, incluyendo formatos de mensajes (utilizados para describir operaciones en detalle), protocolos de transporte y ubicación.

Otros sistemas interactuarían con el servicio web utilizando mensajes SOAP, generalmente mediante HTTP en conjunto con serialización XML y otros estándares relacionados con la web.

El diagrama de arquitectura de un servicio web (nota: el intermediario de servicios es opcional) es:

![arquitectura de servicios web](https://static.api7.ai/uploads/2023/03/02/33VH3pCZ_222063798-1fb4eb54-8e39-4a51-a2c4-579e86d76476.png?imageMogr2/format/webp)

\*Fuente de la imagen (licenciada bajo CC 3.0 BY-SA): [https://en.wikipedia.org/wiki/Web\_service](https://en.wikipedia.org/wiki/Web_service)

La interfaz WSDL oculta información detallada sobre cómo se implementa el servicio, de modo que el uso del servicio es independiente de la plataforma de hardware o software que lo implementa, así como del lenguaje de programación utilizado para escribirlo.

Las aplicaciones basadas en servicios web están débilmente acopladas, son orientadas a componentes y son implementaciones cruzadas de tecnología. Los servicios web pueden usarse individualmente o con otros servicios web para realizar agregaciones complejas o transacciones comerciales.

Los servicios web son las unidades de implementación de la [Arquitectura Orientada a Servicios (SOA)](https://en.wikipedia.org/wiki/Service-oriented_architecture), un método de diseño utilizado para reemplazar sistemas monolíticos. Un sistema extenso puede descomponerse en múltiples servicios web, que luego pueden combinarse en una gran caja negra para proporcionar lógica de negocio externamente. Los populares microservicios basados en contenedores son el reemplazo más reciente de los servicios web. Sin embargo, muchos sistemas heredados ya están basados en servicios web para su implementación y operación, por lo que la compatibilidad con estos sistemas sigue siendo un desafío a pesar de la rápida evolución de la tecnología.

#### WSDL (Lenguaje de Descripción de Servicios Web) <a href="#wsdl-lenguaje-de-descripcion-de-servicios-web" id="wsdl-lenguaje-de-descripcion-de-servicios-web"></a>

WSDL es una notación XML utilizada para describir servicios web. La definición de WSDL instruye a los clientes sobre cómo escribir solicitudes de servicios web y define la interfaz proporcionada por el proveedor del servicio web.

La definición de WSDL se divide en múltiples partes, especificando la interfaz lógica del servicio web y los detalles físicos. Los detalles físicos incluyen información de puntos finales, como el número de puerto HTTP, así como información de enlace que especifica cómo representar el contenido del mensaje SOAP y qué método de transporte utilizar.

![Representación de conceptos definidos por documentos WSDL 1.1 y WSDL 2.0.](https://static.api7.ai/uploads/2023/03/02/BmuJlexJ_222070518-d8ed70a6-f226-4f9b-8a81-6357027cc9f1.png?imageMogr2/format/webp)

_Fuente de la imagen (licenciada bajo CC 3.0 BY-SA):_ [_https://en.wikipedia.org/wiki/Web\_Services\_Description\_Language_](https://en.wikipedia.org/wiki/Web_Services_Description_Language)

* Un archivo WSDL puede contener múltiples servicios.
* Un servicio puede contener múltiples puertos.
* Un puerto define una dirección URL (que puede variar para cada puerto) y puede contener múltiples operaciones.
* Cada operación incluye un tipo de entrada y un tipo de salida.
* Los tipos definen la estructura del mensaje, incluyendo qué campos componen el mensaje, el tipo de datos de cada campo (que puede estar anidado) y el número de campos permitidos.

**1.1 ¿Qué es SOAP?**

SOAP es un formato de mensaje XML utilizado en interacciones de servicios web. Los mensajes SOAP generalmente se envían a través de HTTP o JMS, pero también se pueden utilizar otros protocolos de transporte. La definición de WSDL describe el uso de SOAP en un servicio web específico.

Hay dos versiones comúnmente utilizadas de SOAP: SOAP 1.1 y SOAP 1.2.

![Estructura de SOAP](https://static.api7.ai/uploads/2023/03/02/Urf4a4Jq_222080939-d4bd2517-39a8-423d-b3d7-41905b72073e.png?imageMogr2/format/webp)

_Fuente de la imagen (licenciada bajo CC 3.0 BY-SA):_ [_https://en.wikipedia.org/wiki/SOAP_](https://en.wikipedia.org/wiki/SOAP)

Un mensaje SOAP contiene las siguientes partes:

* Metadatos del encabezado, que generalmente están vacíos
* Cuerpo
  * El tipo de mensaje definido en WSDL
  * Además de respuestas exitosas, también hay mensajes de error estructurados para los tipos de respuesta.

Por ejemplo:

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header></SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getCountryResponse xmlns:ns2="http://spring.io/guides/gs-producing-web-service">
      <ns2:country>
        <ns2:name>Spain</ns2:name>
        <ns2:population>46704314</ns2:population>
        <ns2:capital>Madrid</ns2:capital>
        <ns2:currency>EUR</ns2:currency>
      </ns2:country>
    </ns2:getCountryResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 1.2 ¿Qué es REST? <a href="#id-12-que-es-rest" id="id-12-que-es-rest"></a>

Un servicio web es un concepto abstracto que puede implementarse de cualquier manera; por ejemplo, REST es un método de implementación popular.

[REST](https://en.wikipedia.org/wiki/Representational_state_transfer), abreviatura de Transferencia de Estado Representacional, literalmente significa transferencia de estado de la capa de presentación. Roy Thomas Fielding propuso el término REST en su tesis doctoral en el año 2000. En ese momento, Internet estaba en auge y existía la necesidad de una definición práctica para el desarrollo de software y la interacción con redes.

> Durante mucho tiempo, la investigación de software se ha centrado principalmente en la clasificación del diseño de software y la evolución de los métodos de diseño. Rara vez se evalúa objetivamente el impacto de diferentes elecciones de diseño en el comportamiento del sistema. Por otro lado, la investigación de redes se centra principalmente en los detalles del comportamiento de comunicación entre sistemas y cómo mejorar el rendimiento de mecanismos de comunicación específicos, a menudo pasando por alto que cambiar el estilo de interacción de la aplicación tiene un mayor impacto en el rendimiento general que cambiar el protocolo de interacción. Mi artículo tiene como objetivo comprender y evaluar el diseño de arquitectura de software de aplicaciones basadas en redes que sea funcional, tenga un buen rendimiento y sea adecuado para la comunicación, cumpliendo con los principios arquitectónicos.

Acceder a un sitio web representa un proceso de interacción entre el cliente y el servidor. Durante este proceso, deben producirse cambios en los datos y el estado. El protocolo HTTP no tiene estado, lo que significa que todos los estados se almacenan en el lado del servidor. Por lo tanto, si el cliente desea operar el servidor, debe utilizar algún medio para causar una "transferencia de estado" en el lado del servidor. Dado que esta transferencia se construye en la capa de presentación, se denomina "transferencia de estado de la capa de presentación".

Los cuatro principios básicos de REST son:

1. Usar verbos HTTP: GET, POST, PUT, DELETE;
2. Conexión sin estado, el servidor no debe almacenar demasiado contexto de estado; es decir, cada solicitud es independiente;
3. Establecer un URI para cada recurso;
4. Usar `x-www-form-urlencoded` o JSON como formato de datos;

Convertir SOAP a REST puede facilitar a los usuarios el acceso a servicios web tradicionales de manera RESTful, reduciendo el costo de desarrollo de clientes SOAP. Además, si puede adaptarse dinámicamente a cualquier servicio web con desarrollo de código cero, sería aún más perfecto.

La mayor ventaja de REST es que no tiene esquema, lo que facilita el desarrollo, y JSON tiene una mayor legibilidad y menor redundancia.

### 2. Implementaciones Tradicionales de Proxy SOAP-to-REST <a href="#id-2-implementaciones-tradicionales-de-proxy-soap-to-rest" id="id-2-implementaciones-tradicionales-de-proxy-soap-to-rest"></a>

#### 2.1 Conversión Manual de Plantillas <a href="#id-21-conversion-manual-de-plantillas" id="id-21-conversion-manual-de-plantillas"></a>

Este enfoque requiere proporcionar plantillas de conversión para la solicitud y la respuesta para cada operación del servicio web, lo que también es utilizado por muchos otros productos de puerta de enlace.

Podemos usar el plugin de transformación de cuerpo de APISIX para crear un proxy simple de SOAP a REST y probar este enfoque.

Por ejemplo, construimos una plantilla de solicitud en formato XML para la operación `getCountry` del servicio `CountriesPortService` en el archivo WSDL basado en la definición de tipo.

Aquí, llenamos el campo `name` en el JSON en el campo `name` en `getCountryRequest`.

```bash
req_template=$(cat <<EOF | awk '{gsub(/"/,"\\\"");};1' | awk '{$1=$1};1' | tr -d '\r\n'
<?xml version="1.0"?>
<soap-env:Envelope xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/">
 <soap-env:Body>
  <ns0:getCountryRequest xmlns:ns0="http://spring.io/guides/gs-producing-web-service">
   <ns0:name>{{_escape_xml(name)}}</ns0:name>
  </ns0:getCountryRequest>
 </soap-env:Body>
</soap-env:Envelope>
EOF
)
```

Se necesita proporcionar una plantilla de XML a JSON para la respuesta, lo que puede ser un poco más complejo (especialmente si se deben considerar diferencias de versión de SOAP). Esto se debe a que debe determinarse si la respuesta fue exitosa:

* Para una respuesta exitosa, los campos pueden mapearse directamente a JSON.
* Para una respuesta fallida (es decir, un fallo), se necesita una estructura JSON separada y debe determinarse si están presentes campos opcionales específicos.

```bash
rsp_template=$(cat <<EOF | awk '{gsub(/"/,"\\\"");};1' | awk '{$1=$1};1' | tr -d '\r\n'
{% if Envelope.Body.Fault == nil then %}
{
   "currency":"{{Envelope.Body.getCountryResponse.country.currency}}",
   "population":{{Envelope.Body.getCountryResponse.country.population}},
   "capital":"{{Envelope.Body.getCountryResponse.country.capital}}",
   "name":"{{Envelope.Body.getCountryResponse.country.name}}"
}
{% else %}
{
   "message":{*_escape_json(Envelope.Body.Fault.faultstring[1])*},
   "code":"{{Envelope.Body.Fault.faultcode}}"
   {% if Envelope.Body.Fault.faultactor ~= nil then %}
   , "actor":"{{Envelope.Body.Fault.faultactor}}"
   {% end %}
}
{% end %}
EOF
)
```

Configurar el enrutamiento de APISIX y realizar pruebas:

```bash
curl http://127.0.0.1:9180/apisix/admin/routes/1 \
    -H 'X-API-KEY: xxx' -X PUT -d '
{
    "methods": ["POST"],
    "uri": "/ws/getCountry",
    "plugins": {
        "body-transformer": {
            "request": {
                "template": "'"$req_template"'"
            },
            "response": {
                "template": "'"$rsp_template"'"
            }
        }
    },
    "upstream": {
        "type": "roundrobin",
        "nodes": {
            "localhost:8080": 1
        }
    }
}'
curl -s http://127.0.0.1:9080/ws/getCountry \
    -H 'content-type: application/json' \
    -X POST -d '{"name": "Spain"}' | jq
{
  "currency": "EUR",
  "population": 46704314,
  "capital": "Madrid",
  "name": "Spain"
}
# Respuesta de fallo
{
  "message": "Your name is required.",
  "code": "SOAP-ENV:Server"
}
```

Como podemos ver, este método requiere un entendimiento manual de la definición de cada operación en el archivo WSDL y la dirección del servicio web correspondiente a cada operación. Si el archivo WSDL es grande, contiene un gran número de operaciones y tiene definiciones de tipo anidadas complejas, este enfoque puede ser muy tedioso, difícil de depurar y propenso a errores.

#### 2.2 Apache Camel <a href="#id-22-apache-camel" id="id-22-apache-camel"></a>

[https://camel.apache.org/](https://camel.apache.org/)

Camel es un conocido marco de integración de Java utilizado para implementar tuberías de enrutamiento que convierten diferentes protocolos y lógica de negocio, y SOAP-to-REST es solo uno de sus casos de uso.

Usar Camel requiere descargar e importar el archivo WSDL, generar código stub para el cliente SOAP y escribir código Java:

* Definir puntos finales REST
* Definir rutas de conversión de protocolos, como cómo se mapean los campos JSON a los campos SOAP

Como ejemplo, consideremos un servicio web para la conversión de unidades de temperatura:

[https://apps.learnwebservices.com/services/tempconverter?wsdl](https://apps.learnwebservices.com/services/tempconverter?wsdl)

1. Generar código de cliente SOAP basado en el archivo WSDL usando Maven.

`cxf-codegen-plugin` generará puntos finales de cliente SOAP para que podamos acceder al servicio web.

```xml
<build>
  <plugins>
    <plugin>
      <groupId>org.apache.cxf</groupId>
      <artifactId>cxf-codegen-plugin</artifactId>
      <executions>
        <execution>
          <id>generate-sources</id>
          <phase>generate-sources</phase>
          <configuration>
            <wsdlOptions>
              <wsdlOption>
                <wsdl>src/main/resources/TempConverter.wsdl</wsdl>
              </wsdlOption>
            </wsdlOptions>
          </configuration>
          <goals>
            <goal>wsdl2java</goal>
          </goals>
        </execution>
      </executions>
    </plugin>
  </plugins>
</build>
```

2. Escribir el bean del cliente SOAP.

Nota: recordamos el nombre del bean como `cxfConvertTemp`, que se usará más adelante al definir las rutas de Camel.

```java
import com.learnwebservices.services.tempconverter.TempConverterEndpoint;
@Configuration
public class CxfBeans {
    @Value("${endpoint.wsdl}")
    private String SOAP_URL;
    @Bean(name = "cxfConvertTemp")
    public CxfEndpoint buildCxfEndpoint() {
        CxfEndpoint cxf = new CxfEndpoint();
        cxf.setAddress(SOAP_URL);
        cxf.setServiceClass(TempConverterEndpoint.class);
        return cxf;
    }
}
```

3. Escribir primero la ruta REST descendente.

Desde esta ruta, podemos ver que define URLs de estilo RESTful y sus definiciones de parámetros, y define el siguiente salto de ruta para cada URL. Por ejemplo, `/convert/celsius/to/fahrenheit/{num}` toma la última parte de la URL como un parámetro (de tipo double) y lo proporciona a la siguiente ruta `direct:celsius-to-fahrenheit`.

```java
rest("/convert")
    .get("/celsius/to/fahrenheit/{num}")
    .consumes("text/plain").produces("text/plain")
    .description("Convert a temperature in Celsius to Fahrenheit")
    .param().name("num").type(RestParamType.path).description("Temperature in Celsius").dataType("int").endParam()
    .to("direct:celsius-to-fahrenheit");
```

4. Finalmente, escribir la ruta SOAP ascendente y la transformación entre ascendente y descendente.

```java
from("direct:celsius-to-fahrenheit")
    .removeHeaders("CamelHttp*")
    .process(new Processor() {
        @Override
        public void process(Exchange exchange) throws Exception {
            // Inicializar la solicitud SOAP
            // Llenar el parámetro descendente num en el cuerpo, que es un tipo double simple.
            CelsiusToFahrenheitRequest c = new CelsiusToFahrenheitRequest();
            c.setTemperatureInCelsius(Double.valueOf(exchange.getIn().getHeader("num").toString()));
            exchange.getIn().setBody(c);
        }
    })
    // Especificar la operación SOAP y el espacio de nombres
    // Definido en el archivo application.properties
    .setHeader(CxfConstants.OPERATION_NAME, constant("{{endpoint.operation.celsius.to.fahrenheit}}"))
    .setHeader(CxfConstants.OPERATION_NAMESPACE, constant("{{endpoint.namespace}}"))
    // Enviar el paquete usando el bean de cliente SOAP generado por WSDL.
    .to("cxf:bean:cxfConvertTemp")
    .process(new Processor() {
        @Override
        public void process(Exchange exchange) throws Exception {
            // Manejar la respuesta SOAP
            // Llenar el cuerpo, que es un valor de tipo double, en la cadena
            // Devolver la cadena al descendente
            MessageContentsList response = (MessageContentsList) exchange.getIn().getBody();
            CelsiusToFahrenheitResponse r = (CelsiusToFahrenheitResponse) response.get(0);
            exchange.getIn().setBody("Temp in Farenheit: " + r.getTemperatureInFahrenheit());
        }
    })
    .to("mock:output");
```

5. Prueba

```bash
curl localhost:9090/convert/celsius/to/fahrenheit/50
Temp in Farenheit: 122.0
```

Como podemos ver, usar Camel para SOAP-to-REST requiere definir rutas y lógica de conversión para todas las operaciones usando código Java, lo que incurre en costos de desarrollo.

De manera similar, si el WSDL contiene muchos servicios y operaciones, usar Camel para hacer de proxy también puede ser doloroso.

#### 2.3 Conclusión <a href="#id-23-conclusion" id="id-23-conclusion"></a>

Resumamos los inconvenientes de los métodos tradicionales.

|                    | Módulo                                           | Camel                                                                  |
| ------------------ | ------------------------------------------------ | ---------------------------------------------------------------------- |
| WSDL               | análisis manual                                  | generación de código mediante Maven                                    |
| ascendente         | análisis manual                                  | conversión automática                                                  |
| definir cuerpo     | proporcionar plantillas para juicio y conversión | escribir código de conversión                                          |
| obtener parámetros | variables de Nginx                               | definir en código o llamar a la interfaz del cliente SOAP para obtener |

Ambos enfoques tienen costos de desarrollo, y para cada nuevo servicio web, este costo de desarrollo debe repetirse.

El costo de desarrollo es proporcional a la complejidad del servicio web.

### 3. Proxy SOAP-to-REST de APISIX <a href="#id-3-proxy-soap-to-rest-de-apisix" id="id-3-proxy-soap-to-rest-de-apisix"></a>

Los enfoques tradicionales de proxy requieren proporcionar plantillas de conversión o escribir código de conversión, ambos requieren que los usuarios analicen profundamente los archivos WSDL e incurren en costos de desarrollo significativos.

APISIX proporciona un enfoque automatizado que analiza automáticamente los archivos WSDL y proporciona lógica de conversión para cada operación, eliminando los costos de desarrollo para los usuarios.

**Este es un plugin empresarial,** [**contáctenos**](https://api7.ai/contact) **para más información.**

![Proxy SOAP-to-REST de APISIX](https://static.api7.ai/uploads/2023/06/02/aZcfp3Po_20230602-174814.png?imageMogr2/format/webp)

#### 3.1 Conversión Automática Sin Código <a href="#id-31-conversion-automatica-sin-codigo" id="id-31-conversion-automatica-sin-codigo"></a>

Usando el proxy SOAP de APISIX:

* No se requiere análisis manual o importación de archivos WSDL
* No es necesario definir plantillas de conversión
* No es necesario escribir ningún código de conversión o acoplamiento.

Los usuarios solo necesitan configurar la URL del WSDL, y APISIX realizará la conversión automáticamente. Es adecuado para cualquier servicio web, es un programa genérico y no requiere desarrollo secundario para necesidades específicas.

#### 3.2 Configuración Dinámica <a href="#id-32-configuracion-dinamica" id="id-32-configuracion-dinamica"></a>

* La URL del WSDL puede vincularse a cualquier ruta y, como otros objetos de recursos de APISIX, puede actualizarse en tiempo de ejecución. Los cambios de configuración surten efecto dinámicamente sin necesidad de reiniciar APISIX.
* Las URL(s) del servicio contenidas en el archivo WSDL (que pueden tener múltiples URLs), es decir, la dirección ascendente, se reconocerán automáticamente y se utilizarán como el ascendente SOAP sin necesidad de que los usuarios las analicen y configuren.

#### 3.3 Mecanismo de Implementación <a href="#id-33-mecanismo-de-implementacion" id="id-33-mecanismo-de-implementacion"></a>

* Obtener el contenido del archivo WSDL desde la URL del WSDL y generar automáticamente un objeto proxy después del análisis.
* El objeto proxy es responsable de la conversión de protocolos:
  * Generar solicitudes XML SOAP compatibles basadas en la entrada JSON.
  * Convertir respuestas XML SOAP a respuestas JSON.
  * Acceder al servicio web y manejar automáticamente los detalles del protocolo SOAP, como respuestas de tipo fallo.
  * Soporta SOAP1.1 y SOAP1.2 y varias características de extensión, como WS-Addressing.

#### 3.4 Ejemplo de Configuración <a href="#id-34-ejemplo-de-configuracion" id="id-34-ejemplo-de-configuracion"></a>

Explicación de los parámetros de configuración para el plugin SOAP:

| Parámetro  | ¿Requerido? | Descripción                                                                                |
| ---------- | ----------- | ------------------------------------------------------------------------------------------ |
| `wsdl_url` | Sí          | URL del WSDL, por ejemplo, `https://apps.learnwebservices.com/services/tempconverter?wsdl` |

Prueba:

```bash
# Configurar el enrutamiento de APISIX usando el plugin SOAP
# Nota: una sola ruta puede ejecutar todas las operaciones, con el nombre de la operación especificado usando parámetros de URL
# Esto también refleja los beneficios del proxy dinámico, eliminando la necesidad de análisis manual de cada operación en el archivo WSDL.
curl http://127.0.0.1:9180/apisix/admin/routes/1 \
    -H 'X-API-KEY: xxx' -X PUT -d '
{
    "methods": ["POST"],
    "uri": "/getCountry",
    "plugins": {
        "soap": {
            "wsdl_url": "http://localhost:8080/ws/countries.wsdl"
        }
    }
}'
curl 'http://127.0.0.1:9080/getCountry' \
    -X POST -d '{"name": "Spain"}'
# Llamada exitosa
HTTP/1.1 200 OK
Date: Tue, 06 Dec 2022 08:07:48 GMT
Content-Type: text/plain; charset=utf-8
Transfer-Encoding: chunked
Connection: keep-alive
Server: APISIX/2.99.0
{"currency":"EUR","population":46704314,"capital":"Madrid","name":"Spain"}
# Llamada fallida
HTTP/1.1 502 Bad Gateway
Date: Tue, 03 Jan 2023 13:43:33 GMT
Content-Type: text/plain; charset=utf-8
Transfer-Encoding: chunked
Connection: keep-alive
Server: APISIX/2.99.0
{"message":"Your name is required.","actor":null,"code":"SOAP-ENV:Server","subcodes":null,"detail":null}
```

### 4. Conclusión <a href="#id-4-conclusion" id="id-4-conclusion"></a>

En el mundo actual, los servicios web han avanzado hasta el punto en que muchos usuarios empresariales dependen de servicios web tradicionales basados en SOAP para proporcionar sus servicios. Debido a razones históricas y consideraciones de costos, estos servicios no siempre son adecuados para una refactorización completa en servicios RESTful. Como resultado, existe una demanda significativa de SOAP-to-REST entre muchos usuarios empresariales.

El plugin SOAP-to-REST proporcionado por APISIX puede lograr funcionalidad de proxy sin código, puede configurarse dinámicamente y no requiere desarrollo secundario, lo que es beneficioso para la migración e integración de negocios de costo cero para usuarios empresariales.
