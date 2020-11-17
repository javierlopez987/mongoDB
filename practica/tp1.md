# MongoDB
## Actividad 1
**Conectarse a MongoDB vía CLI**
```js
	mongod
	mongo
```
> MongoDB shell
>
**Crear una nueva base de datos llamada *futbolfifa***
```js
	show dbs
	use futbolfifa
```
**Crear una nueva *collection* llamada *players***
```js
	show collections
	db.createCollection("players")
```
**Insertar 1 documento en la collection *players* con datos básicos**
```js
	db.players.insert(
		{
			name: "Pablo",
			lastname: "Ramirez",
			position: "goalkeeper"
		}
	)
```
**Listar todos los documentos de la collection *players***
```js
	db.players.find()
```
> { "_id" : ObjectId("5f8814ca4e09cb0bcfa4341e"), "name" : "Pablo", "lastname" : "Ramirez", "position" : "goalkeeper" }
>
**Insertar 4 documentos en la collection *players* con datos básicos**
```js
	db.players.insert([
		{
			name: "Pedro",
			lastname: "Marmol",
			position: "center back"
		},
		{
			name: "Sebastian",
			lastname: "Granito",
			position: "central"
		},
		{
			name: "Leonardo",
			lastname: "Caliza",
			position: "striker"
		},
		{
			name: "Joaquin",
			lastname: "Cuarcita",
			position: "winger"
		}
	])
```
> BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 4,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})
>
**Listar todos los documentos de la collection *players***
```js
	db.players.find()
```
> { "_id" : ObjectId("5f8814ca4e09cb0bcfa4341e"), "name" : "Pablo", "lastname" : "Ramirez", "position" : "goalkeeper" }
{ "_id" : ObjectId("5f881d2a05a041237b99bdba"), "name" : "Pedro", "lastname" : "Marmol", "position" : "center back" }
{ "_id" : ObjectId("5f881d2a05a041237b99bdbb"), "name" : "Sebastian", "lastname" : "Granito", "position" : "central" }
{ "_id" : ObjectId("5f881d2a05a041237b99bdbc"), "name" : "Leonardo", "lastname" : "Caliza", "position" : "striker" }
{ "_id" : ObjectId("5f881d2a05a041237b99bdbd"), "name" : "Joaquin", "lastname" : "Cuarcita", "position" : "winger" }
>
**Crear otras collections**
```js
	db.createCollection("teams")
```
> { "ok" : 1 }
```js
	db.createCollection("matches")
```
> { "ok" : 1 }
>
**Mostrar collections**
```js
	show collections
```
> matches
players
teams
>