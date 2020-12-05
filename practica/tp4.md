# MongoDB
## Actividad 4
**Conectarse a MongoDB vía CLI**
```js
	mongod
	mongo
```
> MongoDB shell
>
**Utilizar la misma base de datos de películas**
```js
	show dbs
	use streaming
    show collections
```
> movies
>
**Insertar varias películas con distinto contenido.**
```js
    db.movies.insert ([
       {
            "titulo": "Forrest Gump",
            "year": 1994,
            "rating": 5,
            "genre": "Drama",
            "country": "USA",
            "income": 95000000,
            "duration": 142
        },
        {
            "titulo": "Inocencia interrumpida",
            "year": 1999,
            "rating": 4.5,
            "genre": "Drama",
            "country": "USA",
            "income": 33000000,
            "duration": 127
        },
        {
            "titulo": "Linea mortal",
            "year": 1990,
            "rating": 3.5,
            "genre": "Terror",
            "country": "USA",
            "income": 700000,
            "duration": 115
        },
        {
            "titulo": "El ultimo gran heroe",
            "year": 1993,
            "rating": 4,
            "genre": "Accion",
            "country": "USA",
            "income": 5000000,
            "duration": 131
        },
        {
            "titulo": "Jurassic Park 3D",
            "year": 1993,
            "rating": 4.5,
            "genre": "Aventura",
            "country": "USA",
            "income": 75000000,
            "duration": 128
        },
        {
            "titulo": "El aura",
            "year": 1993,
            "rating": 2.5,
            "genre": "Suspenso",
            "country": "Argentina",
            "income": 20000,
            "duration": 138
        },
        {
            "titulo": "La furia",
            "year": 1997,
            "rating": 3,
            "genre": "Drama",
            "country": "Argentina",
            "income": 30000,
            "duration": 105
        },
        {
            "titulo": "Nueve Reinas",
            "year": 2000,
            "rating": 5,
            "genre": "Suspenso",
            "country": "Argentina",
            "income": 300000,
            "duration": 115
        },
        {
            "titulo": "El secreto de sus ojos",
            "year": 2009,
            "rating": 4.5,
            "genre": "Suspenso",
            "country": "Argentina",
            "income": 250000,
            "duration": 129
        },
        {
            "titulo": "Plata quemada",
            "year": 2000,
            "rating": 2,
            "genre": "Suspenso",
            "country": "Argentina",
            "income": 15000,
            "duration": 125
        },
        {
            "titulo": "El abrazo partido",
            "year": 2004,
            "rating": 1,
            "genre": "Drama",
            "country": "Argentina",
            "income": 1000,
            "duration": 100
        },
        {
            "titulo": "Valentin",
            "year": 2002,
            "rating": 1.5,
            "genre": "Drama",
            "country": "Argentina",
            "income": 3000,
            "duration": 86
        },
        {
            "titulo": "Flubber",
            "year": 1997,
            "rating": 3.5,
            "genre": "Infantil",
            "country": "USA",
            "income": 300000,
            "duration": 94
        },
        {
            "titulo": "Los locos adams",
            "year": 1991,
            "rating": 4,
            "genre": "Infantil",
            "country": "USA",
            "income": 350000,
            "duration": 110
        },
        {
            "titulo": "El divo",
            "year": 2008,
            "rating": 3,
            "genre": "Drama",
            "country": "Italia",
            "income": 35000,
            "duration": 118
        },
        {
            "titulo": "Exterminio",
            "year": 2002,
            "rating": 2.5,
            "genre": "Terror",
            "country": "Italia",
            "income": 30000,
            "duration": 113
        },
        {
            "titulo": "Bajo el sol de Toscana",
            "year": 2003,
            "rating": 3.5,
            "genre": "Romance",
            "country": "Italia",
            "income": 50000,
            "duration": 113
        },
        {
            "titulo": "El huesped",
            "year": 2006,
            "rating": 2.5,
            "genre": "Terror",
            "country": "Corea del Sur",
            "income": 5000,
            "duration": 121
        },
        {
            "titulo": "Thrist",
            "year": 2009,
            "rating": 3.5,
            "genre": "Terror",
            "country": "Corea del Sur",
            "income": 50000,
            "duration": 148
        }
    ])
```
**Crear índice en field rating y luego hacer búsquedas usando este campo.**
```js
    db.movies.createIndex({"rating": 1})
```
> {
        "createdCollectionAutomatically" : false,
        "numIndexesBefore" : 1,
        "numIndexesAfter" : 2,
        "ok" : 1
}
>
```js
    db.movies.find({"rating": 5})
```
> { "_id" : ObjectId("5fcab22993d77894add3854c"), "titulo" : "Rebecca2", "year" : 2020, "rating" : 5, "genre" : "Misterio", "description" : "Una joven recién casada llega a la imponente finca familiar de su marido y lucha contra la sombra de la primera esposa, Rebecca, cuyo legado perdura en la casa mucho después de su muerte.", "actors" : [ "Lily James", "Armie Hammer", "Sam Riley" ], "country" : "Reino Unido", "income" : 8610000, "duration" : 121, "highlighted" : true }
>
> { "_id" : ObjectId("5fcab22993d77894add3854d"), "titulo" : "Call2", "year" : 2020, "rating" : 5, "genre" : "Suspenso", "description" : "The Call, también conocida como Call, es una película de suspenso surcoreana de 2020 dirigida por Lee Chung-hyun, protagonizada por Park Shin-hye y Jeon Jong-seo.", "actors" : [ "Park Shin-hye", "Jeon Jong-seo", "Lee El" ], "country" : "Corea del Sur", "income" : 10150000, "duration" : 112, "highlighted" : true }
>
> { "_id" : ObjectId("5fcac0bc93d77894add38552"), "titulo" : "Abzurdah", "year" : 2018, "rating" : 5, "genre" : "Drama", "country" : "Argentina", "income" : 600000, "duration" : 90 }
>
> { "_id" : ObjectId("5fcac0bc93d77894add38555"), "titulo" : "Titanic", "year" : 1997, "rating" : 5, "genre" : "Drama", "country" : "USA", "income" : 200000000, "duration" : 210 }
>
> { "_id" : ObjectId("5fcac1e193d77894add38557"), "titulo" : "La vida es bella", "year" : 1997, "rating" : 5, "genre" : "Romance", "country" : "Italia", "income" : 34000000, "duration" : 122 }
>
> { "_id" : ObjectId("5fcacdd9ee361b6a6f454e55"), "titulo" : "Forrest Gump", "year" : 1994, "rating" : 5, "genre" : "Drama", "country" : "USA", "income" : 95000000, "duration" : 142 }
>
> { "_id" : ObjectId("5fcacdd9ee361b6a6f454e5c"), "titulo" : "Nueve Reinas", "year" : 2000, "rating" : 5, "genre" : "Suspenso", "country" : "Argentina", "income" : 300000, "duration" : 115 }
>
**Crear índice en title y description, y después hacer búsquedas de texto en estos campos.**
```js
    db.movies.createIndex({
        "titulo": "text",
        "description": "text"
    })
```
> {
        "createdCollectionAutomatically" : false,
        "numIndexesBefore" : 2,
        "numIndexesAfter" : 3,
        "ok" : 1
}
>
```js
    db.movies.find(
        {
            $text: { $search: "bella" }
        }
    )
```
> { "_id" : ObjectId("5fcac1e193d77894add38557"), "titulo" : "La vida es bella", "year" : 1997, "rating" : 5, "genre" : "Romance", "country" : "Italia", "income" : 34000000, "duration" : 122 }
>
