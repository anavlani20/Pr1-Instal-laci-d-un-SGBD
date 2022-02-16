

CFGS-ASIX-M10-UF2

Navlani,Aryan

He instal·lat el Centos 7 Minimal a partir de la ISO proporcionada per el professor,

He actualitzat el sistema (yum Update), obrir els port de SSH(22) per poder

connectar-me remotament i finalment configurar els adaptadors de xarxa per a que

em doni la IP per poder connectar des de l’exterior de la maquina.

Un cop fet tot això he fet clonacions de la maquina per cada part d’aquesta practica.

Aquesta practica el farem sobre l’eina MobaXtrem, que bàsicament, entre moltes

altres coses, es un client SSH i Telnet amb qual podem connectarnos al servei remot

del Centos, en aquest cas, per exemple.

**Pràctica 1: Instal·lació d'un SGBD**

**Part I - INSTAL·LACIÓ SGBD MySQL Percona (màx. 6 punts)**

**ENUNCIAT**

Partint d'una màquina CentOS 7 minimal proporcionada pel professor realitza la instal·lació d'un

SGBD Percona Server mitjançant el gestor de paquets YUM.

**ENLLAÇOS**

**Percona Server 8.0 Doc**

https:[//www.percona.com/doc/percona-server/8.0/index.html](http://www.percona.com/doc/percona-server/8.0/index.html)

**Instal·lació Percona Server8.0 via YUM Repository**

https:[//www.percona.com/doc/percona-server/8.0/installation/yum_repo.html](http://www.percona.com/doc/percona-server/8.0/installation/yum_repo.html)

**Instal·lació MySQL via YUM Repository**

https:[//www.tecmint.com/install-latest-mysql-on-rhel-centos-and-fedora/](http://www.tecmint.com/install-latest-mysql-on-rhel-centos-and-fedora/)

**LLIURAMENT**

El lliurament d'aquesta activitat correspon a la documentació de tots els passos corresponents a la

instal·lació per tenir un SGBD MySQL Percona en funcionament.

En la documentació cal incloure les captures d'imatges que es cregui convenients així com la

webgrafia utilitzada.

**Altres opcions de lliurament:**

• Utilitzar aquest document com a plantilla pel lliurament de l’activitat i penjar-la en

tasca destinada a aquesta activitat dins del curs Moodle

•

Realitzar la documentació sobre un repositori GIT (Bitbucket o GitLab). Utilitzant el

P á g i n a 1 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

format de fitxer MarkDown (MD). **(1 punt)**

•

Dins d'una Wiki. **(1 punt)**

Per les dues últimes opcions d'entrega caldrà indicar en el document penjat en el Moodle la URL a

on es troba la documentació i afegir el compte del professor com a membre de l'equip de treball.

**REALITZA LA DOCUMENTACIÓ NECESSÀRIA PER LA INSTAL·LACIÓ PAS A PAS.**

•

Indica clarament els passos per reproduir la instal·lació en un altra màquina.

P á g i n a 2 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

• Si realitzes algun canvi en la configuració del firewall, o altres elements de seguretat per

poder tenir accés indica quins canvis has hagut de fer.

•

Cal tenir en compte que la documentació va dirigida a tècnics informàtics i no a usuaris no

experts.

•

Es valorarà la presentació, l'organització del text i la facilitat de lectura.

Enllaços utilitzat a part de la pagina oficial de Percona, que també han servit per dur a terme aquesta

practica.

<https://computingforgeeks.com/how-to-install-percona-mysql-server-on-centos-rhel/>

<https://www.gpsos.es/2018/07/habilitar-el-acceso-remoto-mysql-centos-7/>

[https://qastack.mx/programming/43094726/your-password-does-not-satisfy-the-current-policy-](https://qastack.mx/programming/43094726/your-password-does-not-satisfy-the-current-policy-requirements)

[requirements](https://qastack.mx/programming/43094726/your-password-does-not-satisfy-the-current-policy-requirements)

<https://tecadmin.net/change-mysql-password-policy-level/>

<https://www.tecmint.com/change-default-mysql-mariadb-port-in-linux/>

Primer de tot com sempre, hem d’asegurar que la nostra maquina estigui

actualitzada, farem un yum -y Update.

Conf – xarxa:

**INSTAL·LACIÓ PERCONA MYSQL**

Els paquets preparats per utilitzar estan disponibles al servidor Percona per als

repositoris de programari MySQL.

El repositori de Percona yum admet sistemes operatius populars basats en RPM,

com ara CentOS, RHEL, Fedora i Amazon Linux AMI.

Instal·lem el dipòsit de Percona executant l'ordre següent amb sudo.

P á g i n a 3 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Repositori instal·lat correctament.

Hem d'habilitar el dipòsit de Percona Server 8.0 mitjançant la següent comanda.

P á g i n a 4 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Instal·lem el servidor Percona executant l'ordre següent:

Confirmarem amb un y quan l’assistent ho demani.

P á g i n a 5 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Instal·lació finalitzada.

Per comprovar que l’instal·lació ha sigut correcte.

P á g i n a 6 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Ara que el Percona Server 8.0 està instal·lat, iniciem i configurem el servei mysqld perquè s'iniciï a

l'arrencada del sistema.

Comprovem l'estat del servei.

Ara primer, aconseguirem una contrasenya temporal amb l'ordre següent, bàsicament perquè

acabem d’instal·lar el percona mysql.

Executem l'script mysql\_secure\_installation per securituzar el nostre servidor de bases de dades.

L'script mysql\_secure\_installation millora la seguretat de la instal·lació.

Entrarem amb la contrasenya temporal y després podrem introduir la nostra contrasenya, ara de

moment com estem instal·lant, seguirem la política de password per defecte que es aquest d’aqui.

L’hem de complir, per tant una contrasenya com “**P@ssw0rd**”, compleix aquestes polítiques, després

es poden modificar aquestes polítiques.

L'execució de l'script fa el següent:

•

•

•

•

•

Canvia la contrasenya root

No permet l'inici de sessió remot per als comptes root

Elimina usuaris anònims

Elimina la base de dades de prova

Torna a carregar les taules de privilegis

La instrucció següent executa l'script, prioritzarem el canvi de contrasenya, els altres paràmetres son

opcionals depenent de la situació i la preferència del usuari.

P á g i n a 7 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Després de seguir els passos de l’assistent, ja podríem accedir al mySQL de

Percona.

P á g i n a 8 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Aquí veiem com accedint al mysql i mostrarem dades de d’una base de dades oculta que ve per

defecte per demostrar la versió del percona.

**Firewall**

Cal afegir el port de MySQL a aquest firewall perquè hi puguem accedir des de

l'exterior.

Comprovarem el servei de Firewall també.

En principi ja esta tot en ordre, faltaria crear un usuari en el mysql, però ho farem en un dels següents

punts del següent apartat, juntament amb la connexió al exterior.

P á g i n a 9 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

**RESPON O COMPROVA ELS SEGÜENTS APARTATS**

\1. Un cop realitzada la instal·lació realitza una securització de la mateixa. Quin programa

realitza aquesta tasca? Realitza una securització de la instal·lació indicant que la

contrasenya de root sigui patata.

Si de primeres canviem la contrasenya, a patata, dins de la securització,en aquest cas, no

ens deixarà.

Perquè no es compatible amb les polítiques de contrasenya que ve per defecte.

Amb aquesta consulta sobre el mysql podrem veure els paràmetres d’aquestes polítiques,

per després poder canviar-ho segons la contrasenya demanada.

Podem observar que “patata” de primeres no compliria amb aquesta política, per tant

modificant el paràmetre de la mida de caràcters i el paràmetre de la política general a

LOW. Fent això ens serviria.

P á g i n a 10 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Despres de cambiar aquest paràmetres podem cambiar la contrasenya de dues maneres.

OPCIO 1:

Amb la consulta sobre el mysql:

ALTER USER 'root'@'%' IDENTIFIED BY 'patata';

FLUSH PRIVILEGES;

La primera consulta seria canviar la contrasenya al root sobre qualsevol font remota, també

podem posar una IP especifica o localhost, per seguretat.

La segona consulta seria tornar a carregar els permisos.

OPCIO 2:

Directament canviar-ho en el mysql\_secure\_installation, en el meu cas em decantare per

aquesta opció.

P á g i n a 11 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Aixó seria tot

\2. Quines són les instruccions per arrancar / verificar status / apagar servei de la base de

P á g i n a 12 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

dades de Percona Server en el CentOS 7

Iniciem el servei Percona amb l'ordre següent:

\# systemctl start mysql

A continuació, comprovem l'estat del servei executant l'ordre següent:

\# systemctl status mysql

Aturem el servei executant l'ordre següent:

\# systemctl stop mysql

Reiniciem el servei executant l'ordre següent:

\# systemctl restart mysql

\3. A on es troba i quin nom rep el fitxer de configuració del SGBD Percona Server?

**/etc/my.cnf**

\4. A on es troben físicament els fitxers de dades (per defecte). Com ho has sabut?

**/var/lib/mysql/**

A part de veure-ho en alguns moments d’instal·lar-lo, ho vaig veure en la documentació

oficial de Percona.

\5. Crea un usuari anomenat asix en el sistema operatiu i en SGBD de tal manera que aquest

usuari del sistema operatiu no hagi d'introduir l'usuari i *password* cada vegada que cridem

al client mysql?

i. https://dev.mysql.com/doc/refman/8.0/en/password-security-user.html

ii. Usuari SO-→ asix / patata

Crearem l’usuari, le definim la contrasenya i l’afegim al grup de

superusuaris(root).

iii. Usuari MySQL → asix / patata

P á g i n a 13 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Crearem l’usuari i l’otorgarem tots els permisos en qualsevol base de dades

i dispositiu remot.

Configuració

/etc/my.cnf

Afegirem les seguent línies (client y password).

Tambè es podria entrar amb l’usuari sense indicar ni l’usuari, per en aquest cas

l’exercici nomes ens demana la contrasenya.

Aquest punt es opcional, però en un cas real er mantenir la contrasenya segura, el

fitxer no ha de ser accessible per a ningú més que per l’usuari. Per assegurar-vos,

establiu el mode d'accés a fitxers en 400 o 600.

Aquest seria el resultat, no hem indicat password i ha entrat a mysql.

P á g i n a 14 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

\6. El servei de MySQL (mysqld) escolta al port 3306. Quina modificació/passos caldrien fer

per canviar aquest port a 33306 per exemple?

\7. Important: No realitzis els canvis. Només indica els passos que faries.

Editariem el fitxer de configuració del SGBD = /etc/my.cnf

[mysqld]

port = 33306

Afegiriem el port a la configuració a l’apartat de mysqld.

Un cop fet això, guardarem els canvis del fitxer i reiniciarem el servei de mysql (systemctl).

\# netstat -tlpn | grep mysql

Amb aquesta comanda comprovaríem si el servei mysql esta escoltant per el port

desitjat.

Ens sortiria una cosa tal com així

P á g i n a 15 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

En lloc del 3306 ens sortiria el port modificat.

\8. Ensenya al professor que us podeu connectar al SGBD.

En aquest cas utilitzarem com SGBD el MySQL Workbench 8.0 CE.

En aquesta prova entrarem amb l’usuari asix.

El tallafocs hauria de estar obert per el port 3306(en la documentació de l’instal·lació, al final,

podem trobar com fer-ho).

Accedirem per aquesta ip. Es un adaptador-pont de la maquina virtual.

P á g i n a 16 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Connexió successfull.

P á g i n a 17 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

**Part II - INSTAL·LACIÓ SGBD MySQL 8.0 (màx. 2 punt)**

**ENUNCIAT**

Partint d'una màquina CentOS 7 minimal proporcionada pel professor realitza la instal·lació d'un

SGBD MySQL. Concretament la **versió 8.0.**

**Notes**

•

•

**La màquina de la part I i la part II han de ser diferents.**

**No s'ha d'intal·lar MariaDB!!!**

**ENLLAÇOS**

**Fitxer codi font MySQL 8.0** (Generic Linux)

<https://dev.mysql.com/doc/refman/8.0/en>

**LLIURAMENT**

Pots utilitzar aquest document com a plantilla per el lliurament de l’activitat, inclou la webgrafia

utilitzada per la realització de l’activitat.

**Altres opcions de lliurament:**

•

Utilitzar aquest document com a plantilla per el lliurament de l’activitat i penjar-la en

tasca destinada a aquesta activitat dins del curs Moodle

Realitzar la documentació sobre un repositori GIT. Utilitzant el format de fitxer

MarkDown (MD). **(1 punt)**

•

•

Dins d'una WikiMedia. **(1 punt)**

**REALITZA LA DOCUMENTACIÓ NECESSÀRIA PER LA INSTAL·LACIÓ PAS A PAS.**

•

•

Indica clarament els passos per reproduir la instal·lació en un altra màquina.

Si realitzes algun canvi en la configuració del firewall, o altres elements de seguretat per

poder tenir accés indica quins canvis has hagut de fer.

P á g i n a 18 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

•

Cal tenir en compte que la documentació va dirigida a tècnics informàtics i no a usuaris no

Es valorarà la presentació, l'organització del text i la facilitat de lectura.

experts.

•

Enllaços utilitzat a part de la pagina oficial de Percona, que també han servit per dur a terme aquesta

practica.

<https://dev.mysql.com/doc/refman/8.0/en/linux-installation-yum-repo.html>

<https://www.tecmint.com/install-latest-mysql-on-rhel-centos-and-fedora/>

<https://blog.softhints.com/mysql-5-7-vs-mysql-8-do-you-need-to-upgrade-to-mysql-8/>

Primer de tot com sempre, hem d’asegurar que la nostra maquina estigui

actualitzada, farem un yum -y Update.

Conf – xarxa:

**INSTAL·LACIÓ MySQL 8.0**

MySQL 8 és l'última versió del potent sistema de gestió de bases de dades MySQL.

Potencia moltes aplicacions empresarials, llocs web i sistemes transaccionals en

temps real. Per començar a instal·lar el servidor MySQL 8.0 a CentOS 7, heu

d'afegir el dipòsit oficial de la comunitat MySQL al vostre sistema.

Ara descarreguem i afegim el següent repositori de MySQL Yum a la llista de

repositoris del vostre sistema de distribució Linux per instal·lar la darrera versió de

MySQL.

Instalarem els repositori compatible amb el CENTOS/RHEL 7 = 7.1

P á g i n a 19 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Després de descarregar el paquet, instal·larem ara el paquet descarregat amb l'ordre següent.

Instal·larem la darrera versió de MySQL (actualment 8.0) mitjançant l'ordre següent.

P á g i n a 20 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Després d'una instal·lació correcta de MySQL, és hora d'iniciar, habilitar i verificar l'estat del

servidor MySQL amb les ordres següents:

Podem comprovar la versió del MySQL.

Un cop instal·lat el MySQL, hauríem de entrar per poder canviar la contrasenya.

A diferencia de versions antigues, en la nova versió no cal generar una password temporal per

entrar per primera vegada, prenen enter ja entraríem sense password.

P á g i n a 21 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Amb aquesta consulta ja podríem definir una contrasenya.

Tambè podem definir la contrasenya a partir de la securització,tot i que en aquest cas no cal.

P á g i n a 22 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Cal afegir el port de MySQL a aquest firewall perquè hi puguem accedir des de l'exterior.

Instal·lació i configuració del MySQL finalitzada.

**RESPON O COMPROVA ELS SEGÜENTS APARTATS**

\1. A on es troben físicament els fitxers de dades?

Com en totes les versions i burificacions de MySQL, totes les dades

d’emmagatzematge es troben en **/var/lib/mysql**

\2. A on es troba el fitxer de configuració? Quin és el seu contingut?

**/etc/my.cnf**

**/etc/my.cnf.d/mysql-server.conf**

Normalment el fitxer de configuració sempre es el mateix (my.cnf), però en

algunes noves versions poden estar a /my.cnf.d/.

\3. El procés de mysqld escolta al port 3306. Quina modificació/passos caldrien fer per canviar

aquest port a 33306 per exemple? Important: No realitzis els canvis. Només indica els

passos que faries.

/etc/my.cnf.d/mysql-server.conf

[mysqld]

P á g i n a 23 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

port = 33306

Afegiriem el port a la configuració a l’apartat de mysqld.

Un cop fet això, guardarem els canvis del fitxer i reiniciarem el servei de mysql (systemctl).

\# netstat -tlpn | grep mysql

Amb aquesta comanda comprovaríem si el servei mysql esta escoltant per el port

desitjat.

Ens sortiria una cosa tal com així:

En lloc del 3306 ens sortiria el port modificat.

\4. Un cop finalitzada la instal·lació i veure que funciona, mostra el resultat de la comanda:

ps -ef | grep mysql

\5. Quines són les característiques principals que ofereix MySQL 8.0 enfront de la 5.7.

Hi ha algunes diferències que tindran un impacte en el vostre treball amb MySQL si passeu

de la 5.7 a la 8. Per exemple, si voleu canviar la vostra contrasenya d'arrel a MySQL 8,

haureu de fer diferents passos en comparació amb la 5.7.

(Bàsicament quan acabes d’instal·lar el mysql, en versions anteriors s’havia de generar

contrasenyes temporals per accedir al mysql per primera vegada, en la nova versió quan

demana el password, pots donar al enter i entraras sense introduir cap password.)

Altre gran canvi que us pot afectar és el motor d'emmagatzematge MyISAM, que estarà

disponible amb algunes restriccions.

Les metataules de MySQL es mouen a InnoDB. Això s'ha de tenir en compte quan es vol

actualitzar.

P á g i n a 24 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

\6. Ensenya al professor que us podeu connectar al SGBD.

En aquest cas utilitzarem com SGBD el MySQL Workbench 8.0 CE.

En aquesta prova entrarem amb l’usuari asix.

El tallafocs hauria de estar obert per el port 3306(en la documentació de l’instal·lació, al final,

podem trobar com fer-ho).

Accedirem per aquesta ip. Es un adaptador-pont de la maquina virtual.

P á g i n a 25 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Connection Successfull.

P á g i n a 26 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

**PART III - INSTAL·LACIÓ SGBD MongoDB (màx. 1 punt)**

**ENUNCIAT**

Partint d'una màquina CentOS 7 minimal proporcionada pel professor realitza la instal·lació d'un

SGBD NoSQL MongoDB (**última versió**)**.**

**Nota: La màquina de la part I i la part II han de ser diferents.**

**ENLLAÇOS**

**Documentació oficial d’instal·lació MongoDB**

https://docs.mongodb.com/manual/installation/

**LLIURAMENT**

Pots utilitzar aquest document com a plantilla per el lliurament de l’activitat, inclou la webgrafia

utilitzada per la realització de l’activitat.

**Opcions d'entrega:**

•

Utilitzar aquest document com a plantilla per el lliurament de l’activitat i penjar-la en tasca

destinada a aquesta activitat dins del curs Moodle

Realitzar la documentació sobre un repositori GIT. Utilitzant el format de fitxer MarkDown

(MD). **(1 punt)**

•

•

Dins d'una WikiMedia. **(1 punt)**

**REALITZA LA DOCUMENTACIÓ NECESSÀRIA PER LA INSTAL·LACIÓ PAS A PAS.**

•

•

Indica clarament els passos per reproduir la instal·lació en un altra màquina.

Si realitzes algun canvi en la configuració del firewall, o altres elements de seguretat per

pode tenir accés indica quins canvis has hagut de fer.

•

Cal tenir en compte que la documentació va dirigida a tècnics informàtics i no a usuaris no

experts.

P á g i n a 27 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

•

Es valorarà la presentació, l'organització del text i la facilitat de lectura.

•

Incloure en la documentació un petit apartat a on s'expliqui com realitzar la connexió a la

BD.

•

Ensenya al professor que us podeu connectar al SGBD.

Enllaç que he seguit per dur a terme aquesta part de la practica.

<https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/>

Hi ha dues versions, la Community Edition i la Enterprise Edition, la versió Enterprise es mes

exclusiva per així dir-ho, per que inclou algunes funcions de les quals la versió comú no te.

Les funcions bàsiques del servidor per als desenvolupadors són generalment les mateixes, però una

subscripció a MongoDB Enterprise inclou funcions operatives i de gestió addicionals, una llicència

comercial (garantia i indemnització), així com accés a suport proactiu i formació sota demanda.

Però per aquesta practica en el meu cas escolliré la Community Edition.

Conf-xarxa

**INSTAL·LACIÓ MONGODB**

Configura el sistema de gestió de paquets (yum).

Crearem un fitxer /etc/yum.repos.d/mongodb-org-5.0.repo perquè puguem instal·lar

MongoDB directament amb yum:

Si executem la comanda següent podem observar que s’ha afegit al repository la

P á g i n a 28 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

configuració anterior.

Yum repolist

Després d'això, podem instal·lar el paquet mongodb-org amb aquesta comanda.

Instal·lació completa.

P á g i n a 29 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

**Després de l’instal·lació del MongoDB, podem veure en la documentació oficial que hi**

**han moltes configuracions de les politiques de SELinux.**

**Security-Enhanced Linux (SELinux) és una arquitectura de seguretat per als sistemes**

**Linux® que permet que els administradors tinguin més control sobre les persones**

**que hi poden accedir.**

**Aquestes configuracions ens la saltarem perquè son innecessàries respecte al nostre**

**objectiu davant d’aquesta practica, que es fer una instal·lacio i configuració bàsica**

**d’aquest SGBD.**

El procés d'instal·lació configura automàticament MongoDB perquè s'executi com un dimoni

controlat per systemd, el que significa que podem gestionar MongoDB mitjançant les

diferents ordres systemctl.

Tanmateix, aquest procediment d'instal·lació no inicia automàticament el servei.

Executem l'ordre systemctl següent per iniciar i comprovar l'estat del servei MongoDB.

Després de confirmar que el servei s'executa com s'esperava, activem el servei MongoDB.

Iniciem una sessió de mongosh i mongo a la mateixa màquina amfitrió que el mongod.

Podem executar per connectar-nos a un mongod que s'està executant amb el port

predeterminat 27017.

P á g i n a 30 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

És possible que ens interessi disposar d'usuaris que accedeixin amb contrasenya al servei

MongoDB. Si és així hem d'activar l'autenticació a **mongod.conf.**

Està desactivada, així que l'activarem eliminant el caràcter # a l'inici de línia i tot seguit

afegirem una subdirectiva authorization.

Guardem la configuració i reinciem servei.

Crearem un usuari root.

Un cop creat podem provar d’accedir amb l’usuari creat, per comprovar que la creació

P á g i n a 31 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

d’usuari que hem fet al pas anterior es correcte.

Cal afegir el port de MongoDB a aquest firewall perquè hi puguem accedir des de l'exterior.

Per comprovar la connectivitat de MongoDB a un software, utilitzarem Robo 3T.

Robo 3T (abans denominat Robomongo) és una GUI lleugera gratuïta per a MongoDB. El

seu objectiu principal és executar consultes, crear índexs i visualitzar documents. Instal·leu

Robo 3T.

Per dur a terme això, primer de tot configurarem l’arxiu de configuració de MongoDB per

modificar la IP localhost per la IP de l’adaptador-pont(que es el que te connexió a altres

maquines de la mateixa xarxa) o la 0.0.0.0(per 0.0.0.0 deixarà de ser un servei local per

convertir-se en un servei al qual es pugui connectar remotament).

**/etc/mongod.conf**

P á g i n a 32 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Un cop modificat, guardem els canvis i sortim.

Reiniciarem el servei, com sempre hem de fer després de tocar la configuració.

Després anem al software i afegirem una connexió.

P á g i n a 33 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Introduirem les dades de la maquina de MongoDB, amb el port que toca.

En autenticació afegirem l’usuari creat anteriorment amb les seva contrasenya i la base de

dades sobre on vam crear aquest usuari que per defecte es el admin.

Provarem la connexió, veiem que esta tot correcte.

P á g i n a 34 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Finalment directament ens connectem.

Podem veure que la connexió ha sigut successiva i ja podem manipular les dades.

P á g i n a 35 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

**PART IV - INSTAL·LACIÓ SGBD SQLServer (màx. 1+1 punts)**

**ENUNCIAT**

Partint d'una màquina Windows Server realitza la instal·lació d'un SGBD SQLServer (**última**

**versió**)**.**

**LLIURAMENT**

Pots utilitzar aquest document com a plantilla per el lliurament de l’activitat, inclou la webgrafia

utilitzada per la realització de l’activitat.

**Opcions d'entrega:**

•

Utilitzar aquest document com a plantilla per el lliurament de l’activitat i penjar-la en tasca

destinada a aquesta activitat dins del curs Moodle

Realitzar la documentació sobre un repositori GIT (Bitbucket o GITHub). Utilitzant el format

de fitxer MarkDown (MD). **(1 punt)**

Dins d'una WikiMedia. **(1 punt)**

•

•

**REALITZA LA DOCUMENTACIÓ NECESSÀRIA PER LA INSTAL·LACIÓ PAS A PAS.**

•

Indica clarament els passos per reproduir la instal·lació en un altra màquina.

•

Cal tenir en compte que la documentació va dirigida a tècnics informàtics i no a usuaris no

experts.

•

Es valorarà la presentació, l'organització del text i la facilitat de lectura.

•

Incloure en la documentació un petit apartat a on s'expliqui com realitzar la connexió a la

BD.

•

•

(**Opcional +1 punt**) Instal·lar SQL Server en un entorn Windows Server Core.

Ensenya al professor que us podeu connectar al SGBD.

P á g i n a 36 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Dades del servidor.

Dades de xarxa:

Baixem el fitxer de configuració des de la pàgina de descàrregues de SQL Server. Desplaceu-vos cap

avall fins que trobeu l'edició per a desenvolupadors i feu clic al botó Baixa ara.

P á g i n a 37 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Un cop finalitzada la descàrrega, obriu el fitxer de configuració per iniciar el procés d'instal·lació.

**Bàsic**: instal·la SQL Server 2019 amb la configuració predeterminada del motor de base de dades

SQL Server

Personalitzat: En aquesta opció, podem seleccionar les característiques, configurar-les a l'assistent

d'instal·lació

Descarregar medis: descarrega el fitxer ISO o CAB per a la configuració de SQL Server

P á g i n a 38 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

Acceptem els terminis de llicencia.

Ubicació d’instal·lació.

P á g i n a 39 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

P á g i n a 40 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

P á g i n a 41 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

P á g i n a 42 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

P á g i n a 43 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

P á g i n a 44 | 45





CFGS-ASIX-M10-UF2

Navlani,Aryan

P á g i n a 45 | 45

