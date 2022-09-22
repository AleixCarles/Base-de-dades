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
    <td style="width: 33%";>CREATE DATABASE "nom de la base de dades"</td>
  </tr>
</table>
<p align="center">
  <img src="https://user-images.githubusercontent.com/91152783/191807200-4c75ea85-33b7-47e5-86bc-2406709255d7.png" title="Base de dades creada">
</p>
