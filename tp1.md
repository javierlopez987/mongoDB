# MongoDB
## Actividad1

mongod

mongo

show dbs

use futbolfifa

show collections

db.createCollection("players")

db.players.insert(
	{
		name: "Pablo",
		lastname: "Ramirez",
		position: "goalkeeper"
	}
)

db.players.find()
{ "_id" : ObjectId("5f8814ca4e09cb0bcfa4341e"), "name" : "Pablo", "lastname" : "Ramirez", "position" : "goalkeeper" }

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
BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 4,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})

db.players.find()
{ "_id" : ObjectId("5f8814ca4e09cb0bcfa4341e"), "name" : "Pablo", "lastname" : "Ramirez", "position" : "goalkeeper" }
{ "_id" : ObjectId("5f881d2a05a041237b99bdba"), "name" : "Pedro", "lastname" : "Marmol", "position" : "center back" }
{ "_id" : ObjectId("5f881d2a05a041237b99bdbb"), "name" : "Sebastian", "lastname" : "Granito", "position" : "central" }
{ "_id" : ObjectId("5f881d2a05a041237b99bdbc"), "name" : "Leonardo", "lastname" : "Caliza", "position" : "striker" }
{ "_id" : ObjectId("5f881d2a05a041237b99bdbd"), "name" : "Joaquin", "lastname" : "Cuarcita", "position" : "winger" }

db.createCollection("teams")
{ "ok" : 1 }

db.createCollection("matches")
{ "ok" : 1 }

show collections
matches
players
teams