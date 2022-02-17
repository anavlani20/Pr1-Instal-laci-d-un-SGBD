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

## RESPON O COMPROVA ELS SEGÜENTS APARTATS

1.	A on es troben físicament els fitxers de dades?
    >Com en totes les versions i burificacions de MySQL, totes les dades d’emmagatzematge es troben en /var/lib/mysql  

2.	A on es troba el fitxer de configuració? Quin és el seu contingut?
    >**/etc/my.cnf**
    >**/etc/my.cnf.d/mysql-server.conf**
    >Normalment el fitxer de configuració sempre es el mateix (my.cnf), però en algunes noves versions (repositoris) poden estar a (mysql-server.conf).  

    >![image](https://user-images.githubusercontent.com/61285257/154451786-76662cd1-e34c-4a13-adc7-7eae4b039c8b.png)

3.	El procés de mysqld escolta al port 3306. Quina modificació/passos caldrien fer per canviar aquest port a 33306 per exemple? Important: No realitzis els canvis. 
Només indica els passos que faries.
    >Configurarem aquest fitxer.
    >**/etc/my.cnf**

    >![image](https://user-images.githubusercontent.com/61285257/154452657-c9dfc098-4b9b-4b06-8e91-d144b09789d7.png)

    >Afegiriem el port a la configuració a l’apartat de mysqld.
    >Un cop fet això, guardarem els canvis del fitxer i reiniciarem el servei de mysql (systemctl).

    >![image](https://user-images.githubusercontent.com/61285257/154452793-df26aacf-bc1a-4528-bb2e-dec4427a3efc.png)

    >Amb aquesta comanda comprovaríem si el servei mysql esta escoltant per el port desitjat. 
    >Ens sortiria una cosa tal com així:

    >![image](https://user-images.githubusercontent.com/61285257/154452849-4a7091d5-6e9c-4d0b-aae2-69aff337d3ad.png)

    >En lloc del 3306 ens sortiria el port modificat.

4.	Un cop finalitzada la instal·lació i veure que funciona, mostra el resultat de la comanda:

    >![image](https://user-images.githubusercontent.com/61285257/154453042-68326085-4c1a-4518-b6ef-dc90ada84617.png)

    >![image](https://user-images.githubusercontent.com/61285257/154453075-f420a0c2-da23-433b-a89d-74a88d4c3297.png)

5.	Quines són les característiques principals que ofereix MySQL 8.0 enfront de la 5.7.

    >Hi ha algunes diferències que tindran un impacte en el nostre treball amb MySQL si passem de la 5.7 a la 8. Per exemple, si volem canviar la vostra contrasenya d'arrel a       >MySQL 8, haureu de fer diferents passos en comparació amb la 5.7.
    >(Bàsicament quan acabes d’instal·lar el mysql, en versions anteriors s’havia de generar contrasenyes temporals per accedir al mysql per primera vegada, en la nova versió       >quan demana el password, pots donar al enter i entraras sense introduir cap password.)
    >Altre  gran canvi que pot afectar és el motor d'emmagatzematge MyISAM, que estarà disponible amb algunes restriccions.
    >Les metataules de MySQL es mouen a InnoDB. Això s'ha de tenir en compte quan es vol actualitzar.

    >Tambè hi ha alguns tipus de fitxers que ja no estan en la nova versió perquè Oracle gestionara aquests arxius de manera diferent.

    >En resum:
    >MySQL 8.0 hauria de tenir un millor rendiment i demostra que és més eficient durant un benchmark. Funciona molt bé per a la càrrega de treball de lectura/escriptura en         >comparació amb MySQL 5.7. No hi ha cap raó per no utilitzar MySQL 8.0.

6.	Ensenya al professor que us podeu connectar al SGBD.

    >En aquest cas utilitzarem com SGBD el MySQL Workbench 8.0 CE.
    >En aquesta prova entrarem amb l’usuari asix.
    >El tallafocs hauria de estar obert per el port 3306(en la documentació de l’instal·lació, al final, podem trobar com fer-ho).

    >![image](https://user-images.githubusercontent.com/61285257/154453237-acb12779-7799-40e5-bd2a-3026dfe936c6.png)

    >Accedirem per aquesta ip. Es un adaptador-pont de la maquina virtual.

    >![image](https://user-images.githubusercontent.com/61285257/154453298-7f2e4884-4a14-4965-ae65-5ede15d81c3f.png)

    >![image](https://user-images.githubusercontent.com/61285257/154453322-dd20f629-bab9-4e51-9f2e-7207f19d1522.png)

    >![image](https://user-images.githubusercontent.com/61285257/154453347-b1ad8be7-989a-4ea0-ac1e-b31b8762cd94.png)

    >Connection Successfull.

    >![image](https://user-images.githubusercontent.com/61285257/154453383-82cda705-a541-4de5-acc9-f4c89b029576.png)

    >Veiem que podem executar les consultes, en aquest cas per exemple, per saber la versió del MySQL. 








