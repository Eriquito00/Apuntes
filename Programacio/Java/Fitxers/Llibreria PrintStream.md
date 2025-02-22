# Llibreria PrintStream
Per poder escriure a un archiu podem utilitzar PrintStream. Per escriure a arxius amb PrintStream podem utilitzar-ho de la seguent forma:

```Java
PrintStream escriure = new PrintStream("nom arxiu");
```

D'aquesta forma ja tindrem localitzat amb PrintStream el fitxer que volem escriure, per esciure podem fer-ho de la seguent forma:

```Java
//Escriu el text en aquesta linea
escriure.print("string que volem escriure");

//Escriu el text en aquesta linea i fa un cambi de linea
escriure.println("string que volem escriure");
```

D'aquesta forma podem escriure al nostre fitxer el contingut que volguem, sense oblidarnos despres de tancar el fitxer.

```JAVA
escriure.close();
```

Amb aixo ja tindriem tot el necesari per poder escriure a arxius amb PrintStream.