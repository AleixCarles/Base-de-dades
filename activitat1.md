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

<p align="center">Ara fem els inserts on afegim les dades que hi han a la taula</p>
<table align="center";text-align: "center";>
  <tr >
    <td style="width: 33%";>INSERT INTO (nom de la taula)(valor1,valor2)
VALUES ('valor1','valor2'), ('valor1','valor2'), ('valor1','valor2')
);</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/192479999-1be8f548-94a7-420c-96a1-67b04ca0e58a.png" title="Crear insert a la base de dades">
</p>
