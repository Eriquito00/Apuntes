# RRHH DCL
## Base de dades Recursos Humans (RRHH)
Aqui tens la [Base de dades de RRHH](BBDD/bbdd_rrhh.sql)

### Funcions
1. Fes una funció anomenada spPringat, tal que li passem un codi de departament, i ens torni el codi d’empleat que guanya menys d’aquell departament.

```MYSQL
DELIMITER //
CREATE FUNCTION spPringat(vDepartamentid INT) RETURNS INT
DETERMINISTIC
BEGIN
	DECLARE lSalari INT DEFAULT (SELECT empleat_id
			FROM empleats
		WHERE departament_id = vDepartamentid
		AND salari = (SELECT MIN(salari) FROM empleats WHERE departament_id = vDepartamentid)
		LIMIT 1);
	RETURN lSalari;
END;
//
DELIMITER ;
```

2. Fes una funció anomenada spCategoria, tal que donat un codi d’empleat, ens digui en quina categoria professional està. El criteri que volem seguir per determinar la categoria professional és en funció dels anys que porta treballant a l’empresa:
	- Entre 0 i 1 anys -> Auxiliar
	- Entre 2 i 10 anys -> Oficial de Segona
	- Entre 11 i 20 Anys -> Oficial de Primera
	- Més de 20 anys -> Que es jubili!

```MYSQL
DELIMITER //
CREATE FUNCTION spCategoria(vEmpleatid INT) RETURNS CHAR(100)
DETERMINISTIC
BEGIN
	DECLARE lExperiencia INT DEFAULT (SELECT TIMESTAMPDIFF(YEAR,data_contractacio,"2000-12-31") FROM empleats WHERE empleat_id = vEmpleatid);
	DECLARE lCategoria CHAR(100) DEfAULT "";
    
    CASE
		WHEN lExperiencia IN (0,1) THEN SET lCategoria = "Auxiliar";
		WHEN lExperiencia BETWEEN 2 AND 10 THEN SET lCategoria = "Oficial de Segona";
		WHEN lExperiencia BETWEEN 11 AND 20 THEN SET lCategoria = "Oficial de Primera";
		ELSE SET lCategoria = "Que es jubili!";
	END CASE;
    
    RETURN lCategoria;
END;
//
DELIMITER ;
```

3. Fes una funció anomenada spEdat, tal que donada una data per paràmetre ens retorni l'edat d'una persona. Les dates posteriors a la data d'avui han de retornar 0.

```MYSQL
DELIMITER //
CREATE FUNCTION spEdat(vDataNaixement DATE) RETURNS INT
DETERMINISTIC
BEGIN
	DECLARE lEdat INT DEFAULT TIMESTAMPDIFF(YEAR,vDataNaixement,CURDATE());
    IF lEdat < 0 THEN RETURN 0;
    ELSE RETURN lEdat;
    END IF;
END;
//
DELIMITER ;
```
### Procedures
1. Fes un procediment que intercanvii el sou de dos empleats passats per
paràmetre.

```MYSQL
DELIMITER //
CREATE PROCEDURE spCambiaSalaris(vEmpleatid1 INT, vEmpleatid2 INT)
BEGIN
	DECLARE lSalari1 FLOAT DEFAULT (SELECT salari FROM empleats WHERE empleat_id = vEmpleatid1);
	DECLARE lSalari2 FLOAT DEFAULT (SELECT salari FROM empleats WHERE empleat_id = vEmpleatid2);

	UPDATE empleats
		SET salari = lSalari2
	WHERE empleat_id = vEmpleatid1;
    
    UPDATE empleats
		SET salari = lSalari1
	WHERE empleat_id = vEmpleatid2;
END;
//
DELIMITER ;
```

2. Fes un procediment que donat dos Ids d'empleat assigni el codi de
departament del primer en el segon.

```MYSQL
DELIMITER //
CREATE PROCEDURE spCambiaDepartament(vEmpleatid1 INT, vEmpleatid2 INT)
BEGIN
	DECLARE lDepartament1 FLOAT DEFAULT (SELECT departament_id FROM empleats WHERE empleat_id = vEmpleatid1);
	DECLARE lDepartament2 FLOAT DEFAULT (SELECT departament_id FROM empleats WHERE empleat_id = vEmpleatid2);

	UPDATE empleats
		SET departament_id = lDepartament2
	WHERE empleat_id = vEmpleatid1;
    
    UPDATE empleats
		SET departament_id = lDepartament1
	WHERE empleat_id = vEmpleatid2;
END;
//
DELIMITER ;
```
