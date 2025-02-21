# Llibreria FileWriter
Per poder escriure a un archiu podem utilitzar FileWriter. Per escriure a arxius amb FileWriter podem utilitzar-ho de la seguent forma:

```Java
FileWriter escriure = new FileWriter("nom arxiu");
```

D'aquesta forma ja tindrem localitzat amb FileWriter el fitxer que volem escriure, per esciure podem fer-ho de la seguent forma:

```Java
escriure.write("string que volem escriure");
```

D'aquesta forma podem escriure al nostre fitxer el contingut que volguem, sense oblidarnos despres de tancar el fitxer.

```JAVA
escriure.close();
```

Amb aixo ja tindriem tot el necesari per poder escriure a arxius amb FileWriter.