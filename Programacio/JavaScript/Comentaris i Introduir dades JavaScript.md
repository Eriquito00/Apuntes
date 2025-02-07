# Comentaris i Introduir dades JavaScript
## Comentaris
Els comentaris serveixen per anar describint el que fa el nostre codi o algunes parts del nostre codi. De comentaris hi han diferents tipus:
#### Comentaris fins a final de línia
Serveixen per posar una explicació breu.
Comencen amb // i tot el text o codi que hi ha després fins al final de la línia no s'interpretarà.
let edat;    **// Edat de la  persona**
#### Comentaris multilína
Serveixen per posar explicacions més llargues o per comentar blocs de codi.
Tot el text que estigui entre /* i \*/ no s'interpretarà.
/* Funcions auxiliars per gestionar la base de dades:  
    - Afegir  
    - Modificar  
    - Esborrar \*/
#### Comentaris de documentació
Són iguals que els comentaris multilínia però tenen un format específic que, amb les eines adequades, permet generar automàticament un document amb les especificacions del programa.
S'han de posar abans de les definicions de les classes, funcions, variables...
\/*  
  \* Funció per ordenar un conjunt de números enters  
  \* **@param** numeros Array amb els números que s'han d'ordenar  
\*/  
function ordenar(numeros) {  
    // Codi per ordenar una llista de números de més gran a més petit  
}
Es poden posar cometes simples dintre de les dobles o al revés, però només un nivell:  
"Els 'strings' són cadenes de caràcters"  
Per posar cometes d'un tipus dins de cometes del mateix tipus cal posar \\ al davant:  
"Els \\"strings\\" són cadenes de caràcters"
## Introduir dades
### Demanar dades a l'usuari
Per demanar dades a l'usuari tenim diferents metodes i amb diferents objectius cadascun.
El mètodes que permeten fer preguntes a l'usuari són:  
- confirm(pregunta): mostra una finestreta similar a un alert() però amb dos botons: **Acceptar** i **Cancel·lar**. Si l'usuari prem el botó **Acceptar**, retorna true; si prem **Cancel·lar**, retorna false.
- prompt(pregunta): similar a l'anterior però amb un espai perquè l'usuari pugui escriure una resposta.
![](/Imatges/Pasted%20image%2020240920085746.png)
### Tractar les dades de l'usuari
De vegades, els usuaris escriuen espais al principi o al final de la resposta que no s'han de tenir en compte. O cal que la resposta sigui en majúscules però l'escriuen en minúscules o barrejant majúscules i minúscules. Per aquests casos hi ha dos mètodes que es poden aplicar a les respostes per evitar errors en el processament posterior:
- toUpperCase() (o toLowerCase()): converteix tot a majúscules (o a minúscules).
- trim(): elimina els espais que pugui haver al principi i al final del text.
![](/Imatges/Pasted%20image%2020240920085954.png)
### Agafar dades numeriques
Les respostes que s'obtenen amb prompt() sempre són de tipus text, encara que l'usuari escrigui un número. Quan la resposta ha de ser un número per poder fer càlculs matemàtics, cal convertir-la utilitzant els mètodes que s'han vist en capítols anteriors: parseInt() i parseFloat().
![](/Imatges/Pasted%20image%2020240920090158.png)
