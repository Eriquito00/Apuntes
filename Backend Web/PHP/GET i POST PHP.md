# GET i POST
Get inclou tota la informació necesaria a la URL, per tant es visible i s'utilitza a peticions que recuperen dades.

Post no inclou la informació a la URL i tampoc es crea un historial de les dades tractades.

Tant GET com POST son protocols HTTP per tant soliciten una resposta al servidor. Pero per a que es fa servir GET i per a que s'utilitza POST:

- GET: quan volem portar dades emmagatzemades al servidor, per exemple si volem rebre un id per a obtenir un article de la BBDD.

- POST: quan volem fer una modificació de dades, tant per afegir, modificar o eliminar, utilitzarem el protocol POST, per exemple per inserir un nou producte a la BBDD o esborrar-lo o modificar el seu preu.

Amb GET podem veure la informació directament a la URL pero amb el protocol POST que utilitza HTTP 1.1 si utilitzen un atac "Man in the Middle" poden obtenir tambe les dades, per tant s'hauria d'utilitzar HTTPS de totes maneres.

POST - Redirect - GET (Publicar Redirigir Obtenir): Bàsicament seria un exemple com introduir una informació a un formulari com per exemple la info de un cotxe, despresa es guarda la info a la BBDD amb un POST i després s'obtindria la informació re dirigint a l'usuari a un altre vista que no sigui el formulari i mostrar un exemple de una tarjeta amb la informació introduïda del cotxe.

El procés seria:
- POST: omplim form i enviem al servidor web.
- Redirect: es procesen les dades al servidor i es procesa una nova vista per mostrar dades.
- GET: obté les dades que hem omplert al formulari a un altre vista.

En definitiva, tant GET com POST els podem utilitzar per ambdues coses pero esta clar que si enviem dades sensibles amb GET la informació es veuria a la URL per tant no tenim cap seguretat per tant no esta ben aplicat GET en aquest cas de qüestionari.

Hem de centrar-nos en utilitzar GET per lectura de dades de la BBDD i POST per insercions, modificacions o eliminacions. 

Exemple de formulari:

```PHP
<form action="fitxer.php" method"POST">
</form>
```

```PHP
//fitxer.php
<?php
	$nom = $_POST['nom'];
?>
```
# GET PHP
Per obtenir el valor utilitzant GET podem posar al final de la URL el format.

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