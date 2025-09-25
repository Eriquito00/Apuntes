# Trucades a APIs PHP

## Utilitzant Curl
Aquesta petició ens permet fer un seguiment de tots els passos i on pot estar l'error.

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
Aquesta forma és més senzilla que l'anterior i ens permet obtenir les dades d'una forma més ràpida si l'únic que volem fer és un GET.

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