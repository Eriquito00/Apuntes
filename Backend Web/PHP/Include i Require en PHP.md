# Include i Require en PHP
Include tambe es pot utilitzar juntament amb include once igual que require i require once.
Quan utilitzem include once o require once només cal carregar-ho una vegada.

Quan utilitzem Include en cas de error i que no es pugui carregar saltara un warning conforme no es s'ha pogut carregar el que volies, s'utilitza quan el que volem carregar no es una cosa crucial.

Quan utilitzem Require en cas de error amb el que volem carregar saltara directament un error que finalitzarà amb el curs normal del programa, s'utilitza amb connexions amb una BBDD que no ens permet continuar amb el curs del programa.

Les variants que tenim son les següents:
```PHP
<?php
	require("ruta fitxer");
	require_once("ruta fitxer");
	include("ruta fitxer");
	include_once("ruta fitxer");
?>
```