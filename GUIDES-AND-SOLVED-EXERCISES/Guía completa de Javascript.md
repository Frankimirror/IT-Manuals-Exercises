# INTRODUCCIÓN

En este artículo podrás encontrar información esencial e imprescindible sobre el lenguaje de programación Javascript. Lo iré actualizando conforme vaya aprendiendo conceptos y realizando ejercicios para que a la vez que a mí, a tí lector, te pueda servir de gran ayuda. Si ves que he cometido algún error, hablame y házmelo saber ya que puedo haber pasado por alto algo y equivocarme, te agradecería bastante que te pusieras en contacto conmigo y así tener este artículo en perfecto estado para disposición de nuevos estudiantes.
Abajo del todo, en el footer, podrás encontrar una newsletter, suscribete si quieres estar al tanto de cuando subo nuevo contenido, gracias por tu tiempo.

---

# QUÉ ES JAVASCRIPT

JavaScript es un lenguaje de programación interpretado directamente por los navegadores, firefox, opera, chrome, etc. Los programadores suelen utilizarlo para crear una página web dinámica. Desde usarlo para crear un videojuego y animaciones en la página web, a utilizarlo cómo principal lenguaje para hacer un backend. En sus frameworks más usados podemos encontrar Vue, React, node.js ...

Javascript se fundó en 1995, por Brendan Eich. Los estándares de Javascrip se definen por ECMA. Su nomenclatura es ECMAScript 10 (2019). Esto se hace para que se pueda unificar y cómo se debe escribir nuestro código

---

# JAVASCRIPT VS JAVA

Es posible llegar a pensar que Java es el diminutivo de JavaScript, pero no es así, son lenguajes de programación completamente distintos. Tienen un fuerte punto en común, ambos lenguajes provienen del lenguaje de programación C. Por tanto, Java y JavaScript tienen la misma estructura. Sin embargo, son muy diferentes en su funcionamiento y uso. Por ejemplo, JavaScript es un lenguaje interpretado, y Java es a la vez compilado e interpretado. Los programas de JavaScript son archivos de texto que se integra directamente en las páginas HTML y es interpretado (sin estar compilado) por el navegador, mientras que en Java se compilan a un archivo especial para que ser optimizados a un lenguaje intermedio llamado bytecode, y leído posteriormente en un ordenador que lo ejecute.

---

# COMANDOS BÁSICOS DE ALERTAS

Para poder empezar a trabajar con Javascript podemos hacerlo dentro de nuestro archivo .html de la siguiente forma:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <script>
	    alert("Hello world!!!")
    </script>
</body>
</html>
```

O añadiendo un archivo externo:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <script type/text="javascript" src="app.js" > </script>
</body>
</html>
```

> A partir de ahora, voy a trabajar como si tuviera un archivo fuera del html y lo tuvieramos importado, para así se comprenda todo mejor y con un código más limpio y visible 

- Para mandar un error por consola tendrás que ejecutar lo siguiente:

```
console.error("ERROR");
```

- Mandar mensaje de alerta

```
alert("WARNING");
```

- Mandar mensaje de log

```
console.log("Log");
```

- Mandar mensaje de información

```
console.info("información");
```

- Mandar mensaje  warning

```
console.warn("WARNING");
```

> En la consola del navegador podremos ejecutar cualquier script, declarar variables, etc además de poder hacer uso de diferentes herramientas para mostrar mensajes en el navegador, cómo las previamente mencionadas.

---

# VARIABLES

Existen dos tipos de variables: 
 - **Globales**: Las variables globales proporcionan valores reutilizables que se comparten entre reglas.  
 - **Locales**: es una variable temporal que existe sólo mientras se está evaluando una función definida o cuando se está ejecutando un programa definido.


Para crear una variable en javascript voy a mostrar cómo crearlas y sus diferentes tipos: 

- Cómo bien indica su nombre, las variables constantes jamás van a cambiar su valor. Se escribe de la siguiente manera:

```
const = " Hello world!!!";
```

- Las variables let pueden cambiar infinitamente su valor a diferencia de las variables constantes, se escribe de la siguiente manera:

```
let = "Hello world!!!";
```

- Las variables var funcionan igual que las variables let, ya que pueden cambiar su valor siempre que quiera

```
var = "Hello world!!!"; 
```

Las variables tienen un entorno de ejecutación que se le llama scope. Este entorno puede ser global o local, por eso existe una gran diferencia entre let y var.

> La principal diferencia entre las variables let y var es que let te permite 
> declarar variables limitando su alcance (scope) al bloque, declaración, o 
> expresión dónde se está usando. a diferencia de la variable var la cual 
> define una variable global o local en una función sin importar el ámbito del 
> bloque.

## Estándares con variables

En las variables, se suelen utilizar varios estándares, a continuación, procederé a explicar cada uno de ellos:

- Si queremos poner dos o más palabras, la inicial apartir de la segunda palabra será en mayúsculas, por ejemplo:

```
let totalPrice
let calculateTheSum
```

- Si queremos poner solo una palabra nos bastará con ponerlas en minúsculas:

