# Funcions MySQL
- CONCAT(text,text,text...): Retorna un String amb tots els textos que he introduit.
- LENGTH(text): Retorna la longitud del String.
- LOWER(text) i LCASE(text): Retorna el String en minuscules.
- UPPER(text) i UCASE(text): Retorna el String en MAJUSCULES.
- LEFT(text,length): Retorna els (length) caracters començant per l'esquerra.
- RIGHT(text,length): Retorna els (length) caracters començant per la dreta.
- MID(text, pos, len), SUBSTRING(text, pos), SUBSTRING(text, pos, len): S'utilitza per obtenir porcions d'una cadena de text.
- INSTR(text, sub_text): Retorna la posició de la primera aparició de sub_text dins a text.
- LOCATE(sub_text, text), LOCATE(sub_text, text, pos): S'utilitza per obtenir porcions d'una cadena de text. A més podem indicar la posició a iniciar la cerca.
- LPAD(text, len, padtext): Retorna el string text omplint-lo amb el text padtext per l'esquerra fins obtenir la longitud len.
- RPAD(text,len,padtext): Retorna el string text omplint-lo amb el text padtext per la dreta fins obtenir la longitud len.
- TRIM(text), LTRIM(text), RTRIM(text): Retorna el text traient els possibles espais en blanc d'esquerra i dreta.
- REPEAT(text, count): Retorna un string de longitud count repetint el string text.
- SPACE(len): Retorna un string de longitud len només format per espais en blanc.
- REPLACE(text, from, to): Retorna el string text reemplaçant les ocurrències del string from per el string to.
- REVERSE(text): Retorna string text amb l'orde dels caràcters en format invers.
- IFNULL(camp, substitucio): Comprova si el valor es NULL i si es NULL posa el valor que substitueix.
- CAST(camp AS ...): s'utilitza per cambiar un tipus de dada a un altre, per exemple de "UNSIGNED" a "SIGNED".
## Funcions de dates
- YEAR(camp): Agafa l'any d'una data.
- MONTH(camp): Agafa el mes d'una data.
- DAY(camp): Agafa el dia d'una data.
- CURDATE(): Obte la data del dia actual.
- NOW(): Obte la data Y HORA del dia y hora actuals.
- DATE_FORMAT(camp, estructura): A partir del camp, extreu segons el que demanem, %Y (any), %m (mes numeric) i %d (dia numeric).
- TIMESTAMPDIFF(volem, camp, camp): Es pot utilitzar per obtenir, dia, mes o any, restant el primer camp amb el segon camp.
## Funcions de calcul
- COUNT(): Conta quants compleixen certes condicions.
- MAX(): Diu el maxim d'unes dades que compleixen certes condicions.
- MIN(): Diu el minim d'unes dades que compleixen certes condicions.
- AVG(): Calcula la mitjana d'algunes dades.
- STD(): Calcula la mitja de dispersio comu, basicament les dades quant mes s'apropin a la mitjana millor.
- ABS(): Retorna el numero absolut, eliminant qualsevol numero negatiu.

## Funcions MySQL
### IS NULL o NOT NULL
- SOBRETOT si volem comprovar NULL o NOT NULL utilitzarem IS no '='. 

	![](/Imatges/Pasted%20image%2020250123113619.png)

### BETWEEN
- A mes a mes tambe podem utilitzar rangs amb BETWEEN, en els quals tant el inicial com el final estan inclosos, igual que NULL podem utilitzar NOT BETWEEN que no incluira ni el minim ni maxim.

	![](/Imatges/Pasted%20image%2020250123113723.png)

### IN
- Tambe podem utilitzar IN per dir que ens retornin el que estan exactament en aquest valor.

	![](/Imatges/Pasted%20image%2020250123113940.png)

- Si volem un missatge quan hi hagi un NULL a una columna podem utilitzar IFNULL().
	![](/Imatges/Pasted%20image%2020250123114428.png)

### Regular expresions
- Si volem fer una cerca d'un patro, com un regex, podem utilitzar LIKE. Podria ser que depenent com tenim configurada la base de dades ens mostrara els valors que començen per la lletra o nomes els que comencin per la lletra MAJUSCULA o minuscula. Tambe tenim RLIKE per regular expresions.
	LIKE:
	
	![](/Imatges/Pasted%20image%2020250123114613.png)
	![](/Imatges/Pasted%20image%2020250123115116.png)
	RLIKE i REGEXP:
	On he posat REGEXP podem posar tambe RLIKE, funcionen exactament igual nomes que RLIKE va amb "" y dins la expresio regular i REGEXP funciona amb ''.
	
	![](../../../../Imatges/Pasted%20image%2020250223162020.png)
	
	REGEXP_SUBSTR:
	Aqui podem veure que el que fa REGEXP_SUBSTR es extreure un tros d'un string utilitzant regular expresions i en aquest cas ha servit per comparar.
	
	![](../../../../Imatges/Pasted%20image%2020250223162133.png)
## CASE
- Una altre funcio que podem utilitzar es una semblant a fer un if que es CASE. Amb els diferents WHEN que serien els respectius else if y el ultim que es ELSE, aquesta sentencia finalitza amb END AS (nom del camp). A mes a mes tambe es pot utilitzar mes com un switch com en el seguent exemple:

	![](/Imatges/Pasted%20image%2020250129205312.png)

	![](/Imatges/Pasted%20image%2020250130115338.png)

## Funcions fetes a MySQL
### Formata un string amb un format primera majuscula y resta minuscula
- A MySql no tenim una funcio per crear una columna amb la primera en majuscula y la resta en minuscula pero podem utilitzar aquesta funcio,  'CONCAT(UPPER(LEFT(nom,1)),LOWER(SUBSTRING(nom,1)))'.
	![](/Imatges/Pasted%20image%2020250123122537.png)

### Random entre 2 numeros
- A MySql tampoc podem fer un random entre un numero i un altre, pero podem utilitzar la seguent funcio, RAND() \* (max - min + 1).

	![](/Imatges/Pasted%20image%2020250123144034.png)
