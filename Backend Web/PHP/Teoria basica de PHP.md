# Teoria basica de PHP

## Declaracio de variables i constants
La declaracio de les variables i constants es fa de la seguent manera, per les constants es posa un nom y un valor al moment de declarar i a les variables pot posar valor y en cas de no posar sera per defecte null.

```PHP
<?php
	//variable
	$import = 2.2;
	
	//constant
	define("iker", 19);
?>
```

Per sapiguer el tipus de dada que conte una variable podem fer el seguent

```PHP
<?php
	$import = 2.2;
	
	gettype($import); //en aquest cas double
?>
```

I per poder mostar aquest valor per pantalla utilitzarem "echo".

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