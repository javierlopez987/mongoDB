# MongoDB
## Actividad 2
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
            "titulo": "La Juventud",
            "year": 2018,
            "rating": 3,
            "genre": "Romance",
            "country": "Italia",
            "income": 340000,
            "duration": 124
        },
        {
            "titulo": "Bienvenidos al Ayer",
            "year": 2018,
            "rating": 4.5,
            "genre": "Ciencia ficcion",
            "country": "USA",
            "income": 3300000,
            "duration": 106
        },
        {
            "titulo": "Abzurdah",
            "year": 2018,
            "rating": 5,
            "genre": "Drama",
            "country": "Argentina",
            "income": 600000,
            "duration": 90
        },
        {
            "titulo": "Mas notas perfectas",
            "year": 2018,
            "rating": 2,
            "genre": "Comedia",
            "country": "USA",
            "income": 50000,
            "duration": 115
        },
        {
            "titulo": "Mar abierto",
            "year": 2003,
            "rating": 3,
            "genre": "Comedia",
            "country": "USA",
            "income": 50000,
            "duration": 115
        },
        {
            "titulo": "Titanic",
            "year": 1997,
            "rating": 5,
            "genre": "Drama",
            "country": "USA",
            "income": 200000000,
            "duration": 210
        },
                {
            "titulo": "La estafa maestra",
            "year": 2003,
            "rating": 4,
            "genre": "Accion",
            "country": "USA",
            "income": 36900000,
            "duration": 111
        }
    ])
```
```js
    db.movies.insert ([
       {
            "titulo": "La vida es bella",
            "year": 1997,
            "rating": 5,
            "genre": "Romance",
            "country": "Italia",
            "income": 34000000,
            "duration": 122
        },
        {
            "titulo": "La cabaña",
            "year": 2017,
            "rating": 3.5,
            "genre": "Fantasia",
            "country": "USA",
            "income": 4500000,
        },
        {
            "titulo": "Conectados",
            "year": 2017,
            "rating": 4.5,
            "genre": "Drama",
            "country": "USA",
            "income": 61000000,
            "duration": 95
        }
    ])
```
**Listar todas las películas del año 2018.**
```js
    db.movies.find({"year": 2018})
```
>{ "_id" : ObjectId("5fcac0bc93d77894add38550"), "titulo" : "La Juventud", "year" : 2018, "rating" : 3, "genre" : "Romance", "country" : "Italia", "income" : 340000, "duration" : 124 }
>
> { "_id" : ObjectId("5fcac0bc93d77894add38551"), "titulo" : "Bienvenidos al Ayer", "year" : 2018, "rating" : 4.5, "genre" : "Ciencia ficcion", "country" : "USA", "income" : 3300000, "duration" : 106 }   
>
> { "_id" : ObjectId("5fcac0bc93d77894add38552"), "titulo" : "Abzurdah", "year" : 2018, "rating" : 5, "genre" : "Drama", "country" : "Argentina", "income" : 600000, "duration" : 90 }
>
> { "_id" : ObjectId("5fcac0bc93d77894add38553"), "titulo" : "Mas notas perfectas", "year" : 2018, "rating" : 2, "genre" : "Comedia", "country" : "USA", "income" : 50000, "duration" : 115 }
>

**Listar las 10 primeras películas de Hollywood (USA).**
```js
    db.movies.find({"country": "USA"}).limit(10)
