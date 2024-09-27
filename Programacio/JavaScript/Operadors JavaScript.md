# Operadors matematics
### Operador assignació
L'operador assignació (=) serveix per guardar una dada en una variable o constant. La variable o constant s'ha d'haver definit prèviament. La dada pot ser un literal o estar en una altra constant o variable. Es pot definir i assignar en una mateixa sentència (no cal fer-ho en 2 passos). Les constants s'han de definir i inicialitzar en la mateixa sentència.
***
Una variable només pot contenir una dada.  
Si posteriorment se li assigna un altre valor, el valor anterior es perd.

![[Pasted image 20240916184056.png|150x75]]![[Pasted image 20240916183716.png|100x100]] ![[Pasted image 20240916183907.png|100x100]]![[Pasted image 20240916183937.png|100x100]]
Es necessita una tercera variable per poder fer l'intercanvi.
Els passos a seguir són:
1. Guardar el valor d'una de les variables en la variable temporal.
2. Passar del valor de l'altra variable a la primera.
3. Passar el valor de la variable temporal a la segona variable.
![[Pasted image 20240916184333.png|150x100]]![[Pasted image 20240916184419.png|150x75]]![[Pasted image 20240916184539.png|250x75]]
**//intercambi**
![[Pasted image 20240916184741.png|250x75]]![[Pasted image 20240916184806.png|250x75]]
***
### Operadors binaris amb números
Permeten realitzar operacions amb dos valors (dues variables o constants, dos literals, una variable i un literal...) i obtenir el resultat.
En el cas de variables de tipus numèric són:
- Suma (+)
- Resta (-)
- Multiplicació (\*)
- Divisió (/)
![[Pasted image 20240916190319.png|120x100]]
- Operació i assignació (+=, -=, \*=, /=):
![[Pasted image 20240916190402.png|250x125]]
***
### Operador mòdul (%)
En el cas dels **nombres enters**, a més dels operadors anteriors cal afegir l'operació mòdul (%).  
Aquesta operació retorna el residu d'una divisió entera.
![[Pasted image 20240916190627.png|300x50]]
Aquest operador s'utilitza sovint en informàtica:

- Calcular si un número és múltiple d'un altre (si **25 % 5 == 0**, 25 és múltiple de 5).
- Descomposar en múltiples i submúltiples (250 segons equivalen a **250 / 60 minuts** i **250 % 60 segons**).
- Gestionar operacions cícliques (sumar **X** de forma repetida i cada cop que s'arribi a **N**, reiniciar).
***
### Operadors unaris
Són operadors que només afecten a una dada.
- Signe negatiu (-): canvia el signe d'una dada o variable.
- Increment (++): a++ → a = a + 1.
- Decrement (--): a-- → a = a - 1).
![[Pasted image 20240916190851.png|300x50]]
***
## Precedència dels operadors

Si no es posen parèntesis, les operacions s'executen en el següent ordre:

1. Operadors unaris (signe -, increment ++, decrement --)
2. Multiplicació, divisió i residu (\*, /, %)
3. Suma i resta (+, -)
4. Relacionals (<, >, <=, >=, \==, !=)
5. Lògics (!, &&, ||)
---
---
---
# Operadors relacionals i logics
## Operadors relacionals
S'utilitzen per fer comparacions.  
El resultat només pot ser true o false.
- Menor que (<)
- Major que (>)
- Menor o igual que (<=)
- Major o igual que (>=)
- Igual que (\==)
- No igual que (!=)
![[Pasted image 20240923105336.png]]
---
## Operadors logics
S'apliquen a valors binaris (true i false). Es poden utilitzar per combinar el resultat de diferents operacions relacionals. El resultat només pot ser true o false.
- NOT (!): inverteix el valor (si era true, el converteix a false; si era false el converteix a true).
- AND (&&): només si els dos valors són true, el resultat és true.
- OR (||): només que un dels dos valors sigui true, el resultat serà true.
- XOR (^): si els dos valors són iguals, el resultat serà false.
![[Pasted image 20240923105928.png]]
### Taules de veritat
![[Pasted image 20240923110208.png]]