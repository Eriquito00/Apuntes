# Estructura i semantica del SEO
## Coses a tenir en compte
- Escriure URL netes i facils
		`www.elmeusite.com/blog/consells-seo` ✔️
		`www.elmeusite.com/index.php?id=34&cat=12` ✖️
- Ordena amb H1, H2, H3 com si fessis un idex (NOMES 1 H1)
- Fitxers sitemap.xml i robot.txt
- Pensar en paraules clau principals i secundaries
- Afegir context amb conceptes relacionats (LSI)
- Dona-li info extra a Google amb schema.org
## Exemples dels arxius per millorar SEO
### robots.txt
```TXT
# Permetre a tots els robots accedir a tot  
User-agent: *  
Disallow:  
  
# Exemple: bloquejar un directori privat  
User-agent: *  
Disallow: /privat/
```
### sitemap.xml
```XML
<?xml version="1.0" encoding="UTF-8"?>  
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">  
  <url>  
	<loc>https://www.elmeusite.com/</loc>  
    <lastmod>**2025-09-01</lastmod>  
    <priority>1.0</priority>  
  </url>  
  <url>  
    <loc>https://www.elmeusite.com/blog/consells-seo</loc>  
    <lastmod>2025-09-10</lastmod>  
    <priority>0.8</priority>  
  </url>  
</urlset>
```
Ajudar a Google perque no es perdi per la pagina:
- `<loc>`: URL de la pagina
- `<lastmod>`: quan es va actualitzar
- `<priority>`: importancia de 0.0 a 1.0
### schema.org
```JS
<script type="application/ld+json">  
{  
  "@context": "https://schema.org/",  
  "@type": "Recipe",  
  "name": "Pizza casolana",  
  "author": {  
    "@type": "Person",  
    "name": "Maria Cuinera"  
  },  
  "datePublished": "2025-09-20",  
  "description": "Una recepta fàcil de pizza casolana amb massa cruixent.",  
  "prepTime": "PT20M",  
  "cookTime": "PT15M",  
  "totalTime": "PT35M",  
  "recipeYield": "4 racions",  
  "recipeIngredient": [  
    "500g de farina",  
    "300ml d'aigua",  
    "20g de llevat",  
    "Formatge, tomàquet, toppings al gust"  
  ],  
  "recipeInstructions": [  
    "Barrejar la farina amb el llevat i l’aigua.",  
    "Deixar reposar 1 hora.",  
    "Estirar la massa i afegir toppings.",  
    "Coure al forn 15 minuts a 220ºC."  
  ]  
}  
</script>
```
Aixo ajudara a que cerques semblants a les paraules originals de la cerca tambe pugui arribar la nostre web.
[Web per validar el archiu schema.org](https://search.google.com/test/rich-results?hl=ca)