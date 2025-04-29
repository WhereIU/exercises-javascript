
Los datos con los que operamos en nuestros programas pueden tener propiedades importantes, por ejemplo, las cadenas de texto tienen una longitud. Como veremos más adelante, esta propiedad es muy importante para implementar algoritmos relacionados con la manipulación de cadenas (como invertir una cadena). ¿Cómo podemos obtener la longitud de una cadena? En muchos lenguajes de programación, la longitud de una cadena se calcula utilizando una función especial, algo así:

```javascript
import { length } from 'hexlet-basics/string';

const name = 'Robb';
console.log(length(name)); // => 4
```

En JavaScript, las propiedades están incorporadas directamente en el lenguaje. Se acceden utilizando un punto después de la variable (o constante):

```javascript
const name = 'Robb';
const len = name.length;
console.log(len); // => 4
```

Las propiedades están asociadas a los datos de los que se obtienen. Para los tipos de datos primitivos, todas las propiedades están documentadas, como por ejemplo, las [cadenas de texto](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/String). Sin embargo, los números no tienen propiedades.

JavaScript permite acceder a propiedades que no existen (por ejemplo, debido a errores de escritura). En este caso, el valor de esas propiedades es `undefined`:

```javascript
const name = 'Robb';
console.log(name.whatIsThat); // => undefined
```

*Pregunta de autoevaluación. ¿Qué imprimirá el código `console.log(name[name.length])` para `name`, definido anteriormente? ¿Por qué es esa la respuesta?*

<details>
<summary>Respuesta</summary>

El código imprimirá `undefined`, porque se está accediendo a un índice que está fuera de los límites de la cadena. En este caso, `name.length` es 4, pero el índice del último carácter en la cadena es 3.

</details>
