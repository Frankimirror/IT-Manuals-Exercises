## What is PHP
PHP (`Hypertext Preprocessor`) es un lenguaje OpenSource muy popular especialmente usado para el desarrollo web y que puede ser incrustado en HTML. A continuación, voy a exponer la sintaxis para que la uses en tus proyectos, ademas en mi github puedes encontrar algunos ejercicios más.
## HELLO WORLD
``` php
<?php  
echo "Hello World!";  
?>
```
## ECHO VS PRINT
-   ECHO -> muestra una o más cadenas separadas por coma. No tiene un valor de retorno
-   PRINT -> Muestra solo una simple cadena. Devuelve 1, por lo cual puede ser usada en una expresión
## CARÁCTERES ESPECIALES
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
## USO DE  " "  Y  ' ' 
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
## HEREDOC Y NOWDOC
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
## TIPOS DE CONVERSIÓN
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
echo gettype($price);
?>

output = integer
```
## CONCATENACIÓN E INTERPOLACIÓN
```php
// CONCATENACIÓN
<?php
$word1='franc';
$word2='mirror';

echo 'I am '.$word1.$word2;
?>

output = I am francmirror

//INTERPOLACIÓN

<?php
$word1='franc';
$word2='mirror';

echo "I am $word1$word2";
?>

output = I am francmirror
```
## EXTRAER Y BUSCAR
```php
// Extraer
<?php
echo substr("francmirror",5);
?>
output = mirror

<?php
echo substr("Marines Mendez Gallegos",8,6);
?>
output = mendez

<?php
echo substr("Marines Mendez Gallegos",-8);
?>
output = Gallegos

// Buscar
<?php
$newString="I am Francmirror";
$findWord="Francmirror";
echo strpos($newString,$secondString);
?>
output = 5
```
## REEMPLAZO
```php
// Reemplazar espacios
<?php
$search=" ";
$replace=":";
$text="91 75 1A EC 9A C7";
echo str_replace($search,$replace,$text);
?>
output = 91:75:1A:EC:9A:C7

// Reemplazar numero 8
<?php
$search="8";
$replace="*";
$text="93840489";
echo str_replace($search,$replace,$text);
?>
output = 93*404*9

// Contar veces que repite
<?php
$search="8";
$replace="*";
$text="93840489";
str_replace($search,$replace,$text,$count);
echo $count;
?>
output = 2
```

## FORMATEO
https://www.php.net/manual/es/function.sprintf.php
-   `%` -> un carácter de porcentaje literal. No se requiere argumento.
-   `b` -> el argumento es tratado como un valor de tipo integer y presentado como un número binario.
-   `c` -> el argumento es tratado como un valor de tipo integer y presentado como el carácter con ese valor ASCII.
-   `d` -> el argumento es tratado como un valor de tipo integer y presentado como un número decimal (con signo).
-   `e` -> el argumento es tratado con notación científica (e.g. 1.2e+2). El especificador de precisión indica el número de dígitos después del punto decimal a partir de PHP 5.2.1. En versiones anteriores, se tomó como el número de dígitos significativos (menos uno).
-   `E` -> como `%e` pero utiliza la letra mayúscula (e.g. 1.2E+2).
-   `f` -> el argumento es tratado como un valor de tipo float y presentado como un número de punto flotante (considerando la configuración regional).
-   `F` -> el argumento es tratado como un valor de tipo float y presentado como un número de punto flotante (no considerando la configuración regional). Disponible desde PHP 4.3.10 y PHP 5.0.3.
-   `g` -> lo mismo que `%e` y `%f`.
-   `G` -> lo mismo que `%E` y `%f`.
-   `o` -> el argumento es tratado como un valor de tipo integer y presentado como un número octal.
-   `s` -> el argumento es tratado y presentado como un string.
-   `u` -> el argumento es tratado como un valor de tipo integer y presentado como un número decimal sin signo.
-   `x` -> el argumento es tratado como un valor de tipo integer y presentado como un número hexadecimal (con las letras en minúsculas).
-   `X` -> el argumento es tratado como un valor de tipo integer y presentado como un número hexadecimal (con las letras en mayúsculas).

```php
<?php
$arg1=1994;
$arg2='PHP';
$text='En %d fue creado %s';
sprintf($text,$arg1,$arg2);
?>

