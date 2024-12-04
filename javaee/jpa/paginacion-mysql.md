# Paginacion MySQL

```java
JAInteger total = VehiculosFacade.getTotalRegistros();
Integer nuJAVCAeroRegistrosPagina= 500;
if(total < numeroRegistrosPagina){
   total = numeroRegistrosPagina;
}

//Calcular las paginas
Integer paginas = total /numeroRegistrosPagina;
//creamos un método para que recorra todas las filas en base a paginas.
Integer c=0;
Integer inicio=0;
Integer fin = numeroRegistrosPagina;
while( c < paginas) {
     select * from vehiculos limit inicio,fin;
     inicio= fin;
     fin = inicio + numeroRegistrosPagina;
    c++;

}

```
