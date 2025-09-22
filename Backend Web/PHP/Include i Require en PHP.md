# Include i Require en PHP
Include tambe es pot utilitzar juntament amb include once igual que require i require once.
Quan utilitze include once o require once nomes cal carregar-ho una vegada.

Quan utilitzem Include en cas de error i que no es pugui carregar saltara un warning conforme no es s'ha pogut carregar el que volies, s'utilitza quan el que volem carregar no es una cosa crucial.

Quan utilitzem Require en cas de error amb el que voliem carregar saltara directament un error que finalitzara amb el curs normal del programa, s'utilitza amb connexions amb una BBDD que no ens permet continuar amb el curs del programa.

Les variants qie tenim son les seguents:
```PHP
<?php
	require("ruta fitxer");
	require_once("ruta fitxer");
	include("ruta fitxer");
	include_once("ruta fitxer");
?>
```