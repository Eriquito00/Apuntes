# DML MySQL
Data Manipulation Language.
## Parametres MySQL DML
INSERT:
- Insereix nova informacio a una taula sobre diferents columnes que podem seleccionar.

![[Pasted image 20250116164449.png]]

DELETE:
- Si fem un delete sol eliminarem totes les dades la taula. Pero tambe podem eliminar files si compleixen alguna condicio com la que estan a l'exemple.

![[Pasted image 20250116164516.png]]

UPDATE:
- El UPDATE serveix per editar les dades d'alguna columna de la taula, per exemple aqui podem veure que si el id de localitzacio es 1700 afegirem un "\_H", el CONCAT() es equiparable a un +=, i tambe podem veure si es NULL utilitzant IS o si no es null IS NOT.

![[Pasted image 20250116164657.png]]

![[Pasted image 20250116170207.png]]

SELECT:
- Un select es compon per els atributs de la taula que volem veure, en aquest exemple s'agafen dades de la taula empleats i s'agafaran les dades dels camps nom, cognoms i deparatment_id sempre i quan el departament_id de l'empleat sigui 60, tambe tenim el ORDER BY per dir per quin camp volem ordenar i podem utilitzar DESC per que sigui descendent i ASC perque sigui ascendent.

	![[Pasted image 20250116170308.png]]

	FROM: 
	- S'utilitza per indicar de quina taula provenen les dades de les columnes indicades.
	
	![[Pasted image 20250123112816.png]]
	
	- Si tenim algun valor repetit i no volem els repetits podem utilitzar DISTINCT.
	
	![[Pasted image 20250123113007.png]]
	
	- Tambe podem crear una columna que no es guardara amb alguna operacio aritmetica i tambe podem fer-li que mostri un nom personalitzar a la columna.
	
	![[Pasted image 20250123113135.png]]
	
	- Tant al inici del SELECT com al WHERE podem utilitzar operadors aritmetics com el '<', '>', '=', '!=', entre altres.
	
	![[Pasted image 20250123113423.png]]