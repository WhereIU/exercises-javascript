
Muchos lenguajes, además de la estructura condicional *if*, incluyen el **switch**. Es una versión especializada del *if*, diseñada para situaciones particulares. Por ejemplo, tiene sentido utilizarlo cuando hay una cadena de *if else* con comprobaciones de igualdad. Por ejemplo:

```javascript
if (status === 'processing') {
  // Hacer algo
} else if (status === 'paid') {
  // Hacer algo más
} else if (status === 'new') {
  // Hacer algo diferente
} else {
  // Hacer algo más
}
```

Esta comprobación compuesta tiene una característica distintiva: cada rama aquí es una comprobación del valor de la variable `status`. El switch permite escribir este código de forma más concisa y expresiva:

```javascript
switch (status) {
  case 'processing': // status === processing
    // Hacer algo
    break;
  case 'paid': // status === paid
    // Hacer algo más
    break;
  case 'new': // status === new
    // Hacer algo diferente
    break;
  default: // else
    // Hacer algo más
}
```

El switch es una estructura bastante compleja en términos de la cantidad de elementos que la componen:

* Una descripción externa que incluye la palabra clave `switch`. La variable cuyos valores seleccionará el switch para determinar el comportamiento. Y llaves para las opciones de selección.
* Las construcciones `case` y `default`, dentro de las cuales se describe el comportamiento para diferentes valores de la variable considerada. Cada `case` corresponde a un `if` en el ejemplo anterior. `default` es una situación especial que corresponde a la rama `else` en las estructuras condicionales. No es obligatorio especificar `default` (pero el linter siempre lo [recomienda](https://eslint.org/docs/rules/default-case)).
* `break` se utiliza para evitar la "caída". Si no se especifica, después de ejecutar el `case` correspondiente, la ejecución pasará al siguiente `case`, y así sucesivamente hasta el siguiente `break` más cercano o hasta el final del switch.

Las llaves en el switch no definen un bloque de código como en otros lugares. Dentro de él, sólo se permite la sintaxis que se muestra arriba. Es decir, se pueden usar `case` o `default`. Pero dentro de cada `case` (y `default`) la situación es diferente. Aquí se puede ejecutar cualquier código arbitrario:

```javascript
switch (count) {
  case 1:
    // Hacer algo útil
    break;
  case 2:
    // Hacer algo útil
    break;
  default:
    // Hacer algo
}
```

A veces, el resultado obtenido dentro de un `case` es el final de la ejecución de la función que contiene el switch. En este caso, es necesario devolverlo de alguna manera al exterior. Hay dos formas de resolver este problema.

La primera es crear una variable antes del switch, asignarle un valor en los `case` y luego, al final, devolver el valor de esa variable al exterior.

```javascript
(count) => {
  // Declarar una variable
  let result;

  // Asignar un valor
  switch (count) {
    case 1:
      result = 'one';
      break;
    case 2:
      result = 'two';
      break;
    default:
      result = null;
  }

  // Devolver el valor
  return result;
};
```

La segunda forma es más simple y corta. En lugar de crear una variable, el `case` permite hacer un retorno normal de la función dentro de él. Y como después de `return` no se ejecuta ningún código, podemos prescindir del `break`:

```javascript
(count) => {
  switch (count) {
    case 1:
      return 'one';
    case 2:
      return 'two';
    default:
      return null;
  }
};
```

Aunque el switch se encuentra en el código, técnicamente siempre se puede prescindir de él. El beneficio clave de su uso es que expresa mejor la intención del programador cuando se necesitan comprobar valores específicos de una variable. Aunque el código físicamente se vuelve un poco más largo, es más fácil de leer en comparación con los bloques *else if*.
