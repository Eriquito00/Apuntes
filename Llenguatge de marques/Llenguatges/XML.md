# XML
## Tipus de validadors per XML
Principalment com a validadors de XML tenim un mes antic que es DTD i altre mes actual que es XSD. Aqui podem anar a veure quina sintaxi i com podem utilitzar cadascun.

[DTD](Validadors%20XML/DTD.md)

[XSD](Validadors%20XML/XSD.md)
## Conversio i adaptacio de documents XML
Aqui tenim un dels formats per convertir per exemple els nostres XML a HTML i adaptar l'informacio del nostre fitxer XML, en aquest cas tenim XSL:

[XSLT](Conversors%20i%20adaptadors%20XML/XSLT.md)

La sintaxi de xml es molt i molt senzilla, son senzillament etiquetes que nosaltres posem el nom que millor convengui a les nostres necesitats i posarem etiquetes dins d'etiquetes.

```XML
<?xml version="1.0" encoding="UTF-8"?>
<alumnes>
	<alumne>
		<nom>Iker</nom>
		<cognom>Novo</cognom>
	</alumne>
	<alumne>
		<nom>David</nom>
		<cognom>Catalan</cognom>
	</alumne>
</alumnes>
```

Aqui es pot veure que la estructura es de etiquetes dins d'etiquetes segons les dades que volem guardar.
### Diferencies entre DTD i XSD

| Característica     | DTD                         | XSD                                          |
| ------------------ | --------------------------- | -------------------------------------------- |
| **Sintaxi**        | No és XML                   | És XML                                       |
| **Tipus de dades** | Només text (`#PCDATA`)      | `string`, `integer`, `boolean`, `date`, etc. |
| **Restriccions**   | Limitades                   | Avançades (mida, patrons, rangs)             |
| **Espais de noms** | No suportats                | Suport per `xmlns`                           |
| **Compatibilitat** | Documents senzills o antics | Estructures modernes i complexes             |
