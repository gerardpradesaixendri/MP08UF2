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

![1cap](12.png)

## CREACIÓ DE LA BASE DE DADES DE OWNCLOUD

- Primer de tot entrarem a MariaDB amb la següent comanda:

"sudo mysql -u root -p"

![1cap](13.png)

- Crearem la base de dades amb la següent comanda:

"CREATE DATABASE owncloud;"

![1cap](14.png)

- A continuació crearem un usuari anomenat ownclouduser amb la contrasenya "Admin1234" amb la següent comanda:

"CREATE USER 'ownclouduser'@'localhost' IDENTIFIED BY 'Admin1234';"

![1cap](15.png)

- Li donarem accès a la base de dades al usuari amb la següent comanda:

"GRANT ALL ON owncloud.* TO 'ownclouduser'@'localhost' IDENTIFIED BY 'Admin1234' WITH GRANT OPTION;"

![1cap](16.png)

- Aplicarem els canvis i sortirem. Li posarem les següents comandes:

"FLUSH PRIVILEGES;
EXIT;"

![1cap](17.png)

## INSTAL·LACIÓ PHP AMB ELS SEUS MÓDULS NECESSARIS

- Primer de tot ho instal·larem amb les següents comandes:

"sudo apt-get install software-properties-common -y
sudo add-apt-repository ppa:ondrej/php"

![1cap](18.png)
![1cap](19.png)

- Instal·larem el PHP y els seus móduls necessaris. Hem de tenir en compte els requisits de Owncloud abans de instal·lar els móduls. Posarem la següent comanda:

"sudo apt install php7.4 libapache2-mod-php7.4 php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-apcu php7.4-smbclient php7.4-ldap php7.4-redis php7.4-gd php7.4-xml php7.4-intl php7.4-json php7.4-imagick php7.4-mysql php7.4-cli php7.4-mcrypt php7.4-ldap php7.4-zip php7.4-curl -y
"
![1cap](20.png)

- Actualitzarem els paquets amb el repositori afegit amb la següent comanda:

"sudo apt update"

![1cap](21.png)

- Después de la instal·lació editarem el fitxer php.ini i canviarem alguns valors. Li posarem la següent comanda:

"sudo gedit /etc/php/7.4/apache2/php.ini"

![1cap](22.png)

- Una vegada ens ha entrat al bloc de notes, li canviarem la memória limit de 128 a 256 i guardarem:

![1cap](23.png)
![1cap](24.png)

## INSTAL·LACIÓ OWNCLOUD

- Descargarem la última versió del programa y descomprimirem els fitxers, ademés mourem els arxius de Owncloud a "/var/www/html/owncloud"
