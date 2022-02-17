# Part II - INSTAL·LACIÓ SGBD MySQL 8.0 (màx. 2 punt)

![image](https://user-images.githubusercontent.com/61285257/154444763-5f77b2cb-4383-4713-abcb-44d008da62ce.png)


Primer de tot com sempre, hem d’asegurar que la nostra maquina estigui actualitzada, farem un yum -y Update.
Conf – xarxa:

![image](https://user-images.githubusercontent.com/61285257/154444728-bafd4ab4-c209-41bd-a91c-740e0e419554.png)


## INSTAL·LACIÓ MYSQL 8.0

MySQL 8 és l'última versió del potent sistema de gestió de bases de dades MySQL. 

Potencia moltes aplicacions empresarials, llocs web i sistemes transaccionals en temps real. Per començar a instal·lar el servidor MySQL 8.0 a CentOS 7, heu d'afegir el dipòsit oficial de la comunitat MySQL al vostre sistema.

Ara descarreguem i afegim el següent repositori de MySQL Yum a la llista de repositoris del vostre sistema de distribució Linux per instal·lar la darrera versió de MySQL.
Instalarem els repositori compatible amb el CENTOS/RHEL 7 = 7.1

![image](https://user-images.githubusercontent.com/61285257/154446321-d74e8701-c8f1-4cdf-a17e-882bbe254ccc.png)

Després de descarregar el paquet, instal·larem ara el paquet descarregat amb l'ordre següent.

![image](https://user-images.githubusercontent.com/61285257/154446361-ecd2d813-d18e-45a9-9198-350ea13bbc3a.png)

Instal·larem la darrera versió de MySQL (actualment 8.0) mitjançant l'ordre següent.

![image](https://user-images.githubusercontent.com/61285257/154446406-3c57c93c-8a0b-476b-900c-c97dbc1cd8df.png)

![image](https://user-images.githubusercontent.com/61285257/154446430-9fa1991f-f214-4889-ae00-b12543b0f5b2.png)

Després d'una instal·lació correcta de MySQL, és hora d'iniciar, habilitar i verificar l'estat del servidor MySQL amb les ordres següents:

![image](https://user-images.githubusercontent.com/61285257/154446489-0140f9eb-0022-4e7b-b025-c9a5bec87e35.png)

Podem comprovar la versió del MySQL.

![image](https://user-images.githubusercontent.com/61285257/154446544-f7ae4f6f-0fad-472a-8ad4-dae3d5878969.png)

Un cop instal·lat el MySQL, hauríem de entrar per poder canviar la contrasenya.
A diferencia de versions antigues, en la nova versió no cal generar una password temporal per entrar per primera vegada, prenen enter ja entraríem sense password.

![image](https://user-images.githubusercontent.com/61285257/154446593-17ce50e4-37c5-4f0b-8d09-18976065b697.png)

Amb aquesta consulta ja podríem definir una contrasenya.

![image](https://user-images.githubusercontent.com/61285257/154446649-7307d588-9aaa-4f12-80f8-e6c04f948d19.png)

Tambè podem definir la contrasenya a partir de la securització,tot i que en aquest cas no cal.

![image](https://user-images.githubusercontent.com/61285257/154446681-3835954a-7b38-47e4-bbd6-1cee8d064c2a.png)

#### Firewall

Cal afegir el port de MySQL a aquest firewall perquè hi puguem accedir des de l'exterior.

![image](https://user-images.githubusercontent.com/61285257/154446754-d92cb054-3632-44f9-9057-21e1a2ea8afe.png)

Instal·lació i configuració del MySQL finalitzada.
