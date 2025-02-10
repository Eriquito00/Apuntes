# DTD
Es una forma de determinar i definir l'estructura d'un fitxer XML, tot i que es una de les mes antigues i que ja no s'utilitza practicament.

Principalment DTD utilitza elements i atributs per determinar la jerarquia del nostre XML, podem fer-ho directament al XML o a un altre arxiu diferent i s'utilitza a documents molt senzills o antics.

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE biblioteca SYSTEM "biblioteca.dtd">
<biblioteca nom="Biblioteca Central" ciutat="Barcelona">
    <llibre isbn="978-84-9823-991-4" idioma="català">
        <titol>El petit príncep</titol>
        <autor>Antoine de Saint-Exupéry</autor>
        <genere>Fantasia</genere>
        <preu moneda="EUR">12.50</preu>
        <data_publicacio>1943-04-06</data_publicacio>
    </llibre>
    <llibre isbn="978-84-376-0494-7" idioma="espanyol">
        <titol>Cien años de soledad</titol>
        <autor>Gabriel García Márquez</autor>
        <preu moneda="EUR">18.75</preu>
    </llibre>
</biblioteca>
```

```DTD
<!ELEMENT biblioteca (llibre+)>
<!ATTLIST biblioteca nom CDATA #REQUIRED>
<!ATTLIST biblioteca ciutat CDATA #IMPLIED>

<!ELEMENT llibre (titol, autor, genere?, preu, data_publicacio?)>
<!ATTLIST llibre isbn CDATA #REQUIRED>
<!ATTLIST llibre idioma CDATA "català">

<!ELEMENT titol (#PCDATA)>
<!ELEMENT autor (#PCDATA)>
<!ELEMENT genere (#PCDATA)>
<!ELEMENT preu (#PCDATA)>
<!ATTLIST preu moneda (EUR|USD|GBP) "EUR">

<!ELEMENT data_publicacio (#PCDATA)>
```
## Components basics
- **Elements**: Defineixen les etiquetes i la seva estructura.
- **Atributs**: Proporcionen informació extra als elements.
- **Entitats**: Representen valors predefinits o caràcters especials.
- **PCDATA**: Contingut de text dins d’un element que pot ser interpretat.
- **CDATA**: Contingut de text que no serà interpretat.