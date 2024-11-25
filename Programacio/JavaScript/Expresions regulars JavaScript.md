Les expresions regultars son utils per la comprovacio de textos que hagin de complir un format especific, per exemple:
- Matricules
- DNI
- Nº telefon
## Patrons
En JS les expresions es tracten de forma que obrim amb "/" i tanquem amb "/".
Els modificadors mes utilitzats son els seguents:
- g: coincidencia global. (totes les vegades que aparegui el patro)
- i: coincidencia intensitiva. (sense diferenciar majuscula i minuscula)
- m: cerca multilinea. (no ve limitada per salts de linea)
## Caracters especials
Els següents caràcters tenen un significat especial.
\[ ] ( ) { } \ ^ $ | ? * + .

Si es volen utilitzar com a caràcters a detectar, cal posar \ al davant (\\*   \\.   \\+   \\(   \\\\...).

- \[ ]: per especificar un **conjunt** de caràcters.
- ( ): per **agrupar**.
- { }: per indicar un nombre de repeticions.
- \: per poder utilitzar caràcters especials, per representar caràcters especials o per conjunts de caràcters.
- ^: té dos possibles significats:
	- indicar que la coincidència ha d'estar al principi de la línia.
	- si es posa com a primer caràcter dins de [ ], implica negació ([^AEIOUaeiou] detectarà qualsevol caràcter que no sigui una vocal).

- $: indica que la coincidència ha d'estar al final de la línia.
- |: per triar entre diferents possibilitats.
- ?: indica que el caràcter o grup anterior pot aparèixer una o cap vegada.
- +: indica que el caràcter o grup anterior ha d'aparèixer una o més vegades.
- \*: indica que el caràcter o grup anterior pot aparèixer zero, una o més vegades.
- .: equival a qualsevol caràcter.

Les següents expressions tenen un significat especial (caràcters especials o conjunt de caràcters).
**\t   \n   \s   \S   \d   \D   \w   \W**

- \t: representa un tabulador.
- \n: representa un salt de línia.
- \s: representa qualsevol caràcter que sigui un separador. És equivalent a \[ \t\n\x0B\f\r].
- \S: representa qualsevol caràcter que no sigui un separador. És equivalent a \[^\s].
- \d: representa qualsevol caràcter que sigui un dígit. És equivalent a \[0-9].
- \D: representa qualsevol caràcter que no sigui un dígit. És equivalent a \[^0-9].
- \w: representa qualsevol caràcter que pot formar una paraula. És equivalent a \[a-zA-Z_0-9].
- \W: representa qualsevol caràcter que no formi part d'una paraula. És equivalent a \[^\w].
## Comandes de la classe _String_ que utilitzen expressions regulars

- string.match(regex): retorna un _array_ amb les coïnciències que ha trobat.
- string.split(regex): divideix el text creant un _array_ de _strings_ utilitzant com a separador l'expressió regular.
- regex.test(string): retorna _true_ si troba l'expressió regular dins del _string_.