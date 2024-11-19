# String
Els textos (cadenes de caràcters o _strings_) són immutables.  
Això vol dir que, un cop creats, no es poden modificar directament.
![[Pasted image 20240916191842.png|650x75]]
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
- splice(posicio, nº eliminacions): Permet afegir o eliminar elementrs a una array.
- sort(): Ordena l'_array_ **alfabèticament** de més petit a més gran.
- reverse(): Inverteix la posició de tots els elements: si es vol ordenar un _array_ inversament, primer s'utilitza la comanda sort() i després reverse().
### Caràcters especials
Hi ha uns caràcters especials que representen accions en lloc de símbols.  
Aquests caràcters s'anomenen codis d'escapament (_escape codes_).
- '\\n': salt de línia.
- '\\\\': barra invertida.
- '\\'': cometa simple.
- '\\"': cometa doble.
# Math
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
### Generar números aleatoris entre dos valors determinats
// Enter aleatori **entre 'min' i 'max'**, tots dos inclosos  
let n = Math.floor((Math.random() * (max - min + 1) + min));
// Real aleatori **des de 'min' fins a 'max' (aquest últim no inclòs)**
let d = Math.random() * (max - min) + min;
### Problemes de precisió i desbordament
Els valors que es poden utilitzar estan limitats.  
Si no es tenen en compte aquests límits, es poden produir resultats erronis.
![[Pasted image 20240916191637.png|700x250]]