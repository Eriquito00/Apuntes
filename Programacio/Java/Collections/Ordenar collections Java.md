# Ordenar collections Java
Per ordenar collections podem utilitzar sort. Per comparar podem fer ho de diferents formes, com Comparable y Comparator:
## Comparable
Als objectes que volguem compara per poder ordenarlos haurem d'implementarlis la interficie Comparable de la seguent forma:

```Java
public class Caixa implements Comparable<Caixa>{}
```

Y per comparar entre objectes podem utilitzar compareTo(), pasantli un objecte y ens els comparara segons un atribut que nosaltres volguem del objecte per exemple:

```Java
//Atributs de nom i pes de cada caixa
Caixa a = new Caixa("caixa1",15);
Caixa b = new Caixa("caixa2",10);
a.getPes().compareTo(b.getPes());
```

## Comparator
Per comparar amb criteris diferents als predefinits del objecte utilitzarem Comparator i haurem d'implementarlis la interficie Comparator de la seguent forma:

```Java
public class Caixa implements Comparator<Caixa>{}
```

Si utilitzem Comparator podem utilitzar compare, que aquest ens compara directament dos objectes com en el exemple seguent:

```JAVA
//Atributs de nom i pes de cada caixa
Caixa a = new Caixa("caixa1", 15);
Caixa b = new Caixa("caixa2", 10);
int resultat = Integer.compare(a.getPes(), b.getPes());
```

## Sort
Podem utilitzar sort en cas de tenir una ArrayList de objectes o de dades y poder ordenarles de petit a gran, per exemple:

```JAVA
ArrayList<Caixa> caixes = new ArrayList<Caixa>();

//Atributs de nom i pes de cada caixa
caixes.add(new Caixa("caixa1", 15));
caixes.add(new Caixa("caixa2", 10));

//PETIT - GRAN
//Utilitzant una funcio Lambda
caixes.sort((u1, u2) ->
			u1.getPes() - u2.getPes());

//Utilitzant compator
caixes.sort(Comparator.comparingInt(Caixa::getPes));

//GRAN - PETIT
//Utilitzant una funcio Lambda
caixes.sort((u1, u2) ->
			u2.getPes() - u1.getPes());

//Utilitzant compator
caixes.sort(Comparator.comparingInt(Caixa::getPes).reversed());
```

## Stream
Si volem fer un filtre per exemple utilitzant Stream per poder ordenar objectes utilitzant menys codi i amb funcions lambda:

```JAVA
ArrayList<Caixa> caixes = new ArrayList<Caixa>();

//Atributs de nom i pes de cada caixa
caixes.add(new Caixa("caixa1", 15));
caixes.add(new Caixa("caixa2", 10));

//FILTRE
int total = caixes.stream()
		.filter(x -> x.getPes() > 5)
		.count();
```