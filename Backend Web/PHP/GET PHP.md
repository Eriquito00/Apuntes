# GET PHP
Per obtenir el valor utilitzant GET podem posar al final de la url el format.

**?(clau)=(valor)

```PHP
<?php

	//url ?nom=manolo
	
	//una ternaria per obtenir el nom i si no posar El anonimos
	$nom = isset($_GET['nom']) ? $_GET['nom'] : "El anonimos";
	
	//treure el valor
	echo $nom;
	
?>
```