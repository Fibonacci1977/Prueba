# Métodos de ordenamiento

{% file src="../../.gitbook/assets/Ordenacion.pdf" %}

Los problemas más comunes en la informática son la búsqueda y el ordenamiento. El proceso de ordenar consiste en recolocar los elementos de un _array_ o colección ya sea de mayor a menor o viceversa con el fin de acelerar la búsqueda de la información.

En este aspecto existe una multitud de algoritmos de ordenamiento clasificados de diversas formas como la estabilidad, su complejidad, ubicación del proceso al ordenar, etc.

Entre los múltiples algoritmos tenemos:

* Ordenamiento por burbuja
* Ordenamiento por montículos
* Ordenamiento por selección
* Ordenamiento por inserción
* Ordenamiento rápido (_QuickSort_)
* Ordenamiento _shell_

<br>

**Ordenamiento por burbuja**

La clase con el siguiente código permite ordenar los elementos de un _array_ unidimensional mediante este método.

```java
package ordenamiento;public class Ordena {        //Ordenamiento de burbuja    public static void burbuja(Integer[] data) {        for (int i = 0; i < data.length; i++) {            for (int j = 0; j < data.length - 1; j++) {                if (data[j] > data[j + 1]) {                    Integer temp = data[j];                    data[j] = data[j + 1];                    data[j + 1] = temp;                }            }        }    }}
```

Para comprobar el funcionamiento se utiliza lo siguiente:

```java
package test;import ordenamiento.Ordena;public class TestOrdenar {    public static void main(String[] args) {        Integer[] vals = {15, 60, 8, 16, 44, 27, 12, 35};        Ordena.burbuja(vals);        for (Integer val : vals) {            System.out.println(val);        }    }}
```

La salida del resultado sería:

```
8
12
15
16
27
35
44
60
```

Se comprueba el funcionamiento de este algoritmo.

<br>

**Ordenamiento por selección**

La clase con el siguiente código permite ordenar los elementos de un _array_ unidimensional mediante este método.

```java
package ordenamiento;public class Ordena {        //Ordenamiento por selección    public static void seleccion(Integer[] data) {        for (int i = 0; i < data.length; i++) {            for (int j = i; j < data.length; j++) {                if (data[i] > data[j]) {                    Integer aux = data[j];                    data[j] = data[i];                    data[i] = aux;                }            }        }    }}
```

Para comprobar el funcionamiento se utiliza lo siguiente:

```java
package test;import ordenamiento.Ordena;public class TestOrdenar {    public static void main(String[] args) {        Integer[] vals = {15, 60, 8, 16, 44, 27, 12, 35};        Ordena.seleccion(vals);        for (Integer val : vals) {            System.out.println(val);        }    }}
```

La salida del resultado sería:

```
8
12
15
16
27
35
44
60
```

Se comprueba el funcionamiento de este algoritmo.

<br>

**Ordenamiento por inserción**

La clase con el siguiente código permite ordenar los elementos de un _array_ unidimensional mediante este método.

```java
package ordenamiento;public class Ordena {        //Ordenamiento por inserción    public static void insercion(Integer[] data) {        for (int i = 1; i < data.length; i++) {            Integer aux = data[i];            int j = i - 1;            while (j >= 0 && data[j] > aux) {                data[j + 1] = data[j];                j--;            }            data[j + 1] = aux;        }    }}
```

Para comprobar el funcionamiento se utiliza lo siguiente:

```java
package test;import ordenamiento.Ordena;public class TestOrdenar {    public static void main(String[] args) {        Integer[] vals = {15, 60, 8, 16, 44, 27, 12, 35};        Ordena.insercion(vals);                for (Integer val : vals) {            System.out.println(val);        }    }}
```

La salida del resultado sería:

```
8
12
15
16
27
35
44
60
```

Se comprueba el funcionamiento de este algoritmo.

<br>

**Ordenamiento por montículos (HeapSort)**

La clase con el siguiente código permite ordenar los elementos de un _array_ unidimensional mediante este método.

```java
package ordenamiento;public class Ordena {        //Ordenamiento por montículos    public static void heapsort(Integer[] data) {        data = monticulo(data, data.length);        for (int i = 0; i < data.length; i++) {            data = eliminarRaiz(data, data.length - i);            data = monticulo(data, data.length - i - 1);        }    }        //Función para construir montículo    private static Integer[] monticulo(Integer[] data, int n) {        for (int i = 0; i < n; i++) {            if (padre(i) != -1) {                int p = data[padre(i)];                if (data[i] > p) {                    data[padre(i)] = data[i];                    data[i] = p;                    monticulo(data, n);                }            }        }        return data;    }                //Función para determinar padres    private static int padre(int index) {        return (index == 0) ? -1 : (index - 1) / 2;    }    //Función para eliminar las raices    private static Integer[] eliminarRaiz(Integer[] data, int n) {        Integer aux;        aux = data[n - 1];        data[n - 1] = data[0];        data[0] = aux;        return data;    }}
```

Para comprobar el funcionamiento se utiliza lo siguiente:

```java
package test;import ordenamiento.Ordena;public class TestOrdenar {    public static void main(String[] args) {        Integer[] vals = {15, 60, 8, 16, 44, 27, 12, 35};        Ordena.heapsort(vals);        for (Integer val : vals) {            System.out.println(val);        }    }}
```

La salida del resultado sería:

```
8
12
15
16
27
35
44
60
```

Se comprueba el funcionamiento de este algoritmo.
