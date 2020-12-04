# MongoDB
## Actividad 2
**Conectarse a MongoDB vía CLI**
```js
	mongod
	mongo
```
> MongoDB shell
>
**Crear una nueva base de datos de un sistema de streaming de video (ej. Netflix, Flow, Amazon Prime) que permita almacenar *movies*.**
```js
	show dbs
	use streaming
    show collections
	db.createCollection("movies")
```
**Para cada movie, se debería guardar información como título (String), year (Number), rating (Number, entre 1.0 y 5.0), genre (String), description (String), actors (Array<String>), country (String), income (Number), duration (Number).**
**Agregar películas usando insert()**
```js
	db.movies.insert([
        {
            "titulo": "Mosul",
            "year": 2020,
            "rating": 4,
            "genre": "Drama",
            "description": "Between 2014 and 2017, ISIS occupied the Iraqi city of Mosul.",
            "actors": ["Waleed Elgadi", "Hayat Kamille", "Thaer Al-Shayei"],
            "country": "USA",
            "income": 3420000,
            "duration": 101
        },
        {
            "titulo": "El secreto",
            "year": 2020,
            "rating": 2,
            "genre": "Drama",
            "description": "The Secret: Dare to Dream es una película de drama estadounidense de 2020 basada en el libro de autoayuda de 2006 The Secret de Rhonda Byrne.",
            "actors": ["Hayat Williams", "Sean Watson", "George Davidson"],
            "country": "USA",
            "income": 610000,
            "duration": 107
        }
    ])
```
> BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 2,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})
>
**Agregar películas usando insertOne()**
```js
	db.movies.insertOne({
        "titulo": "Voces",
        "year": 2020,
        "rating": 3,
        "genre": "Terror",
        "description": "Voces es una película española de terror sobrenatural de 2020 dirigida por Ángel Gómez Hernández, siendo este su primer largometraje.",
        "actors": ["Ana Fernandez Garcia", "Rodolfo Sancho", "Belen Fabra"],
        "country": "España",
        "income": 820000,
        "duration": 87
    })
```
> {
        "acknowledged" : true,
        "insertedId" : ObjectId("5fcab20693d77894add3854b")
}
>
**Agregar películas usando insertMany()**
```js
	db.movies.insertMany([
        {
            "titulo": "Rebecca2",
            "year": 2020,
            "rating": 5,
            "genre": "Misterio",
            "description": "Una joven recién casada llega a la imponente finca familiar de su marido y lucha contra la sombra de la primera esposa, Rebecca, cuyo legado perdura en la casa mucho después de su muerte.",
            "actors": ["Lily James", "Armie Hammer", "Sam Riley"],
            "country": "Reino Unido",
            "income": 8610000,
            "duration": 121
        },
        {
            "titulo": "Call2",
            "year": 2020,
            "rating": 5,
            "genre": "Suspenso",
            "description": "The Call, también conocida como Call, es una película de suspenso surcoreana de 2020 dirigida por Lee Chung-hyun, protagonizada por Park Shin-hye y Jeon Jong-seo.",
            "actors": ["Park Shin-hye", "Jeon Jong-seo", "Lee El"],
            "country": "Corea del Sur",
            "income": 10150000,
            "duration": 112
        }
    ])
```
> {
        "acknowledged" : true,
        "insertedIds" : [
                ObjectId("5fcab22993d77894add3854c"),
                ObjectId("5fcab22993d77894add3854d")
        ]
}
>
```js
	db.movies.insertMany([
        {
            "titulo": "Rebecca",
            "year": 1986,
            "rating": 5,
            "genre": "Misterio",
            "description": "Una joven recién casada llega a la imponente finca familiar de su marido y lucha contra la sombra de la primera esposa, Rebecca, cuyo legado perdura en la casa mucho después de su muerte.",
            "actors": ["Lily James", "Armie Hammer", "Sam Riley"],
            "country": "Reino Unido",
            "income": 8610000,
            "duration": 121
        },
        {
            "titulo": "Call",
            "year": 1980,
            "rating": 5,
            "genre": "Suspenso",
            "description": "The Call, también conocida como Call, es una película de suspenso surcoreana de 2020 dirigida por Lee Chung-hyun, protagonizada por Park Shin-hye y Jeon Jong-seo.",
            "actors": ["Park Shin-hye", "Jeon Jong-seo", "Lee El"],
            "country": "Corea del Sur",
            "income": 10150000,
            "duration": 112
        }
    ])
```
> {
        "acknowledged" : true,
        "insertedIds" : [
                ObjectId("5fcab24393d77894add3854e"),
                ObjectId("5fcab24393d77894add3854f")
        ]
}
>
**Actualizar películas agregando el field highlighted=true a aquellas con rating > 4.5.**
```js
    db.movies.updateMany(
        {"rating": {$gt: 4.5}},
        {
            $set: {
                "highlighted": true
            }
        }
    )
```
> { "acknowledged" : true, "matchedCount" : 4, "modifiedCount" : 4 }
>
**Actualizar películas cambiando el genre “drama” por “bored”.**
```js
    db.movies.updateMany(
        {"genre": "Drama"},
        {
            $set: {
                "genre": "Bored"
            }
        }
    )
```
> { "acknowledged" : true, "matchedCount" : 2, "modifiedCount" : 2 }
>
**Borrar todas las películas que tengan más de 30 años.**
```js
    db.movies.deleteMany(
        {"year": {$lt: 2020-30}}
    )
```
> { "acknowledged" : true, "deletedCount" : 2 }
>
**Buscar todas las películas argentinas.**
```js
    db.movies.find(
        {"country": "Argentina"}
    )
```
> 
>
**Buscar todas las películas surcoreanas.**
```js
    db.movies.find(
        {"country": "Corea del Sur"}
    )
```
> { "_id" : ObjectId("5fcab22993d77894add3854d"), "titulo" : "Call2", "year" : 2020, "rating" : 5, "genre" : "Suspenso", "description" : "The Call, también conocida como Call, es una película de suspenso surcoreana de 2020 dirigida por Lee Chung-hyun, protagonizada por Park Shin-hye y Jeon Jong-seo.", "actors" : [ "Park Shin-hye", "Jeon Jong-seo", "Lee El" ], "country" : "Corea del Sur", "income" : 10150000, "duration" : 112, "highlighted" : true }
>
**Buscar todas las películas de acción con un buen rating (ej. > 4.0) que hayan salido los últimos 2 años.**
```js
    db.movies.find(
        {
            "rating": {$gt: 4},
            "year": {$gte: 2020-2}
        }
    )
```
> { "_id" : ObjectId("5fcab22993d77894add3854c"), "titulo" : "Rebecca2", "year" : 2020, "rating" : 5, "genre" : "Misterio", "description" : "Una joven recién casada llega a la imponente finca familiar de su marido y lucha contra la sombra de la primera esposa, Rebecca, cuyo legado perdura en la casa mucho después de su muerte.", "actors" : [ "Lily James", "Armie Hammer", "Sam Riley" ], "country" : "Reino Unido", "income" : 8610000, "duration" : 121, "highlighted" : true }
>
> { "_id" : ObjectId("5fcab22993d77894add3854d"), "titulo" : "Call2", "year" : 2020, "rating" : 5, "genre" : "Suspenso", "description" : "The Call, también conocida como Call, es una película de suspenso surcoreana de 2020 dirigida por Lee Chung-hyun, protagonizada por Park Shin-hye y Jeon Jong-seo.", "actors" : [ "Park Shin-hye", "Jeon Jong-seo", "Lee El" ], "country" : "Corea del Sur", "income" : 10150000, "duration" : 112, "highlighted" : true }
>