output = En 1994 fue creado PHP
```
## PCRE
La biblioteca PCRE es un conjunto de funciones que implementan comparaciones de patrones de expresiones regulares empleando la misma sintaxis y semántica que Perl 5
-   [preg_filter](https://www.php.net/manual/es/function.preg-filter.php) — Realiza una búsqueda y sustitución de una expresión regular
-   [preg_grep](https://www.php.net/manual/es/function.preg-grep.php) — Devuelve entradas de matriz que coinciden con el patrón
-   [preg_last_error_msg](https://www.php.net/manual/es/function.preg-last-error-msg.php) — Returns the error message of the last PCRE regex execution
-   [preg_last_error](https://www.php.net/manual/es/function.preg-last-error.php) — Devuelve el código de error de la última ejecución de expresión regular de PCRE
-   [preg_match_all](https://www.php.net/manual/es/function.preg-match-all.php) — Realiza una comparación global de una expresión regular
-   [preg_match](https://www.php.net/manual/es/function.preg-match.php) — Realiza una comparación con una expresión regular
-   [preg_quote](https://www.php.net/manual/es/function.preg-quote.php) — Escapar caracteres en una expresión regular
-   [preg_replace_callback_array](https://www.php.net/manual/es/function.preg-replace-callback-array.php) — Realizar una búsqueda y sustitución de expresión regular con retrollamadas
-   [preg_replace_callback](https://www.php.net/manual/es/function.preg-replace-callback.php) — Realiza una búsqueda y sustitución de una expresión regular usando una llamada de retorno
-   [preg_replace](https://www.php.net/manual/es/function.preg-replace.php) — Realiza una búsqueda y sustitución de una expresión regular
-   [preg_split](https://www.php.net/manual/es/function.preg-split.php) — Divide un string mediante una expresión regular
## OPERADORES
- Unarios -> operando operador operando (-5)
- Binarios -> operando1 operador operando2 (5+5)
- Ternario -> operando1 operador operando2 operador operando3 (true ? 'francmirror' : 'hola')
### Comparación
```php
// IGUAL
echo var_dump($example==21);
// IDÉNTICO
echo var_dump($example===21);
// DIFERENTE
echo var_dump($example!=21);
echo var_dump($example!==21);
echo var_dump($example<>21);
// MAYOR QUE 
echo var_dump($example>21);
// MENOR QUE
echo var_dump($age<21);
// MENOR O IGUAL QUE
echo var_dump($age<=21);
// MAYOR O IGUAL QUE
echo var_dump($age>=21);
```
### Ternario, elvis y fusión  null

```php
// Ternerario = (expresion bool)?expresion:expresion;
<?php
$age=18;
echo($age>=18)?'Eres mayor de edad':'Eres menor de edad';
output = Eres mayor de edad

// Elvis (binario) 
$age=null;
echo $age?:'No hay edad';
output = No hay edad

// Fusion null
$age=null;
echo $age??'No hay edad';
output = No hay edad
?>
```
## CONDICIONALES

### If, else y else if
```php
<?php 
// If, else
$age=18;
if($age>=18){
	echo 'Puedes ver la pelicula';
} else {
	echo 'No puedes ver la pelicula';
}

// If, else if
$age=43;
if($age>=18 && $age<=30){
	echo 'Puedes ver la pelicula';
} else if($age>30) {
	echo 'Tienes demasiados años';
} else{
	echo 'Eres demasiado pequeño para la pelicula';
}
output = Tienes demasiados años
?>
```
### Switch
```php
<?php
$jeans='rojos'
switch($jeans){
	case 'amarillos':
		echo 'Son de color amarillos';
	break;
	case 'verdes':
		echo 'Son de color verdes';
	break;
	case 'marrones':
		echo 'Son de color marrones';
	break;
	default:
		echo 'No encontramos lo que busca';
	break;
}
output = No encontramos lo que busca