```
let total
let sum 
```

- Para las constantes, el estándar es que las constantes que definamos deberán ir completamente en mayúsculas. Además si queremos poner más de dos palabras, deberán de ir acompañadas de guiones bajos:

```
const LOCATION 
const DEFAULT_LOCATION
```

---

# TIPOS DE DATOS

Podemos encontrar los siguientes tipos de datos:

> - Numers: números
> - Strings: textos
> - Booleans: true/false
> - Undefined: no definido
> - (*)Null: valor nulo

## Numbers:

- Cualquier número positivo o negativo:

```
1, 2, 3, -1, -2, -3, 0...
```

- Con decimales o sin ellos:

```
1.00 , 10000, 2.99...
```

- Puede realizar operaciones como sumas, restas, multiplicaciones y divisones. Además también puede comparar numeros. Aquí lo podemos ver de manera gráfica:

```
// + Sumar
console.log(2 + 2)
// - Restar
console.log(3 - 1)
// * Multiplicar
console.log(3 * 2)
// / Dividir
console.log(4 / 2)
// < Menor que
console.log(10 < 20)
// > Mayor que
console.log(40 > 20)
// <= Menor o igual que
console.log(10 <= 20)
// >= Mayor o igual que
console.log(50 >= 40)
// == Igual que (Check value)
console.log(40 == 40) // TRUE
console.log(40 == '40') // TRUE
// === Igual que (Check value and type)
console.log(40 === 40) // TRUE
console.log(40 === '40') // FALSE
// != No es igual que
console.log(30 !== 30)
```

>
> EJERCICIO 1. En una cena de amigos os llega la cuenta y queréis dividir entre 
> todos ¿Cuánto os toca pagar a cada uno? La cena ha costado un total de 102€ y 
> las personas que tienen que pagar serán un total de 6.
> 
> ```
> const PEOPLE = 6;
> const TOTAL_PRICE = 102;
> 
> const EACH_PERSON = totalPrice / people;
> document.write("The price to pay each person is " + eachPerson);
> ```
>

> EJERCICIO 2. En un carrito de la compra el usuario ha elegido diferentes 
> productos que deben sumarse. Y por ser su primera compra deberás aplicar un 
> total de 10% de descuento a los siguientes productos. 
> Móvil (300€) + cascos (30€) + funda (10€). Decuento del 10%
>
> ```
> const DISCOUNT = 10;
> const MOBILE = 300;
> const HEADPHONES = 30;
> const CASE= 10;
>
> const TOTAL = MOBILE + HEADPHONE + CASE;
> const DISCOUNT_TOTAL = TOTAL * DISCOUNT / 100;
> const SUBTOTAL = TOTAL - DISCOUNT_TOTAL;
> document.write("The total price with the 10% discount will be " + SUBTOTAL);
> ``` 

## Strings 

Un string es cualquier cadena de carácter o texto

```
"Hello world"
```

Se puede concatenar con otras cadenas de texto

```
"hello" + "world"
```

Además también podemos hacer comparaciones de valores, igual que..., distinto que...

> Podemos utilizar lo siguiente para poder gestionar cadenas de texto:

```
// template literals
const name = 'francmirror'
console.log(`Hello ${name} whatever`)

// typeof
console.log(typeof name)

// .length
console.log(name.length)

// .includes()
console.log(name.includes('asdfasdf'))

// .slice(start, end)
console.log(name.slice(2, 5))

// .replace(‘este texto', ‘por este otro’)
console.log(name.replace('na', 'asdfas'))

// .trim()
const text = '   as dfas a asdfasd a    '
console.log(text.trim())

// .split(‘,’)
const geolocation = 'Calle whatever. 7. 1D'
console.log(geolocation.split('.'))
```

> EJERCICIO 1. Te han pedido que incluyas en el texto de la próxima newsletter
> unas variables dinámicas que te vienen del usuario. Nombre: francmirror. 
> Videojuego: The last of us. Descuento: 30%.
>
>```
> <p class="newsletter-text"></p>
>
> const NAME = "Francmirror";
> const VIDEOGAME = "The last of us";
> const DISCOUNT = 30; 
>
> const NEWSLETTER = `Hola ${NAME}, 
>     Como regalo de bienvenida al Club de gamers,
>     queremos ofrecer un descuento del ${DISCOUNT}
>     en el próximo lanzamiento de tu interés ${GAME}
>     Esperamos lo disfrutes,
>     Un saludo,`
> 
> document.querySelector('.newsletter-text').innerHTML = NEWSLETTE> 
> document.write(NEWSLETTER)
>```

## Boolean

Solo admite dos valores: true/false. Es muy útil para comprobar ciertos estados de nuestra aplicación. Es recomendable que cuando lo declaremos le demos una posición inicial de positivo. También se le suele llamar variable bandera. Nos permitirá extraer el valor de ciertas variable o condiciones. Para gestionar los booleans podemos usar lo siguiente:

