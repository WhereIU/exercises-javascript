
Las variables son útiles no solamente para almacenar y reutilizar información, sino también para simplificar cálculos complejos. Veamos un ejemplo: necesitamos convertir euros a yuanes a través de dólares. Los bancos a menudo realizan conversiones similares a través de una moneda intermedia al realizar compras en el extranjero.

Primero, convirtamos 50 euros a dólares. Supongamos que un euro equivale a 1.25 dólares:

```javascript
let dollarsCount = 50 * 1.25;
console.log(dollarsCount); // => 62.5
```

En la lección anterior, asignamos un valor específico a una variable. Pero aquí, `let dollarsCount = 50 * 1.25;`, a la derecha del signo igual, hay una **expresión**. El intérprete calculará el resultado, que es `62.5`, y lo asignará a la variable. Desde el punto de vista del intérprete, no importa si hay `62.5` o `50 * 1.25`, ambos son expresiones que deben evaluarse. Y se evalúan en el mismo valor, `62.5`.

Cualquier cadena de texto es una expresión. La concatenación de cadenas también es una expresión. Cuando el intérprete encuentra una expresión, la procesa y genera un resultado, que es el **valor de la expresión**. Aquí hay algunos ejemplos de expresiones y sus valores resultantes:

```javascript
62.5             // 62.5
50 * 1.25        // 62.5
120 / 10 * 2     // 24

'hello'          // hello
'Good' + 'will'  // Goodwill
```

Las reglas de construcción del código (gramática del lenguaje) permiten que en los lugares donde se espera una expresión, se pueda colocar cualquier cálculo (no solo matemático, sino también, por ejemplo, de concatenación de cadenas) y el programa seguirá funcionando. Por esta razón, no es posible describir y mostrar todos los casos de uso de todas las operaciones.

Los programas están compuestos por muchas combinaciones de expresiones, y comprender este concepto es uno de los pasos clave en tu camino.

Basándonos en lo dicho anteriormente, ¿crees que este código funcionará?

```javascript
let who = "dragon's" + 'mother';
console.log(who);
```

<details>
<summary>Respuesta</summary>

Sí, funcionará. Se imprimirá la cadena `dragon'smother`.

</details>

Volvamos a nuestro programa de conversión de moneda. Guardemos el valor del dólar en yuanes como una variable separada. Calculemos el precio de 50 euros en dólares multiplicándolos por `1.25`. Supongamos que 1 dólar equivale a 6.91 yuanes:

```javascript
let yuansPerDollar = 6.91;
let dollarsCount = 50 * 1.25; // 62.5
let yuansCount = dollarsCount * yuansPerDollar; // 431.875

console.log(yuansCount);
```

Ahora agreguemos texto a la salida utilizando concatenación:

```javascript
let yuansPerDollar = 6.91;
let dollarsCount = 50 * 1.25; // 62.5
let yuansCount = dollarsCount * yuansPerDollar; // 431.875

console.log('The price is ' + yuansCount + ' yuans');
```

<pre class='hexlet-basics-output'>
The price is 431.875 yuans
</pre>

Cualquier variable puede ser parte de cualquier expresión. En el momento de la evaluación, el valor de la variable se sustituye en lugar de su nombre.

El intérprete calcula el valor de `dollarsCount` antes de que esta variable se utilice en otras expresiones. Cuando llega el momento de usar la variable, JavaScript "conoce" su valor porque ya lo ha calculado.
