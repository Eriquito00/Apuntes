# xQuery
xQuery es un llenguatge de marques que s'utilitza per fer consultes a una "base de dades" en xml, te una sintaxi i us similar al llenguatge MySQL. Jo utilitzare BaseX per tant aquesta seguent linea ens servira molt per obtenir els resultats de la nostre consulta de forma ordenada.

```xQUERY
declare option output:indent "yes";
```

Per carregar i mirar la informacio d'un fitxer ho farem de la seguent forma, per cada consulta cal fer un for i tambe de quin fitxer xml volem extreure la informacio.

```xquery
for $(nom variable) in doc("(ruta document)") (ruta a quina etiqueta ens referim)
```

Aqui tindriem la estructura, si volem fer una consulta en cas real tenim aquest exemple:

```xml
<empresa>
	<comandes>
		<comanda>
			<numero>1</numero>
			<preu>50</preu>
			<client>A</client>
		</comanda>
		<comanda>
			<numero>2</numero>
			<preu>100</preu>
			<client>B</client>
		</comanda>
		<comanda>
			<numero>3</numero>
			<preu>75</preu>
			<client>A</client>
		</comanda>
	</comandes>
	<clients>
		<client>
			<id>A</id>
			<nom>Angel</nom>
		</client>
		<client>
			<id>B</id>
			<nom>Brian</nom>
		</client>
	</clients>
</empresa>
```

```xquery
for $com in doc("empresa.xml") /empresa/comandes/comanda
```

Ara que ja tenim l'inici de la consulta farem una restriccio per exemple quan el preu de la comanda sigui major a 60.

```xquery
for $com in doc("empresa.xml") /empresa/comandes/comanda
where $com/preu > 60
```

Ara ja tenim la restriccio feta per tant podem fer el return dels resultats que volem. Amb return podem retornar les dades que volem del xml com aqui que nomes retorno el numero en format text de cada comanda que compleixi el where.

```xquery
for $com in doc("empresa.xml") /empresa/comandes/comanda
where $com/preu > 60
return
<comanda>
  <n>{$com/numero/text()}</n>
</comanda>
```

Ara volem obtenir totes les comandes amb un increment en el preu de un 21% per l'IVA, per aixo farem una variable.

```xquery
for $com in doc("empresa.xml") /empresa/comandes/comanda
let $iva = $com/preu/number() * 1.21
return
<comanda>
	<n>{$com/numero/text()}</n>
	<n>{$iva/number()}</n>
</comanda>
```

Si volem ordenar el nostre resultat de consultes podem utilitzar un order by per ordenar per una condicio com al seguent exemple que volem ordenar per preu de major a menor.

```xquery
for $com in doc("empresa.xml") /empresa/comandes/comanda
order by xs:decimal($com/preu) descending
return
<comanda>
	<n>{$com/numero/text()}</n>
	<n>{$com/preu/number()}</n>
</comanda>
```

Ara pongem el cas que volem contar quantes comandes tenim en total, podem utilitzar count amb una consulta com aquesta.

```xquery
for $com in doc("empresa.xml") /empresa/comandes/comanda

return
<comanda>
	<n>{count($com)}</n>
</comanda>
```

Ara posem el cas que volem obtenir les comandes i el nom del client que les ha fet, per tant necesitarem fer dues consultes diferents que s'uneixin per una cosa que tinguin a veure, en aquest cas es el nom del client.

```xquery
for $comanda in doc("empresa.xml")/empresa/comandes/comanda
for $client in doc("empresa.xml") /empresa/clients/client
where $comanda/client = $client/id
return
<comanda>
	<numero>{$comanda/numero/text()}</numero>
	<preu>{$comanda/preu/text()}</preu>
	<client>{$client/nom/text()}</client>
</comanda>
```

A mes a mes tambe podem utilitzar xquery dins de html per obtenir, gracies a BaseX un html amb les dades ja de la consulta ordenades per exemple a una taula.

```xquery
declare option output:indent "yes";

<html>
  <head>
    <title>Comandes</title>
  </head>
  <body>
    <h1>Llistat de Comandes amb el Nom del Client</h1>
    <table>
      <tr>
        <th>Comanda</th>
        <th>Preu</th>
        <th>Client</th>
      </tr>
      {
        for $comanda in doc("empresa.xml")/empresa/comandes/comanda
        for $client in doc("empresa.xml")/empresa/clients/client
        where $comanda/client = $client/id
        return
          <tr>
            <td>{$comanda/numero/text()}</td>
            <td>{$comanda/preu/text()}</td>
            <td>{$client/nom/text()}</td>
          </tr>
      }
    </table>
  </body>
</html>
```

Tambe podem editar el head del html i afegir aquesta linea i enllaçar un css per decorar.

```xquery
<link rel="stylesheet" href="style.css" type="text/css"/>
```

```css
body {
	padding: 0px;
	margin: 0px;
	background-color: white;
}

.titulo {
	font-size: 50px;
} 

h1 {
	font-size: 30px;
	text-align: center;
	font-family: Arial, Helvetica, sans-serif;
} 

table, tr, th, td {
	border: 1px solid black;
	border-collapse: collapse;
	padding: 5px;
}

table {
	width: 100%;
}

th {
	background-color: cornflowerblue;
	color: white;
	font-size: 20px;
}
```