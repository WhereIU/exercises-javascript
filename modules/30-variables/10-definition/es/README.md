
Imagina que tienes la tarea de imprimir en la pantalla la frase *¡Father!* dos veces, o incluso cinco veces. Puedes resolver este problema de manera directa:

```javascript
console.log('Father!');
console.log('Father!');
```

En el caso más simple, esto funciona bien. Sin embargo, si la frase *¡Father!* se utiliza con más frecuencia, y en diferentes partes del programa, tendrás que repetirla en todas partes. Los problemas con este enfoque comienzan cuando necesitas cambiar la frase, lo cual ocurre con bastante frecuencia. Tendrás que encontrar todos los lugares donde se utiliza la frase *¡Father!* y realizar el cambio necesario. Pero hay otra forma de hacerlo. En lugar de copiar nuestra expresión, simplemente podemos crear una variable con esta frase.

```javascript
// greeting - se traduce como saludo
let greeting = '¡Father!';
console.log(greeting); // => Father!
console.log(greeting); // => Father!
```

Una variable apunta a los datos que se le han asignado. Gracias a esto, los datos se pueden utilizar múltiples veces sin necesidad de duplicarlos constantemente. La variable en sí se crea y se llena con datos (se inicializa) utilizando la instrucción `let greeting = 'Father!'`.

Para el nombre de la variable, se puede utilizar cualquier conjunto de caracteres permitidos, que incluyen letras del alfabeto inglés, números, así como los símbolos *_* y *$*. Sin embargo, no se puede colocar un número al principio. Los nombres de las variables distinguen entre mayúsculas y minúsculas, es decir, `hello` y `heLLo` son dos nombres diferentes, y por lo tanto, dos variables diferentes. En JavaScript, el registro es importante, nunca lo olvides.

No es necesario inicializar una variable con datos al momento de declararla. A veces, es necesario crearla y luego llenarla más adelante:

```javascript
let greeting;

// Uso
console.log(greeting); // undefined

// Cambiar la variable en la siguiente lección
```

Una variable declarada pero no inicializada contiene el valor `undefined`. Este es un valor especial que se utiliza cuando nada está definido.

No hay límite en la cantidad de variables que se pueden crear, los programas grandes contienen decenas o incluso cientos de miles de nombres de variables:

```javascript
let greeting1 = 'Father!';
console.log(greeting1);
console.log(greeting1);

let greeting2 = 'Mother!';
console.log(greeting2);
console.log(greeting2);
```

Para facilitar el análisis del programa, se recomienda crear variables lo más cerca posible del lugar donde se utilizan.
