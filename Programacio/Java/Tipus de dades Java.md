Java es keysensitive, aixo vol dir que ens detecta com que "nom" "Nom" i "NOM" son diferents.
# Numeriques
## Enters
byte
- Aquest tipus pot guardar numeros enters entre 0 i 255.

short
- Aquest tipus pot guardar valors numerics entre -32000 i 32000

int
- Aquest tipus pot guardar valors numerics entre -2000000000 i 2000000000. Es el mes utilitzat.

long
- Aquest tipus pot guardar valors numerics encara mes grans que tots els anteriors.
## Decimals
float
- Aquest tipus pot guardar valors numerics amb decimals amb precicio de aproximadament 7 decimals.

double
- Aquest tipus pot guardar valors numerics amb decimals amb precicio de aproximadament 15 decimals.
# Text
char
- Guarda el primer valor d'un valor de text.

string
- Guarda un valor de tipus text.

# Array
array
- int [] a = {1,2,3} //amb valors nomes declararla
- int [] a = new int [3] //amb la longitud que tindra
- si li diem que te 3 de longitud no podra tenir ni mes ni menys
- si li diem que tindra int han de ser tots els valors de tipus int
# Funcions
NO retorna valor
- crearem una funcio que contingui void, com aqui:
	![[Pasted image 20241209113824.png]]

retorna valor
- li direm el tipus de valor que retorna com aqui:
	![[Pasted image 20241209114241.png]]
# Precedència dels operadors
Si no es posen parèntesis, les operacions s'executen en el següent ordre:
1. Operadors unaris (signe -, increment ++, decrement --)
2. Multiplicació, divisió i residu (\*, /, %)
3. Suma i resta (+, -)
4. Relacionals (<, >, <=, >=, \==, !=)
5. Lògics (!, &&, ||)