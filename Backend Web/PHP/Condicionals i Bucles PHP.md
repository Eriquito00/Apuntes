# Condicionals i Bucles PHP
## IF
El condicional if a PHP te un us molt util, podem utilitzar-lo de la forma convencional que seria la següent:

```PHP
<?php
$edad = 20;
if ($edad > 18){
	echo "Major de edad";
}
else if ($edad == 18){
	echo "Uf por los pelos";
}
else {
	echo "Menor de edad";
}
?>
```

Pero PHP ens permet utilitzar tambe HTML dins seu, per aixó es, per tant podem utilitzar-ho de la següent manera sempre i quan posem en contes de "else if" ho deixem junt "elseif". Que tambe es podria utilitzar a l'anterior cas.

```PHP
<?php
$edad = 20;
?>

<?php if ($edad > 18) : ?>
	<h1>"Major de edad"</h1>
<?php elseif ($edad == 18) : ?>
	<h1>"Uf por los pelos"</h1>
<?php else : ?>
	<h1>"Menor de edad"</h1>
<?php endif; ?>
```

## Switch ✖️ 👴 Match ✔️ 👨
Quines avantatges te Match sobre Switch:
- Assignació directa a una variable del valor final després de les comprovacions.
- Estructura simple i mes entenedora.
- Necesitat de menys codi pel mateix resultat.

```PHP
<?php
$edad = 20;

$msgEdad = match (true) {
	$edad < 5 => "Eres un bebe",
	$edad < 12 => "Eres un niño",
	$edad < 18 => "Eres un adolescente",
	$edad < 30 => "Eres un joven adulto",
	$edad < 60 => "Eres un adulto",
	default => "Estas viejito",
}

switch (true) {
    case ($edad < 5):
        $msgEdad = "Eres un bebe";
        break;
    case ($edad < 12):
        $msgEdad = "Eres un niño";
        break;
    case ($edad < 18):
        $msgEdad = "Eres un adolescente";
        break;
    case ($edad < 30):
        $msgEdad = "Eres un joven adulto";
        break;
    case ($edad < 60):
        $msgEdad = "Eres un adulto";
        break;
    default:
        $msgEdad = "Estas viejito";
        break;
}

?>
```

## Foreach
[MiduDev PHP curso](https://youtu.be/BcGAPkjt_IE?t=3654)