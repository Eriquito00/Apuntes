# Excepcions Java
Un event que apareix per avisar d'un error durant l'execucio d'un programa i que interromp el flux normal. De forma que captura un event i el gestiona, de forma que el captura y atura el programa.
## Errors i Excepcions
Error: situacio irrecuparable que no te solucio i que el programador no necesita capturar, per exemple si no podem accedir a un BBDD.

Excepcio: Situacio que apareix durant la execucio del programa que es pot gestionar per continuar amb el programa.
### Excepcions
RuntimeException: Errors que el programador no esta obligat a capturar i gestionar. Errors que no es revisen al codi d'un programa perque donden per asumit que no es poden produir pero nosaltres volem provocarles, com per exemple si volem que una variable no tingui valor inferior a 0.
No RuntimeException: Excepcions que el programador esta obligat a gestionar. Com per exemple quan no trobem un arxiu que hem de llegir o escriure.
## Mostrar Excepcions
Orientat a mostrar el missatge que hem posat quan llençem l'error.
- System.out.println(e.getMessage());

Orientat al programador informant a la funcio, linea y recorregut que ha fet fins que s'ha causat l'error.
- e.printStackTrace(); 
