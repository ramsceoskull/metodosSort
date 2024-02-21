# Metodos de ordenamiento

Los métodos de ordenamiento son algoritmos que realizan la operación de arreglar los registros de una tabla en algún orden secuencial de acuerdo a un criterio de ordenamiento. El ordenamiento se efectúa con base en el valor de algún campo en un grupo de datos. El ordenamiento puede estar dado de forma iterativa o recursiva según la naturaleza y forma de ejecución del mismo.

## Metodo de insercion

El algoritmo de ordenamiento por inserción es un algoritmo de fácil aplicación que permite el ordenamiento de una lista.
Su funcionamiento consiste en el recorrido por la lista seleccionando en cada iteración un valor como clave y compararlo con el resto insertándolo en el lugar correspondiente.

Estabilidad: estable  | Complejidad computacional:
------------- | -------------
**Método:** Inserción  | Mejor caso: O(n)
**Comparativo:** Si  | Caso promedio: O(n²)
**Uso de memoria:** 1  | Peor caso: O(n²)

```java
 public static void insercionDirecta(int A[]){                                            
    int p, j;
    int aux;
    for (p = 1; p < A.length; p++){ // desde el segundo elemento hasta
              aux = A[p];           // el final, guardamos el elemento y
              j = p - 1;            // empezamos a comprobar con el anterior
              while ((j >= 0) && (aux < A[j])){ // mientras queden posiciones y el                                
                                                // valor de aux sea menor que los
                             A[j + 1] = A[j];   // de la izquierda, se desplaza a
                             j--;               // la derecha
              }
              A[j + 1] = aux;       // colocamos aux en su sitio
    }
}
```

## Metodo de burbuja
El ordenamiento burbuja hace múltiples pasadas a lo largo de una lista. Compara los ítems adyacentes e intercambia los que no están en orden. Cada pasada a lo largo de la lista ubica el siguiente valor más grande en su lugar apropiado. En esencia, cada ítem "burbujea" hasta el lugar al que pertenece.

```java
// Algoritmo burbuja
// Repetimos el procesos n-1 veces para un arreglo de tamaño n.
        for(int i=0; i < vec.length-1; i++){
         // En cada iteración llegamos hasta n-1-i ya que hemos ordenado i enteros
         //en las i iteraciones pasadas.
               for(int j=0; j < (vec.length-1-i); j++){ 
                   //Comparamos e intercambiamos si se cumple la condición
                    if(vec[j] > vec[j+1]){ 
                            aux=vec[j];                
                            vec[j]=vec[j+1];          
                            vec[j+1]=aux;
                     }   
               }
          }
```

## Metodo de seleccion
El ordenamiento por selección mejora el ordenamiento burbuja haciendo un sólo intercambio por cada pasada a través de la lista. Para hacer esto, un ordenamiento por selección busca el valor mayor a medida que hace una pasada y, después de completar la pasada, lo pone en la ubicación correcta. Al igual que con un ordenamiento burbuja, después de la primera pasada, el ítem mayor está en la ubicación correcta. Después de la segunda pasada, el siguiente mayor está en su ubicación. Este proceso continúa y requiere n−1 pasadas para ordenar los n ítems, ya que el ítem final debe estar en su lugar después de la (n−1)-ésima pasada.

```java
// Algoritmo seleccion
public static void ordenarPorSeleccion(int[] arreglo) {
    for (int i = 0; i < arreglo.length - 1; i++) {
        for (int j = i + 1; j < arreglo.length; j++) {
            if (arreglo[i] > arreglo[j]) {
                // ...intercambiarlos, es decir, mover el actual a la derecha y el de la derecha al actual
                int temporal = arreglo[i];
                arreglo[i] = arreglo[j];
                arreglo[j] = temporal;
            }
        }
    }
}
```
