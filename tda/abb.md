---
title: Árbol Binario de Búsqueda
permalink: /tps/abb/
trabajo: ABB
---
{% assign TP = site.data.trabajos[page.trabajo] %}

Árbol Binario de Búsqueda
=========================

El trabajo que deben entregar de **forma grupal** es el tipo de dato abstracto Árbol Binario de Búsqueda (ABB), que es la implementación del tipo `DiccionarioOrdenado` (una extensión del `Diccionario` de la entrega anterior). 
Tanto el DiccionarioOrdenado como el ABB deben estar también dentro del paquete `diccionario`.
Se incluye en [la página de descargas]({{site.skel}}) el archivo `diccionario_ordenado.go` que se describe a continuación:

```GoLang
type DiccionarioOrdenado[K comparable, V any] interface {
	Diccionario[K, V]

	IterarRango(desde *K, hasta *K, visitar func(clave K, dato V) bool)
	IteradorRango(desde *K, hasta *K) IterDiccionario[K, V]
}
```

Todas las primitivas anteriores deben funcionar también, con el agregado que tanto el iterador interno (`Iterar`) como externo (`Iterador`) deben iterar en el orden que corresponda al ordenamiento del diccionario. Se agregan las primitivas que permiten iterar por rangos dados. En caso que `desde` sea `nil`, se debe iterar desde la primera clave, y en caso de que `hasta` sea `nil` se debe iterar hasta la última (por lo cual, si `desde == hasta == nil`, se debe comportar como el iterador sin rango). 

Además, la primitiva de creación del ABB deberá ser:
```GoLang
func CrearABB[K comparable, V any](funcion_cmp func(K, K) int) DiccionarioOrdenado[K, V]
```

La función de comparación recibe dos claves y devuelve:
* Un entero menor que $0$ si la primera clave es menor que la segunda.
* Un entero mayor que $0$ si la primera clave es mayor que la segunda.
* $0$ si ambas claves son iguales.

Qué implica que una clave sea igual, mayor o menor que otra va a depender del usuario del TDA.
Por ejemplo, `strings.Compare` cumple con esta especificación (si las claves son cadenas).

Como siempre, deben subir el código completo a la [página de entregas de la materia]({{site.entregas}}).

### Estructura del módulo

Dado que el ABB es otra implementación de diccionario, simplemente deberán agregar los archivos al mismo paquete. Es decir:
```
tdas
   |--> pila
   |--> cola
   |--> lista
   |--> diccionario
   		|--> hash.go
   		|--> diccionario.go
   		|--> diccionario_test.go
   		|--> abb.go
   		|--> diccionario_ordenado.go
   		|--> diccionario_ordenado_test.go
   |--> go.mod
```

**No olviden revisar las [preguntas frecuentes del árbol binario de búsqueda](/algoritmos/faq/abb)**.

---
### Bibliografia recomendada
* Weiss, Mark Allen, "Data Structures and Algorithm Analysis": *Chapter 4: Trees*, en particular desde *4.3. The Search Tree ADT- - Binary Search Trees*.
* Cormen, Thomas H. "Introduction to Algorithms": *12. Binary Search Trees*.

