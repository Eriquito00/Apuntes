# CSS
La estructura de CSS es molt senzilla, es pot posar estil depenent del tipus d'etiqueta, per la classe o per la id:

## Formes d'aplicar
### Etiqueta
De la seguent manera totes les etiquetes "h1" tindran aquest estil

```CSS
h1 {
	color: white;
}
```
### Classe
Amb aixo nomes a les etiquetes que li posem aquesta classe tindran aquest estil.

```HTML
<h1 class="alinea">titol</h1>
```

```CSS
.alinea {
	text-align: center;
}
```

### ID
Amb ID funciona exactament igual que la clase pero en comptes de clase s'utilitza ID que tambe es pot utilitzar amb JavaScript en cas de que volem fer alguna cosa amb aquesta etiqueta.

```HTML
<h1 id="titulo">titol</h1>
```

```CSS
#titulo {
	text-align: center;
}
```

### Varies etiquetes
A mes a mes tambe podem aplicar un estil a varies etiquetes. Per no haver de repetir varies vegades el mateix estil pero per diferents components.

```HTML
<h1>titol</h1>
<h2>titol2</h2>
```

```CSS
h1, h2 {
	text-align: center;
}
```

## Etiquetes mes utilitzades
### Text
- `color`: Color del text
- `font-size`: Mida de la lletra
- `font-family`: Tipografia
- `text-align`: Alineació (left, center, right)
- `text-decoration`: Subratllat, tatxat, etc
### Fons
- `background-color`: Color de fons
- `background-image`: Imatge de fons
### Mida i espaiat
- `width` / `height`: Amplada / Alçada
- `margin`: Marges externs
- `padding`: Espai interior
- `border`: Vora del element
### Disposicio
- `display`: Tipus de visualització (block, inline, flex)
- `position`: Posició (relative, absolute, fixed)
- `float`: Flotació a esquerra/dreta
