# Instalacio del servei FTP
Primer instalarem el servei FTP per poder utilitzar-lo, per instalar i comprovar el funcionarem utilitzarem:

```BASH
sudo apt install proftpd
```

Ara comprovarem que esta funcionant correctament:

```BASH
sudo systemctl status proftpd
```

Ara podem accedir a la ruta del fitxer de configuracio del servei FTP a la ruta `/etc/proftpd/proftpd.conf`.

Ara haurem de instalar el Filezilla per poder fer-lo servir com a client FTP executant la comanda.

```BASH
sudo apt install filezilla
```

Una vegada fet aixo podem entrar a Filezilla i fer una connexio al servidor FTP, amb la configuracio per defecte podem veure que podem accedir a qualsevol directori del servidor amb tota llibertat, aixo no esta be per temes de seguretat per tant haurem de retornar al fitxer `/etc/proftpd/proftpd.conf` i modificar la seguent linea que estara comentada i la haurem de descomentar:

```BASH
DefaultRoot ~
```

Per poder crear usuaris nomes pel servei FTP i no usuaris per poder accedir al propi dispositiu Linux podem descomentar aquesta linea per poder fer que els usuaris nomes puguin accedir al servei FTP i no al sistema.

```BASH
RequireValidShell off
```

Ara podem crear una "fake shell" per assignar als usuaris que volguem que nomes puguin entrar al servei FTP, per fer-ho podem accedir a les shells.

```BASH
sudo nano etc/shell
```

Aqui creem una shell falsa al final afegint per exemple `/usr/bin/ftpshell`.

Ara quan creem un usuari podem utilitzar la comanda adduser o useradd per fer-ho, podem crear l'usuari de la seguent forma:

```BASH
sudo useradd -s "/usr/bin/ftpshell" -m (nom usuari)
```

Ens sortira un warning conforme no existeix pero no hi ha problema, de fet es el que volem. Tambe li posem una contrasenya clar.

```BASH
sudo passwd (nom usuari)
```

Ara amb aquesta linea descomentada i amb el usuari amb una fake shell podem entrar al servei FTP pero no podem en si iniciar sesio al servidor del servei FTP.