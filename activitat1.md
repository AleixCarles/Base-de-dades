<h1 align="center">Instal·lació PostgreSQL</h1>

<p align="center">Per instal·lar el PostgreSQL farem la comanda següent:<p>
<table align="center";text-align: "center";>
  <tr >
    <td style="width: 33%";>apt-get install postgresql-14</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/189316972-4e572623-945b-423b-b3e2-ddbfd382fd6d.png" title="Comanda de instal·lació">
</p>

<p align="center"> Per veure l'estat amb el qual es troba el servei de Postgre farem la següent comanda: </p>
<table align="center";text-align: "center";>
  <tr >
    <td style="width: 33%";>service postgresql status</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/189327782-8f79b5c3-3722-47dc-bb95-26bdb1761b1a.png" title="Comanda status del servei">
</p>

<p align="center"> Per accedir a la base de dades ho fem amb la comanda següent:</p>
<table align="center";text-align: "center";>
  <tr >
    <td style="width: 33%";>sudo -u postgres psql</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/189477247-c6c4f895-7c0b-4f65-967e-adac4788d718.png" title="Comanda d'accés postgres">
</p>

<p align="center">Per crear la base de dades haurem de ficar una vegada dins de postgres aquesta línia:</p>
<table align="center";text-align: "center";>
  <tr >
    <td style="width: 33%";>CREATE DATABASE "nom de la base de dades";</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/191807200-4c75ea85-33b7-47e5-86bc-2406709255d7.png" title="Base de dades creada">
</p>
<p align="center">Per veure les base de dades que tenim farem el seguent:</p>
<table align="center";text-align: "center";>
  <tr >
    <td style="width: 33%";>\l</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/191808105-2d90ea9a-20e6-488c-afbb-02a333212d8e.png" title="Llista base de dades">
</p>
<p align="center">Per entrar a la base de dades farem:</p>
<table align="center";text-align: "center";>
  <tr >
    <td style="width: 33%";>\c "nom de la base de dades"</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/191808635-7693df73-dfd7-4ac7-bfd0-bbc9f4510499.png" title="Entrar base de dades">
</p>
                                                                                                                                                
																		
<p align="center">Ara fem la creació de la base de dades amb un serial, un varchar i un integer:</p>
<table align="center";text-align: "center";>
  <tr >
    <td style="width: 33%";>CREATE TABLE estatsACS (
	id serial PRIMARY KEY,
	nom VARCHAR (20),
	superficie INT
);</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/191812173-18250cf5-c16c-4bf6-b920-ca55fb017bf1.png" title="Creant taula a la base de dades">
</p>

<p align="center">Ara fem els inserts on afegim les dades que hi han a la taula:</p>
<table align="center";text-align: "center";>
  <tr >
    <td style="width: 33%";>INSERT INTO (nom de la taula)(valor1,valor2)
VALUES ('valor1','valor2'), ('valor1','valor2'), ('valor1','valor2');</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192479999-1be8f548-94a7-420c-96a1-67b04ca0e58a.png" title="Crear insert a la base de dades">
</p>
<p align="center">Ara creem la taula de les ciutats:</p>
<table align="center";text-align: "center";>
  <tr >
    <td style="width: 33%";>CREATE TABLE ciutatsACS (
	id serial PRIMARY KEY,
	nom VARCHAR (25),
	habitants INT,
	estat INT,
	FOREIGN KEY (estat) REFERENCES estatsACS (id)
);
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192491537-dcef05d5-b4bf-4725-9866-a76d4eb1fa7a.png" title="Crear taula ciutats">
</p>


