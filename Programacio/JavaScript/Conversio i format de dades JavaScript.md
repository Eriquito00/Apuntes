## Conversio entre text i numeros
### De numero a text
Podem convertit tant fent:
- "" + valor
- variable.toString()
![[Pasted image 20240920084507.png]]
### De text a numero
Podem utilitzar un o altre segons per a que utilitzem el valor:
- parseInt()
- parseFloat()
Int sera per a numeros enters; 1, 2, 3.
Float per a numeros decimals; 1.1, 2.3 3.1.
![[Pasted image 20240920084723.png]]
**Si el text no conté un valor numèric, retorna el valor especial NaN (Not a Number).**
### Formatar numeros
Per mostrar resultats es habitual demanar un nombre de decimals per separar decimals o milers. Per fer-ho es pot fer com en el seguent exemple pero hem de tenir en compte que ho pasara a **string**:
![[Pasted image 20240920085055.png]]
Si es vol separar milers i decimals amb els caracters correctes podem fer-ho de la seguent manera:
![[Pasted image 20240920085246.png]]
Aixi segons del pais desde on es faci es veure d'una o d'altre forma, podem veure que en un separa per comes els milers i l'altre els decimals.