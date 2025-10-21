# DOM amb TypeScript
## Window
Amb window podem accedir a informacio que conte la nostre pagina i inclus alguna informacio de navegacio interna de la nostre pagina de l'usuari, els parametres mes utilitzats de window son els seguents:
- **document**: conté la pàgina actual (un document HTML).
- **location**: conté informació sobre la URL de la pàgina actual.
- **history**: conté informació sobre les pàgines vistes en aquest _window_.
- **navigator**: conté informació sobre el navegador que s'està utilitzant.
- **screen**: conté informació sobre la pantalla on està obert el navegador.
- **console**: proporciona mètodes per proporcionar informació a través de la consola del navegador.
## Propietats i metodes
Propietats principals del objecte:
- **innerWidth** i **innerHeight**: Mida de la finestra sense scrolls.
- **outerWidth** i **outerHeight**: Mida de la finestra incloent scrolls.
- **scrollX** i **scrollY** (**offset**): Desplaçament de la pagina respecte la finestra.
- **frames** (**iframes**): Els marcs que conte la pagina.

Els mètodes més importants són:
- alert(): per fer aparèixer missatges de tipus.
- confirm(): per demanar confirmació.
- prompt(): per demanar una dada.
- getComputedStyle(): per obtenir l'estil aplicat actualment a un element.
- scrollBy(): desplaçar la pàgina una quantitat de determinada de píxels.
- scrollTo(): desplaçar la pàgina a una posició determinada en píxels.
## Document
- title: conté el títol del document.
- body: conté el document (l'element `<body>`).
- URL: conté la URL del document HTML.
- defaultView: : conté l'objecte window que conté el document.
- write(c): escriu codi HTML dins del document.
- writeln(c): igual que write però afegint un salt de línia \n.
- getElementById(id): obté una referència a l'objecte amb l'identificador id.
- getElementsByTagName(tag): obté un _array_ amb tots els elements amb l'etiqueta especificada.
- getElementsByClassName(class): obté un _array_ amb tots els elements que tenen la classe especificada.
- getElementsByName(name): obté un _array_ amb tots els elements amb el nom especificat.
- querySelector(q): retorna el primer element que coïncideix amb el selector CSS especificat.
- querySelectorAll(q): retorna un _array_ amb tots els elements que coïncideixen amb el selector CSS especificat.
- createElement(tag): crea un element amb l'etiqueta especificada.
## Location
- **href**: url sencera de la web. (https://www.ejemplo.com)
- **protocol**: tipus de protocol. (http o https)
- **pathname**: adreça de la web. (www.ejemplo.com)
- **assign(URL)**: carrega un nou document i es afegir a history.
- **replace(URL)**: igual que l'anterior pero substitueix l'actual en history.
- **reload()**: torna a carregar el document actual.
## History
- **back()**: carrega la pagina de historial anterior.
- **forward()**: carrega la pagina de historial seguent.
- **go(n)**: carrega una pagina determinada del historial.
## Navigator
- **userAgent**: retorna informacio sobre el sistema operatiu i la versio del navegador.
- **userAgentData**: conte un objecte amb informacio sobre el sistema operatiu i la versio del navegador.
- **language**: conte informacio sobre l'idioma configurat al navegador.
## Screen
- **width**: amplada total de la pantalla en pixels.
- **height**: alçada total de la pantalla en pixels.
- **availWidth**: amplada descartant de les barres de tasques.
- **availHeight**: alçada descartant les barres de tasques.