# Tipus de variables PHP
## Declaració de variables i constants
La declaració de les variables i constants es fa de la següent manera, per les constants es posa un nom i un valor al moment de declarar i a les variables pot posar valor i en cas de no posar serà per defecte null.

```PHP
<?php
	//variable
	$import = 2.2;
	
	//constant
	define("iker", 19);
	
	// constant local (a la classe que treballem o al fitxer)
	const EDAD = 18;
?>
```

Per saber el tipus de dada que conté una variable podem fer el següent

```PHP
<?php
	$import = 2.2;
	
	gettype($import); //en aquest cas double
?>
```

I per poder mostrar aquest valor per pantalla utilitzarem "echo".

```PHP
<?php
	// en variables
	$import = 2.2;
	
	echo $import
	
	// en constants
	
	define("iker", 19);
	
	echo iker
?>
```

## Comprovació de variables
Segur que amb PHP en ser un llenguatge no tipat i dinàmic ens ha passat que hem tingut dos tipus de valor a una mateixa variable i no sabem que conté ara, podem fer una verificació retornant true o false dels diferents tipus de variables de la següent manera.

```PHP
$variable = ?;

//strings
is_string($variable);

//booleans
is_bool($variable);

//numeros enters
is_int($variable);

//numeros amb decimals
is_double($variable);
is_float($variable);
```
## Operador ternari
Per aplicar un operador ternari podem fer-ho de la següent forma.

```PHP
<?php
	$edat = 18;
	
	//en caso de que edad no tenga valor tendra el valor del string
	$edat = (isset($edat)) ? $edat : 'El usuari no ha establert la seva edat';
	
	//si te valor el valor si no el string (en aquest exemple)
	echo 'Edat: ' . $edat;
?>
```
## Formes de treure valors

```PHP
<?php
	$valor = "valor";
	
	// "valor"
	echo $valor;
	
	//string(5) "valor"
	var_dump($valor);
?>
```

## Manipulació de Strings
```PHP
<?php
	
	$text = 'Eric';
	
	// treu espais abans i despres del text	
	echo trim($text);
	
	// obte la longitud total del string
	echo strlen($text);
	
	// mostra el string entre els numeros de caracters, inclosos els dos, en aquest exemple seria "ic"
	echo substr($text, 2, 4);
	
	// si volem canviar alguns caracters d'algun string podem utilitzar
	echo str_replace('c', 'k', $text); // canvia la c per la k
	
	//concatenacio de strings
	$nom = "Manolo";
	$edad = 25;
	echo "Hola " . $nom . ", con una edad de " . $edad;
	//SORTIDA: Hola Manolo, con una edad de 25
	
	//Pero tambe es pot fer el seguent per concatenar
	$num1 = 1;
	$num2 = 2;
	echo $num1 . $num2;
	//SORTIDA: 12
	
	//inclus podem utilitzar aquest operador
	$nom = "Hola " . $nom;
	$nom ·= ", con una edad de " . $edad;
?>
```

## Tipus d'array
### Array
Per crear una array podem fer-ho de les següents maneres exactament iguals.

```PHP
<?php
	
	// crea arrays
	$variable = array ('dilluns', 'dimarts', 'dimecres', 'dijous', 'divendres', 'dissabte', 'diumenge');
	
	$variable = ['dilluns', 'dimarts', 'dimecres', 'dijous', 'divendres', 'dissabte', 'diumenge'];
	
	//afegir un valor a la array en x posicio
	$variable[10] = "valor";
	
	//afegir un valor al final
	$variable[] = "valor2";
	
?>
```
### Array associatiu
Per crear arrays associatius podem fer-ho de la següent forma que seria tenir dades formades clau valor.

```PHP
<?php
	
	//crear array asociativo
	$cotxe = array('marca' => 'audi', $model =>'A3', 'matricula'=>'1111BBB', 'any'=>2004);
	
	//obtener el valor de la clave 
	echo $cotxe['matricula'];
	
	//cambiar el valor de una clave
	$cotxe['matricula']= '5555ZZZ';
	
?>
```
### Array bidimensional
És una array que conté arrays dins seu.

```PHP

<?php
	
	$cotxe = array(
		array('audi',2004),
		array('opel',2010),
		array('ford',2017)
	);
	
	//donaria 2004 referencia de la array audi
	echo $cotxe[0][1];
	
	//longitud total de la array
	count($cotxe);
	
?>
```
## Manipulació de arrays
```PHP
<?php
	$mesos = array(
	'Gener', 'Febrer', 'Març', 'Abril',
	'Maig', 'Juny', 'Juliol', 'Agost',	
	'Setembre', 'Octubre', 'Novembre', 'Desembre'
	);
	
	// elimina el ultimo
	array_pop($mesos);
	
	// saca todos por pantalla unidos por "-"
	echo join('-', $mesos);
	
	// obtiene la medida de la array
	count($mesos);
	
	// ordena alfabeticamente o de pequeño a grande
	sort($mesos);
	
	// ordena alfabeticamente al reves o de grande a pequeño
	rsort($mesos);
	
	// obtiene la misma array pero al reves
	$mesos_invertits = array_reverse($mesos);
?>
```