
Sabemos que hay dos tipos de datos diferentes: números y cadenas de texto. Por ejemplo, podemos sumar números porque la operación de suma es una operación para el tipo "número".

¿Pero qué sucede si aplicamos esta operación a un número y una cadena de texto?

```javascript
console.log(1 + '7'); // => 17
```

A pesar de que `'7'` es una cadena de texto y no un número, el intérprete de JavaScript devuelve el resultado `17`, como si estuviéramos concatenando dos cadenas de texto. Cuando JavaScript encuentra una incompatibilidad de tipos, intenta convertir la información por sí mismo. En este caso, convirtió el número `1` en la cadena de texto `'1'` y luego realizó la concatenación de `'1'` y `'7'`.

No todos los lenguajes hacen esto. JavaScript es un lenguaje con **tipado débil**. Conoce la existencia de diferentes tipos (números, cadenas de texto, etc.), pero no es muy estricto en su uso, intentando convertir la información cuando parece razonable. A veces, JavaScript incluso llega a extremos. La mayoría de las expresiones que no funcionan en otros lenguajes funcionan perfectamente en JavaScript. Prueba a realizar cualquier operación aritmética (excepto la suma) con cadenas de texto u otros tipos de datos (excepto cuando ambos operandos son números o cadenas de texto que contienen solo números) y verás que siempre funcionarán y devolverán `NaN`, lo cual es bastante lógico.

```javascript
const result = 'one' * 'two';
console.log(result); // => NaN
```

En los lenguajes con **tipado fuerte**, no se puede sumar un número y una cadena de texto.

JavaScript fue creado para Internet, y en Internet toda la información es una cadena de texto. Incluso cuando ingresas un número de teléfono o una fecha de nacimiento en un sitio web, esa información llega al servidor como una cadena de texto y no como un número. Por eso, los creadores del lenguaje decidieron que convertir automáticamente los tipos era correcto y conveniente.

Esta conversión automática e implícita de tipos es, por un lado, realmente conveniente. Pero en la práctica, esta característica del lenguaje crea muchos errores y problemas difíciles de encontrar. El código puede funcionar a veces y no funcionar en otras ocasiones, dependiendo de si la conversión automática tuvo "suerte" en un caso particular. El programador no se dará cuenta de esto de inmediato.

En los próximos ejercicios, te encontrarás con este comportamiento en varias ocasiones. A menudo te preguntarás "¿por qué mi código no funciona como espero?".

El tipado débil es un tema recurrente en el desarrollo en JavaScript.