> ```
> // True (Verdadero)
>
> // 1
> // "Whatever"
> // 3.14
> // 100 > 5
> // 1 < 100
> // '1' == 1
> console.log(Boolean(1))
> console.log(Boolean('Whatever'))
> console.log(Boolean(3.14))
> console.log(Boolean(100 > 5))
> console.log(Boolean(1 < 100)> )
> console.log(Boolean('1' == 1> 
>
>
> // False (Falso)
> // 0, -0
> // ""
> // NaN
> // null
> // undefined
> // '1' === 1
> console.log(Boolean(0))
> console.log(Boolean(-0))
> console.log(Boolean(''))
> console.log(Boolean(NaN))
> console.log(Boolean(null))
> console.log(Boolean(undefined))
> console.log(Boolean('1' === 1))
> ```

> EJERCICIO 1. Mostrar una información al usuario dependiendo de si eestá 
> conectado o no. Mensaje si no está conectado: 'Debes registrarte para leer 
> este 
> artículo'. Mensaje si está conectado: 'Haz click aquí para ver el contenido'
>
> ```
> let boolean = true;
> let conectado;
> let desconectado;
>
> if (conectado == true) {
>     alert("Haz click aquí para ver el contenido")
> } else {
>     alert("Debes registrarte para leer este artículo")
> }
> 
> ```

## Undefined

Esto quiere decir que existe una ausencia de valor. Por ejemplo:

```
var a;
console.log(a)
console.log(typeof a) //undefined
```
---

# OPERADORES DE COMPARACIÓN

> - Igual =
> - Estrictamente igual ==
> 
> - Desigualdad !=
> - Desigualdad estricta !==
> 
> - Mayor que >
> - Menos que <
> 
> - Mayor o igual que >=
> - Menos o igual que <=
> 

---

# OPERADORES LÓGICOS

Los operadores lógicos comparan valores booleanos y devuelven respuestas booleanas. Se representan de la siguiente manera:

- && - AND

```
//true
let edad = 18
console.log(edad < 19 && edad >16  )
```

- || - OR

```
//true
let edad = 18
console.log(edad < 19 || edad >16  )
```

- ! - NOT
- ?? - NULLISH COALESCING

---

# TRUTHY AND FALSY

- Los valores convertibles a false se conocen como falsy o falsey, y son aquellos que cuando se encuentran en un contexto de booleano, JavaScript los convierte a false. Los valores Truthy son el resto de valores, ya que son convertibles a true. Los valores son los siguientes:

```
// todos los siguientes retornan "false"

Boolean(false)
Boolean(0)
Boolean(-0)
Boolean(0n)
Boolean("")
Boolean('')
Boolean(``)
Boolean(null)
Boolean(undefined)
Boolean(NaN)

// cualquier otro valor retorna "true"

Boolean(true)
Boolean([])
Boolean({})
Boolean('Hola mundo')
Boolean(new Date())
```
---

# COERCIÓN DE TIPOS

Llamamos esto al proceso mediante el cual JavaScript convierte el valor de una variable de un tipo a otro. También se le suele llamar Type coercion. Tenemos los siguientes ejemplos:

```
console.log(10 + "5");
console.log("10" == 10);
console.log([] == 0);
console.log(Number("10") + 10);
```

<!-- ---

# Diferencia entre == y ===
 -->
---

# ENTRADA DE DATOS POR TECLADO

- Prompt, mostramos en pantalla una sección dónde el usuario introducirá datos. por ejemplo, si pedimos al usuario datos, y estos datos que introdujo el lo almacenamos en variables.
- ParseInt, analizamos una cadena para determinar si contiene un valor entero. Esta función devuelve todas las filas que contienen un valor decimal, entero o nulo y omite las que no lo tienen. 

> Haz un programa que cargue el nombre de un usuario y su
> mail por teclado. Mostrar posteriormente los datos en pantalla:
> ```
> let name = prompt("What is your name?");
> let mail = prompt("What is your personal email");
>
> document.write("Your name is " + name);
> document.write("<br>");
> document.write("Your personal email is " + mail);
> ```

Usando prompt pedimos al usuario que escriba su nombre y su
email y por último imprimimos en pantalla los datos con un
salto de línea para que cuando se nos

---

# ESTRUCTURAS SECUENCIALES DE PROGRAMACIÓN

Las estructuras secuencial de programación es cuando en un
problema sólo participan operaciones, entradas y salidas. A
continuación vamos a realizar un problema para que podamos
comprenderlo a la perfección.

> Realizar la carga del lado de un cuadrado, mostrar por
> pantalla el perímetro del mismo (El perímetro de un
> cuadrado se calcula multiplicando el valor del lado por
> cuatro).
> ```
> let cuadrado = parseInt(prompt("Introduce la medida del lado"));
> let perimetro = parseInt(cuadrado) * 4;
>
> document.write("El perímetro del cuadrado es de " + perimetro);
> ```
>
> 1. Definimos el cuadrado y pedimos al usuario que
> introduzca la medida del lado
> 2. Definimos el perímetro, multiplicando la
> variable cuadrado por 4 (que son los lados de un cuadrado).
> 3. Imprimimos en pantalla el perímetro del
> cuadrado.

---



