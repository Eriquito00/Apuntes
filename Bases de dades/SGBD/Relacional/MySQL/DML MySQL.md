# DML MySQL
Data Manipulation Language.
## Parametres MySQL DML
INSERT:
- Insereix nova informacio a una taula sobre diferents columnes que podem seleccionar.

![](/Imatges/Pasted%20image%2020250116164449.png)

DELETE:
- Si fem un delete sol eliminarem totes les dades la taula. Pero tambe podem eliminar files si compleixen alguna condicio com la que estan a l'exemple.

![](/Imatges/Pasted%20image%2020250116164516.png)

UPDATE:
- El UPDATE serveix per editar les dades d'alguna columna de la taula, per exemple aqui podem veure que si el id de localitzacio es 1700 afegirem un "\_H", el CONCAT() es equiparable a un +=, i tambe podem veure si es NULL utilitzant IS o si no es null IS NOT.

![](/Imatges/Pasted%20image%2020250116164657.png)

![](/Imatges/Pasted%20image%2020250116170207.png)

SELECT:
- Un select es compon per els atributs de la taula que volem veure, en aquest exemple s'agafen dades de la taula empleats i s'agafaran les dades dels camps nom, cognoms i deparatment_id sempre i quan el departament_id de l'empleat sigui 60, tambe tenim el ORDER BY per dir per quin camp volem ordenar i podem utilitzar DESC per que sigui descendent i ASC perque sigui ascendent.

	![](/Imatges/Pasted%20image%2020250116170308.png)

	FROM: 
	- S'utilitza per indicar de quina taula provenen les dades de les columnes indicades.
	
	![](/Imatges/Pasted%20image%2020250123112816.png)
	
	- Si tenim algun valor repetit i no volem els repetits podem utilitzar DISTINCT.
	
	![](/Imatges/Pasted%20image%2020250123113007.png)
	
	- Tambe podem crear una columna que no es guardara amb alguna operacio aritmetica i tambe podem fer-li que mostri un nom personalitzar a la columna.
	
	![](/Imatges/Pasted%20image%2020250123113135.png)

	WHERE:
	- Tant al inici del SELECT com al WHERE podem utilitzar operadors aritmetics com el '<', '>', '=', '!=', entre altres.
	
	![](/Imatges/Pasted%20image%2020250123113423.png)

	GROUP BY:
	- S'utilitza per crear un grup segons la columna que li diem i les dades que volem mostrar, per exemple si volem mostrar la mitjana de salari segons un codi de feina com a la consulta que podem veure.
	
	![](../../../../Imatges/Pasted%20image%2020250211151344.png)

	ORDER BY:
	- S'utilitza per ordenar els resultats que donem a la consulta en un format ascendent o descendent segons el camp que li diguem.
	
	![](../../../../Imatges/Pasted%20image%2020250211151100.png)

	HAVING:
	- Despres tenim el HAVING que seria com un "WHERE" del nostre GROUP BY, s'utilitza per posar condicions logiques com al WHERE pero aquest s'executa mes tard per tant el podem utilitzar amb algunes funcions que requereixen fer algun calcul y despres comprovar el calcul, cosa que amb el WHERE no podriem o seria menys eficient.
	
	![](../../../../Imatges/Pasted%20image%2020250211151602.png)