## Placa base
Components importants de la placa base son:
- Socket de CPU
- Banks de RAM
- BIOS (i la seva pila (La pila de la BIOS es model CR2032, la pila pot estar en vertical i pot ser dificil de veure))
- Slots d'expansio
- Pont del Nord
- Pont del Sud
![[Pasted image 20240924095832.png| 600x500]]
#### Arquitectura de Von Neumann
Es basa en una arquitectura la qual esta composa per:
- CPU
- Memoria principal (RAM actual)
- Entrada (teclat o tarjeta perforada) i Sortida (pantalla o impresora)
- Bus del sistema (connexio entre els anteriors components)
![[Pasted image 20240923100254.png| 500]]
Uns anys despres es va modificar aquesta arquitectura creant el Pont del nord i Pont del sud que s'encarregaven de treure feina al processador com per exemple esperar les respostes de la memoria principal o de la grafica i el pont del sud s'encarregava de l'audio, el disc dur, la xarxa...
![[Pasted image 20240924093752.png| 400]]
Despres es va començar a optimitzar i es va conectar la RAM a la CPU i es van unificar el pont nord i el pont sud.
![[Pasted image 20240930093345.png]]
### Trampas
Pont nord i sud junts
Processadors soldats a la placa