$jeans='rojos'
switch($jeans){
	case 'amarillos':
		echo 'Son de color amarillos';
	break;
	case 'verdes':
		echo 'Son de color verdes';
	break;
	case 'rojos':
		echo 'Son de color rojos';
	break;
	default:
		echo 'No encontramos lo que busca';
	break;
}
output = Son de color rojos
?>
```
### For
```php
<?php
for($i=1;$i<=5;$i++){
	echo "I am Francmirror $i \n";
}
output = I am Francmirror 1
		 I am Francmirror 2
		 I am Francmirror 3
		 I am Francmirror 4
		 I am Francmirror 5
?>
```

### While, Do while
```php
<?php
// While
$cont=1;
while($cont<=5){
	echo "Camiseta numero $cont \n";
	$cont++;
}
output = Camiseta numero 1
		 Camiseta numero 2
		 Camiseta numero 3
		 Camiseta numero 4
		 Camiseta numero 5

// Do while
$cont=1;
do{
	echo "Camiseta numero $cont \n";
	$cont++;
} while($cont<=5);
output = Camiseta numero 1
		 Camiseta numero 2
		 Camiseta numero 3
		 Camiseta numero 4
		 Camiseta numero 5
?>
```
### Foreach
```php
<?php
$animal=array('perro', 'gacela', 'gato');
foreach($animal as $animal){
	echo "El animal es $animal";
}
output = El animal es perro
		 El animal es gacela
		 El animal es gato

$datos=array('Name'=>'Franc','LastName'=>'mirror','Genre'=>'Fem');
?>
```
## ARRAYS
Los arrays son datos estructurados que almacenan un conjunto de datos homogéneo. Podemos encontrar los siguientes tipos.

### Arrays indexados
```php
<?php
$color=array('rojo','magenta','marron');
print_r($color);
output = rojo,magenta,marron
?>
```
### Array asociativo
```php
<?php
$me=array('name'=>'franc','LastName'=>'mirror','age'=>18);
echo $me['name'];
output = franc
?>
```
### Array multidimensional
```php
<?php
$battleShip=array(
	'A'=>array('Mar','Barco','Mar','Mar'),
	'B'=>array('Mar','Mar','Mar','Mar'),
	'C'=>array('Mar','Mar','Barco','Mar'),
	'D'=>array('Mar','Mar','Mar','Mar'),
	);
$coordinates=$battleShip['A'][1];
output = Barco
?>
```
### Recorrer tipos de Array
```php
<?php
// Recorrer array indexado (for)
$color=array('rojo','magenta','marron');
for($i=0;$i<sizeof($color);$i++){
	echo "Indice: $i Valor:{$color[$i]} \n";
}
output = Indice: 0 Valor:rojo
		 Indice: 1 Valor:magenta
		 Indice: 2 Valor:marron

// Recorrer array asociativo (foreach)
$me=array('name'=>'franc','LastName'=>'mirror','age'=>18);
foreach($person as $key=>$value){
	echo "$key:$value \n";
}
output = name: franc
		 LastName: mirror
		 age: 18

// Recorrer array multidimensional (for & foreach)
$battleShip=array(
	'A'=>array('Mar','Barco','Mar','Mar'),
	'B'=>array('Mar','Mar','Mar','Mar'),
	'C'=>array('Mar','Mar','Barco','Mar'),
	'D'=>array('Mar','Mar','Mar','Mar'),
);
foreach($battleShip as $key=>$value){
	for($i=0;$i<sizeof($value),$i++){
		echo "coordenadas: Fila $key Columna $i \n"
	}
}
?>
```