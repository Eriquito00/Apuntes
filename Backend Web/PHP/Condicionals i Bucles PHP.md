# Condicionals i Bucles PHP
## IF
El condicional if a PHP té un ús molt útil, podem utilitzar-lo de la forma convencional que seria la següent:

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

Però PHP ens permet utilitzar també HTML dins seu, per això és, per tant, podem utilitzar-ho de la següent manera sempre que posem en comptes de "else if" ho deixem junt "elseif". Que també es podria utilitzar a l'anterior cas.

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
Quins avantatges te Match sobre Switch:
- Assignació directa a una variable del valor final després de les comprovacions.
- Estructura simple i més entenedora.
- Necessitat de menys codi pel mateix resultat.

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
Foreach també ens permet ser utilitzat com l'anterior ús que li hem donat a l'if else, podem utilitzar-lo dins de codi de la següent manera:

```PHP
<?php
$languages = ["JS","TS","Java","PHP"];

foreach($languages as $lang){
	echo $lang;
}
?>
```

O com he comentat anteriorment mostrar-ho amb format específic com una llista a l'HTML.

```PHP
<?php
$languages = ["JS","TS","Java","PHP"];
?>

<ul>
	<?php foreach($languages as $lang) : ?>
		<li><php echo $lang ?></li>
	<?php endforeach; ?>
</ul>
```

També podem obtenir l'índex per on va de la array de la següent manera:

```PHP
<?php
$languages = ["JS","TS","Java","PHP"];

foreach($languages as $key => $lang){
	echo $key . " " . $lang;
}
?>



<ul>
	<?php foreach($languages as $key => $lang) : ?>
		<li><php echo $key . " " . $lang ?></li>
	<?php endforeach; ?>
</ul>
```