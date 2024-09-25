Els textos (cadenes de caràcters o _strings_) són immutables.  
Això vol dir que, un cop creats, no es poden modificar directament.
![[Pasted image 20240916191842.png|650x75]]
***
### Propietats i mètodes dels "strings"
Els mètodes més importants són:
- length: **és una variable** que conté el nombre de caràcters que té la cadena.
- charAt(n): retorna el caràcter en la posició n-èsima.
- toLowerCase() i toUpperCase(): retorna la cadena convertida a minúscules o majúscules, respectivament.
- trim(): retorna una cadena eliminant els espais del principi i del final. També hi ha trimStart() i trimEnd() que només eliminan els del principi o els del final, respectivament.
- includes(text\[, posicio]): comprova si una cadena conté una altra cadena (retorna true o false).  
    El paràmetre opcional posicio serveix per començar a buscar a partir d'un caràcter en lloc de començar des del principi del text. El primer caràcter d'un text és el 0.
- indexOf(text\[, posicio]): retorna la primera posició on es troba el text buscat, o -1 si no el troba.  
    El paràmetre opcional posicio permet començar la cerca a partir d'una posició determinada.
- lastIndexOf(text\[, posicio]): igual que l'anterior però començant pel final del text.
- substring(inici\[, final]): retorna la subcadena entre els índexs inici i final (o fins al final).  
    El caràcter en la posició final no s'inclou.
- replace(t1, t2) i replaceAll(t1, t2): retorna la cadena després de substituir t1 per t2.  
    Substitueix la primera aparició o totes, respectivament.
- repeat(n): retorna la cadena repetida n vegades.
- padStart(n, text) i padEnd(n, text): enganxa text a l'_string_ tantes vegades com sigui necessari fins que tingui la ongitud indicada en n.  
    Ho enganxa al principi o al final de l'_string_, respectivament.
- startsWith(text) o endsWith(text): comprova si la cadena comença o acaba amb la subcadena especificada, respectivament.
- split(text): retorna un _array_ de _String_ que és el resultat de separar la cadena utilitzant una altra cadena com a separador.
### Caràcters especials
Hi ha uns caràcters especials que representen accions en lloc de símbols.  
Aquests caràcters s'anomenen codis d'escapament (_escape codes_).
- '\\n': salt de línia.
- '\\\\': barra invertida.
- '\\'': cometa simple.
- '\\"': cometa doble.