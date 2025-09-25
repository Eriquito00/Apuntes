# Trucades a APIs PHP

## Utilitzant Curl
Aquesta peticion ens permet fer un seguiment de tots els pasos i on pot estar el error.

```PHP
<?php
// Constant amb la suposada URL per obtenir dades de la api
define(API_URL,"(url a una api)");

// INICIALITZACIO del CurlHandle (sessio de curl)
$ch = curl_init(API_URL);

// Indicar que volem obtenir el resultat sense mostrarlo
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

// Guardem el resultat de la api a una variable
$result = curl_exec($ch);

// Transforma el resultat de la peticio a una Array Associatiu
$data = json_decode($result, true);

// IMPORTANT TANCAR LA CONNEXIO CURL
curl_close($ch);
?>
```
## Utilitzant File Get Contents
Aquesta forma es mes sencilla que la anterior i ens permet obtenir les dades d'una forma mes rapida si l'unic que volem fer es un GET.

```PHP
<?php
// Constant amb la suposada URL per obtenir dades de la api
define(API_URL,"(url a una api)");

// Obtenir la informacio en format JSON directament de la API
$result = file_get_contents(API_URL);

// Transforma el resultat de la peticio a una Array Associatiu
$data = json_decode($result, true);
?>
```