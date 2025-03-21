# YAML
YAML es un llenguatge de marques sobretot utilitzar per automatitzar la configuracio de xarxa o instalacio, configuracio i posada a punt de serveix, en el seguent cas explicare el funcionament amb un exemple instalan i desplegant apache2.

Els fitxers YAML sobretot han de tenir comentat amb la estructura seguent un petit titol amb el que fa cada task i amb el titol del que fa el fitxer:
```YAML
- name: Desplegar Apache amb pàgina personalitzada
  hosts: webservers
  become: true
```
Aqui com podem veure es un petit titol descriptiu sobre el que fara aquest fitxer, el host on sera executat i basicament si l'execucio requerira a no permisos, en aquest cas si.

Ara començariem amb les tasques que volem fer:
- En el nostre cas volem comprovar que no hi hagin paquets per actualitzar per no causar errors
- Instalar el servei, en aquest cas apache2
- Iniciarlo i habilitarlo per posar-lo operatiu
- Copiar un fitxer html que ja tenim per mostrarlo en comptes de la pagina per defecte
```YAML
tasks:
    - name: Actualitzar la llista de paquets
      apt:
        update: yes
        
    - name: Instal·lar Apache
      apt:
        name: apache2
        state: present
        
    - name: Iniciar i habilitar Apache
      service:
        name: apache2
        state: started
        enabled: yes
  
    - name: Copiar la página HTML personalitzada
      copy:
        src: index.html
        dest: /var/www/html/index.html
```
Per fer-ho posarem totes les tasques dins de tasks amb un tabulador i posarem un titol descriptiu per cada tasca i el procediment que ha de fer per fer la tasca com podem veure.

El fitxer sencer quedaria aixi i el podem executar tenint ansible, tambe es important que com hem posat que nomes es pot executar amb permisos quan l'executem posem "--ask-become-pass" per demanar la contrasenya i poder executarlo sense errors.
```YAML
- name: Desplegar Apache amb pàgina personalitzada
  hosts: webservers
  become: true

tasks:
    - name: Actualitzar la llista de paquets
      apt:
        update: yes
        
    - name: Instal·lar Apache
      apt:
        name: apache2
        state: present
        
    - name: Iniciar i habilitar Apache
      service:
        name: apache2
        state: started
        enabled: yes
  
    - name: Copiar la página HTML personalitzada
      copy:
        src: index.html
        dest: /var/www/html/index.html
```