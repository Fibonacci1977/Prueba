# Ejemplo de internacionalización de JSF 2

En una aplicación JSF, puedes cambiar la configuración regional de tu aplicación mediante programación de esta manera:

```java

//this example change locale to france
FacesContext.getCurrentInstance().getViewRoot().setLocale(new Locale('fr');
Copiar
```

Esto facilita la compatibilidad de JSF con la internacionalización o varios idiomas.

### Ejemplo completo de internacionalización de JSF

En este tutorial, le mostramos una aplicación web JSF 2.0 que muestra una página de bienvenida, recupera un mensaje de bienvenida de un archivo de propiedades y cambia el mensaje de bienvenida dinámicamente según el idioma seleccionado.

### 1. Carpeta del proyecto

Estructura de directorios para este ejemplo.

<img src="https://mkyong.com/wp-content/uploads/2010/11/jsf2-internationalization-folder.png" alt="carpeta de internacionalización de jsf2" height="437" width="327">

### 2. Archivo de propiedades

Aquí hay dos archivos de propiedades para almacenar mensajes en inglés y chino.

_bienvenidos.propiedades_

```bash

welcome.jsf = Happy learning JSF 2.0
Copiar
```

_welcome\_zh\_CN.properties_

```bash

welcome.jsf = \u5feb\u4e50\u5b66\u4e60 JSF 2.0
Copiar
```

**Nota:**\
Para caracteres UTF-8 o caracteres que no sean en inglés, por ejemplo, caracteres chinos, debe codificarlos con la herramienta [native2ascii](https://mkyong.com/java/java-convert-chinese-character-to-unicode-with-native2ascii/) .

### 3. faces-config.xml

Incluya el archivo de propiedades anterior en su aplicación JSF y declare "en" como la configuración regional predeterminada de su aplicación.

_faces-config.xml_

```markup

<?xml version="1.0" encoding="UTF-8"?>
<faces-config
    xmlns="http://java.sun.com/xml/ns/javaee"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://java.sun.com/xml/ns/javaee 
    http://java.sun.com/xml/ns/javaee/web-facesconfig_2_0.xsd"
    version="2.0">
     <application>
     	   <locale-config>
     	        <default-locale>en</default-locale>
     	   </locale-config>
	   <resource-bundle>
		<base-name>com.mkyong.welcome</base-name>
		<var>msg</var>
	   </resource-bundle>
     </application>
</faces-config>
Copiar
```

### 4. Managed Bean

Un bean administrado, que proporciona una lista de selección de idioma y un detector de eventos de cambio de valor para cambiar la configuración regional mediante programación.

_LanguageBean .java_

```java

package com.mkyong;

import java.io.Serializable;
import java.util.LinkedHashMap;
import java.util.Locale;
import java.util.Map;

import javax.faces.bean.ManagedBean;
import javax.faces.bean.SessionScoped;
import javax.faces.context.FacesContext;
import javax.faces.event.ValueChangeEvent;
 
@ManagedBean(name="language")
@SessionScoped
public class LanguageBean implements Serializable{
	
	private static final long serialVersionUID = 1L;
	
	private String localeCode;
	
	private static Map<String,Object> countries;
	static{
		countries = new LinkedHashMap<String,Object>();
		countries.put("English", Locale.ENGLISH); //label, value
		countries.put("Chinese", Locale.SIMPLIFIED_CHINESE);
	}

	public Map<String, Object> getCountriesInMap() {
		return countries;
	}

	
	public String getLocaleCode() {
		return localeCode;
	}


	public void setLocaleCode(String localeCode) {
		this.localeCode = localeCode;
	}

	//value change event listener
	public void countryLocaleCodeChanged(ValueChangeEvent e){
		
		String newLocaleValue = e.getNewValue().toString();
		
		//loop country map to compare the locale code
                for (Map.Entry<String, Object> entry : countries.entrySet()) {
        
        	   if(entry.getValue().toString().equals(newLocaleValue)){
        		
        		FacesContext.getCurrentInstance()
        			.getViewRoot().setLocale((Locale)entry.getValue());
        		
        	  }
               }
	}

}
Copiar
```

### 5. Página JSF

Una página JSF para mostrar un mensaje de bienvenida desde un archivo de propiedades y adjuntar un detector de eventos de cambio de valor a un cuadro desplegable.

```markup

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml"   
      xmlns:h="http://java.sun.com/jsf/html"
      xmlns:f="http://java.sun.com/jsf/core"
      xmlns:ui="http://java.sun.com/jsf/facelets"
      >
     
    <h:body>
    	
    	<h1>JSF 2 internationalization example</h1>
		
     <h:form>
			
	<h2>
		<h:outputText value="#{msg['welcome.jsf']}" />
	</h2>
			
	<h:panelGrid columns="2">
				
		Language : 
		<h:selectOneMenu value="#{language.localeCode}" onchange="submit()"
			valueChangeListener="#{language.countryLocaleCodeChanged}">
   			<f:selectItems value="#{language.countriesInMap}" /> 
   		</h:selectOneMenu>

	</h:panelGrid>
			
      </h:form>
		
    </h:body>
</html>
Copiar
```

### 6. Demostración

URL: _http://localhost:8080/JavaServerFaces/faces/default.xhtml_

Por defecto, se muestra en inglés.

<img src="https://mkyong.com/wp-content/uploads/2010/11/jsf2-internationalization-example-1.png" alt="jsf2-internacionalización-ejemplo-1" height="302" width="640">

Si el usuario cambia el idioma del menú desplegable, se activará un detector de eventos de cambio de valor y se modificará la configuración regional de la aplicación en consecuencia.

<img src="https://mkyong.com/wp-content/uploads/2010/11/jsf2-internationalization-example-2.png" alt="jsf2-internacionalización-ejemplo-2" height="313" width="639">

### Descargar código fuente

Descárguelo: [JSF-2-Internationalization-Example.zip](https://mkyong.com/wp-content/uploads/2010/11/JSF-2-Internationalization-Example.zip) (11 KB)

### Referencia

1. [Paquete de recursos en JSF 2.0](https://mkyong.com/jsf2/jsf-2-0-and-resource-bundles-example/)
2. [Crear una configuración regional (Tutorial de Oracle)](http://download.oracle.com/javase/tutorial/i18n/locale/create.html)
3. [Ejemplo de internacionalización de Spring MVC](https://mkyong.com/spring-mvc/spring-mvc-internationalization-example/)
4. [Conjunto de caracteres W3C](http://www.w3.org/International/O-HTTP-charset)
