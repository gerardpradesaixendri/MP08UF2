# Instal·lació Moodle

## Creació màquina virtual

- Primer de tot, posarem "adaptador pont" a la màquina i li posarem la iso de ubuntu server.

![1](1.png)
![1](2.png)

## Instal·lació Moodle

1. Primer de tot posarem la comanda "ssh (usuari@IP)"

```
shh gprades@192.168.203.224
```
![1](3.png)
![1](4.png)

4. Instal·larem l'apache

![1](6.png)

5. Instal·larem MariaDB

![1](7.png)

6. Ara insta·larem la configuració de seguretat de mysql

![1](8.png)
![1](9.png)

7. Comprovem que podem entrar

![1](10.png)

8. Instal·larem el php7.3. Per fer-ho haurem d'instal·lar diferents coses.

![1](11.png)
![1](11.1.png)


9. Seguidament editarem el següent fitxer per a que ens mostre index.php enves de index.html.

![1](12.png)
![1](13.png)

10. Reiniciarem el servidor apache per a que s'aguardin tots els canvis.

![1](14.png)

11. Finalment veurem l'estat del servidor apache fent un status.

![1](15.png)

12. Crearem el fitxer index.php

![1](16.png)
![1](17.png)

13. Seguidament instal·larem el moodle amb la següent comanda:

![1](5.png)

14. Descomprimirem la carpeta

![1](18.png)

15. Canviarem els permisos

![1](19.png)

16. Entrarem al directori /home, crearem la carpeta "moodledata" i li donarem permisos.

![1](20.png)

17. Accedirem a la base de dades amb mode root.

![1](21.png)

18. Crearem l'usuari moodlemanager dins de la base de dades.

![1](22.png)

19. Crearem la base de dades de moodle.

![1](23.png)

20. Li donarem permisos a l'usuari.

![1](24.png)
![1](25.png)

21. Entrarem al buscador i posarem (la nostra ip)/moodle

![1](26.png)
![1](27.png)

22. 
