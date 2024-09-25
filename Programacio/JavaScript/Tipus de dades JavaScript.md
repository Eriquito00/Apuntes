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