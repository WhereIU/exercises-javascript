
A veces es necesario obtener un solo carácter de una cadena. Por ejemplo, si un sitio web conoce el nombre y apellido del usuario, y en algún momento se requiere mostrar esta información en el formato *A. Ivanov*, entonces es necesario tomar el primer carácter del nombre.

```javascript
const firstName = 'Tirion';

console.log(firstName[0]); // => T
```

Los corchetes con un número son una sintaxis especial para extraer un carácter de una cadena. El número se llama **índice**, que es la posición del carácter dentro de la cadena. Los índices comienzan desde 0 en casi todos los lenguajes de programación, por lo tanto, para obtener el primer carácter, se debe especificar el índice `0`. El índice del último elemento es igual a la longitud de la cadena menos uno:

```javascript
// La longitud de la cadena es 6, por lo tanto, el último índice es 5
const firstName = 'Tirion';

console.log(firstName[5]); // => n
```

Pregunta de autoevaluación. ¿Qué mostrará este código?

```
const magic = '\nyou';
console.log(magic[1]); // => ?
```

<details>
<summary>Respuesta</summary>

Este código mostrará el carácter `y`

</details>

El índice puede ser no solamente un número específico, sino también el valor de una variable. Aquí hay un ejemplo que dará el mismo resultado, que es mostrar el carácter *T* en la pantalla, pero el índice dentro de los corchetes se escribe no como un número, sino como una constante:

```javascript
const firstName = 'Tirion';
const index = 0;

console.log(firstName[index]); // => T
```

Técnicamente, se puede especificar un índice fuera de los límites de la palabra. Para nuestro ejemplo, estos son números a partir de 6. JavaScript no considera este comportamiento como un error. Acceder a un índice inexistente devolverá el valor `undefined`.

```javascript
const firstName = 'Tirion';

console.log(firstName[10]); // => undefined
```
