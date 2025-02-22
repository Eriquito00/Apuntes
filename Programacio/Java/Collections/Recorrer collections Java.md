# Recorrer collections
Totes les collections es poden recorrer de la mateixa forma:

![](../../../Imatges/Pasted%20image%2020250222135801.png)

## For

```Java
ArrayList<String> llista = new ArrayList<String>();

for (int i = 0; i < llista.size(); i++){
	System.out.println(llista.get(i));
}
```

## For Loop

```Java
ArrayList<String> llista = new ArrayList<String>();

for (String e: llista){
	System.out.println(e);
}
```

## Iterators

```Java
ArrayList<String> llista = new ArrayList<String>();

iterator<String> it = llista.iterator();

while (it.hasNext()){
	String e = it.next();
	System.out.println(e);
}
```

## ForEach()

```Java
ArrayList<String> llista = new ArrayList<String>();

//Amb foreach
llista.forEach(System.out::println);

//Amb funcio lambda al foreach
llista.forEach(e -> System.out:println(e));
```