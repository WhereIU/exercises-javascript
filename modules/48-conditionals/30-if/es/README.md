
Las estructuras condicionales permiten cambiar el comportamiento de un programa según las condiciones que se evalúen. Gracias a ellas, podemos escribir programas complejos que se comporten de manera diferente según la situación.

Por ejemplo, escribamos una función que determine el tipo de una oración dada. Al principio, esta función distinguirá entre oraciones normales y preguntas.

```javascript
const getTypeOfSentence = (sentence) => {
  const lastChar = sentence[sentence.length - 1];
  if (lastChar === '?') {
    return 'question';
  }

  return 'general';
};

getTypeOfSentence('Hodor');  // general
getTypeOfSentence('Hodor?'); // question
```

`if` es una estructura del lenguaje que controla el orden de ejecución de las instrucciones. Entre paréntesis se le pasa una expresión booleana, y luego se describe un bloque de código entre llaves. Este bloque de código se ejecutará solo si el predicado es verdadero.

Si el predicado es falso, se omitirá el bloque de código entre llaves y la función continuará su ejecución. En nuestro caso, la siguiente línea de código, `return 'general';`, hará que la función devuelva una cadena y termine.

Como puedes ver, `return` puede estar en cualquier lugar de la función, incluso dentro del bloque de código condicional.

Si después de `if` entre llaves solo hay una línea de código, las llaves se pueden omitir y hacerlo así:

```javascript
const getTypeOfSentence = (sentence) => {
  const lastChar = sentence[sentence.length - 1];
  if (lastChar === '?')
    return 'question';

  return 'general';
};

console.log(getTypeOfSentence('Hodor'));  // => general
console.log(getTypeOfSentence('Hodor?')); // => question
```

Recomendamos no hacer esto y **siempre escribir las llaves**. De esta manera, se ve claramente dónde comienza y termina el cuerpo de la condición. El código se vuelve más claro y comprensible.
