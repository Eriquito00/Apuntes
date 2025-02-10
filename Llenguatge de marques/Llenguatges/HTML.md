# HTML
Aquest llenguatge s'utilitza per "l'esquelet" de la nostre pagina web de forma habitual i el podem trobar a practicament qualsevol web.
```HTML
<!DOCTYPE html>
<html lang="ca">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>Document</title>
	</head>
	<body>
		<h1>Pagina web</h1>
		<p>Hola mon!</p>
	</body>
</html>
```
Aqui tindriem una estructura base de una pagina web super senzilla amb un titol i un text, aqui podem veure que es poden intriduir metadades com el titol que surt a la pestanya del navegador i tambe podriem fer link a un css que tinguem nosaltres.
## Taules
Aqui podem veure un exemple d'una taula senzilla amb "th" podem fer que estigui resaltat en coptes de "td" que seria per fer una columna normal.

```HTML
<table border="1" style="width:100%">
	<tr>
		<th>Nom</th>
		<th>Cognoms</th>
	</tr>
	<tr>
		<td>Salvador</td>
		<td>Dalí</td>
	</tr>
</table>
```

Aqui podem veure que he complementat la taula posant "colspan" que serveix perque la nostre columna ocupi 2 de ample o mes com en aquest exemple. Tambe podem utilitzar "rowspan" que fa exactament el mateix pero en comptes de fila ocupa 2 o mes casselles de columna.

```HTML
<table border="1" style="width:100%">
	<tr>
		<th>Nom</th>
		<th colspan="2">Telefon</th>
	</tr>
	<tr>
		<td>Salvador</td>
		<td>782 928 928</td>
		<td>829 929 818</td>
	</tr>
</table>
```
## Llistes
### No ordenades
Aqui tindriem un exemple de llista no ordenada, podem posar mes "li" per posar mes atributs fins els que volguem.

```HTML
<ul>
	<li>Pomes</li>
	<li>Taronges</li>
	<li>Sindria</li>
</ul>
```
### Ordenades
Aqui tindriem un exemple de llista ordenada, podem posar mes "li" per posar mes atributs fins els que volguem. Exactament com la llista no ordenada.

```HTML
<ol>
	<li>Marc</li>
	<li>David</li>
	<li>Joel</li>
</ol>
```
### Descriptives
Aqui tindriem un exemple de llista descriptiva, que com podem veure es totalment diferent a les anteriors, aqui seria convenient aplicar css per diferenciar el "dt" del "dd". El "dt" seria el principal y el "dd" seria com el secundari d'aquest "dt" com veiem a aquest exemple

```HTML
<dl>
	<dt>DAW 1</dt>
		<dd>David</dd>
		<dd>Joel</dd>
	<dt>DAW 2</dt>
		<dd>Iker</dd>
</dl>
```

## Etiquetes de estructura
- header: Defineix la capçalera d'un document o d’una secció.
- nav: Defineix un contenidor per als enllaços de navegació.
- section: Defineix una secció en un document.
- article: Defineix un article autònom independent.
- aside: Defineix el contingut a part del contingut (com una barra lateral).
- footer: Defineix el peu de pàgina d'un document o d’una secció.
- details: Defineix detalls addicionals.
- summary: Defineix un títol per a l'element de dades.

## Formularis
Per crear un formulari podem utilitzar la etiqueta "form" d'aquesta forma podem crear un formulari y posteriorment enviarlo:

```HTML
<form>
	<label>Nom</label>
	<input type="text">
	
	<label>Sexe</label>
	<input type="radio" name="sex" value="home">
	<input type="radio" name="sex" value="dona">
	
	<label>Contrasenya</label>
	<input type="password">
	
	<label>Vehicle</label>
	<input type="checkbox" name="vehicle" value="coche">
	<input type="checkbox" name="vehicle" value="moto">
	
	<label>Marca</label>
	<select>
		<option value="honda"></option>
		<option value="bmw"></option>
	</select>
</form>
```
### Type
- text: text normal.
- radio: es pot escollir una de les opcions no mes.
- password: quan escrius nomes es veuen punts.
- checkbox: es pot escollir un o mes de les opcions.
### Name
Els name s'utilitzen per identificar de quina checkbox o de quin radio pertanyen, d'aquesta forma en cas de que hi hagin 2 checkbox cada un sap a quin pertany.
### Value
Valor que es recull en cas de estar seleccionat.
## Com enllaçar un CSS?
Per enllaçar un CSS es tan senzill com utilitzar la etiqueta "link" d'aquesta forma:

```HTML
<link rel="stylesheet" type="text/css" href="(ruta al enllaç)">
```

Apren mes de CSS aqui: [CSS](CSS.md)