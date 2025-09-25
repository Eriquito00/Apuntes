# Efectes CSS
## Transformacions
Les transformacions modifiquen un element després de posicionar-lo en el layout, sense afectar l'espai dels altres.
### Funcions principals
```css
/* Translació */
transform: translate(50px, 100px);

/* Rotació */
transform: rotate(45deg);

/* Escalat */
transform: scale(2, 1.5);

/* Biaix (skew) */
transform: skew(20deg, 10deg);
```
### Característiques
- No canvien l’espai reservat de l’element.
- Es poden acumular diverses transformacions.
- L’ordre importa: `rotate → translate` ≠ `translate → rotate`.  
- Punt d’origen configurable:

```CSS
transform-origin: 0% 0%; /* per defecte és 50% 50% */
```
## Transicions
Permeten afegir un efecte suau entre dos estats d’un element (inicial i final).
### Propietats bàsiques
```CSS
transition: (propietat) (durada retard funcio);
```
### Exemple simple
```CSS
div {
	width: 100px;
	height: 100px;   
	background: red;   
	transition: width 2s; 
}

div:hover {   
	width: 300px; 
}
```
### Exemple amb múltiples propietats
```CSS
div {   
	width: 100px;   
	height: 100px;   
	background: red;   
	transition: width 2s, height 2s, transform 2s; 
}

div:hover {   
	width: 200px;   
	height: 200px;   
	transform: rotate(180deg);
}
```
## Animacions
A diferència de les transicions, permeten definir múltiples estats intermedis amb **@keyframes**.
### Propietats principals
- `animation-name`: nom dels keyframes.
- `animation-duration`: durada.
- `animation-delay`: retard inicial.
- `animation-iteration-count`: nombre de repeticions (`infinite` per sempre).
- `animation-direction`: direcció
	- `normal`: d'inici a final sempre.
	- `reverse`: de final a inici sempre.
	- `alternate`: d'inici a final i de final a inici.
	- `alternate-reverse`: de final a inici i d'inici a final.
- `animation-timing-function`: ritme
    - `linear`: mateix ritme tot el temps.
    - `ease`: comença lent, accelera i acaba lent.
    - `ease-in`: comença lent i acaba de pressa.
    - `ease-out`: comença de pressa i acaba lent.
- `animation-fill-mode`: estils abans i després 
	- `none`: no aplica cap estil.
	- `forwards`: manté l'últim estat de l'animació en finalitzar.
	- `backwards`: aplica l'estat inicial mentre espera `animation-delay`.
	- `both`: combina `forward` i `backward` (mentre espera a `animation-delay` queda en estat inicial i després acaba en l'últim estat de l'animació).
### Exemple
```CSS
@keyframes girar {
	from { transform: rotate(0deg); }   
	to { transform: rotate(360deg); }
}

.box {   
	width: 100px;   
	height: 100px;   
	background: blue;   
	animation: girar 3s infinite linear;
}

/* tambe podem aplicar percentatges per una animacio mes detallada */
@keyframes girar {
	0% {
		transform: rotate(0deg) scale(1);
	}
	
	25% {
		transform: rotate(90deg) scale(0.5);
	}
	
	50% {
		transform: rotate(180deg) scale(1);
	}
	
	75% {
		transform: rotate(270deg) scale(0.5);
	}
	
	100% {
		transform: rotate(360deg) scale(1);
	}
}
```