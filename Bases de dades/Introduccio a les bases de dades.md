## Entitat
Una **entitat** és qualsevol objecte o concepte del món real que pot ser identificat de manera única i sobre el qual es vol emmagatzemar informació en una base de dades. Sempre es posa en majuscula y en singular.
## Entitat Feble
Una entitat feble NO te atribut identificador, per tant com no te atribut identificador SEMPRE dependra de una entitat normal i mai pot ser 1,N i 1,M ha de ser 1,1 i 1,N o 0,1 i 1,N.
## Atribut
Un **atribut** és una característica o propietat d’una entitat. Els atributs descriuen l’entitat i contenen les dades específiques que volem emmagatzemar. En el cas de l’entitat “ALUMNE”, els atributs són “nom”, “cognom 1", i “cognom 2”. Aquests atributs proporcionen detalls sobre cada estudiant.
## Dada calculada
Aquesta es una dada que per algun motiu no es rellevant per guardarla a la base de dades o nomes es necesari utilitzarla de forma temporal.
### Atribut compost
Un atribut compost es com el nom indica un atribut el qual esta format per altres atributs, per exemple podem veure que "nom complet" esta format per "nom", "cognom1" i "cognom2" pero aquest atribut es el valor de aquests tres atributs, es a dir, no pot ser nomes per exemple "nom" i "cognom1" han de ser el tres.
## Relació
Una **relació** descriu com dues o més entitats estan connectades entre si. Per exemple, un estudiant pot estar matriculat en diverses assignatures, i aquesta connexió es representaria com una relació entre les entitats “ALUMNE” i “ASSIGNATURA”.
## N o M
Es un valor infinit que es posa quan es fa una relacio entre dos entitats i no tenim cap maxim, en cas de en una relacio siguin mes d'un valor que no te maxim es posa N i M i en cas de nomes necesitar un numero infinit en cas de no tenir cap maxim especificat es posa N.
![[Pasted image 20240918113946.png]]
![[Pasted image 20241002115133.png]]
[[Entitat Relacio]]