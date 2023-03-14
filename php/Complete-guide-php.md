# What is PHP
PHP (`Hypertext Preprocessor`) es un lenguaje OpenSource muy popular especialmente usado para el desarrollo web y que puede ser incrustado en HTML. A continuación, voy a exponer la sintaxis para que la uses en tus proyectos, ademas en mi github puedes encontrar algunos ejercicios más.
# Hello world
``` php
<?php  
echo "Hello World!";  
?>
```
# Echo vs Print
-   ECHO -> muestra una o más cadenas separadas por coma. No tiene un valor de retorno
-   PRINT -> Muestra solo una simple cadena. Devuelve 1, por lo cual puede ser usada en una expresión
# Special characters
```
`\n` -> avance de línea (LF o 0x0A (10) en ASCII)

`\r` -> retorno de carro (CR o 0x0D (13) en ASCII)

`\t` -> tabulador horizontal (HT o 0x09 (9) en ASCII)

`\v` -> tabulador vertical (VT o 0x0B (11) en ASCII) (desde PHP 5.2.5)

`\e` -> escape (ESC o 0x1B (27) en ASCII) (desde PHP 5.4.4)

`\f` -> avance de página (FF o 0x0C (12) en ASCII) (desde PHP 5.2.5)

`\\` -> barra invertida

`\$` -> signo de dólar

`\"` -> comillas dobles

`\[0-7]{1,3}` -> la secuencia de caracteres que coincida con la expresión regular es un carácter en notación octal, que silenciosamente desborda para encajar en un byte (p.ej. "\400" === "\000")

`\x[0-9A-Fa-f]{1,2}` -> la secuencia de caracteres que coincida con la expresión regular es un carácter en notación hexadecimal

`\u{[0-9A-Fa-f]+}` -> la secuencia de caracteres que coincida con la expresión regular es un punto de código de Unicode, la cual será imprimida al string como dicha representación UTF-8 del punto de código (añadido en PHP 7.0.0)
```
# Use  " " and ' ' 
' ' muestra el texto en su interior y no entiende las variables. ' ' si es capaz de representar las variables.
```php
// With ""
<?php
$animal="bear";
echo "Hello $animal"
?>
output: Hello, bear.

// With ''
<?php
$animal="bear";
echo "Hello $animal"
?>
output: Hello, $animal.
```
Para escribir más comillas en una frase podemos hacerlo de la siguiente manera:
```php
<?php
echo 'Hello, "francmirror" it\'s my name'
?>
```
# Heredoc y nowdoc
```php
// heredoc
<?php
$me=<<<SENTENCE
"Hello, my name's francmirror"
SENTENCE;
echo $me;
?>

// nowdoc
<?php
$me=<<<'SENTENCE'
"Hello, my name's francmirror"
SENTENCE;
echo $me;
?>
```
# Type conversion
```php
<?php
// Double
$price=2034.6;
// Integer
$age=20;
// String
$animal='bear';
// Boolean
$isBear=true;
?>
```
Forzar que la variable que es doble sea entera:
```php
<?php
// Double
$price=2034.6;
$price=(int)$price;
echo gettype($price)
?>

output = integer
```