```
> { "_id" : ObjectId("5fcab1fc93d77894add38549"), "titulo" : "Mosul", "year" : 2020, "rating" : 4, "genre" : "Bored", "description" : "Between 2014 and 2017, ISIS occupied the Iraqi city of Mosul.", "actors" : [ "Waleed Elgadi", "Hayat Kamille", "Thaer Al-Shayei" ], "country" : "USA", "income" : 3420000, "duration" : 101 }
>
> { "_id" : ObjectId("5fcab1fc93d77894add3854a"), "titulo" : "El secreto", "year" : 2020, "rating" : 2, "genre" : "Bored", "description" : "The Secret: Dare to Dream es una película de drama estadounidense de 2020 basada en el libro de autoayuda de 2006 The Secret de Rhonda Byrne.", "actors" : [ "Hayat Williams", "Sean Watson", "George Davidson" ], "country" : "USA", "income" : 610000, "duration" : 107 }   
>
> { "_id" : ObjectId("5fcac0bc93d77894add38551"), "titulo" : "Bienvenidos al Ayer", "year" : 2018, "rating" : 4.5, "genre" : "Ciencia ficcion", "country" : "USA", "income" : 3300000, "duration" : 106 }     
>
> { "_id" : ObjectId("5fcac0bc93d77894add38553"), "titulo" : "Mas notas perfectas", "year" : 2018, "rating" : 2, "genre" : "Comedia", "country" : "USA", "income" : 50000, "duration" : 115 }
>
> { "_id" : ObjectId("5fcac0bc93d77894add38554"), "titulo" : "Mar abierto", "year" : 2003, "rating" : 3, "genre" : "Comedia", "country" : "USA", "income" : 50000, "duration" : 115 }
>
> { "_id" : ObjectId("5fcac0bc93d77894add38555"), "titulo" : "Titanic", "year" : 1997, "rating" : 5, "genre" : "Drama", "country" : "USA", "income" : 200000000, "duration" : 210 }
>
> { "_id" : ObjectId("5fcac0bc93d77894add38556"), "titulo" : "La estafa maestra", "year" : 2003, "rating" : 4, "genre" : "Accion", "country" : "USA", "income" : 36900000, "duration" : 111 }
>
> { "_id" : ObjectId("5fcac1e193d77894add38558"), "titulo" : "La cabaña", "year" : 2017, "rating" : 3.5, "genre" : "Fantasia", "country" : "USA", "income" : 4500000 }
>
> { "_id" : ObjectId("5fcac1e193d77894add38559"), "titulo" : "Conectados", "year" : 2017, "rating" : 4.5, "genre" : "Drama", "country" : "USA", "income" : 61000000, "duration" : 95 }
>
**Listar las 5 películas más taquilleras.**
```js
    db.movies.find({}).limit(5).sort(
        { "income": -1 }
    )
```
> { "_id" : ObjectId("5fcac0bc93d77894add38555"), "titulo" : "Titanic", "year" : 1997, "rating" : 5, "genre" : "Drama", "country" : "USA", "income" : 200000000, "duration" : 210 }
>
> { "_id" : ObjectId("5fcac1e193d77894add38559"), "titulo" : "Conectados", "year" : 2017, "rating" : 4.5, "genre" : "Drama", "country" : "USA", "income" : 61000000, "duration" : 95 }
>
> { "_id" : ObjectId("5fcac0bc93d77894add38556"), "titulo" : "La estafa maestra", "year" : 2003, "rating" : 4, "genre" : "Accion", "country" : "USA", "income" : 36900000, "duration" : 111 }
>
> { "_id" : ObjectId("5fcac1e193d77894add38557"), "titulo" : "La vida es bella", "year" : 1997, "rating" : 5, "genre" : "Romance", "country" : "Italia", "income" : 34000000, "duration" : 122 }
>
> { "_id" : ObjectId("5fcab22993d77894add3854d"), "titulo" : "Call2", "year" : 2020, "rating" : 5, "genre" : "Suspenso", "description" : "The Call, también conocida como Call, es una película de suspenso surcoreana de 2020 dirigida por Lee Chung-hyun, protagonizada por Park Shin-hye y Jeon Jong-seo.", "actors" : [ "Park Shin-hye", "Jeon Jong-seo", "Lee El" ], "country" : "Corea del Sur", "income" : 10150000, "duration" : 112, "highlighted" : true }
>
**Listar el 2do conjunto de 5 películas más taquilleras.**
```js
    db.movies.find({}).skip(5).limit(5).sort(
        { "income": -1 }
    )
