---
title: TP0
permalink: /tps/tp0/
trabajo: TP0
---
{% assign TP = site.data.trabajos[page.trabajo] %}

Trabajo Práctico 0
==================

El adjunto en [el sitio de descargas]({{site.skel}}) contiene varios archivos.
Deben editar el archivo `tp0.go`, completando las cuatro funciones que
aparecen en el código fuente: `Swap()`,  `Maximo()`, `Comparar()`, `Seleccion()`, `Suma()` y `EsPalindromo()`.
Se puede ver en el archivo `tp0_interfaz.go` la documentación que indica lo que debe hacer cada función. 

De todos los archivos que pueden encontrar en el sitio de descargas, sólo deben modificar `tp0.go`. 
El resto de archivos del zip no los deben modificar. Sí pueden, no obstante, leer el archivo `tp0_test.go` para entender qué verificaciones realizaremos sobre su código.

La compilación se realiza con el siguiente comando:

    go build tp0

Las pruebas deben dar todas OK, y las pueden ejecutar con:

    go test tp0_test.go

O simplemente:
	
	go test

La entrega se hará de forma digital subiendo el código a la [página de entregas de la materia]({{site.entregas}}).
Deben entregar un archivo `zip` con los entregables. No es necesario que entreguen ningún archivo aparte de `tp0.go`. 

**No olviden revisar los [primeros pasos en Linux](/algo2/faq/primeros-pasos) y las [preguntas frecuentes](/algo2/faq/).**
