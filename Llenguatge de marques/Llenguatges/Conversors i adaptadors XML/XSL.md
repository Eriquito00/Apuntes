# XSL
XSL es una forma de transformar els nostres XML a un document HTML amb la informacio del XML, aixi podrem mostrar la informacio del nostre XML en aquest format, poguent aplicar CSS i amb una estructura mes visible i entenedora per l'usuari. Aqui tenim un exemple de un document XSL:

```XML
<?xml version="1.0" encoding="UTF-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
    <xsl:template match="/">
        <html>
            <head>
	            //Link al nostre css
                <link rel="stylesheet" type="text/css" href="styles.css"/>
                <title>Exemple XSL</title>
            </head>
            <body>
                <h1>Lista d'elements</h1>
				//per cada element item mostrara aquesta info
				<xsl:for-each select="items/item">
					<h1>
						//valor mostrat directament
						<xsl:value-of select="nombre"/>
					</h1>
					
					<p>
						//if - else 
						<xsl:choose>
							//Preu alt en cas de ser mes gran de 100
							<xsl:when test="precio &gt; 100">
								<em>Precio alto</em>
							</xsl:when>
							
							//Preu baix si no
							<xsl:otherwise>
								<em>Precio bajo</em>
							</xsl:otherwise>
						</xsl:choose>
					</p>
					
					<p>
						//condicional if 
						<xsl:if test="@oferta='true'">
							<span style="color: red;"> ¡En oferta!</span>
						</xsl:if>
					</p>
				</xsl:for-each>
            </body>
        </html>
    </xsl:template>
</xsl:stylesheet>
```
## Etiquetes
Podem veure que per fer un HTML utilitzem exactament les mateixes etiquetes, exatament amb el css que nomes el podrem aplicar a aquelles etiquetes del nostre XSL que siguin de HTML pero les propies de XML son les seguents:

- xsl:foreach : Basicament fara un foreach per cada element d'aquest tipus i mostrara la informacio que hi posem dins.
- xsl:choose : Una estructura IF - ELSE, si la condicio que posem al xsl:when es compleix mostrara el que hi posem dins, si no mostrara el que hi es dins del xsl:otherwise
- xsl:if : Un condicional normal i corrent en el que si no es compleix la condicio no pasara res i si es compleix es mostrara el que posem dins.
## Operadors
- **&gt;** : Operador MAJOR QUE, >.
- **&lt;** : Operador MENOR QUE, <.
- **=** : Operador de igual, =.