```
> { "_id" : ObjectId("5fcab22993d77894add3854c"), "titulo" : "Rebecca2", "year" : 2020, "rating" : 5, "genre" : "Misterio", "description" : "Una joven recién casada llega a la imponente finca familiar de su marido y lucha contra la sombra de la primera esposa, Rebecca, cuyo legado perdura en la casa mucho después de su muerte.", "actors" : [ "Lily James", "Armie Hammer", "Sam Riley" ], "country" : "Reino Unido", "income" : 8610000, "duration" : 121, "highlighted" : true }
>
> { "_id" : ObjectId("5fcac1e193d77894add38558"), "titulo" : "La cabaña", "year" : 2017, "rating" : 3.5, "genre" : "Fantasia", "country" : "USA", "income" : 4500000 }
>
> { "_id" : ObjectId("5fcab1fc93d77894add38549"), "titulo" : "Mosul", "year" : 2020, "rating" : 4, "genre" : "Bored", "description" : "Between 2014 and 2017, ISIS occupied the Iraqi city of Mosul.", "actors" : [ "Waleed Elgadi", "Hayat Kamille", "Thaer Al-Shayei" ], "country" : "USA", "income" : 3420000, "duration" : 101 }
>
> { "_id" : ObjectId("5fcac0bc93d77894add38551"), "titulo" : "Bienvenidos al Ayer", "year" : 2018, "rating" : 4.5, "genre" : "Ciencia ficcion", "country" : "USA", "income" : 3300000, "duration" : 106 }  
>
> { "_id" : ObjectId("5fcab20693d77894add3854b"), "titulo" : "Voces", "year" : 2020, "rating" : 3, "genre" : "Terror", "description" : "Voces es una película española de terror sobrenatural de 2020 dirigida por Ángel Gómez Hernández, siendo este su primer largometraje.", "actors" : [ "Ana Fernandez Garcia", "Rodolfo Sancho", "Belen Fabra" ], "country" : "España", "income" : 820000, "duration" : 87 } 
>
**Repetir query 3 y 4 pero retornando sólo el título y genre.**
```js
    db.movies.find(
        {"country": "USA"}, 
        {"titulo": 1, "genre": 1, "_id": 0}
    ).limit(10)
```
> { "titulo" : "Mosul", "genre" : "Bored" }
>
> { "titulo" : "El secreto", "genre" : "Bored" }
>
> { "titulo" : "Bienvenidos al Ayer", "genre" : "Ciencia ficcion" }
>
> { "titulo" : "Mas notas perfectas", "genre" : "Comedia" }
>
> { "titulo" : "Mar abierto", "genre" : "Comedia" }
>
> { "titulo" : "Titanic", "genre" : "Drama" }
>
> { "titulo" : "La estafa maestra", "genre" : "Accion" }
>
> { "titulo" : "La cabaña", "genre" : "Fantasia" }
>
> { "titulo" : "Conectados", "genre" : "Drama" }
>
```js
    db.movies.find({},
        {"titulo": 1, "genre": 1, "_id": 0}
    ).limit(5).sort(
        { "income": -1 }
    )
```
> { "titulo" : "Titanic", "genre" : "Drama" }
>
> { "titulo" : "Conectados", "genre" : "Drama" }
>
> { "titulo" : "La estafa maestra", "genre" : "Accion" }
>
> { "titulo" : "La vida es bella", "genre" : "Romance" }
>
> { "titulo" : "Call2", "genre" : "Suspenso" }
**Mostrar los distintos países que existen en la base de datos.**
```js
    db.movies.distinct("country")
```
> [
        "Argentina",
        "Corea del Sur",
        "España",
        "Italia",
        "Reino Unido",
        "USA"
]
>