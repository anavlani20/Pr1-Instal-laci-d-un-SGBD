# Part I - INSTAL·LACIÓ SGBD MySQL Percona (màx. 6 punts)

![image](https://user-images.githubusercontent.com/61285257/154440402-8b1e2c3d-6c5a-4c6f-a041-f9981b6dcbe8.png)

Primer de tot com sempre, hem d’asegurar que la nostra maquina estigui actualitzada, farem un yum -y Update.
Conf – xarxa:

![Imagen1](https://user-images.githubusercontent.com/61285257/154336835-f408799e-fc19-4b72-96b2-7809e019dcd2.png)

## INSTAL·LACIÓ PERCONA MYSQL
Els paquets preparats per utilitzar estan disponibles al servidor Percona per als repositoris de programari MySQL. 
El repositori de Percona yum admet sistemes operatius populars basats en RPM, com ara CentOS, RHEL, Fedora i Amazon Linux AMI. 

Instal·lem el dipòsit de Percona executant l'ordre següent amb sudo.

![image](https://user-images.githubusercontent.com/61285257/154341235-64fa0714-a250-49ff-ab3b-c3ebd4afc826.png)

Repositori instal·lat correctament.

![image](https://user-images.githubusercontent.com/61285257/154341915-3223f0c1-ea6b-4372-b7df-f4f5eb09ee94.png)

Hem d'habilitar el dipòsit de Percona Server 8.0 mitjançant la següent comanda.

![image](https://user-images.githubusercontent.com/61285257/154341960-9327136f-1b99-44f6-9771-8c41a62abe5a.png)

Instal·lem el servidor Percona executant l'ordre següent:
Confirmarem amb un y quan l’assistent ho demani.

![image](https://user-images.githubusercontent.com/61285257/154342017-35116b0a-3468-48ea-8380-1f33687a5d56.png)

![image](https://user-images.githubusercontent.com/61285257/154342088-0dd527b0-3d58-49b5-982d-1e89fb638ee7.png)

![image](https://user-images.githubusercontent.com/61285257/154342536-98b22e7c-740d-4b5a-bd2f-9e871ca8519a.png)

Instal·lació finalitzada.


Per comprovar que l’instal·lació ha sigut correcte, executarem la següent comanda.

![image](https://user-images.githubusercontent.com/61285257/154342760-0d645fde-49b7-4527-83fd-bb2403ddf61d.png)

Ara que el Percona Server 8.0 està instal·lat, iniciem i configurem el servei mysqld perquè s'iniciï a l'arrencada del sistema. 
Comprovem l'estat del servei.

![image](https://user-images.githubusercontent.com/61285257/154342798-e97ecf8e-55c9-4d8c-8efc-3d8eefb9903e.png)

Ara primer, aconseguirem una contrasenya temporal amb l'ordre següent, bàsicament perquè acabem d’instal·lar el percona mysql.

![image](https://user-images.githubusercontent.com/61285257/154342842-60fbd176-2f68-41ef-9297-17f0f2d832cc.png)

Executem l'script mysql_secure_installation per securitzar el nostre servidor de bases de dades. 
L'script mysql_secure_installation millora la seguretat de la instal·lació. 
Entrarem amb la contrasenya temporal y després podrem introduir la nostra contrasenya, ara de moment com estem instal·lant, seguirem la política de password per defecte que es aquest d’aqui.

![image](https://user-images.githubusercontent.com/61285257/154342957-dfe764a2-ea9a-4efc-93e3-1a5d93ff2d5a.png)

L’hem de complir, per tant una contrasenya com “P@ssw0rd”, compleix aquestes polítiques, després es poden modificar aquestes polítiques.
L'execució de l'script fa el següent: 
•	Canvia la contrasenya root 
•	No permet l'inici de sessió remot per als comptes root 
•	Elimina usuaris anònims 
•	Elimina la base de dades de prova 
•	Torna a carregar les taules de privilegis
 La instrucció següent executa l'script, prioritzarem el canvi de contrasenya, els altres paràmetres son opcionals depenent de la situació i la preferència del usuari.

![image](https://user-images.githubusercontent.com/61285257/154343017-47a4a334-1aac-4b26-8572-e2da01a05f42.png)

Després de seguir els passos de l’assistent, ja podríem accedir al mySQL de Percona.

![image](https://user-images.githubusercontent.com/61285257/154343046-dccedbdd-d593-45d5-8a12-e399470a93cb.png)

Aquí veiem com accedint al mysql i mostrarem dades de d’una base de dades oculta que ve per defecte per demostrar la versió del percona.

![image](https://user-images.githubusercontent.com/61285257/154343092-1bc02bd5-b0a8-4c2d-8352-28592d72044b.png)

#### Firewall
Cal afegir el port de MySQL a aquest firewall perquè hi puguem accedir des de l'exterior.

![image](https://user-images.githubusercontent.com/61285257/154343147-8bd0c122-5d68-4e58-837d-41bec4d4437f.png)

Comprovarem el servei de Firewall també.

![image](https://user-images.githubusercontent.com/61285257/154343244-bf76771d-c144-41e0-95eb-ee92965de614.png)

En principi ja esta tot en ordre, faltaria crear un usuari en el mysql, però ho farem en un dels següents punts del següent apartat, juntament amb la connexió al exterior.

## RESPON O COMPROVA ELS SEGÜENTS APARTATS

1. Un cop realitzada la instal·lació realitza una securització de la mateixa. Quin programa realitza aquesta tasca? Realitza una securització de la instal·lació indicant que la contrasenya de root sigui patata.  
   >Si de primeres canviem la contrasenya, a patata, dins de la securització,en aquest cas, no ens deixarà.
   Perquè no es compatible amb les polítiques de contrasenya que ve per defecte.

   >![image](https://user-images.githubusercontent.com/61285257/154345139-7ffac2e0-fed1-4ec8-a1c2-95798e0cbed5.png)

   >Amb aquesta consulta sobre el mysql podrem veure els paràmetres d’aquestes polítiques, per després poder canviar-ho segons la contrasenya demanada.

   >![image](https://user-images.githubusercontent.com/61285257/154345188-306d64f9-b277-4137-97c0-95a49996489e.png)

   >Podem observar que “patata” de primeres no compliria amb aquesta política, per tant modificant el paràmetre de la mida de caràcters i el paràmetre de la política general a LOW. Fent això ens serviria.

   >![image](https://user-images.githubusercontent.com/61285257/154345260-48d3c6b7-fce5-4a12-9835-e385bb08f00a.png)

   >Després de canviar aquest paràmetres podem canviar la contrasenya de dues maneres.
   >OPCIO 1:
   >Amb la consulta sobre el mysql:

   >![image](https://user-images.githubusercontent.com/61285257/154345442-f23f6e8b-1459-4c5e-bd12-73a367e1297a.png)

   >La primera consulta seria canviar la contrasenya al root sobre qualsevol font remota, també podem posar una IP especifica o localhost, per seguretat.
   >La segona consulta seria tornar a carregar els permisos.

   >OPCIO 2:
   >Directament canviar-ho en el mysql_secure_installation, en el meu cas em decantare per aquesta opció.

   >![image](https://user-images.githubusercontent.com/61285257/154345523-b3e718ba-9473-40c3-8284-5c9bff5d29d3.png)

   >![image](https://user-images.githubusercontent.com/61285257/154345542-b258140f-4438-4ffb-a421-af00e85ee5b2.png)

   >Bàsicament podem observar que en aquestes últimes captures, després d'afegir la contrasenya "patata", la securització ens farà unes preguntes, les respostes pot dependre de la nostra preferència, menys la pregunta de "Disallow root login remotly?", en aquesta hem de posar un no, per després poder connectar amb un usuari root des de qualsevol entorn extern a la màquina.
   Això seria tot.


2. Quines són les instruccions per arrancar / verificar status / apagar servei de la base de dades de Percona Server en el CentOS 7.  
    >Iniciem el servei Percona amb l'ordre següent:   
    >**systemctl start mysql**   
    >A continuació, comprovem l'estat del servei executant l'ordre següent:   
    >**systemctl status mysql**   
    >Aturem el servei executant l'ordre següent:   
    >**systemctl stop mysql**  
    >Reiniciem el servei executant l'ordre següent:   
    >**systemctl restart mysql**  

3.	A on es troba i quin nom rep el fitxer de configuració del SGBD Percona Server?  
    >**/etc/my.cnf**

    >![image](https://user-images.githubusercontent.com/61285257/154346719-b28d8bef-038d-420e-bf1f-5606d6105794.png)  

4.	A on es troben físicament els fitxers de dades (per defecte). Com ho has sabut?  
    >**/var/lib/mysql/**
    >
    >![image](https://user-images.githubusercontent.com/61285257/154346925-476afafb-3f85-497f-b57a-b99a0559e58d.png)
    >
    >A part de veure-ho en alguns moments d’instal·lar-lo, ho vaig veure en la documentació oficial de Percona.  

5.	Crea un usuari anomenat asix en el sistema operatiu i en SGBD de tal manera que aquest usuari del sistema operatiu no hagi d'introduir l'usuari i password cada vegada que cridem al client mysql?  
     i.	https://dev.mysql.com/doc/refman/8.0/en/password-security-user.html
     ii.	Usuari SO-→ asix / patata

     >![image](https://user-images.githubusercontent.com/61285257/154349155-96b38163-566d-4049-8a5d-99a2349af293.png)

     >Crearem l’usuari, le definim la contrasenya i l’afegim al grup de superusuaris(root).

     >iii.	Usuari MySQL → asix / patata

     >![image](https://user-images.githubusercontent.com/61285257/154349392-0513ab7f-14f0-4a79-8217-fcf089fd7bcb.png)

     >Crearem l’usuari i l’otorgarem tots els permisos en qualsevol base de    dades i dispositiu remot.

     >**Configuració**  
     >*/etc/my.cnf*  

     >![image](https://user-images.githubusercontent.com/61285257/154349502-9c2bd0cd-524e-44a9-b2fe-f8eec5ee0058.png)

     >Afegirem les seguent línies (client y password).  
     >Tambè es podria entrar amb l’usuari sense indicar ni l’usuari, per en aquest cas l’exercici nomes ens demana la contrasenya.  

     >![image](https://user-images.githubusercontent.com/61285257/154349558-d7328658-41cd-42da-905a-6669d7b292b8.png)

     >Aquest punt es opcional, però en un cas real er mantenir la contrasenya segura, el fitxer no ha de ser accessible per a ningú més que per l’usuari. Per assegurar-vos,       establiu el mode d'accés a fitxers en 400 o 600.  

     >![image](https://user-images.githubusercontent.com/61285257/154349816-c30707a3-6e27-4004-a376-1c2a276b6d76.png)

     >Aquest seria el resultat, no hem indicat password i ha entrat a mysql.

     >![image](https://user-images.githubusercontent.com/61285257/154349861-7ec8e7f5-42bd-4ba1-ba94-ac74f693b290.png)  

6.	El servei de MySQL (mysqld) escolta al port 3306. Quina modificació/passos caldrien fer per canviar aquest port a 33306 per exemple?
7.	Important: No realitzis els canvis. Només indica els passos que faries.

     >Editarem el fitxer de configuració del MySQL = **/etc/my.cnf**  

     >![image](https://user-images.githubusercontent.com/61285257/154439376-c27b20df-dc5a-4b83-940e-24219801b57d.png)

     >Afegiriem el port a la configuració a l’apartat de mysqld.  
     >Un cop fet això, guardarem els canvis del fitxer i reiniciarem el servei de mysql (systemctl).  

     >![image](https://user-images.githubusercontent.com/61285257/154439522-21480473-0154-44ac-9ad5-30d6644757a5.png)

     >Amb aquesta comanda comprovaríem si el servei mysql esta escoltant per el port desitjat.   
     >Ens sortiria una cosa tal com així:  

     >![image](https://user-images.githubusercontent.com/61285257/154439584-06983285-9a9c-4d2c-8a41-5586e79a0ed2.png)

     >En lloc del 3306 ens sortiria el port modificat.

     >En aquest cas utilitzarem com SGBD el MySQL Workbench 8.0 CE.  
     >En aquesta prova entrarem amb l’usuari asix.  
     >El tallafocs hauria de estar obert per el port 3306(en la documentació de l’instal·lació, al final, podem trobar com fer-ho).  

     >![image](https://user-images.githubusercontent.com/61285257/154439685-41702f39-ab14-4b9d-bc81-a93656ae4fd0.png)

     >Accedirem per aquesta ip. Es un adaptador-pont de la maquina virtual.  

     >![image](https://user-images.githubusercontent.com/61285257/154439753-639cc879-e319-4a94-ab51-ea2c0111f166.png)
     >![image](https://user-images.githubusercontent.com/61285257/154439786-558542cc-85e9-4416-9c8b-bfba6681ff51.png)

     >![image](https://user-images.githubusercontent.com/61285257/154439807-9ec53a3e-3406-4ed7-bcb6-7b54bd7407f2.png)

     >Connexió successfull.

     >![image](https://user-images.githubusercontent.com/61285257/154443538-c34f3683-ba3f-450f-b3f8-5451e5b5bc58.png)

     >Podem executar qualsevol consulta, en aquest  cas com un exemple, per saber la versió. 

















    


 
