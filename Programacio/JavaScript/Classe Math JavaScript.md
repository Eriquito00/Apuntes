JavaScript té aquesta classe per ajudar en la realització càlculs matemàtics.
Aquesta classe inclou algunes constants matemàtiques útils.  
Proporciona els següents valors amb molts dígits de precisió:
- Math.PI: **nombre pi** = 3.141592...
- Math.E: **nombre e** = 2.718...
- Math.SQRT2: **arrel de 2** = 1.414...

També inclou moltes funcions matemàtiques.  
Aquestes funcions necessiten un o dos paràmetres i retornen un resultat:
- Math.abs(n): valor absolut (converteix els números negatius a positius)
- Math.min(n1, n2): retorna el valor més petit entre els dos arguments que se li passin.
- Math.max(n1, n2): retorna el valor més gran entre els dos arguments que se li passin.
- Math.ceil(n): arrodoneix cap a dalt.
- Math.floor(n): arrodoneix cap a baix.
- Math.round(n): arrodoneix cap al número enter més proper.
- Math.random(): retorna un número entre 0 i 1 (l'1 no està inclòs: **0 <= n < 1**).
- Math.pow(x, y): retorna x elevat a y (**xy**). Actualment també es pot fer x ** y
- Math.sqrt(n): calcula l'arrel quadrada.
- Math.hypot(n): calcula la hipotenusa a partir de la base i l'altura d'un triangle rectangle.
- Math.sin(n): calcula el sinus (n ha d'estar en radians: **n = graus * Math.PI / 180**).
- Math.cos(n): calcula el cosinus (n ha d'estar en radians: **n = graus * Math.PI / 180**).
- Math.tan(n): calcula la tangent (n ha d'estar en radians: **n = graus * Math.PI / 180**).
***
### Generar números aleatoris entre dos valors determinats
==// Enter aleatori **entre 'min' i 'max'**, tots dos inclosos  
let n = Math.floor((Math.random() * (max - min + 1) + min));  
// Real aleatori **des de 'min' fins a 'max' (aquest últim no inclòs)**  
let d = Math.random() * (max - min) + min;==
***
### Problemes de precisió i desbordament
Els valors que es poden utilitzar estan limitats.  
Si no es tenen en compte aquests límits, es poden produir resultats erronis.
![[Pasted image 20240916191637.png|700x250]]