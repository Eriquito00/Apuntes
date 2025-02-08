# Condicionals JavaScript
## Condicional simple
Si el resultat de l'expressio logica es "true" s'executa un bloc de codi; si es "false", no s'executa. En diagrama de flux es representaria de la seguent forma:

![](/Imatges/Pasted%20image%2020240923104720.png)

Es recomana la següent forma:

![](/Imatges/Pasted%20image%2020240923105426.png)

Si el codi consta de més d'una sentència o es preveu que més endavant se n'hi poden afegir més, cal afegir les claus { i } per delimitar el codi que s'ha d'executar quan la condició sigui certa:

![](/Imatges/Pasted%20image%2020240923105512.png)

### Condicional amb dos blocs de codi alternatius
Si el resultat de l'expressió lògica és true s'executa un bloc de codi; si és false, s'executa l'altre. En diagrama de flux seria de la seguent forma:

![](/Imatges/Pasted%20image%2020240923105605.png)

Es recomana la següent forma:

![](/Imatges/Pasted%20image%2020240923105624.png)

Si el codi consta de més d'una sentència o es preveu que més endavant se n'hi poden afegir més, cal afegir les claus { i } per delimitar el codi que s'ha d'executar quan la condició sigui certa:

![](/Imatges/Pasted%20image%2020240923105652.png)

### Condicionals encadenat amb mes de dos blocs alternatius
Si hi ha més de dos possibles blocs cal utilitzar aquesta estructura en diagrama de flux:

![](/Imatges/Pasted%20image%2020240923110727.png)

El codi equivalent seria:

![](/Imatges/Pasted%20image%2020240923110746.png)

## Condicional avançat
Aquesta estructura s'utilitza sobretot a condicions senzilles. S'utilitza "?" per separar la condicio de la resta de l'estructura i entre "?" i ":" es posa el valor si la condicio es cerca i despres del ":" es dona el valor si la condicio es falsa. Aqui podem veure un exemple:

![](/Imatges/Pasted%20image%2020240927091921.png)

Serveix per simplificar el seguent condicional:

![](/Imatges/Pasted%20image%2020240927091942.png)

Aquests dos codis fan el mateix pero gracies al ternari ho podem fer de forma mes simplificada.

## Estructura de seleccio

![](/Imatges/Pasted%20image%2020240930105328.png)

Aquesta estructura te un funcionament similar a "if ... else if ... else ..." pero amb alguna diferencia important.
- La comparacio sempre es fa entre una unica variable i diversos valors constants o literals.
- Nomes permet comparar si la variable es igual a uns valors determinats.

![](/Imatges/Pasted%20image%2020240930105544.png)

Aqui podem veure un exemple, al qual en cas de NO posar break quan el case 1 acabes començaria sense tenir en compte la condicio el case 2. Al default no es necesari posar break ja que al acabar default ja sortira.

![](/Imatges/Pasted%20image%2020240930105756.png)

Aqui podem veure un altre cas en el cual en qualsevol dels casos poma, cirera o banana fara el alert i si es llimona o pinya fara l'altre.