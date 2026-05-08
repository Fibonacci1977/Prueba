# Page 1

### **¿Qué es un algoritmo de ordenación?** <a href="#qu-es-un-algoritmo-de-ordenaci-n" id="qu-es-un-algoritmo-de-ordenaci-n"></a>

Los algoritmos de ordenación son un conjunto de instrucciones que toman un arreglo o lista como entrada y organizan los elementos en un orden particular.

Las ordenaciones suelen ser numéricas o una forma de orden alfabético (o lexicográfico), y pueden ser en orden ascendente (AZ, 0-9) o descendente (ZA, 9-0).

### **Por qué los algoritmos de ordenación son importantes** <a href="#por-qu-los-algoritmos-de-ordenaci-n-son-importantes" id="por-qu-los-algoritmos-de-ordenaci-n-son-importantes"></a>

Dado que a menudo pueden reducir la complejidad de un problema, los algoritmos de ordenación son muy importantes en informática. Estos algoritmos tienen aplicaciones directas en algoritmos de búsqueda, algoritmos de bases de datos, métodos divide y vencerás, algoritmos de estructura de datos y muchos más.

### **Compensaciones de los algoritmos de** ordenación <a href="#compensaciones-de-los-algoritmos-de-ordenaci-n" id="compensaciones-de-los-algoritmos-de-ordenaci-n"></a>

Al elegir un algoritmo de ordenación, se deben hacer algunas preguntas: ¿Cuán grande es la colección que se ordena? ¿Cuánta memoria hay disponible? ¿La colección necesita crecer?

Las respuestas a estas preguntas pueden determinar qué algoritmo funcionará mejor para cada situación. Algunos algoritmos como la ordenación por combinación pueden necesitar mucho espacio o memoria para ejecutarse, mientras que la ordenación por inserción no siempre es la más rápida, pero no requiere muchos recursos para ejecutarse.

Debes determinar cuáles son tus requisitos y considerar las limitaciones de tu sistema antes de decidir qué algoritmo de ordenación usar.

### **Algunos algoritmos de** ordenación **comunes** <a href="#algunos-algoritmos-de-ordenaci-n-comunes" id="algunos-algoritmos-de-ordenaci-n-comunes"></a>

Algunos de los algoritmos de ordenación más comunes son:

* Selection sort (selección)
* Bubble sort (burbuja)
* Insertion sort (inserción)
* Merge sort (combinación)
* Quick sort (rápida)
* Heap sort (montón)
* Counting sort (conteo)
* Radix sort (raíz)
* Bucket sort (cubo)

Pero antes de entrar en cada uno de estos, aprendamos un poco más sobre qué clasifica a un algoritmo de ordenación.

### **Clasificación de un algoritmo de** ordenación <a href="#clasificaci-n-de-un-algoritmo-de-ordenaci-n" id="clasificaci-n-de-un-algoritmo-de-ordenaci-n"></a>

Los algoritmos de ordenación se pueden clasificar en función de los siguientes parámetros:

