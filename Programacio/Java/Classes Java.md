# Classes Java
## Tipus de classes
- **public**: permet l'accés des de qualsevol altra classe.
- **private**: només permet l'accés des de la mateixa classe.
- **protected**: permet l'accés des de les classes del mateix paquet i des de les subclasses.
- **(default/package)**: només permet l'accés des de una classe del mateix paquet.

Tambe tenim alguns modificadors com: 
- `static`: indica que es tracta d'un unic membre.
- `final`: es una dada que no es pot modificar, se li dona un valor al declararla y no es modifica.
## Estatiques
Les classes i dades que son estatiques son dades que corresponen directament sobre un unic objecte, como nomes hi ha un no es necesari crear objectes ni res. Les dades es declaren de la seguent forma:
`public static int edad = 18;`
## Dinamiques
Les classes i dades que son dinamiques s'utilitzen a la programacio orientada a objectes de forma que cada objecte tindra les seves propies dades.
## Herencia de classes
A Java podem tenir una super clase com per exemple la clase Persona que te com a subclases Alumne i Profesor de forma que a persona tindriem nom, cognom i dni i a Alumne i Professor tindriem el mateix i a mes a mes les seves especifiques.

A mes a mes tambe tindriem els metodes equals() per comparar les referencies de memoria.

Tambe, toString() que es un metode que s'ha de crear a la classe del objecte y ens serveix per treure un string amb totes les dades del objecte. Si volem crear un metode per comparar les dades de dos objectes hauriem de crear com un "equals()" fet per nosaltres en el que li pasem les dades dels objectes i ens el compari.

Ara per crear una clase mare y una clase filla podem fer-ho de la seguent forma:
Clase mare
`public class Animal{...}`

Classes filles
`public class Mamifer extends Animal{...}`
`public class Peix extends Animal{...}`
`public class Ocell extends Animal{...}`

Tambe en el seguent exemple podem veure com portar atributs de la classe mare a les classes filles. Podem veure qeu s'inicialitza un atribut directe per Peix com 'profunditat' i que tenim l'atribut 'nom' de la clase mare:

`public class Peix extends Animal {  
    ``int profunditat;
  
    public Peix(String nom, int profunditat) {  
        super(nom);
        this.profunditat = profunditat;
    }
  
    public int getProfunditat() {
        return profunditat
    }
``}

Ara si volem fer una array amb els objectes Animal no hi ha cap problema en afegir les subclases, per exemple si creem una array de la clase Animal podem afegir Peix i Mamifer i tots els que siguin fills de Animal.

``Animal[] animals = new Animal[5];  
``Animal ovella = new Mamifer("Ovella");  
``animals[0] = ovella;
``animals[1] = new Peix("Sardina", 100);

Si volem sapiguer el nom de clase de un Objecte de una array podem utilitzar getClass() per obtenir la clase i getSimpleName() per obtenir el nom simple de la clase.

``String classe = animals[1].**getClass().getSimpleName()**;// classe = "Peix"

## Abstractes
### Classes
Les clases abstractes s'utilitzen per a que no es puguin crear objectes d'aquest tipus de clase, es a dir si tenim Animal i com a subclase Peix i Ocell. Podem posar com a clase abstracta la clase Animal per a que no es puguin crear animals generics pero si que es podran crear animals que siguin subclases de Animal, es a dir, podriem crear Peixos pero no Animals.

``public abstract class Animal {  
    ``public abstract void moure();  
``}

Si tenim la clase animal d'aquesta forma es podran crear Peixos pero no en si Animals.
### Funcions
Tambe igual que les classes podem tenir funcions abstractes, que son funcions que es declaren a les classes abstractes pero no s'els hi dona cap valor ni res del que han de fer, simplement es declaren, y despres a les subclases haurem de dir obligatoriament el que ha de fer.

CLASSE:
``public abstract class Animal{
	``public abstract void moure();
``}

SUBCLASSE:
``public class Mamifer extends Animal {
	``public void moure(){
		``System.out.println("M'estic movent");
	``}
``}

D'aquesta manera directament podem fer una funcio que pertany a totes les subclasses pero que sigui personalitzada per cadascuna.