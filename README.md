He instal·lat el Centos 7 Minimal a partir de la ISO proporcionada per el professor, 
He actualitzat el sistema (yum Update), obrir els port de SSH(22) per poder connectar-me remotament i finalment configurar els adaptadors de xarxa per a que em doni la IP per poder connectar des de l’exterior de la maquina.

Un cop fet tot això he fet clonacions de la maquina per cada part d’aquesta practica.

Aquesta practica el farem sobre l’eina MobaXtrem, que bàsicament, entre moltes altres coses, es un client SSH i Telnet amb qual podem connectarnos al servei remot del Centos, en aquest cas, per exemple.

# Pràctica 1: Instal·lació d'un SGBD

## Part I - INSTAL·LACIÓ SGBD MySQL Percona (màx. 6 punts)

Primer de tot com sempre, hem d’asegurar que la nostra maquina estigui actualitzada, farem un yum -y Update.
Conf – xarxa:
![Imagen1](https://user-images.githubusercontent.com/61285257/154336835-f408799e-fc19-4b72-96b2-7809e019dcd2.png)

### INSTAL·LACIÓ PERCONA MYSQL
Els paquets preparats per utilitzar estan disponibles al servidor Percona per als repositoris de programari MySQL. 
El repositori de Percona yum admet sistemes operatius populars basats en RPM, com ara CentOS, RHEL, Fedora i Amazon Linux AMI. 

Instal·lem el dipòsit de Percona executant l'ordre següent amb sudo.
![image](https://user-images.githubusercontent.com/61285257/154341235-64fa0714-a250-49ff-ab3b-c3ebd4afc826.png)
