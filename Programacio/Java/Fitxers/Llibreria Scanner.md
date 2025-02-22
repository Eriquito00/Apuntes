# Llibreria Scanner
Per llegir amb Scanner tambe podem llegir fitxers, de la seguent forma podem crear un reader per el nostre fitxer:

```JAVA
Scanner llegir = new Scanner("nom del fitxer");
```

Amb aixo hem creat un reader per aquest fitxer, ara per anar absorvint el text del fitxer podem utilitzar algunes de les seguents funcions.

```JAVA
//Comprova si hi ha mes paraules sense absorvir el contingut
llegir.hasNext();

//Comprova si hi ha mes linies al fitxer sense absorvir el contingut
llegir.hasNextLine();

//Agafa el contingut de la seguent paraula que existeixi
llegir.next();

//Agafa el congingut de la seguent linea que existeixi
llegir.nextLine();
```

Amb questes funcions podriem fer un codi senzill per anar absorvint la informacio poc a poc com per exemple de la seguent forma:

```JAVA
//Fitxer que absorvim
File archivo = new File("./readme.txt");

//Scanner que llegira el fitxer
Scanner llegir = new Scanner(archivo);

//String que emmagatzemara el contingut
String contingut = "";

//Bucle per recorre el fitxer sempre i quan hi ha mes linies
while(llegir.hasNextLine()){

	//Guardar el contingut de cada linea a la variable
	contingut += llegir.nextLine();
}
```

D'aquesta forma tindriem el nostre contingut del fitxer emmagatzemat al string o el podriem anar treien per consola o el que volguem.