1. **La cantidad de intercambios o inversiones requeridas:** Esta es la cantidad de veces que el algoritmo intercambia elementos para ordenar la entrada. La ordenación por selección requiere el número mínimo de intercambios.
2. **El número de comparaciones:** Este es el número de veces que el algoritmo compara elementos para ordenar la entrada. Usando [la notación Big-O](https://guide.freecodecamp.org/computer-science/notation/big-o-notation/) , los ejemplos de algoritmos de ordenación enumerados anteriormente requieren al menos `O(nlogn)`comparaciones en el mejor de los casos y `O(n^2)` comparaciones en el peor de los casos para la mayoría de los resultados.
3. **Ya sea que usen recursividad o no:** Algunos algoritmos de ordenación, como la ordenación rápida, usan técnicas recursivas para ordenar la entrada. Otros algoritmos de ordenación, como la ordenación por selección o la ordenación por inserción, utilizan técnicas no recursivas. Por último, algunos algoritmos de ordenación, como la ordenación por fusión, utilizan técnicas tanto recursivas como no recursivas para ordenar la entrada.
4. **Ya sean estables o inestables:** Los algoritmos de ordenación estables mantienen el orden relativo de los elementos con valores iguales o claves. Los algoritmos de ordenación inestables no mantienen el orden relativo de los elementos con valores/claves iguales.\
   \
   Por ejemplo, imagina que tienes el arreglo de entrada `[1, 2, 3, 2, 4]`. Y para ayudar a diferenciar entre los dos valores iguales, `2` actualicémoslos a `2a` y `2b`, creando el arreglo de entrada `[1, 2a, 3, 2b, 4]`.\
   \
   Los algoritmos de ordenación estables mantendrán el orden de `2a` y `2b`, lo que significa que el arreglo de salida será `[1, 2a, 2b, 3, 4]`. Los algoritmos de ordenación inestables no mantienen el orden de los valores iguales y el arreglo de salida puede ser `[1, 2b, 2a, 3, 4]`.\
   \
   La ordenación por inserción, la ordenación por fusión y la ordenación por burbuja son estables. La ordenación en montón y la ordenación rápida son inestables.
5. **La cantidad de espacio adicional requerido:** Algunos algoritmos de ordenación pueden ordenar una lista sin crear una lista completamente nueva. Estos se conocen como algoritmos de ordenación en el lugar y requieren un `O(1)` espacio adicional constante para la ordenación. Mientras tanto, los algoritmos de ordenación fuera de lugar crean una nueva lista durante la ordenación.\
   \
   La ordenación por inserción y la ordenación rápida son algoritmos de ordenación en el lugar, ya que los elementos se mueven alrededor de un punto de pivote y no usan un arreglo separado.\
   \
   Merge sort es un ejemplo de un algoritmo de ordenación fuera del lugar, ya que el tamaño de la entrada debe asignarse de antemano para almacenar la salida durante el proceso de ordenación, lo que requiere memoria adicional.

### **Bucket Sort (O**rdenación **de cubo)** <a href="#bucket-sort-ordenaci-n-de-cubo" id="bucket-sort-ordenaci-n-de-cubo"></a>

La ordenación de cubos es un algoritmo de ordenación por comparación que opera en elementos dividiéndolos en diferentes cubos y luego ordenando estos cubos individualmente. Cada depósito se ordena individualmente utilizando un algoritmo de ordenación independiente, como la ordenación por inserción, o aplicando el algoritmo de ordenación de cubos de forma recursiva.

La ordenación de cubos es principalmente útil cuando la entrada se distribuye uniformemente en un rango. Por ejemplo, imagina que tienes una gran variedad de enteros de punto flotante distribuidos uniformemente entre un límite superior e inferior.

Puedes usar otro algoritmo de ordenación, como la ordenación por combinación, la ordenación por montones o la ordenación rápida. Sin embargo, esos algoritmos garantizan una complejidad de tiempo en el mejor de los casos de `O(nlogn)`.

Usando la ordenación de cubos, la ordenación del mismo arreglo se puede completar a `O(n)`tiempo.

#### **Pseudocódigo para** ordenación **de cubo:** <a href="#pseudoc-digo-para-ordenaci-n-de-cubo" id="pseudoc-digo-para-ordenaci-n-de-cubo"></a>

```
void bucketSort(float[] a,int n)

{

    for(each floating integer 'x' in n)

    {
        insert x into bucket[n*x]; 
    }

    for(each bucket)

    {
        sort(bucket);
    }

}
```

### **Counting Sort (**&#x4F;rdenación **de conteo)** <a href="#counting-sort-ordenaci-n-de-conteo" id="counting-sort-ordenaci-n-de-conteo"></a>

El algoritmo de ordenación por conteo funciona creando primero una lista de los conteos u ocurrencias de cada valor único en la lista. Luego crea una lista ordenada final basada en la lista de conteos.

Una cosa importante que debes recordar es que la ordenación por conteo solo se puede usar cuando conoces de antemano el rango de valores posibles en la entrada.

#### **Ejemplo:** <a href="#ejemplo" id="ejemplo"></a>

```
Digamos que tienes una lista de números enteros del 0 al 5:
 
input = [2, 5, 3, 1, 4, 2]

Primero, debes crear una lista de recuentos para cada valor único en
la lista `entrada`. Como sabes que el rango de la `entrada` es de 0 a
5, puedes crear una lista con cinco marcadores de posición para los valores del 0 al 5, respectivamente:

count = [0, 0, 0, 0, 0, 0]
  # val: 0  1  2  3  4  5

Luego, revisas la lista `input` e iteras el índice para cada valor en uno.

Por ejemplo, el primer valor en la lista `input` es 2, por lo que agrega uno
al valor en el segundo índice de la lista `count`, que representa
el valor 2:

count = [0, 0, 1, 0, 0, 0]
  # val: 0  1  2  3  4  5
       
El siguiente valor en la lista `input` es 5, por lo que agrega uno al valor en el último índice de la lista `count`, que representa el valor 5:

count = [0, 0, 1, 0, 0, 1]
  # val: 0  1  2  3  4  5

Continúa hasta que tengas el recuento total de cada valor en la `entrada`
lista:

count = [0, 1, 2, 1, 1, 1]
  # val: 0  1  2  3  4  5

Finalmente, dado que sabes cuántas veces cada valor en la lista `input`
aparece, puedes crear fácilmente una lista de `salida` ordenada. Bucle a través de la lista `recuento`, y para cada recuento, agrega el valor correspondiente (0 - 5) al arreglo `output` tantas veces.

Por ejemplo, no había 0 en la lista de 'entradas', pero había una aparición del valor 1, por lo que agrega ese valor al arreglo `output`
una vez:

output = [1]

Luego hubo dos apariciones del valor 2, por lo que las agrega a la
lista `output`:

output = [1, 2, 2]

Y así sucesivamente hasta que tengas la lista final ordenada de "salida" (output):

output = [1, 2, 2, 3, 4, 5]
```

#### **Propiedades** <a href="#propiedades" id="propiedades"></a>

* Complejidad de espacio:`O(k)`
* Rendimiento del mejor caso:`O(n+k)`
* Rendimiento del caso promedio:`O(n+k)`
* Rendimiento en el peor de los casos:`O(n+k)`
* Estable: Sí ( `k`es el rango de los elementos en el arreglo)

#### **Implementación en JavaScript** <a href="#implementaci-n-en-javascript" id="implementaci-n-en-javascript"></a>

```js
let numbers = [1, 4, 1, 2, 7, 5, 2];
let count = [];
let output =[];
let i = 0;
let max = Math.max(...numbers);

// inicializa el contador
for (i = 0; i <= max; i++) {
  count[i] = 0;
}

// inicializa el arreglo de salida
for (i = 0; i < numbers.length; i++) {
  output[i] = 0;
}

for (i = 0; i < numbers.length; i++) {
  count[numbers[i]]++;
}

for (i = 1; i < count.length; i++) {
  count[i] += count[i-1];
}

for (i = numbers.length - 1; i >= 0; i--) { 
  output[--count[numbers[i]]] = numbers[i];
}

// arreglo ordenado de salida
for (i = 0; i < output.length; i++) {
  console.log(output[i]);
}
```

#### **Implementación de C++** <a href="#implementaci-n-de-c" id="implementaci-n-de-c"></a>

```cpp
#include <iostream>

#include <vector>

void countSort(int upperBound, int lowerBound, std::vector < int > numbersToSort) 
// Límites inferior y superior de los números en el vector
{
  int i;
  int range = upperBound - lowerBound; // Crea un rango lo suficientemente grande para obtener todos los números entre el mínimo y el máximo
  std::vector < int > counts(range + 1); // Inicializar conteos del tamaño del rango
  std::fill(counts.begin(), counts.end(), 0); // Rellenar vector de ceros
  std::vector < int > storedNumbers(numbersToSort.size()); // Inicializar los números almacenados del mismo tamaño que el vector de entrada
  std::fill(storedNumbers.begin(), storedNumbers.end(), 0); // Rellenar vector de números almacenados de ceros
  for (i = 0; i < numbersToSort.size(); i++) {
    int index = numbersToSort[i] - lowerBound; // Por ejemplo, si 5 es el límite inferior y numberToSort[i] es 5, el índice será 0 y el
    counts[index] += 1; // recuento de 5 se almacenará en recuentos[0]
  }

  for (i = 1; i < counts.size(); i++) {
    counts[i] += counts[i - 1];
  }

  for (i = numbersToSort.size() - 1; i >= 0; i--) { // Copiar elementos de numbersToSort a storedNumbers según el conteo
    storedNumbers[--counts[numbersToSort[i] - lowerBound]] = numbersToSort[i];
  }

  for (i = 0; i < storedNumbers.size(); i++) {
    std::cout << storedNumbers[i];
    if (i != storedNumbers.size() - 1)
      std::cout << ", ";
  }
  std::cout << std::endl;
}
```

#### **Implementación en Swift** <a href="#implementaci-n-en-swift" id="implementaci-n-en-swift"></a>

```swift
func countingSort(_ array: [Int]) {
  // Crea un arreglo para almacenar el conteo de cada elemento
  let maxElement = array.max() ?? 0
  var countArray = [Int](repeating: 0, count: Int(maxElement + 1))
  
  for element in array {
    countArray[element] += 1
  }
  
  for i in 1 ..< countArray.count {
    countArray[i] += countArray[i-1];
  }
  
  var sortedArray = [Int](repeating: 0, count: array.count)
  
  // copia elementos del arreglo a sortedArray de acuerdo con el conteo
  for i in (0 ..< array.count) .reversed() {
    countArray[array[i]] -= 1
    sortedArray[countArray[array[i]]] = array[i];
  }
  
  print(sortedArray)
}
```

### **Insertion Sort (**&#x4F;rdenación **de inserción)** <a href="#insertion-sort-ordenaci-n-de-inserci-n" id="insertion-sort-ordenaci-n-de-inserci-n"></a>

La ordenación por inserción es un algoritmo de ordenación simple para una pequeña cantidad de elementos.

#### **Ejemplo:** <a href="#ejemplo--1" id="ejemplo--1"></a>

En la ordenación por inserción, compara el elemento `key` con los elementos anteriores. Si los elementos anteriores son mayores que el elemento `key`, mueve el elemento anterior a la siguiente posición.

Comienza desde el índice 1 hasta el tamaño del arreglo de entrada.

\[ 8 3 5 1 4 2 ]

Paso 1 :

```
      key = 3 //a partir del 1er índice.

      Aquí `key`(clave) se comparará con los elementos anteriores.

      En este caso, `key` se compara con 8. como 8 > 3, mueve el elemento 8
      a la siguiente posición e inserta `key` en la posición anterior.

      Result: [ 3 8 5 1 4 2 ]
```

Paso 2 :

<figure><img src="https://github.com/blulion/freecodecamp-resource/blob/master/insertion_sort/2.png?raw=true" alt="[ 3 8 5 1 4 2 ]" height="400" width="600"><figcaption></figcaption></figure>

```
      key = 5 //2º índice

      8 > 5 // mueve 8 al segundo índice e inserta 5 en el primer índice.

      Result: [ 3 5 8 1 4 2 ]
```

Paso 3 :

<figure><img src="https://github.com/blulion/freecodecamp-resource/blob/master/insertion_sort/3.png?raw=true" alt="[ 3 5 8 1 4 2 ]" height="400" width="600"><figcaption></figcaption></figure>

```
      //3er índice

      8 > 1     => [ 3 5 1 8 4 2 ]  

      5 > 1     => [ 3 1 5 8 4 2 ]

      3 > 1     => [ 1 3 5 8 4 2 ]

      Result: [ 1 3 5 8 4 2 ]
```

Paso 4 :

<figure><img src="https://github.com/blulion/freecodecamp-resource/blob/master/insertion_sort/4.png?raw=true" alt="[ 1 3 5 8 4 2 ]" height="400" width="600"><figcaption></figcaption></figure>

```
      key = 4 // 4º índice

      8 > 4   => [ 1 3 5 4 8 2 ]

      5 > 4   => [ 1 3 4 5 8 2 ]

      3 > 4   ≠>  stop

      Result: [ 1 3 4 5 8 2 ]
```

Paso 5 :

<figure><img src="https://github.com/blulion/freecodecamp-resource/blob/master/insertion_sort/5.png?raw=true" alt="[ 1 3 4 5 8 2 ]" height="400" width="600"><figcaption></figcaption></figure>

```
      key = 2 // 5º índice

      8 > 2   => [ 1 3 4 5 2 8 ]

      5 > 2   => [ 1 3 4 2 5 8 ]

      4 > 2   => [ 1 3 2 4 5 8 ]

      3 > 2   => [ 1 2 3 4 5 8 ]

      1 > 2   ≠> stop

      Result: [1 2 3 4 5 8]
```

<figure><img src="https://github.com/blulion/freecodecamp-resource/blob/master/insertion_sort/6.png?raw=true" alt="[ 1 2 3 4 5 8 ]" height="400" width="600"><figcaption></figcaption></figure>

El algoritmo que se muestra a continuación es una versión ligeramente optimizada para evitar cambiar el elemento `key`  en cada iteración. Aquí, el elemento  `key`   se intercambiará al final de la iteración (paso).

```
    InsertionSort(arr[])
      for j = 1 to arr.length
         key = arr[j]
         i = j - 1
         while i > 0 and arr[i] > key
            arr[i+1] = arr[i]
            i = i - 1
         arr[i+1] = key
```

Aquí hay una implementación detallada en JavaScript:

```js
function insertion_sort(A) {
    var len = array_length(A);
    var i = 1;
    while (i < len) {
        var x = A[i];
        var j = i - 1;
        while (j >= 0 && A[j] > x) {
            A[j + 1] = A[j];
            j = j - 1;
        }
        A[j+1] = x;
        i = i + 1;
    }
}
```

A continuación se muestra una implementación rápida en Swift:

```swift
  var array = [8, 3, 5, 1, 4, 2]

  func insertionSort(array:inout Array<Int>) -> Array<Int>{
      for j in 0..<array.count {
          let key = array[j]
          var i = j-1

          while (i > 0 && array[i] > key){
              array[i+1] = array[i]
              i = i-1
          }
          array[i+1] = key
      }
      return array
  }
```

El ejemplo de Java se muestra a continuación:

```java
public int[] insertionSort(int[] arr)
      for (j = 1; j < arr.length; j++) {
         int key = arr[j]
         int i = j - 1
         while (i > 0 and arr[i] > key) {
            arr[i+1] = arr[i]
            i -= 1
         }
         arr[i+1] = key
      }
      return arr;
```

Y en c...

```c
void insertionSort(int arr[], int n) 
{ 
   int i, key, j; 
   for (i = 1; i < n; i++) 
   { 
       key = arr[i]; 
       j = i-1;
       while (j >= 0 && arr[j] > key) 
       { 
           arr[j+1] = arr[j]; 
           j = j-1; 
       } 
       arr[j+1] = key; 
   } 
} 
```

#### **Propiedades:** <a href="#propiedades" id="propiedades"></a>

* Complejidad de espacio: O(1)
* Complejidad de tiempo: O(n), O(n\* n), O(n\* n) para los mejores, promedios y peores casos respectivamente.
* Mejor caso: El arreglo ya está ordenado
* Caso promedio: El arreglo se ordena aleatoriamente
* En el peor de los casos: El arreglo se ordena de forma inversa.
* Ordenación en el lugar: Sí
* Estable: Sí

### **Heapsort (Ordenación por montones)** <a href="#heapsort-ordenaci-n-por-montones" id="heapsort-ordenaci-n-por-montones"></a>

Heapsort es un algoritmo de ordenación eficiente basado en el uso de montones máximos/mínimos. Un montón es una estructura de datos basada en un árbol que satisface la propiedad del montón, es decir, para un montón máximo, la clave de cualquier nodo es menor o igual que la clave de su padre (si tiene un padre).

Esta propiedad se puede aprovechar para acceder al elemento máximo en el montón en tiempo O (logn) usando el método maxHeapify. Realizamos esta operación n veces, cada vez que movemos el elemento máximo en el montón a la parte superior del montón y lo extraemos del montón y lo colocamos en un arreglo ordenado. Por lo tanto, después de n iteraciones, tendremos una versión ordenada del arreglo de entrada.

El algoritmo no es un algoritmo en el lugar y requeriría que se construyera primero una estructura de datos de montón. El algoritmo también es inestable, lo que significa que al comparar objetos con la misma clave, no se conservará el orden original.

Este algoritmo se ejecuta en tiempo O(nlogn) y espacio adicional O(1) \[O(n) incluido el espacio requerido para almacenar los datos de entrada] ya que todas las operaciones se realizan completamente en el lugar.

La complejidad de tiempo del caso mejor, peor y promedio de Heapsort es O (nlogn). Aunque heapsort tiene una mejor complejidad en el peor de los casos que quicksort, una ordenación rápida bien implementada se ejecuta más rápido en la práctica. Este es un algoritmo basado en la comparación, por lo que se puede usar para conjuntos de datos no numéricos en la medida en que se pueda definir alguna relación (propiedad del montón) sobre los elementos.

Una implementación en Java es como se muestra a continuación:

```java
import java.util.Arrays;
public class Heapsort {

	public static void main(String[] args) {
		//test array
        //arreglo de prueba
		Integer[] arr = {1, 4, 3, 2, 64, 3, 2, 4, 5, 5, 2, 12, 14, 5, 3, 0, -1};
		String[] strarr = {"hope you find this helpful!", "wef", "rg", "q2rq2r", "avs", "erhijer0g", "ewofij", "gwe", "q", "random"};
		arr = heapsort(arr);
		strarr = heapsort(strarr);
		System.out.println(Arrays.toString(arr));
		System.out.println(Arrays.toString(strarr));
	}
	
	//O(nlogn) TIME, O(1) SPACE, NOT STABLE
    //O(nlogn) TIEMPO, O(1) ESPACIO, NO ESTABLE
	public static <E extends Comparable<E>> E[] heapsort(E[] arr){
		int heaplength = arr.length;
		for(int i = arr.length/2; i>0;i--){
			arr = maxheapify(arr, i, heaplength);
		}
		
		for(int i=arr.length-1;i>=0;i--){
			E max = arr[0];
			arr[0] = arr[i];
			arr[i] = max;
			heaplength--;
			arr = maxheapify(arr, 1, heaplength);
		}
		
		return arr;
	}
	
	//Creates maxheap from array
//Crea maxheap a partir de un arreglo
	public static <E extends Comparable<E>> E[] maxheapify(E[] arr, Integer node, Integer heaplength){
		Integer left = node*2;
		Integer right = node*2+1;
		Integer largest = node;
		
		if(left.compareTo(heaplength) <=0 && arr[left-1].compareTo(arr[node-1]) >= 0){
			largest = left;
		}
		if(right.compareTo(heaplength) <= 0 && arr[right-1].compareTo(arr[largest-1]) >= 0){
			largest = right;
		}	
		if(largest != node){
			E temp = arr[node-1];
			arr[node-1] = arr[largest-1];
			arr[largest-1] = temp;
			maxheapify(arr, largest, heaplength);
		}
		return arr;
	}
}
```

Implementación en C++

```cpp
#include <iostream>
using namespace std;
void heapify(int arr[], int n, int i) 
{ 
    int largest = i; 
    int l = 2*i + 1;  
    int r = 2*i + 2;
    if (l < n && arr[l] > arr[largest]) 
        largest = l;
    if (r < n && arr[r] > arr[largest]) 
        largest = r;
    if (largest != i) 
    { 
        swap(arr[i], arr[largest]); 
  
        
        heapify(arr, n, largest); 
    } 
} 
  
 
void heapSort(int arr[], int n) 
{ 
    
    for (int i = n / 2 - 1; i >= 0; i--) 
        heapify(arr, n, i); 
  
    
    for (int i=n-1; i>=0; i--) 
    { 

        swap(arr[0], arr[i]); 
  
        
        heapify(arr, i, 0); 
    } 
} 
void printArray(int arr[], int n) 
{ 
    for (int i=0; i<n; ++i) 
        cout << arr[i] << " "; 
    cout << "\n"; 
} 
int main() 
{ 
    int arr[] = {12, 11, 13, 5, 6, 7}; 
    int n = sizeof(arr)/sizeof(arr[0]); 
  
    heapSort(arr, n); 
  
    cout << "Sorted array is \n"; 
    printArray(arr, n); 
}
```

### Ordenación **Radix** <a href="#ordenaci-n-radix" id="ordenaci-n-radix"></a>

Requisito previo: Ordenar por conteo

QuickSort, MergeSort y HeapSort son algoritmos de ordenación basados ​​en comparaciones. CountSort no lo es. Tiene la complejidad de O(n+k), donde k es el elemento máximo del arreglo de entrada. Entonces, si k es O(n), CountSort se convierte en una ordenación lineal, que es mejor que los algoritmos de ordenación basados ​​en comparación que tienen una complejidad de tiempo O(nlogn).

La idea es extender el algoritmo CountSort para obtener una mejor complejidad de tiempo cuando k pasa a O(n2). Aquí viene la idea de Radix Sort.

#### **El algoritmo:** <a href="#el-algoritmo" id="el-algoritmo"></a>

Para cada dígito i donde i varía del dígito menos significativo al dígito más significativo de un número, ordena el arreglo de entrada utilizando el algoritmo de ordenación de acuerdo con el i-ésimo dígito. Usamos la ordenación por conteo porque es una ordenación estable.

Ejemplo: Supón que el arreglo de entrada es:

10, 21, 17, 34, 44, 11, 654, 123

Según el algoritmo, ordenaremos el arreglo de entrada según el dígito de uno (dígito menos significativo).

0: 10\
1: 21 11\
2:\
3: 123\
4: 34 44 654\
5:\
6:\
7: 17\
8:\
9:

Entonces, el arreglo se convierte en 10, 21, 11, 123, 24, 44, 654, 17.

Ahora, ordenaremos según el dígito de las decenas:

0:\
1: 10 11 17\
2: 21 123\
3: 34\
4: 44\
5: 654\
6:\
7:\
8:\
9:

Ahora, el arreglo se convierte en: 10, 11, 17, 21, 123, 34, 44, 654.

Finalmente, ordenamos según el dígito de las centenas (dígito más significativo):

0: 010 011 017 021 034 044\
1: 123\
2:\
3:\
4:\
5:\
6: 654\
7:\
8:\
9:

El arreglo se convierte en: 10, 11, 17, 21, 34, 44, 123, 654 que está ordenado. Así es como funciona nuestro algoritmo.

Una implementación en C:

```c
void countsort(int arr[],int n,int place){

        int i,freq[range]={0};         //el rango de números enteros es 10 ya que los dígitos van del 0 al 9

        int output[n];

        for(i=0;i<n;i++)
                freq[(arr[i]/place)%range]++;

        for(i=1;i<range;i++)
                freq[i]+=freq[i-1];
        
        for(i=n-1;i>=0;i--){
                output[freq[(arr[i]/place)%range]-1]=arr[i];
                freq[(arr[i]/place)%range]--;
        }
        
        for(i=0;i<n;i++)
                arr[i]=output[i];
}

void radixsort(ll arr[],int n,int maxx){            //maxx es el elemento máximo en el arreglo

        int mul=1;
        while(maxx){
                countsort(arr,n,mul);
                mul*=10;
                maxx/=10;
        }
}
```

### **Selection Sort (**&#x4F;rdenación **de selección)** <a href="#selection-sort-ordenaci-n-de-selecci-n" id="selection-sort-ordenaci-n-de-selecci-n"></a>

Selection Sort es uno de los algoritmos de ordenación más simples. Este algoritmo recibe su nombre de la forma en que itera a través del arreglo: Selecciona el elemento más pequeño actual y lo cambia de lugar.

Así es como funciona:

1. Encuentra el elemento más pequeño en el arreglo y lo intercambia con el primer elemento.
2. Encuentra el segundo elemento más pequeño y lo intercambia con el segundo elemento del arreglo.
3. Encuentra el tercer elemento más pequeño y lo intercambia con el tercer elemento del arreglo.
4. Repite el proceso de encontrar el siguiente elemento más pequeño y cambiarlo a la posición correcta hasta que se ordene todo el arreglo.

Pero, ¿cómo escribirías el código para encontrar el índice del segundo valor más pequeño en un arreglo?

Una manera fácil es notar que el valor más pequeño ya se ha cambiado al índice 0, por lo que el problema se reduce a encontrar el elemento más pequeño en el arreglo que comienza en el índice 1.

La ordenación por selección siempre toma el mismo número de comparaciones clave — N(N − 1)/2.

#### **Implementación en C/C++** <a href="#implementaci-n-en-c-c" id="implementaci-n-en-c-c"></a>

El siguiente programa en C++ contiene una implementación iterativa y recursiva del algoritmo de ordenación por selección. Ambas implementaciones se invocan en la función  `main()`.

```cpp
#include <iostream>
#include <string>
using namespace std;

template<typename T, size_t n>
void print_array(T const(&arr)[n]) {
    for (size_t i = 0; i < n; i++)
        std::cout << arr[i] << ' ';
    cout << "\n";
}

int minIndex(int a[], int i, int j) {
    if (i == j)
        return i;
    int k = minIndex(a, i + 1, j);
    return (a[i] < a[k]) ? i : k;
}

void recurSelectionSort(int a[], int n, int index = 0) {
    if (index == n)
        return;
    int k = minIndex(a, index, n - 1);
    if (k != index)
        swap(a[k], a[index]);
    recurSelectionSort(a, n, index + 1);
}

void iterSelectionSort(int a[], int n) {
    for (int i = 0; i < n; i++)
    {
        int min_index = i;
        int min_element = a[i];
        for (int j = i + 1; j < n; j++)
        {
            if (a[j] < min_element)
            {
                min_element = a[j];
                min_index = j;
            }
        }
        swap(a[i], a[min_index]);
    }
}

int main() {
    int recurArr[6] = { 100,35, 500, 9, 67, 20 };
    int iterArr[5] = { 25, 0, 500, 56, 98 };

    cout << "Recursive Selection Sort"  << "\n";
    print_array(recurArr); // 100 35 500 9 67 20
    recurSelectionSort(recurArr, 6);
    print_array(recurArr); // 9 20 35 67 100 500

    cout << "Iterative Selection Sort" << "\n";
    print_array(iterArr); // 25 0 500 56 98
    iterSelectionSort(iterArr, 5);
    print_array(iterArr); // 0 25 56 98 500
}
```

#### **Implementación en JavaScript** <a href="#implementaci-n-en-javascript-1" id="implementaci-n-en-javascript-1"></a>

```js
function selection_sort(A) {
    var len = A.length;
    for (var i = 0; i < len - 1; i = i + 1) {
        var j_min = i;
        for (var j = i + 1; j < len; j = j + 1) {
            if (A[j] < A[j_min]) {
                j_min = j;
            } else {}
        }
        if (j_min !== i) {
            swap(A, i, j_min);
        } else {}
    }
}

function swap(A, x, y) {
    var temp = A[x];
    A[x] = A[y];
    A[y] = temp;
}
```

#### **Implementación en Python** <a href="#implementaci-n-en-python" id="implementaci-n-en-python"></a>

```ps
def seletion_sort(arr):
         if not arr:
         return arr
    for i in range(len(arr)):
         min_i = i
         for j in range(i + 1, len(arr)):
              if arr[j] < arr[min_i]:
                  min_i = j
         arr[i], arr[min_i] = arr[min_i], arr[i]
```

#### **Implementación en Java** <a href="#implementaci-n-en-java" id="implementaci-n-en-java"></a>

```java
public void selectionsort(int array[])
{
    int n = array.length;            // método para encontrar la longitud del arreglo
    for (int i = 0; i < n-1; i++)
    {
        int index = i;
        int min = array[i];                  // tomando el elemento min como i-ésimo elemento del arreglo
        for (int j = i+1; j < n; j++)
        {
            if (array[j] < array[index])
            {
                index = j;
                min = array[j];
            }
        }
        int t = array[index];         //Intercambiar los lugares de los elementos
        array[index] = array[i];
        array[i] = t;
    }
}
```

#### **Implementación en MATLAB** <a href="#implementaci-n-en-matlab" id="implementaci-n-en-matlab"></a>

```
function [sorted] = selectionSort(unsorted)
    len = length(unsorted);
    for i = 1:1:len
        minInd = i;
        for j = i+1:1:len
           if unsorted(j) < unsorted(minInd) 
               minInd = j;
           end
        end
        unsorted([i minInd]) = unsorted([minInd i]);    
    end
    sorted = unsorted;
end
```

#### **Propiedades** <a href="#propiedades-1" id="propiedades-1"></a>

* Complejidad espacial:   **O(n)**
* Complejidad del tiempo:   **O(n2)**
* Ordenación en el lugar:   **Sí**
* Estable:   **No**

### **Bubble Sort (Ordenación de burbuja)** <a href="#bubble-sort-ordenaci-n-de-burbuja" id="bubble-sort-ordenaci-n-de-burbuja"></a>

Al igual que las burbujas se elevan desde el fondo de un vaso, **la ordenación de burbujas** es un algoritmo simple que ordena una lista, lo que permite que los valores más bajos o más altos aparezcan en la parte superior. El algoritmo atraviesa una lista y compara valores adyacentes, intercambiandolos si no están en el orden correcto.

Con una complejidad en el peor de los casos de O(n^2), la ordenación de burbujas es muy lenta en comparación con otros algoritmos de ordenación como la ordenación rápida. La ventaja es que es uno de los algoritmos de ordenación más fáciles de entender y codificar desde cero.

Desde una perspectiva técnica, la ordenación por burbuja es razonable para ordenar arreglos de tamaño pequeño o especialmente cuando se ejecutan algoritmos de ordenación en ordenadores con recursos de memoria notablemente limitados.

#### **Ejemplo:** <a href="#ejemplo--2" id="ejemplo--2"></a>

#### **Primer paso por la lista:** <a href="#primer-paso-por-la-lista" id="primer-paso-por-la-lista"></a>

* Comenzando con `[4, 2, 6, 3, 9]`, el algoritmo compara los dos primeros elementos del arreglo, 4 y 2. Los intercambia porque 2 < 4:`[2, 4, 6, 3, 9]`
* Compara los siguientes dos valores, 4 y 6. Como 4 < 6, estos ya están en orden, y el algoritmo continúa:`[2, 4, 6, 3, 9]`
* Los siguientes dos valores también se intercambian porque 3 < 6:`[2, 4, 3, 6, 9]`
* Los dos últimos valores, 6 y 9, ya están en orden, por lo que el algoritmo no los intercambia.

#### **Second pass through the list:** **Segundo paso por la lista:** <a href="#second-pass-through-the-list-segundo-paso-por-la-lista" id="second-pass-through-the-list-segundo-paso-por-la-lista"></a>

* 2 < 4, por lo que no hay necesidad de intercambiar posiciones:`[2, 4, 3, 6, 9]`
* El algoritmo intercambia los siguientes dos valores porque 3 < 4:`[2, 3, 4, 6, 9]`
* Sin intercambio porque 4 < 6:`[2, 3, 4, 6, 9]`
* De nuevo, 6 < 9, por lo que no se produce intercambio:`[2, 3, 4, 6, 9]`

La lista ya está ordenada, pero el algoritmo de ordenación de burbujas no se da cuenta de esto. Más bien, necesita completar una pasada completa a través de la lista sin intercambiar ningún valor para saber que la lista está ordenada.

#### **Tercer paso por la lista:** <a href="#tercer-paso-por-la-lista" id="tercer-paso-por-la-lista"></a>

* `[2, 3, 4, 6, 9]` => `[2, 3, 4, 6, 9]`
* `[2, 3, 4, 6, 9]` => `[2, 3, 4, 6, 9]`
* `[2, 3, 4, 6, 9]` => `[2, 3, 4, 6, 9]`
* `[2, 3, 4, 6, 9]` => `[2, 3, 4, 6, 9]`

Claramente, la ordenación por burbujas está lejos de ser el algoritmo de ordenación más eficiente. Aún así, es simple entenderlo e implementarlo por ti mismo.

**Propiedades**

* Complejidad del espacio: O(1)
* Rendimiento en el mejor caso: O(n)
* Rendimiento promedio de casos: O(n\*n)
* Rendimiento en el peor de los casos: O(n\*n)
* Estable: Sí

#### **Vídeo Explicación (en inglés)** <a href="#v-deo-explicaci-n-en-ingl-s" id="v-deo-explicaci-n-en-ingl-s"></a>

[Algoritmo de ordenación de burbujas](https://www.youtube.com/watch?v=Jdtq5uKz-w4)

#### **Ejemplo en JavaScript** <a href="#ejemplo-en-javascript" id="ejemplo-en-javascript"></a>

```js
let arr = [1, 4, 7, 45, 7,43, 44, 25, 6, 4, 6, 9],
    sorted = false;

while(!sorted) {
  sorted = true;
  for(var i=0; i < arr.length; i++) {
    if(arr[i] < arr[i-1]) {
      let temp = arr[i];
      arr[i] = arr[i-1];
      arr[i-1] = temp;
      sorted = false;
    }
  }
}
```

#### **Ejemplo en Java** <a href="#ejemplo-en-java" id="ejemplo-en-java"></a>

```java
public class BubbleSort {
    static void sort(int[] arr) {
        int n = arr.length;
        int temp = 0;
         for(int i=0; i < n; i++){
                 for(int x=1; x < (n-i); x++){
                          if(arr[x-1] > arr[x]){
                                 temp = arr[x-1];
                                 arr[x-1] = arr[x];
                                 arr[x] = temp;
                         }

                 }
         }

    }
    public static void main(String[] args) {

		for(int i=0; i < 15; i++){
			int arr[i] = (int)(Math.random() * 100 + 1);
		}

                System.out.println("array before sorting\n");
                for(int i=0; i < arr.length; i++){
                        System.out.print(arr[i] + " ");
                }
                bubbleSort(arr);
                System.out.println("\n array after sorting\n");
                for(int i=0; i < arr.length; i++){
                        System.out.print(arr[i] + " ");
                }

        }
}
```

#### **Ejemplo en C++** <a href="#ejemplo-en-c" id="ejemplo-en-c"></a>

```cpp
// Implementación recursiva
void bubblesort(int arr[], int n)
{
	if(n==1)	//Initial Case  
//Caso inicial
		return;
	bool swap_flag = false;
	for(int i=0;i<n-1;i++)	//Después de este paso, el elemento más grande se moverá a la ubicación deseada.
	{
		if(arr[i]>arr[i+1])
		{
			int temp=arr[i];
			arr[i]=arr[i+1];
			arr[i+1]=temp;
			swap_flag = true;
		}
	}
               
// SI no se intercambiaron dos elementos en el ciclo, luego regresa, ya que el arreglo está ordenado
	if(swap_flag == false)
		return;
	bubblesort(arr,n-1);	//Recursividad para el arreglo restante
}
```

#### **Ejemplo en Swift** <a href="#ejemplo-en-swift" id="ejemplo-en-swift"></a>

```swift
func bubbleSort(_ inputArray: [Int]) -> [Int] {
    guard inputArray.count > 1 else { return inputArray } 
    // asegúrandose de que nuestro arreglo de entrada tenga más de 1 elemento
    var numbers = inputArray // los argumentos de la función son constantes por defecto en Swift, así que hacemos una copia
    for i in 0..<(numbers.count - 1) {
        for j in 0..<(numbers.count - i - 1) {
            if numbers[j] > numbers[j + 1] {
                numbers.swapAt(j, j + 1)
            }
        }
    }
    return numbers // devuelve el arreglo ordenado
} 
```

#### **Ejemplo en Python** <a href="#ejemplo-en-python" id="ejemplo-en-python"></a>

```py
def bubbleSort(arr): 
    n = len(arr) 
    for i in range(n):
        for j in range(0, n-i-1):
                if arr[j] > arr[j+1] : 
                        arr[j], arr[j+1] = arr[j+1], arr[j]
    print(arr)
```

#### **Ejemplo en PHP** <a href="#ejemplo-en-php" id="ejemplo-en-php"></a>

```php
function bubble_sort($arr) {
    $size = count($arr)-1;
    for ($i=0; $i<$size; $i++) {
        for ($j=0; $j<$size-$i; $j++) {
            $k = $j+1;
            if ($arr[$k] < $arr[$j]) {
                // Intercambiar elementos en índices: $j, $k
                list($arr[$j], $arr[$k]) = array($arr[$k], $arr[$j]);
            }
        }
    }
    return $arr; // devuelve el arreglo ordenado
}

$arr = array(1,3,2,8,5,7,4,0);
print("Antes de ordenar");
print_r($arr);

$arr = bubble_sort($arr);
print("Después de ordenar usando ordenación por burbujas");
print_r($arr);
```

#### **Ejemplo en C**  <a href="#ejemplo-en-c" id="ejemplo-en-c"></a>

```c
#include <stdio.h>

int BubbleSort(int array[], int n);

int main(void) {
  int arr[] = {10, 2, 3, 1, 4, 5, 8, 9, 7, 6};
  BubbleSort(arr, 10);

  for (int i = 0; i < 10; i++) {
    printf("%d", arr[i]);
  }
  return 0;
}
int BubbleSort(int array[], n)
{
for (int i = 0 ; i < n - 1; i++)
  {
    for (int j = 0 ; j < n - i - 1; j++)     //n es la longitud del arreglo
    {
      if (array[j] > array[j+1])      // Para uso en orden decreciente
      {
        int swap   = array[j];
        array[j]   = array[j+1];
        array[j+1] = swap;
      }
    }
  }
}
```

### **Ordenación rápida** <a href="#ordenaci-n-r-pida" id="ordenaci-n-r-pida"></a>

Quick sort es un eficiente algoritmo de ordenación divide y vencerás. La complejidad de tiempo del caso promedio de Quick Sort es O (nlog (n)) y la complejidad de tiempo del peor caso es O (n ^ 2) dependiendo de la selección del elemento pivote, que divide el arreglo actual en dos sub arreglos.

Por ejemplo, la complejidad de tiempo de Quick Sort es aproximadamente `O(nlog(n))` cuando la selección del pivote divide el arreglo original en dos subarreglos de tamaño casi igual.

Por otro lado, si el algoritmo, que selecciona el elemento pivote de los arreglos de entrada, genera consistentemente 2 subarreglos con una gran diferencia en términos de tamaños de arreglo, el algoritmo de ordenación rápida puede lograr la complejidad de tiempo del peor caso de O(n^2 ).

Los pasos involucrados en Quick Sort son:

* Elige un elemento para que sirva como pivote, en este caso, el último elemento del arreglo es el pivote.
* Particionamiento: Ordena el arreglo de tal manera que todos los elementos menores que el pivote estén a la izquierda y todos los elementos mayores que el pivote estén a la derecha.
* Llama a Quicksort de forma recursiva, teniendo en cuenta el pivote anterior para subdividir adecuadamente los arreglos izquierdo y derecho. (Se puede encontrar una explicación más detallada en los comentarios a continuación)

### **Implementaciones de ejemplo en varios lenguajes** <a href="#implementaciones-de-ejemplo-en-varios-lenguajes" id="implementaciones-de-ejemplo-en-varios-lenguajes"></a>

#### **Implementación en JavaScript:** <a href="#implementaci-n-en-javascript" id="implementaci-n-en-javascript"></a>

```js
const arr = [6, 2, 5, 3, 8, 7, 1, 4];

const quickSort = (arr, start, end) => {

  if(start < end) {

   // Puedes obtener información sobre cómo se deriva el valor de pivote en los comentarios a continuación
    let pivot = partition(arr, start, end);

   // Asegúrate de leer los comentarios a continuación para comprender por qué se usan pivote - 1 y pivote + 1
// Estas son las llamadas recursivas a quickSort
    quickSort(arr, start, pivot - 1);
    quickSort(arr, pivot + 1, end);
  } 

}

const partition = (arr, start, end) => { 
  let pivot = end;
    // Establece i en start - 1 para que puedas acceder al primer índice en caso de que el valor en arr[0] sea mayor que arr[pivot]
  // Los comentarios posteriores se expondrán sobre el comentario anterior
  let i = start - 1,
      j = start;

  // Incrementa j hasta el índice que precede al pivote
  while (j < pivot) {

    // If the value is greater than the pivot increment j
    // Si el valor es mayor que el pivote incrementa j
    if (arr[j] > arr[pivot]) {
      j++;
    }

    // Cuando el valor en arr[j] es menor que el pivote:
    // incrementa i (arr[i] será un valor mayor que arr[pivot]) e intercambia el valor en arr[i] y arr[j]
    else {
      i++;
      swap(arr, j, i);
      j++;
    }

  }

  //El valor de arr[i + 1] será mayor que el valor de arr[pivot]
  swap(arr, i + 1, pivot);

    //Devuelves i + 1, ya que los valores a la izquierda son menores que arr[i+1], y los valores a la derecha son mayores que arr[i + 1]
   // Como tal, cuando se llama a las ordenaciones rápidas recursivas, los nuevos subconjuntos no incluirán este valor de pivote utilizado anteriormente 
  return i + 1;
}

const swap = (arr, firstIndex, secondIndex) => {
  let temp = arr[firstIndex];
  arr[firstIndex] = arr[secondIndex];
  arr[secondIndex] = temp;
}

quickSort(arr, 0, arr.length - 1);
console.log(arr);
```

#### **Implementación en C** <a href="#implementaci-n-en-c" id="implementaci-n-en-c"></a>

```c
#include<stdio.h>  
void swap(int* a, int* b) 
{ 
    int t = *a; 
    *a = *b; 
    *b = t; 
}
int partition (int arr[], int low, int high) 
{ 
    int pivot = arr[high];     
    int i = (low - 1);  
  
    for (int j = low; j <= high- 1; j++) 
    { 
        if (arr[j] <= pivot) 
        { 
            i++;    
            swap(&arr[i], &arr[j]); 
        } 
    } 
    swap(&arr[i + 1], &arr[high]); 
    return (i + 1); 
}
void quickSort(int arr[], int low, int high) 
{ 
    if (low < high) 
    {
        int pi = partition(arr, low, high); 
  
        quickSort(arr, low, pi - 1); 
        quickSort(arr, pi + 1, high); 
    } 
} 
  

void printArray(int arr[], int size) 
{ 
    int i; 
    for (i=0; i < size; i++) 
        printf("%d ", arr[i]); 
    printf("n"); 
} 
  

int main() 
{ 
    int arr[] = {10, 7, 8, 9, 1, 5}; 
    int n = sizeof(arr)/sizeof(arr[0]); 
    quickSort(arr, 0, n-1); 
    printf("Sorted array: n"); 
    printArray(arr, n); 
    return 0; 
} 
```

#### **Implementación en Python3** <a href="#implementaci-n-en-python3" id="implementaci-n-en-python3"></a>

```
import random

z=[random.randint(0,100) for i in range(0,20)]

def quicksort(z):
    if(len(z)>1):        
        piv=int(len(z)/2)
        val=z[piv]
        lft=[i for i in z if i<val]
        mid=[i for i in z if i==val]
        rgt=[i for i in z if i>val]

        res=quicksort(lft)+mid+quicksort(rgt)
        return res
    else:
        return z
        
ans1=quicksort(z)
print(ans1)
```

#### **Implementación en MATLAB** <a href="#implementaci-n-en-matlab-1" id="implementaci-n-en-matlab-1"></a>

```
a = [9,4,7,3,8,5,1,6,2];

sorted = quicksort(a,1,length(a));

function [unsorted] =  quicksort(unsorted, low, high)
    if low < high
        [pInd, unsorted] = partition(unsorted, low, high);
        unsorted = quicksort(unsorted, low, pInd-1);
        unsorted = quicksort(unsorted, pInd+1, high);
    end

end

function [pInd, unsorted] = partition(unsorted, low, high)
    i = low-1;
    for j = low:1:high-1
        if unsorted(j) <= unsorted(high)
            i = i+1;
            unsorted([i,j]) = unsorted([j,i]);
            
        end
    end
    unsorted([i+1,high]) = unsorted([high,i+1]);
    pInd = i+1;

end
```

La complejidad espacial de ordenación rápida es `O(n)`. Esta es una mejora con respecto a otros algoritmos de ordenación de divide y vencerás, que ocupan espacio `O(nlong(n))`.

La ordenación rápida logra esto cambiando el orden de los elementos dentro del arreglo dado. Compara esto con el algoritmo [de ordenación por combinación](https://guide.freecodecamp.org/algorithms/sorting-algorithms/merge-sort) que crea 2 arreglos, cada longitud `n/2`, en cada llamada de función.

Sin embargo, existe el problema de que este algoritmo de ordenación es de tiempo `O(n*n)`si el pivote siempre se mantiene en el medio. Esto se puede superar utilizando un pivote aleatorio.

#### **Complejidad** <a href="#complejidad" id="complejidad"></a>

Mejor, promedio, peor, memoria: n log(n)n log(n)n 2log(n). No es un algoritmo estable, y la ordenación rápida generalmente se realiza en el lugar con el espacio de pila O (log (n)).

La complejidad espacial de ordenación rápida es O(n). Esta es una mejora con respecto a otros algoritmos de ordenación de divide y vencerás, que ocupan espacio O(n log(n)).

### **Timsort** <a href="#timsort" id="timsort"></a>

Timsort es un algoritmo de ordenación rápido que funciona con una complejidad estable de O(N log(N)).

Timsort es una mezcla de Insertion Sort y Mergesort. Este algoritmo se implementa en Arrays.sort() de Java, así como en sorted() y sort() de Python. Las partes más pequeñas se ordenan mediante Ordenación por inserción y luego se fusionan mediante Mergesort.

Una implementación rápida en Python:

```py
def binary_search(the_array, item, start, end):
    if start == end:
        if the_array[start] > item:
            return start
        else:
            return start + 1
    if start > end:
        return start

    mid = round((start + end)/ 2)

    if the_array[mid] < item:
        return binary_search(the_array, item, mid + 1, end)

    elif the_array[mid] > item:
        return binary_search(the_array, item, start, mid - 1)

    else:
        return mid

"""
Ordenación por inserción que usa timsort si el tamaño del arreglo es pequeño o si el tamaño de la "carrera" es pequeño
"""
def insertion_sort(the_array):
    l = len(the_array)
    for index in range(1, l):
        value = the_array[index]
        pos = binary_search(the_array, value, 0, index - 1)
        the_array = the_array[:pos] + [value] + the_array[pos:index] + the_array[index+1:]
    return the_array

def merge(left, right):
    """
  Toma dos listas ordenadas y devuelve una sola lista ordenada comparando los
    elementos de uno en uno.
    [1, 2, 3, 4, 5, 6]
    """
    if not left:
        return right
    if not right:
        return left
    if left[0] < right[0]:
        return [left[0]] + merge(left[1:], right)
    return [right[0]] + merge(left, right[1:])

def timsort(the_array):
    runs, sorted_runs = [], []
    length = len(the_array)
    new_run = [the_array[0]]

    # para cada i en el rango de 1 a la longitud del arreglo
    for i in range(1, length):
        # si i está al final de la lista
        if i == length - 1:
            new_run.append(the_array[i])
            runs.append(new_run)
            break
        # si el i-ésimo elemento del arreglo es menor que el anterior
        if the_array[i] < the_array[i-1]:
            # si new_run se establece en Ninguno (NULL)
            if not new_run:
                runs.append([the_array[i]])
                new_run.append(the_array[i])
            else:
                runs.append(new_run)
                new_run = []
        # de lo contrario si es igual o mayor 
        else:
            new_run.append(the_array[i])

    # para cada elemento en las ejecuciones, agrégalo usando la ordenación por inserción
    for item in runs:
        sorted_runs.append(insertion_sort(item))
    
    # por cada ejecución en sorted_runs, fusionarlos

    sorted_array = []
    for run in sorted_runs:
        sorted_array = merge(sorted_array, run)

    print(sorted_array)

timsort([2, 3, 1, 5, 6, 7])
```

#### **Complejidad:** <a href="#complejidad" id="complejidad"></a>

Tim sort tiene una complejidad estable de O(N log(N)) y se compara muy bien con Quicksort. [En este cuadro](https://cdn-images-1.medium.com/max/1600/1*1CkG3c4mZGswDShAV9eHbQ.png) se puede encontrar una comparación de complejidades.

### **Merge Sort (Ordenar por fusión)** <a href="#merge-sort-ordenar-por-fusi-n" id="merge-sort-ordenar-por-fusi-n"></a>

Merge Sort es un algoritmo [Divide y vencerás](https://guide.freecodecamp.org/algorithms/divide-and-conquer-algorithms). Divide el arreglo de entrada en dos mitades, se llama a sí mismo para las dos mitades y luego fusiona las dos mitades ordenadas. La mayor parte del algoritmo tiene dos matrices ordenadas, y tenemos que fusionarlas en un único arreglo ordenado. Todo el proceso de ordenar un arreglo de N enteros se puede resumir en tres pasos:

* Divide el arreglo en dos mitades.
* Ordena la mitad izquierda y la mitad derecha usando el mismo algoritmo recurrente.
* Combina las mitades ordenadas.

Hay algo conocido como el [algoritmo de dos dedos](https://en.wikipedia.org/wiki/Cheney's_algorithm) que nos ayuda a fusionar dos arreglos ordenados. El uso de esta subrutina y la llamada a la función de ordenación por fusión en las mitades del arreglo de forma recursiva nos dará el arreglo ordenado final que estamos buscando.

Dado que este es un algoritmo basado en la recursión, tenemos una relación de recurrencia para él. Una relación de recurrencia es simplemente una forma de representar un problema en términos de sus subproblemas.

`T(n) = 2 * T(n / 2) + O(n)`

Poniéndolo en lenguaje sencillo, dividimos el subproblema en dos partes en cada paso y tenemos una cantidad lineal de trabajo que tenemos que hacer para unir las dos mitades ordenadas en cada paso.

#### **Complejidad** <a href="#complejidad-1" id="complejidad-1"></a>

La mayor ventaja de usar Merge sort es que la [complejidad del tiempo](https://www.youtube.com/watch?v=V42FBiohc6c\&list=PL2_aWCzGMAwI9HK8YPVBjElbLbI3ufctn) es solo n\*log(n) para ordenar un Array completo. Es mucho mejor que n ^ 2 tiempo de ejecución de ordenación de burbuja o ordenación de inserción.

Antes de escribir el código, comprendamos cómo funciona la ordenación por combinación o fusión con la ayuda de un diagrama.

<figure><img src="https://www.freecodecamp.org/news/content/images/2021/06/4712ef1a5d856dbb4af393fcc08a820a38787395.png" alt="4712ef1a5d856dbb4af393fcc08a820a38787395" height="400" width="600"><figcaption></figcaption></figure>

* Inicialmente tenemos un arreglo de 6 enteros no ordenados Arr(5, 8, 3, 9, 1, 2)
* Dividimos el arreglo en dos mitades Arr1 = (5, 8, 3) y Arr2 = (9, 1, 2).
* De nuevo, los dividimos en dos mitades: Arr3 = (5, 8) and Arr4 = (3) and Arr5 = (9, 1) and Arr6 = (2)
* De nuevo, los dividimos en dos mitades: Arr7 = (5), Arr8 = (8), Arr9 = (9), Arr10 = (1) y Arr6 = (2)
* Ahora compararemos los elementos en estos subconjuntos para fusionarlos.

#### **Propiedades:** <a href="#propiedades--1" id="propiedades--1"></a>

* Complejidad espacial: O(n)
* Complejidad temporal: O(n\*log(n)). La complejidad del tiempo para Merge Sort podría no ser obvia a primera vista. El factor log(n) que entra se debe a la relación de recurrencia que hemos mencionado antes.
* Ordenar en el lugar: No en una implementación típica
* Estable: Sí
* Paralelizable: sí (varias variantes paralelas se analizan en la tercera edición de Introducción a los algoritmos de Cormen, Leiserson, Rivest y Stein).

#### **Implementación de C++** <a href="#implementaci-n-de-c--1" id="implementaci-n-de-c--1"></a>

```cpp
void merge(int array[], int left, int mid, int right)
{
    int i, j, k;

    // Tamaño de la sublista izquierda
int size_left = mid - left + 1;

// Tamaño de la sublista derecha
int size_right =  right - mid;

/* crea arreglos temporales */
int Left[size_left], Right[size_right];

/* Copiar datos a arreglos temporales L[] y R[] */
for(i = 0; i < size_left; i++)
{
    Left[i] = array[left+i];
}

for(j = 0; j < size_right; j++)
{
    Right[j] = array[mid+1+j];
}

// Combinar los arreglos temporales de nuevo en arr[left..right]
i = 0; // Índice inicial del subarreglo izquierdo
j = 0; // Índice inicial del subarreglo derecho
k = left; // Índice inicial del subarreglo fusionado

while (i < size_left && j < size_right)
{
    if (Left[i] <= Right[j])
    {
        array[k] = Left[i];
        i++;
    }
    else
    {
        array[k] = Right[j];
        j++;
    }
    k++;
}

// Copia los elementos restantes de Left[]
while (i < size_left)
{
    array[k] = Left[i];
    i++;
    k++;
}

// Copiar el resto de elementos de Right[]
while (j < size_right)
{
    array[k] = Right[j];
    j++;
    k++;
}
}

void mergeSort(int array[], int left, int right)
{
    if(left < right)
    {
        int mid = (left+right)/2;

        // Ordenar la primera y la segunda mitad
    mergeSort(array, left, mid);
    mergeSort(array, mid+1, right);

    // Finalmente fusionarlas
    merge(array, left, mid, right);
}
}
```

#### **Implementación de JavaScript** <a href="#implementaci-n-de-javascript" id="implementaci-n-de-javascript"></a>

```js
function mergeSort (arr) {
  if (arr.length < 2) return arr;
  var mid = Math.floor(arr.length /2);
  var subLeft = mergeSort(arr.slice(0,mid));
  var subRight = mergeSort(arr.slice(mid));
  return merge(subLeft, subRight);
}
```

Primero verificamos la longitud del arreglo. Si es 1, simplemente devolvemos el arreglo. Este sería nuestro caso base. De lo contrario, encontraremos el valor medio y dividiremos el arreglo en dos mitades. Ahora ordenaremos ambas mitades con llamadas recursivas a la función MergeSort.

```js
function merge (a,b) {
    var result = [];
    while (a.length >0 && b.length >0)
        result.push(a[0] < b[0]? a.shift() : b.shift());
    return result.concat(a.length? a : b);
}
```

Cuando fusionamos las dos mitades, almacenamos el resultado en un arreglo auxiliar. Compararemos el elemento inicial del arreglo izquierdo con el elemento inicial del arreglo derecho. Cualquiera que sea menor se insertará en el arreglo de resultados y lo eliminaremos de los arreglos respectivos usando el operador \[shift()]. Si aún terminamos con valores en el arreglo izquierdo o derecho, simplemente los concatenaremos al final del resultado. Aquí está el resultado ordenado:

```js
var test = [5,6,7,3,1,3,15];
console.log(mergeSort(test));

>> [1, 3, 3, 5, 6, 7, 15]
```

#### **Un tutorial de YouTube de ordenación por combinación** <a href="#un-tutorial-de-youtube-de-ordenaci-n-por-combinaci-n" id="un-tutorial-de-youtube-de-ordenaci-n-por-combinaci-n"></a>

Aquí hay un buen video de YouTube que [explica el tema en detalle](https://www.youtube.com/watch?v=TzeBrDU-JaY) .

#### **Implementación en JS** <a href="#implementaci-n-en-js" id="implementaci-n-en-js"></a>

```js
const list = [23, 4, 42, 15, 16, 8, 3]

const mergeSort = (list) =>{
  if(list.length <= 1) return list;
  const middle = list.length / 2 ;
  const left = list.slice(0, middle);
  const right = list.slice(middle, list.length);
  return merge(mergeSort(left), mergeSort(right));
}

const merge = (left, right) => {
  var result = [];
  while(left.length || right.length) {
    if(left.length && right.length) {
      if(left[0] < right[0]) {
        result.push(left.shift())
      } else {
        result.push(right.shift())
      }
    } else if(left.length) {
        result.push(left.shift())
      } else {
        result.push(right.shift())
      }
    }
  return result;
}

console.log(mergeSort(list)) // [ 3, 4, 8, 15, 16, 23, 42 ]
```

#### **Implementación en C** <a href="#implementaci-n-en-c-1" id="implementaci-n-en-c-1"></a>

```c
#include<stdlib.h> 
#include<stdio.h>
void merge(int arr[], int l, int m, int r) 
{ 
    int i, j, k; 
    int n1 = m - l + 1; 
    int n2 =  r - m; 
  
    
    int L[n1], R[n2]; 
  
    for (i = 0; i < n1; i++) 
        L[i] = arr[l + i]; 
    for (j = 0; j < n2; j++) 
        R[j] = arr[m + 1+ j];
    i = 0; 
    j = 0; 
    k = l; 
    while (i < n1 && j < n2) 
    { 
        if (L[i] <= R[j]) 
        { 
            arr[k] = L[i]; 
            i++; 
        } 
        else
        { 
            arr[k] = R[j]; 
            j++; 
        } 
        k++; 
    } 
  
    
    while (i < n1) 
    { 
        arr[k] = L[i]; 
        i++; 
        k++; 
    } 
  
    while (j < n2) 
    { 
        arr[k] = R[j]; 
        j++; 
        k++; 
    } 
} 
  
void mergeSort(int arr[], int l, int r) 
{ 
    if (l < r) 
    {  
        int m = l+(r-l)/2; 
  
        
        mergeSort(arr, l, m); 
        mergeSort(arr, m+1, r); 
  
        merge(arr, l, m, r); 
    } 
}
void printArray(int A[], int size) 
{ 
    int i; 
    for (i=0; i < size; i++) 
        printf("%d ", A[i]); 
    printf("\n"); 
} 
int main() 
{ 
    int arr[] = {12, 11, 13, 5, 6, 7}; 
    int arr_size = sizeof(arr)/sizeof(arr[0]); 
  
    printf("Given array is \n"); 
    printArray(arr, arr_size); 
  
    mergeSort(arr, 0, arr_size - 1); 
  
    printf("\nSorted array is \n"); 
    printArray(arr, arr_size); 
    return 0; 
```

#### **Implementación en C++** <a href="#implementaci-n-en-c" id="implementaci-n-en-c"></a>

Consideremos el arreglo A = {2,5,7,8,9,12,13} y el arreglo B = {3,5,6,9,15} y queremos que el arreglo C también esté en orden ascendente.

```cpp
void mergesort(int A[],int size_a,int B[],int size_b,int C[])
{
     int token_a,token_b,token_c;
     for(token_a=0, token_b=0, token_c=0; token_a<size_a && token_b<size_b; )
     {
          if(A[token_a]<=B[token_b])
               C[token_c++]=A[token_a++];
          else
               C[token_c++]=B[token_b++];
      }
      
      if(token_a<size_a)
      {
          while(token_a<size_a)
               C[token_c++]=A[token_a++];
      }
      else
      {
          while(token_b<size_b)
               C[token_c++]=B[token_b++];
      }

}
```

#### **Implementación en Python** <a href="#implementaci-n-en-python-1" id="implementaci-n-en-python-1"></a>

```py
def merge(left,right,compare):
	result = [] 
	i,j = 0,0
	while (i < len(left) and j < len(right)):
		if compare(left[i],right[j]):
			result.append(left[i])
			i += 1
		else:
			result.append(right[j])
			j += 1
	while (i < len(left)):
		result.append(left[i])
		i += 1
	while (j < len(right)):
		result.append(right[j])
		j += 1
	return result

def merge_sort(arr, compare = lambda x, y: x < y):
    #Utilizando la función lambda para ordenar el arreglo en orden (creciente y decreciente).
     #Por defecto ordena el arreglo en orden creciente
	if len(arr) < 2:
		return arr[:]
	else:
		middle = len(arr) // 2
		left = merge_sort(arr[:middle], compare)
		right = merge_sort(arr[middle:], compare)
		return merge(left, right, compare) 

arr = [2,1,4,5,3]
print(merge_sort(arr))
```

#### **Implementación en Java** <a href="#implementaci-n-en-java-1" id="implementaci-n-en-java-1"></a>

```java
public class mergesort {

	public static int[] mergesort(int[] arr,int lo,int hi) {
		
		if(lo==hi) {
			int[] ba=new int[1];
			ba[0]=arr[lo];
			return ba;
		}
		
		int mid=(lo+hi)/2;
		int arr1[]=mergesort(arr,lo,mid);
		int arr2[]=mergesort(arr,mid+1,hi);
		return merge(arr1,arr2);
	}
	
	public static int[] merge(int[] arr1,int[] arr2) {
		int i=0,j=0,k=0;
		int n=arr1.length;
		int m=arr2.length;
		int[] arr3=new int[m+n];
		while(i<n && j<m) {
			if(arr1[i]<arr2[j]) {
				arr3[k]=arr1[i];
				i++;
			}
			else {
				arr3[k]=arr2[j];
				j++;
			}
			k++;
		}
		
		while(i<n) {
			arr3[k]=arr1[i];
			i++;
			k++;
		}
		
		while(j<m) {
			arr3[k]=arr2[j];
			j++;
			k++;
		}
		
		return arr3;
		
	}
	
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int arr[]= {2,9,8,3,6,4,10,7};
		int[] so=mergesort(arr,0,arr.length-1);
		for(int i=0;i<arr.length;i++)
			System.out.print(so[i]+" ");
	}

}
```

#### **Ejemplo en Java** <a href="#ejemplo-en-java-1" id="ejemplo-en-java-1"></a>

```java
public class mergesort {
  public static int[] mergesort(int[] arr, int lo, int hi) {
    if (lo == hi) {
      int[] ba = new int[1];
      ba[0] = arr[lo];
      return ba;
    }
    int mid = (lo + hi) / 2;
    int arr1[] = mergesort(arr, lo, mid);
    int arr2[] = mergesort(arr, mid + 1, hi);
    return merge(arr1, arr2);
  }

  public static int[] merge(int[] arr1, int[] arr2) {
    int i = 0, j = 0, k = 0;
    int n = arr1.length;
    int m = arr2.length;
    int[] arr3 = new int[m + n];
    while (i < n && j < m) {
      if (arr1[i] < arr2[j]) {
        arr3[k] = arr1[i];
        i++;
      } else {
        arr3[k] = arr2[j];
        j++;
      }
      k++;
    }
    while (i < n) {
      arr3[k] = arr1[i];
      i++;
      k++;
    }
    while (j < m) {
      arr3[k] = arr2[j];
      j++;
      k++;
    }
    return arr3;
  }

  public static void main(String[] args) {
    int arr[] = {2, 9, 8, 3, 6, 4, 10, 7};
    int[] so = mergesort(arr, 0, arr.length - 1);
    for (int i = 0; i < arr.length; i++)
      System.out.print(so[i] + " ");
  }
}
```
