# OWNCLOUD

OwnCloud és una aplicació de programari d'allotjament de fitxers, que permet l'emmagatzematge i aplicacions al núvol. Permet tenir un control total sobre els fitxers de la d'empresa, com saber on s'ubiquen les dades a més de dir qui i qui no tens accés a carpetes i fitxers.

## REQUISITS PREVIS

- Apache
- MariaDB
- Crear la base de dades de Owncloud
- Instal·lar PHP i els seus moduls necessaris

### INSTAL·LACIÓ APACHE

- Primer de tot instal·larem l'Apache2. Per fer-ho posarem la següent comanda: 

"sudo apt install apache2"

![1cap](1.png)

- A continuació  mirarem l'estat del Apache amb la següent comanda 

"sudo apache2 status"

![1cap](2.png)

- Seguidament, entrarem al directori "/var/www/html" i desactivarem el llistat de directoris del servidor amb la següent comanda:

"sudo sed -i "s/Options Indexes FollowSymLinks/Options FollowSymLinks/" /etc/apache2/apache2.conf"

![1cap](3.png)

### INSTAL·LACIÓ MARIADB

- Per començar instal·larem el MariaDB amb la següent comanda: 

"sudo apt-get install mariadb-server mariadb-client -y"

![1cap](4.png)

- Seguidament configurarem la instal·lació:

"sudo mysql_secure_installation"
Una vegada hem posat la comanda ens demanarà la contrasenya del sistema ubuntu per entrar al root.

![1cap](5.png)

- Ens preguntarà si volem canviar al socket de unix. Li posarem que no "n":

![1cap](6.png)

- Seguidament ens preguntarà si volem canviar la contrasenya de root. Li direm que no "n":

![1cap](7.png)

- A continuació ens preguntarà si volem eliminar els usuaris anonims. Li direm que si "y"

![1cap](8.png)

- Ens preguntarà si volem deshabilitar l'acces remot com a root. Li direm que no "n":

![1cap](9.png)

- Ens preguntarem si volem eliminar les base de dades de testeig i l'accés. Li direm que si "y":

![1cap](10.png)

- Finalment ens preguntarà si volem actualitzar les taules de privilegis. Li direm que si "y":

![1cap](11.png)

- Y per últim reiniciarem el MariaDB amb la següent comanda:

"sudo systemctl restart mariadb.service` o `sudo service mariadb.service restart"
