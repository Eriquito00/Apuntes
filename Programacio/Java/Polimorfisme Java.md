# Polimorfisme Java
El polimorfisme consta en crear funcions mes especifiques depenent dels nostres objectes, es a dir, els peixo neden, i els mamifers caminen, per tant podem crear una funcio generica de Animal que sigui moure.

``public class Animal {  
    ``public void moure() {  
        ``System.out.println("M'estic movent");  
    ``}  
``}

Aqui podem veure que la funcio moure de Animal sera que s'esta movent, pero ara tenim un Peix que volem crearli la funcio moure pero adaptada, ja que els peixos neden.

``public class Peix extends Animal {  
    ``public void moure() {  
    ``//super.moure();
        ``System.out.println("Estic nedant");  
    ``}  
``}

Aqui podem veure la funcio que es especifica per aquesta subclase. I podem veure al comentari que podem utilitzar la funcio generica de la clase mare Animal.