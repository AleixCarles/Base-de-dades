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
