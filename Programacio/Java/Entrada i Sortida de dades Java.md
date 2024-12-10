# Entrada
Primer haurem d'importar la llibreria Scanner de la seguent forma:
`import java.util.Scanner`
Aquesta llibreria, com totes, s'importara a l'inici de l'arxiu. Ara ja podem crear el nostre scanner de una forma seguent:
`static Scanner scan = new Scanner(System.in);`
Ara ja tenim el nostre scanner creat, per poder introduir la dada ara farem el seguent per poder donar el valor que s'introdueix a una variable:
`int a = scan.nextLine(); // en cas de String`
`int a = scan.nextInt(); // en cas de numero int`
Y aixi amb la resta dels tipus de valors.
# Sortida
## Print
Treu un valor per consola de forma normal i tradicional i la seguent sortida anira al costat.
`print("Hello World!");`
## Println
Treu un valor per consola de forma normal pero fa un canvi de linea de forma que el seguent valor que es tregui per sonsola sortira abaix.
`println("Hello World!");`
## Printf
Es fa una sortida per consola de forma que es posara un string com a missatge y per mig del string uns "%" y segons el tipus de dada que volem treure:
`printf("La persona te %d edat y es diu %s", 18, "Eric");`
Aqui podem veure que segons el tipus de dada treu unes o altres dades y que estan separades. Segons el tipus de dada es posara:
d: digits enters
s: strings
t: 