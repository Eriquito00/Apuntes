# Comentaris
Els comentaris serveixen per anar describint el que fa el nostre codi o algunes parts del nostre codi. De comentaris hi han diferents tipus:
### Comentaris fins a final de línia
Serveixen per posar una explicació breu.
Comencen amb // i tot el text o codi que hi ha després fins al final de la línia no s'interpretarà.
int edat;    **// Edat de la  persona**
### Comentaris multilína
Serveixen per posar explicacions més llargues o per comentar blocs de codi.
Tot el text que estigui entre /* i \*/ no s'interpretarà.
/* Funcions auxiliars per gestionar la base de dades:  
    - Afegir  
    - Modificar  
    - Esborrar \*/
### Comentaris de documentació
Són iguals que els comentaris multilínia però tenen un format específic que, amb les eines adequades, permet generar automàticament un document amb les especificacions del programa.
S'han de posar abans de les definicions de les classes, funcions, variables...
\/*  
  \* Funció per ordenar un conjunt de números enters  
  \* **@param** numeros Array amb els números que s'han d'ordenar  
\*/  
  public static void ordenar(int[] numeros) {
    // Codi per ordenar una llista de números de més gran a més petit  
}