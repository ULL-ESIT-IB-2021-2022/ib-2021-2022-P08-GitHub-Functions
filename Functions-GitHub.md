# Práctica 8. Funciones. Repositorios de código. GitHub y git.

# Factor de ponderación: 6

### Objetivos
Los objetivos de esta práctica son que el alumnado:
* Desarrolle con mayor fluidez programas sencillos en C++.
* Profundice en el uso de funciones en sus programas.
* Conozca los conceptos básicos del desarrollo de pruebas unitarias de código y escriba a mano pruebas unitarias para sus programas.
* Comience a utilizar la plataforma Jutge para autoevaluar la corrección de sus programas.
* Comience a escribir comentarios de cabecera en todos sus ficheros de código.

### Rúbrica de evaluacion de esta práctica
En esta práctica y las siguientes ya no será admisible la presentación de un programa que, al margen de su funcionamiento,
pudiera tener deficiencias en cuanto a reglas de estilo y formato. 
Ante tal situación **la práctica se calificará como suspendida**.
Todo el código que se presente a evaluación ha de cumplir los estándares definidos en la 
[Guía de Estilo de Google para C++](https://google.github.io/styleguide/cppguide.html).

Se señalan a continuación otros aspectos (la lista no es exhaustiva) que se tendrán en cuenta a la hora de evaluar esta práctica.
El alumnado ha de acreditar que:

* Conoce los conceptos expuestos en el material de referencia de esta práctica.
* Ha realizado todos los ejercicios propuestos, así como que es capaz de desarrollar otros de complejidad similar.
* Sus programas se compilan correctamente utilizando la utilidad `make` y un fichero `Makefile`.
* Todos los identificadores que utilice en su programa (constantes, variables, etc.) deberán ser
  siempre significativos. No utilice nunca identificadores de una única letra, tal vez con la excepción de las
  variables que utilice para iterar en un bucle.
* Dispone de una cuenta en la plataforma [Jutge](https://jutge.org/) y es capaz de auto-evaluar un programa en esa plataforma.

### Comentarios de cabecera
Una buena práctica en el ámbito de la documentación del código consiste en incluir un bloque de comentarios al comienzo
de todos los ficheros de un proyecto de desarrollo de software.
El siguiente es un ejemplo de comentario de bloque que debería incluirse al comienzo de todos los ficheros
(`*.cc`, `*.h`) de sus proyectos de programación en el ámbito de esta asignatura:

```
/**
  * Universidad de La Laguna
  * Escuela Superior de Ingeniería y Tecnología
  * Grado en Ingeniería Informática
  * Informática Básica 2021-2022
  *
  * @file integer_division_and_reminder.cc
  * @author Albert Einstein aeinstein@ull.es
  * @date Feb 30 2022
  * @brief The program reads two natural numbers a and b, with b > 0, and prints 
  *        the integer division d and the remainder r of a divided by b.
  *        By definition, d and r must be the only integer numbers such that 0=<r<b and db+r=a.
  * @bug There are no known bugs
  * @see https://jutge.org/problems/P48107
  */
```

Todo fichero debiera contener (etiqueta `@brief`) una breve descripción del contenido del fichero.
Si fuera necesario se incluirá a continuación una descripción más detallada.
Obviamente el comentario específico así como el nombre del fichero debieran particularizarse para cada caso
concreto.

Incluya siempre un bloque de comentarios similar al anterior en todos sus ficheros.
Preste cuidado a la práctica habitual de "copiar y pegar" estos comentarios de un proyecto a otro, puesto que parte de la
información cambiará.

En proyectos de desarrollo de software de cierta entidad es común que este bloque de comentarios de cabecera de los ficheros
incluya además la licencia de software bajo la que se publica el programa en cuestión.
A título de ejemplo, 
[consulte el texto](https://www.gnu.org/licenses/gpl-3.0.html)
que se debiera incluir en los ficheros para publicarlos bajo licencia GPLv3.

### Pruebas Unitarias
Las pruebas unitarias (unit tests en inglés), son pruebas que se utilizan para comprobar el correcto funcionamiento de
componentes individuales de un programa.
Se llaman "unidades de código" a aquellas partes de un programa cuyo funcionamiento se comprueba mediante tests 
y habitualmente son clases, funciones o grupos ellas, e incluso todo un programa.

Las pruebas consisten en suministrar al código un conjunto de entradas y determinar si  el conjunto de salida es el esperado. 
Es decir, comprobar si los valores devueltos son correctos o no, y gestionar los fallos, en caso de que la salida no sea la esperada.
El propósito de este tipo de pruebas, es el garantizar que cada componente funcione aisladamente y que todo funciona como se espera que funcione.

Por lo general, la propia programadora que escribe el código es quien tiene que escribir 
los test unitarios para probar su código, aunque lo deseable sería que el código y los tests los escriban
equipos diferentes, puesto que quien escribe el código suele ser menos exigente a la hora de escribir
los tests.
Por otra parte conviene siempre escribir las pruebas **antes** de escribir el código que se va a probar.

A la hora de escribir tests conviene centrar la atención en aquellas entradas del programa (o unidad de código)
que son más proclives a producir errores.
Supongamos por ejemplo que se está desarrollando una función (unidad de código) que calcula la suma de dos números enteros.
Tests unitarios que validen la corrección de esa función podrían: 
* Comprobar que lo que reciba la función sean realmente dos parámetros
* Que esos dos parámetros sean números
* Que lo que devuelva la función sea otro número
* Que ese número corresponda realmente con la suma
* Que la suma se calcule correctamente para cualquier combinación de números con valores negativos, positivos o con valor cero.

Todas estas podrían ser posibles pruebas unitarias que se realicen sobre la función.
Las pruebas unitarias  se suelen desarrollar utilizando entornos de pruebas especializados que estudiaremos en el futuro
pero por ahora el propósito en la asignatura es que antes de escribir un programa se escriban a mano un conjunto de pruebas
que sirvan para, una vez finalizado el programa, acreditar la corrección del mismo al menos para un cierto número de situaciones.

La regla a seguir de ahora en adelante es **Convierta en un hábito la escritura de tests para sus programas**.

### La plataforma Jutge
[Jutge](https://jutge.org/) es una plataforma que ha sido desarrollada en la
[UPC](https://www.upc.edu/en) para uso docente en asignaturas de programación.
La plataforma ofrece una gran cantidad de problemas que los estudiantes han
de resolver y el Jutge (juez en catalán) asigna un 
[veredicto](https://jutge.org/documentation/verdicts) 
a cada solución que se suba a la plataforma.

Jutge solo evalúa los programas desde el punto de vista de la corrección del resultado que ofrecen, 
no evalúa la calidad del código en cuanto a otros aspectos: diseño, estilo, formato, etc.
Para determinar si un programa es correcto o no, Jutge aplica varios tests al programa (tests unitarios)
que tratan de acreditar la bondad de la solución, que podría ser parcialmente correcta.
Algunos de esos tests son públicos y la programadora debiera encargarse de asegurar que su programa pasa
esos tests públicos (ofrece los resultados esperados) antes de enviar el programa al juez.

[Este documento](https://docs.google.com/presentation/d/14UvZPw4OJvogp6afLeouOAODcBNo5JhgePBQfkiAkic/edit?usp=sharing)
contiene información algo más detallada sobre el uso de la plataforma Jutge. 
Estúdielas antes de comenzar a trabajar con la misma.

A la hora de escribir un programa para enviarlo a Jutge ha de tener en cuenta que el programa no ha 
de escribir otra información como salida que la requerida por los tests de Jutge.
De este modo, el mensaje inicial que se utiliza para que el programa escriba en pantalla tanto la utilidad
del mismo como su modo de uso ha de omitirse.
La recomendación que hacemos es que ese mensaje se escriba en una función que será (o no) invocada desde `main()`.

Una vez que tenga su cuenta en Jutge, realice cuantos ejercicios sea capaz de programar y súbalos para su evaluación
por el juez, hasta obtener un veredicto de 
[AC](https://jutge.org/documentation/verdicts/AC)
(Accepted).
Cuantos más problemas resuelva, más incrementará sus capacidades como programadora.

### Ejercicios
* Escriba programas que solucionen los siguientes problemas y evalúe su solución utilizando Jutge.
* Escriba todos los programas de modo que estén estructurados en funciones.
Debiera haber como mínimo dos funciones siendo `main()` una de ellas.
* Recuerde que Jutge solo evalúa la corrección de su programa desde un punto de vista del funcionamiento.
Su código ha de cumplir adicionalmente con los requisitos de modularidad, formato y estilo.

1. [P48107](https://jutge.org/problems/P48107) Integer division and remainder of two natural numbers
2. [P29973](https://jutge.org/problems/P29973) Triangle
3. [P90615](https://jutge.org/problems/P90615) Maximum of three integer numbers
4. [P70955](https://jutge.org/problems/P70955) How many seconds are they?
5. [P34279](https://jutge.org/problems/P34279) Add one Second.
6. [P51352](https://jutge.org/problems/P51352) Elementos.
7. [P51126](https://jutge.org/problems/P51126) Intervals (I)
8. [P33839](https://jutge.org/problems/P33839) Sum of Digits 
9. [P97969](https://jutge.org/problems/P97969) Counting a's (I)
10. [P80660](https://jutge.org/problems/P80660) The sequence of Collatz

### Referencias
* [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)
* [Jutge web site](https://jutge.org/)
* [Jutge information](https://docs.google.com/presentation/d/14UvZPw4OJvogp6afLeouOAODcBNo5JhgePBQfkiAkic/edit?usp=sharing)
* [Jutge documentation](https://jutge.org/documentation)

