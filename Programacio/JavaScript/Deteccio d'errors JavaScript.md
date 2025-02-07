# Detecció d'errors JavaScript

## Estructures de control

Per controlar els errors dels nostres programes sense que petin podem utilitzar estructures dins del nostre codi per evitar un mal funcionament. Per exemple tenim la següent estructura:

![](/Imatges/Pasted%20image%2020241129090659.png)

Aquí podem veure que si dins del codi de "try" hi passa algun error "catch" guardarà l'error que ha passat al nostre programa i executarà el codi que estigui dins seu. Per últim tenim "finally", que el codi que posem dins s'executarà SEMPRE, peti o no peti el codi i sense importar el codi que hi havia dins de "try" o "catch".
També tenim el codi d'error que posem dins de "catch" que aquest error el podem llençar per consola per poder veure l'error que ha passat.

## Throw

Aquesta comanda es pot utilitzar dins de "try" per comunicar un error i sol·licitar que es tracti. Després es seguirà executant "catch" o "finally".

![](/Imatges/Pasted%20image%2020241129091558.png)
