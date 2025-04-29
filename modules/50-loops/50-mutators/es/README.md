
Del lenguaje C a JavaScript se han trasladado dos operaciones: **incremento** `++` y **decremento** `--`, que se encuentran muy a menudo en combinación con bucles. Estas operaciones unarias aumentan y disminuyen en uno el número almacenado en una variable:

```javascript
let i = 0;
i++; // 0
i++; // 1

i--; // 2
i--; // 1
```

Además de la forma posfija, también tienen una forma prefija:

```javascript
let i = 0;
++i; // 1
++i; // 2

--i; // 1
--i; // 0
```

Parece que no hay ninguna diferencia entre las formas posfija y prefija. Pero aquí es donde empiezan las complicaciones.

A diferencia de todas las demás operaciones, que no tienen efectos secundarios y simplemente devuelven un nuevo valor, el incremento y el decremento no solo devuelven un valor, sino que también **modifican** el valor de la variable.

Al utilizar la notación prefija, primero se produce la modificación de la variable y luego se devuelve.

Al utilizar la notación posfija, ocurre lo contrario: se puede considerar que primero se devuelve y luego se modifica la variable.

Esta regla se aplica de la misma manera tanto al incremento como al decremento. Para simplificar, consideremos solamente el incremento:

```javascript
let x = 5;

console.log(++x); // => 6
console.log(x);   // => 6

console.log(x++); // => 6
console.log(x);   // => 7
```

¿Qué está sucediendo aquí?

1. Imprimimos en la pantalla `++x`. Esto es un incremento prefijo, por lo que primero se incrementa el valor de la variable en 1, luego se devuelve el resultado y se imprime en la pantalla.
2. Como el valor ha cambiado, `console.log(x)` imprime 6.
3. Ahora imprimimos en la pantalla `x++`. Esto es un incremento posfijo, por lo que se devuelve el valor que tenía la variable antes de incrementarse en 1.
4. Como el valor ha cambiado, `console.log(x)` imprime 7.

---

Esto se vuelve especialmente confuso cuando se inserta el incremento dentro de otras operaciones: `x = i++ - 7 + --h`. Es casi imposible entender este código, y su escritura debería considerarse una violación grave.

Por ejemplo, en JavaScript, el linter (un programa que verifica el código) comienza a mostrar advertencias tan pronto como encuentra el uso de incremento o decremento.

Recomendaciones de uso:

* Nunca mezcle operaciones/funciones sin efectos secundarios con operaciones/funciones que sí los tienen en el mismo expresión.
* Utilice el incremento y el decremento solo donde no haya diferencia entre la forma prefija y la forma posfija: por separado de todo, en su propia línea de código.
