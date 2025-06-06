
La definición de funciones propias simplifica en gran medida la escritura y el mantenimiento de programas. Las funciones permiten combinar operaciones complejas en una sola. Por ejemplo, enviar un correo electrónico en un sitio web es un proceso bastante complejo que implica interactuar con sistemas externos (Internet). Gracias a la capacidad de definir funciones, toda esta complejidad puede estar oculta detrás de una función simple:

```javascript
// Ejemplo hipotético
// Lugar de donde se obtiene la función
import { send } from 'mailer';

const email = 'support@hexlet.io';
const title = 'Ayuda';
const body = 'He escrito una historia de éxito, ¿cómo puedo obtener un descuento?';

// Una pequeña llamada - y mucha lógica interna
send(email, title, body);
```

Internamente, la realización de una llamada de este tipo tiene bastante lógica. Se conecta al servidor de correo, forma una solicitud correcta basada en el encabezado y el cuerpo del mensaje, y luego lo envía, sin olvidar cerrar la conexión.

Creemos nuestra primera función. Su tarea es mostrar un saludo en la pantalla:

<pre class='hexlet-basics-output'>Hello, Hexlet!</pre>

```javascript
// Definición de la función
// La definición no llama ni ejecuta la función
// Sólo estamos diciendo que ahora existe esta función
const showGreeting = () => {
  // Dentro del cuerpo, se indentan 2 espacios para facilitar la lectura
  const text = 'Hello, Hexlet!';
  console.log(text);
}

// Llamada a la función
showGreeting(); // => Hello, Hexlet!
```

A diferencia de los datos normales, las funciones realizan acciones, por lo que sus nombres casi siempre deben ser verbos: "construir algo", "dibujar algo", "abrir algo".

Todo lo que se describe dentro de las llaves `{}` se llama cuerpo de la función. Dentro del cuerpo se puede escribir cualquier código. Considéralo como un pequeño programa independiente, un conjunto de instrucciones arbitrarias. El cuerpo se ejecuta exactamente en el momento en que se ejecuta la función. Además, cada llamada a la función ejecuta el cuerpo de forma independiente de otras llamadas. Por cierto, el cuerpo puede estar vacío:

```javascript
// Definición mínima de una función
const noop = () => {
  // Aquí podría haber código, pero no lo hay
}

noop();
```

La definición de una función se parece sospechosamente a la creación de una constante. De hecho, en realidad, la definición de una función consta de dos partes: la definición en sí `() => { }` y la asignación a una constante:

1. Definición: `() => { }`
2. Asignación: `const nameOfFunction = ...`

Técnicamente, es posible crear una función que esté simplemente definida, pero que no se pueda utilizar porque no tiene nombre:

```javascript
() => {
  // Código funcional, pero inútil
};
```

El concepto de "crear una función" tiene muchos sinónimos: "declarar", "definir" e incluso "implementar" (de la palabra implement). Todos ellos se encuentran en la práctica diaria en este trabajo.
