# Estructures de control
Per controlar els errors dels nostres programes sense que petin podem utilitzar estructures dins del nostre codi per evitar un mal funcionament. Per exemple tenim la seguent estructura:
![[Pasted image 20241129090659.png]]
Aqui podem veure que si dins del codi de "try" hi pasa algun error "catch" guardara l'error que ha pasat al nostre programa i executara el codi que estigui dins seu. Per ultim tenim "finally", que el codi que posem dins s'executara SEMPRE, peti o no peti el codi y sense importar el codi que hi havia dins de "try" o "catch".
Tambe tenim el codi d'error que posem dins de "catch" que aquest error el podem llençar per consola per poder veure l'error que ha pasat.
# Throw
Aquesta comanda es pot utilitzar dins de "try" per comunicar un error i solicitar que es tracti. Despres es seguira executant "catch" o "finally".
![[Pasted image 20241129091558.png]]