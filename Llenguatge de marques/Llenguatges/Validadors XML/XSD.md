# XSD
És una forma més avançada i flexible de definir l’estructura d’un fitxer XML. A diferència de DTD, XSD permet especificar tipus de dades, restriccions i jerarquies complexes, i es basa en el mateix format XML.

XSD s’utilitza per validar documents XML complexos i permet definir regles precises com:  
- Tipus de dades (string, integer, date, boolean, etc.)  
- Valors per defecte i requerits  
- Estructures reutilitzables

```XML
<?xml version="1.0" encoding="UTF-8"?>
<biblioteca xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
    xsi:noNamespaceSchemaLocation="biblioteca.xsd" nom="Biblioteca Central" ciutat="Barcelona">
    
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

```XSD
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">

    <xs:element name="biblioteca">
        <xs:complexType>
            <xs:sequence>
                <xs:element name="llibre" type="LlibreType" maxOccurs="unbounded"/>
            </xs:sequence>
            <xs:attribute name="nom" type="xs:string" use="required"/>
            <xs:attribute name="ciutat" type="xs:string"/>
        </xs:complexType>
    </xs:element>

    <xs:complexType name="LlibreType">
        <xs:sequence>
            <xs:element name="titol" type="xs:string"/>
            <xs:element name="autor" type="xs:string"/>
            <xs:element name="genere" type="xs:string" minOccurs="0"/>
            <xs:element name="preu">
                <xs:complexType>
                    <xs:simpleContent>
                        <xs:extension base="xs:decimal">
                            <xs:attribute name="moneda" type="xs:string" default="EUR"/>
                        </xs:extension>
                    </xs:simpleContent>
                </xs:complexType>
            </xs:element>
            <xs:element name="data_publicacio" type="xs:date" minOccurs="0"/>
        </xs:sequence>
        <xs:attribute name="isbn" type="xs:string" use="required"/>
        <xs:attribute name="idioma" type="xs:string" default="català"/>
    </xs:complexType>

</xs:schema>
```

## Components basics
- **Elements (`xs:element`)**: Defineixen les etiquetes i el seu tipus de dada.
- **Atributs (`xs:attribute`)**: Defineixen informació extra per als elements.
- **Tipus simples (`xs:simpleType`)**: Valors com `string`, `integer`, `date`, etc.
- **Tipus complexos (`xs:complexType`)**: Agrupen elements i atributs en estructures jeràrquiques.
- **Restriccions (`xs:restriction`)**: Defineixen valors permesos, longituds, patrons, etc.
- **Referències (`xs:sequence`, `xs:choice`, `xs:all`)**: Controlen l’ordre i opcionalitat dels elements.
