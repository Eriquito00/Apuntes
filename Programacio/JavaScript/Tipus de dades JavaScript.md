#### Valors simples
- **Números**: enters o decimals.
- **Text**: caràcters, dígits, altres símbols, paraules i frases.
- **Booleans**: si/no, vertader/fals...
#### Valors compostos
- **Dates**: 
- **Llistes**: 
- **Objectes**: 
### Literals
Els **literals** representen un valor que ja es coneix en el moment d'escriure el programa.  
No es guarden en memòria sinò que formen part del codi del programa.
- **Literals numèrics**: 2768, 12.59 o 3.45e3.
- **Literals de text**: "Hola", '74' o '@'.
- **Literals booleans**: true o false.

### Constants i variables
Les dades que necessita un programa es guarden a la memòria. Per reservar espai a la memòria, cal definir **constants** i **variables**. La diferència és que el valor que es guarda en una constant no es pot modificar posteriorment.
Els noms de les constants i variables han de seguir unes regles:
- Ha de ser una paraula (no pot contenir espais entre mig)
- Pot contenir números però no pot començar amb un número
- Pot començar amb guió baix (\_) o $ però, de moment, millor no utilitzar-los
- No pot ser una paraula reservada de JavaScript
- No pot contenir caràcters especials, excepte el guió baix
- Les majúscules i minúscules es consideren diferents (_case-sensitive_)
- Els noms de constants i variables han de ser significatius
##### Exemple de constant
Els noms de les constants es posaran en majúscules i, si contenen més d'una paraula, separades per guió baix.
const MAX_NOTA = 10;
##### Exemple de variable
Els noms de les variables el posaran en minúscules i, si contenen més d'una paraula, cada nova paraula es posarà amb la primera lletra majúscula (_camelCase_)
let notaAlumne = 7;

---
---
---
# Les constants
Normalment quan es comença a programar no s'utilitzen constants ja que normalment es posa el valor literal al codi encara que una constant seria mes util en cas de que en un futur canvï seria molt mes facil i rapid que hi hagues una constant.
El que normalment es fa:
![[Pasted image 20240923084131.png]]
El que s'hauria de fer:
![[Pasted image 20240923084159.png]]
### Avantatges d'utilitzar constants
- Utilitzar un nom ens dona mes informacio que un valor directament com "NOTA_MAX" i "10".
- Si cal canviar el valor nomes s'ha de fer alla on s'hagi declarat la constant, si es un valor s'haura de canviar a tots llocs on estigui.
- Pot ser que mes endavant s'hagi de canviar el valor o canviar per una variable, en cas d'utilitzar constant sera mes rapid i facil.
---
---
---
# Conversio i format de dades
## Conversio entre text i numeros
### De numero a text
Podem convertit tant fent:
- "" + valor
- variable.toString()
![[Pasted image 20240920084507.png]]
### De text a numero
Podem utilitzar un o altre segons per a que utilitzem el valor:
- parseInt()
- parseFloat()
Int sera per a numeros enters; 1, 2, 3.
Float per a numeros decimals; 1.1, 2.3 3.1.
![[Pasted image 20240920084723.png]]
**Si el text no conté un valor numèric, retorna el valor especial NaN (Not a Number).**
### Formatar numeros
Per mostrar resultats es habitual demanar un nombre de decimals per separar decimals o milers. Per fer-ho es pot fer com en el seguent exemple pero hem de tenir en compte que ho pasara a **string**:
![[Pasted image 20240920085055.png]]
Si es vol separar milers i decimals amb els caracters correctes podem fer-ho de la seguent manera:
![[Pasted image 20240920085246.png]]
Aixi segons del pais desde on es faci es veure d'una o d'altre forma, podem veure que en un separa per comes els milers i l'altre els decimals.