<p align="center">Afegim les ciutats amb el seu nom, habitants i la id del estat que esta:</p>
<table align="center";text-align: "center";>
  <tr >
    <td style="width: 33%";>INSERT INTO (nom de la taula)(valor1,valor2,valor3(id_estat)
VALUES ('valor1','valor2',valor3(id_estat)), ('valor1','valor2',valor3(id_estat)), ('valor1','valor2',valor3(id_estat);</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192502229-b2fda3e7-6bb0-44ca-8437-9f26acf8eff2.png" title="Insert de ciutat">
</p>

<p align="center">Aqui podem veure amb un select una part dels estats que hem afegit:</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>select * from estatsacs;</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192504007-435cbdfb-297a-4c65-9573-24c3eb3c1412.png" title="Select dels estats">
</p>
<p align="center">Aqui podem veure amb un select una part de les ciutats que hem afegit:</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>select * from ciutatsacs;</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192506608-91e464ee-3a98-41dc-92bf-2ed21b6f3b4f.png" title="Select de les ciutats">
</p>

<p align="center">Ara farem el SELECT des de python el qual tenim que buscar <strong>tots els estats amb una superfície més gran que 200.000 Km2</strong></p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>SELECT nom, superficie  
                        FROM estatsacs  
                        WHERE superficie > 200000;</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192621201-28cdb72b-aec4-4fc1-8874-1536feabc6ab.png" title="Select de estats mes gran 200km">
</p>
<p align="center">El resultat es aquest:</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192622095-d856a0cf-fbf2-4b0d-897e-c4810704b399.png" title="Select de resultat de estats mes gran 200km">
</p>


<p align="center">Ara farem el mateix pero ara tenim que buscar <strong>tots els estats amb una superfície més petita que 100.000Km2 i més gran que 20.000Km2</strong></p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>SELECT nom, superficie  
                        FROM estatsacs  
                    WHERE superficie < 100000 AND superficie>20000;</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192624388-24fe20a9-bbe2-493b-8800-ac62266652de.png" title="Select de estats mes petit 100km i mes gran de 20km">
</p>
<p align="center">El resultat es aquest:</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192625123-dba0bd5e-bdc2-46fa-ba9e-891ebf860b27.png" title="Select de resultat de estats mes petit 100km i mes gran de 20km">
</p>

<p align="center">Ara farem el SELECT el qual tenim que buscar <strong>totes les ciutats amb més de 1.000.000 d'habitants</strong></p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>SELECT nom, habitants  
                        FROM ciutatsacs  
                    WHERE habitants > 1000000</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192626240-06223f7c-0d6b-44fb-8e8e-402ac1e25f06.png" title="Select de les ciutats amb més de 1.000.000 d'habitants">
</p>
<p align="center">El resultat es aquest:</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192626313-bb74f0d6-c64e-40b3-aa66-3cf8c886207e.png" title="Select de resultat de les ciutats amb més de 1.000.000 d'habitants">
</p>

<p align="center">Ara farem el SELECT el qual tenim que buscar <strong>totes les ciutats amb menys de 1.000.000 d'habitants i més de 650.000 habitants</strong></p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>SELECT nom, habitants  
                        FROM ciutatsacs  
                    WHERE habitants < 1000000 AND habitants > 650000</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192626874-ff896bc1-c00e-4084-974c-3322609f9d88.png" title="Select de les ciutats amb menys de 1.000.000 d'habitants i més de 650.000 habitants">
</p>
<p align="center">El resultat es aquest:</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192626934-1ef9cb29-3848-4c7c-8317-da1def3c9578.png" title="Select de resultat de les ciutats amb menys de 1.000.000 d'habitants i més de 650.000 habitants">
</p>

<p align="center">Creem un usuari root per poder fer la copia de la base de dades:</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>CREATE USER root WITH PASSWORD 'root';</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/193284848-5038c0a2-0910-4394-bdf9-ed34b66bfd73.png" title="Creacio del usuari root">
</p>

<p align="center">Fiquem al usuari permisos a la base de dades.</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>GRANT ALL PRIVILEGES ON DATABASE "nom de la base de dades" TO "usuari";</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/193285621-76151ce2-7601-4dc2-859d-cede68631f06.png" title="Permisos al root">
</p>

<p align="center">I fiquem al usuari que hem creat en super usuari.</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>ALTER USER "nom del usuari" WITH superuser;</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/193286099-6ab433aa-e14a-4f95-a05a-f95e4bd6f610.png" title="Usuari en superusuari">
</p>

<p align="center">Ara ens fiquem en mode root i fem la següent comanda per fer la copia de seguretat</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>pg_dump "nom de la base de dades" > "ubicacio de on vols que es guarde la copia"</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/193288515-89fb5371-ba87-495e-a2fb-24a16e7f6822.png" title="Fer copia">
</p>

<p align="center">Per restaurar primer de tot crearem la base de dades on voldrem ficar la copia. Després de crear-ho fem la comanda següent aquest ficara el contingut de la copia a la nova base de dades.</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>psql "nom de la base de dades" </td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/193290876-78b631cd-05ba-4719-80f7-fa48891b1588.png" title="Ficar base de dades la copia de seguretat">
</p>

<p align="center">Farem un select dins de la base de dades on hem ficat la copia per confirma que la copia esta feta correctament</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>select * from "nom de una taula" </td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/193295799-f6bce2ca-dba4-483c-a815-d4bcb7cb72aa.png" title="Select per confirmar 1">	
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/193296270-d033bdd8-3395-42bf-a32c-82b514d1d9ac.png" title="Select per confirmar 2">

<p align="center">Farem un \l per veure la base de dades i farem el seguentt per esborrar-la:</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>DROP DATABASE uf4acs_copia; </td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/193677834-9b7e9d18-d12f-483f-8443-c605fdfd767d.png" title="Esborrar copia"></p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/193677942-9e51f0cd-3e66-46f9-8e0e-e8f682c9ad97.png" title="Confirma esborrar copia"></p>
	
<p align="center">Ara voldrem esborrar de la taula d'estats tots els que comensen amb I. Que son aquests:</p>  
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/194153864-f1ffe573-5964-4bb2-8f66-858be7c0f2be.png" title="Indicar esborrar estats I"></p>

<p align="center">Per esborrar els estats primer de tot tindrem que esborrar la constraint que hi ha lligada des de ciutats per tant farem el següent:</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>ALTER TABLE "nom de la taula" DROP CONSTRAINT "nom de la constraint";</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/194154526-63af4b27-cab6-49da-b253-8cae0e3bcd04.png" title="Esborrar Contraint de ciutats"></p>
  
  <p align="center">Una vegada fet el pas anterior esborrarem ara si els estats amb la primera lletra I:</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>DELETE FROM estatsacs WHERE nom like 'I%';</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/194155512-85898ee2-e386-401e-9a04-1359fadd1c1c.png" title="Esborrar estats amb I"></p>

<p align="center">Podrem veure que si tornem a fer el select aquests ja no estaran.</p>  
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/194156918-44ee97a2-a4b8-4280-9bcb-cfaba940dd86.png" title="Indicar esborrar estats I"></p>

<p align="center">Ara esborrem tots els estats inferior a una superficie de 100.000, d'aquesta manera s'esborrar, primer faig un select per a que es veigui que sol hi han 12 i al eliminar son els que indica que s'han borrat.</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>DELETE FROM "taula" WHERE superficie < 100000;</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/194158834-e02250ae-ba4d-49d5-b451-83b48cf01052.png" title="Esborrar estats amb inferior de 100000"></p>
  
  <p align="center">Eliminem la taula d'estats:</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>DROP TABLE estatsacs;</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/194160622-251651d9-59e0-408b-bb5d-f322a7a55ab3.png" title="Esborrar taula estats"></p>
  
  <p align="center">Ara tenim que alterar la taula ciutatsXYZ afegint un camp que es digui atacsDeGodzilla i sigui de tipus sencer. El valor del camp serà 0.</p>
<table align="center";text-align: "center";>
  <tr >
	  <td style="width: 33%";>ALTER TABLE ciutatsacs ADD COLUMN atacsDeGodzilla integer;</td>
	  
  </tr>
	<p align="center">Per ficar el valor del camp 0 es fara això: </p>
  <tr >
	  <td style="width: 33%";>ALTER TABLE ciutatsacs ALTER COLUMN atacsDeGodzilla SET DEFAULT 0;</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/194163543-8d2ec61e-5dc5-454a-88b1-0f151bc8ccc3.png" title="Afegir atacsDeGodzilla"></p>
