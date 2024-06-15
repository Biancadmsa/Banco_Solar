### DESAFÍO EVALUADO " BANCO SOLAR "

```
Banco Solar

```

## Instalar las dependencias para que nuestro código funcione:

```
npm install axios cors dotenv express pg nodemon

El servidor se inicia con:
node servidor.js
o
nodemon servidor.js

```

### Acerca de este desafío

```
Se realizó un proyecto que incluye una base de datos llamada bancosolar, que debe permitir registrar nuevos usuarios con un balance inicial y basados en estos, realizar transferencias de saldos entre ellos.

```

### Consultas CRUD

```
Contiene las siguientes consultas CRUD:

 ● /GET: Devuelve la aplicación cliente disponible en el apoyo de la prueba.
● /usuario POST: Recibe los datos de un nuevo usuario y los almacena en PostgreSQL.
● /usuarios GET: Devuelve todos los usuarios registrados con sus balances.
● /usuario PUT: Recibe los datos modificados de un usuario registrado y los actualiza.
● /usuario DELETE: Recibe el id de un usuario registrado y lo elimina .
● /transferencia POST: Recibe los datos para realizar una nueva transferencia. Se debe ocupar una transacción SQL en la consulta a la base de datos.
● /transferencias GET: Devuelve todas las transferencias almacenadas en la base de datos en formato de arreglo.


```


### Para iniciar con la persistencia de datos se deben ocupar las siguientes instrucciones SQL:

```
CREATE DATABASE bancosolar;

CREATE TABLE usuarios (
id SERIAL PRIMARY KEY,
nombre VARCHAR(50),
balance FLOAT CHECK (balance >= 0)
);

CREATE TABLE transferencias (
id SERIAL PRIMARY KEY,
emisor INT,
receptor INT,
monto FLOAT,
fecha TIMESTAMP,
FOREIGN KEY (emisor) REFERENCES usuarios(id) ON DELETE CASCADE,
FOREIGN KEY (receptor) REFERENCES usuarios(id) ON DELETE CASCADE
);

SELECT * FROM transferencias

SELECT * FROM usuarios


```

###  Se modificó la columna fecha porque daba un error y se inicializó:


```
 ALTER TABLE transferencias ALTER COLUMN fecha SET DEFAULT CURRENT_TIMESTAMP;

```
