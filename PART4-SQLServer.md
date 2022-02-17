# PART IV - INSTAL·LACIÓ SGBD SQLServer (màx. 1+1 punts)

*Aquest apartat s'ha utilitzat un Windows Server 2016 Datacenter, on instal·larem el SQL Server 2019.*

SQL Server és una solució de gestió de bases de dades relacionals que ofereix Microsoft.

![image](https://user-images.githubusercontent.com/61285257/154462534-93ecaa77-c036-4b87-895e-e21506f034ea.png)

Dades del servidor:  

![image](https://user-images.githubusercontent.com/61285257/154462724-d74ddfdd-f6f7-46b6-9406-4181ee22fcdf.png)

Dades de xarxa:

![image](https://user-images.githubusercontent.com/61285257/154462862-7305f67b-61df-4b2b-8c06-2cdd7897e6c2.png)

![image](https://user-images.githubusercontent.com/61285257/154475835-2ac7dbb0-7a8d-4882-a6f9-c9269187a4ba.png)

Baixem el fitxer de configuració des de la pàgina de descàrregues de SQL Server. Desplaceu-vos cap avall fins que trobeu l'edició per a desenvolupadors i feu clic al botó Baixa ara.

Un cop finalitzada la descàrrega, obriu el fitxer de configuració per iniciar el procés d'instal·lació.

![image](https://user-images.githubusercontent.com/61285257/154475900-25955963-edaa-4bf7-a398-9c1544d782de.png)

**Bàsic**: instal·la SQL Server 2019 amb la configuració predeterminada del motor de base de dades SQL Server
**Personalitzat**: En aquesta opció, podem seleccionar les característiques, configurar-les a l'assistent d'instal·lació
**Descarregar medis**: descarrega el fitxer ISO o CAB per a la configuració de SQL Server.

L’opció de Descarregar medis ens permet descarregar primer els fitxers de configuració i instal·lar l'SQL Server més tard. A part de que també podem configurar usuaris y base de dades en l’assistent de la instal·lació.
Aquesta opció es recomanable per un entorn real, mes que res per la personalització.

Però en aquest cas, com que nomes volem instal·lar i poder connectar-nos per fer demostracions, escollirem la instal·lació bàsica.

![image](https://user-images.githubusercontent.com/61285257/154476477-f2a9d3f5-6981-4c38-9fcb-3c0932b4d7da.png)

Acceptem els terminis de llicencia.

![image](https://user-images.githubusercontent.com/61285257/154476521-20bcd4dd-4a9e-4699-b09c-6556e29acc66.png)

Ubicació d’instal·lació.

![image](https://user-images.githubusercontent.com/61285257/154476564-107178bd-8286-460e-ad45-8b742c940a59.png)

Instal·lació en proces.

![image](https://user-images.githubusercontent.com/61285257/154476743-ae97d387-1f71-408a-9dfc-e1c3bcc2190c.png)

![image](https://user-images.githubusercontent.com/61285257/154477539-9abf705f-3c48-4b24-844b-c3dd0dde5415.png)

Instal·lació Finalitzada, juntament amb un resum dels parametres que podem veure en la captura.

Per interactuar amb SQL Server, cal tenir una eina de client SQL Server.

Microsoft ens proporciona SQL Server Management Studio (SSMS). SQL Server Management Studio és un programari per consultar, dissenyar i gestionar SQL Server al vostre ordinador local o al núvol. Ens proporciona eines per configurar, supervisar i administrar instàncies d'SQL Server.
Com podem vuere en la captura anterior l'assistent un cop finalitzat ja ens dona un enllaç directe per instal·lar aquest client, pero tambè, podem descarregar l'SSMS des del lloc web de Microsoft mitjançant l'enllaç següent:
https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15 


![image](https://user-images.githubusercontent.com/61285257/154478356-be031297-1b63-4b94-8f88-5e6d9e0089ab.png)

Un cop descarregat el fitxer, instal·larem aquest client.

Seguirem els simples passos de l'assistent següent:

Ens demanara l'ubicació i un cop finalitzat haurem de reiniciar la maquina.

![image](https://user-images.githubusercontent.com/61285257/154478442-a3698238-6f9c-43c9-b206-ca3632cf0c17.png)

![image](https://user-images.githubusercontent.com/61285257/154478546-126258cf-1942-4338-8233-e8292b037394.png)

Reiniciem la maquina.

![image](https://user-images.githubusercontent.com/61285257/154478579-cdd9eba2-91b2-4013-aab9-4ba54400abfb.png)





