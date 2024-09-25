## Demanar dades a l'usuari
Per demanar dades a l'usuari tenim diferents metodes i amb diferents objectius cadascun.
El mètodes que permeten fer preguntes a l'usuari són:  
- confirm(pregunta): mostra una finestreta similar a un alert() però amb dos botons: **Acceptar** i **Cancel·lar**. Si l'usuari prem el botó **Acceptar**, retorna true; si prem **Cancel·lar**, retorna false.
- prompt(pregunta): similar a l'anterior però amb un espai perquè l'usuari pugui escriure una resposta.
![[Pasted image 20240920085746.png]]
## Tractar les dades de l'usuari
De vegades, els usuaris escriuen espais al principi o al final de la resposta que no s'han de tenir en compte. O cal que la resposta sigui en majúscules però l'escriuen en minúscules o barrejant majúscules i minúscules. Per aquests casos hi ha dos mètodes que es poden aplicar a les respostes per evitar errors en el processament posterior:
- toUpperCase() (o toLowerCase()): converteix tot a majúscules (o a minúscules).
- trim(): elimina els espais que pugui haver al principi i al final del text.
![[Pasted image 20240920085954.png]]
## Agafar dades numeriques
Les respostes que s'obtenen amb prompt() sempre són de tipus text, encara que l'usuari escrigui un número. Quan la resposta ha de ser un número per poder fer càlculs matemàtics, cal convertir-la utilitzant els mètodes que s'han vist en capítols anteriors: parseInt() i parseFloat().
![[Pasted image 20240920090158.png]]