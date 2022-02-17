# PART III - INSTAL·LACIÓ SGBD MongoDB (màx. 1 punt)

![image](https://user-images.githubusercontent.com/61285257/154456331-270cbc5a-8806-475d-b81f-a952d357984f.png)

MongoDB és la més representativa de les bases de dades conegudes com a NoSQL, acrònim de Not only SQL. També podem anomenar-la amb el terme de base de dades documental, ja que el que emmagatzemem són purs documents JSON i no registres, com passa a les taules de les bases de dades relacionals.

Hi ha dues  versions, la Community Edition i la Enterprise Edition, la versió  Enterprise es mes exclusiva per així dir-ho, per que inclou algunes funcions de les quals la versió comú no te.

Les funcions bàsiques del servidor per als desenvolupadors són generalment les mateixes, però una subscripció a MongoDB Enterprise inclou funcions operatives i de gestió addicionals, una llicència comercial (garantia i indemnització), així com accés a suport proactiu i formació sota demanda.

Però per aquesta practica en el meu cas escolliré la Community Edition.

Conf-xarxa:

![image](https://user-images.githubusercontent.com/61285257/154457524-12f86594-d989-4c14-b0dc-763208fa1278.png)

## INSTAL·LACIÓ MONGODB

Configura el sistema de gestió de paquets (yum). 
Crearem un fitxer /etc/yum.repos.d/mongodb-org-5.0.repo perquè puguem instal·lar MongoDB directament amb yum:

![image](https://user-images.githubusercontent.com/61285257/154457731-a829627c-fff8-451e-b66e-eee23e38ecb7.png)

Si executem la comanda següent podem observar que s’ha afegit al repository la configuració anterior.
Yum repolist

![image](https://user-images.githubusercontent.com/61285257/154457778-d1e291d4-fc2a-4478-8965-88c2d902b50d.png)

Després d'això, podem instal·lar el paquet mongodb-org amb aquesta comanda.

![image](https://user-images.githubusercontent.com/61285257/154457808-34361bc9-dc9a-452e-89c9-0e62049fe337.png)
![image](https://user-images.githubusercontent.com/61285257/154457833-96682c2e-f450-4b2f-84c0-c9018dd16f9b.png)

Instal·lació completa.

*Després de l’instal·lació del MongoDB, podem veure en la documentació oficial que hi han moltes configuracions de les politiques de SELinux.*

*Security-Enhanced Linux (SELinux) és una arquitectura de seguretat per als sistemes Linux® que permet que els administradors tinguin més control sobre les persones que hi poden accedir.*

*Aquestes configuracions ens la saltarem perquè son innecessàries respecte al nostre objectiu davant d’aquesta practica, que es fer una instal·lacio i configuració bàsica d’aquest SGBD.* 


El procés d'instal·lació configura automàticament MongoDB perquè s'executi com un dimoni controlat per systemd, el que significa que podem gestionar MongoDB mitjançant les diferents ordres systemctl. 
Tanmateix, aquest procediment d'instal·lació no inicia automàticament el servei. 
Executem l'ordre systemctl següent per iniciar i comprovar l'estat del servei MongoDB. Després de confirmar que el servei s'executa com s'esperava, activem el servei MongoDB.

![image](https://user-images.githubusercontent.com/61285257/154459263-a756b9ff-51ff-4022-821f-5c713dc3b5a2.png)

Iniciem una sessió de mongosh i mongo a la mateixa màquina amfitrió que el mongod. Podem executar per connectar-nos a un mongod que s'està executant amb el port predeterminat 27017.

![image](https://user-images.githubusercontent.com/61285257/154459300-138b65b5-e295-4679-a88b-6ec241d46685.png)

![image](https://user-images.githubusercontent.com/61285257/154459318-bc17dd7e-949c-4cd0-9f43-9bc512944171.png)

És possible que ens interessi disposar d'usuaris que accedeixin amb contrasenya al servei MongoDB. Si és així hem d'activar l'autenticació a **mongod.conf**.
Està desactivada, així que l'activarem eliminant el caràcter # a l'inici de línia i tot seguit afegirem una subdirectiva authorization.

![image](https://user-images.githubusercontent.com/61285257/154459398-91afdb97-3b17-4ae8-9280-362adadcad5e.png)

Guardem  la  configuració i reinciem servei.

![image](https://user-images.githubusercontent.com/61285257/154459453-7249a677-c758-4b17-9bd5-b054695a822a.png)

Crearem un usuari root.

![image](https://user-images.githubusercontent.com/61285257/154459496-1a95e5dc-6475-4725-8208-24b10dc6c46b.png)

Un cop creat podem provar d’accedir amb l’usuari creat, per comprovar que la creació d’usuari que hem fet al pas anterior es correcte.

![image](https://user-images.githubusercontent.com/61285257/154459526-0c4d01bf-59f7-4f29-8493-f618f3d534c4.png)

Cal afegir el port de MongoDB a aquest firewall perquè hi puguem accedir des de l'exterior.

![image](https://user-images.githubusercontent.com/61285257/154459561-017dcc8c-b8e4-42b2-9553-f6579c5d2e4e.png)

![image](https://user-images.githubusercontent.com/61285257/154459579-ac66e93c-23aa-4d32-a628-b1db8f9afac6.png)

Per comprovar la connectivitat de MongoDB a un software, utilitzarem Robo 3T.

Robo 3T (abans denominat Robomongo) és una GUI lleugera gratuïta per a MongoDB. El seu objectiu principal és executar consultes, crear índexs i visualitzar documents. Instal·leu Robo 3T.

Per dur a terme això, primer de tot configurarem l’arxiu de configuració de MongoDB per modificar la IP localhost per la IP de l’adaptador-pont(que es el que te connexió a altres maquines de la mateixa xarxa) o la 0.0.0.0(per 0.0.0.0 deixarà de ser un servei local per convertir-se en un servei al qual es pugui connectar remotament).
**/etc/mongod.conf**

![image](https://user-images.githubusercontent.com/61285257/154459643-5e58a76d-3ff2-4e32-b733-c97f3df65d1d.png)

Un cop modificat, guardem els canvis i sortim.

Reiniciarem el servei, com sempre hem de fer després de tocar la configuració.

![image](https://user-images.githubusercontent.com/61285257/154459691-bfe8d97d-0b20-4f38-9db3-e10c4d0a151e.png)

Després anem al software i afegirem una connexió.

![image](https://user-images.githubusercontent.com/61285257/154459730-4440a3db-d4b8-4328-98b2-11ad8f1653f1.png)

Introduirem les dades de la maquina de MongoDB, amb el port que toca.

![image](https://user-images.githubusercontent.com/61285257/154459766-8313dcf8-0fab-4cb2-a7e2-c1553ae67023.png)

En autenticació afegirem l’usuari creat anteriorment amb les seva contrasenya i la base de dades sobre on vam crear aquest usuari que per defecte es el admin.

![image](https://user-images.githubusercontent.com/61285257/154459804-0c202bed-ad77-4afa-bc5f-8b8172a78767.png)

Provarem la connexió, veiem que esta tot correcte.

![image](https://user-images.githubusercontent.com/61285257/154459840-04c971cf-c565-4f7a-89fc-8a89e2a77398.png)

Finalment directament ens connectem.

![image](https://user-images.githubusercontent.com/61285257/154459876-d380e373-eede-4f35-aa53-829f1621d20d.png)

![image](https://user-images.githubusercontent.com/61285257/154459904-f5a782d4-b357-4168-875f-507ebbef98a3.png)

Podem veure que la connexió ha sigut successiva i ja podem manipular les dades.



