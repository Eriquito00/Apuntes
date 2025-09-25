# GET i POST
Get inclou tota la informació necessària l'URL, per tant, és visible i s'utilitza a peticions que recuperen dades.

Post no inclou la informació a l'URL i tampoc es crea un historial de les dades tractades.

Tant GET com POST són protocols HTTP, per tant, sol·liciten una resposta al servidor. Però per a què es fa servir GET i per a què s'utilitza POST:

- GET: quan volem portar dades emmagatzemades al servidor, per exemple si volem rebre un ID per a obtenir un article de la BBDD.

- POST: quan volem fer una modificació de dades, tant per afegir, modificar o eliminar, utilitzarem el protocol POST, per exemple per inserir un nou producte a la BBDD o esborrar-lo o modificar el seu preu.

Amb GET podem veure la informació directament a l'URL, però amb el protocol POST que utilitza HTTP 1.1 si utilitzen un atac "Man in the Middle" poden obtenir també les dades, per tant, s'hauria d'utilitzar HTTPS de totes maneres.

POST - Redirect - GET (Publicar Redirigir Obtenir): Bàsicament, seria un exemple com introduir una informació a un formulari com per exemple la informació d'un cotxe, despresa es guarda la informació a la BBDD amb un POST i després s'obtindria la informació redirigint a l'usuari a una altra vista que no sigui el formulari i mostrar un exemple d'una targeta amb la informació introduïda del cotxe.

El procés seria:
- POST: omplim formulari i enviem al servidor web.
- Redirect: es processen les dades al servidor i es processa una nova vista per mostrar dades.
- GET: obté les dades que hem omplert al formulari a una altra vista.

En definitiva, tant GET com POST els podem utilitzar per a ambdues coses, però queda clar que si enviem dades delicades amb GET la informació es veuria a l'URL, per tant, no tenim cap seguretat, per tant, no està ben aplicat GET en aquest cas de qüestionari.

Hem de centrar-nos a utilitzar GET per lectura de dades de la BBDD i POST per insercions, modificacions o eliminacions. Exemple de formulari:

```PHP
<form action="fitxer.php" method"POST">
</form>
```

```PHP


<?php
	$nom = $_POST['nom'];
?>
```
# GET PHP
Per obtenir el valor utilitzant GET podem posar al final de l'URL el format.

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