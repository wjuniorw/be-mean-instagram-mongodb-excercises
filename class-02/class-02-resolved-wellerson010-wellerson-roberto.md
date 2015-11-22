# MongoDB - Aula 02 - Exerc�cio
autor: Wellerson Roberto

## Listagem das databases (passo 2)
```
> show dbs
be-mean           0.078GB
be-mean-pokemons  0.078GB
local             0.078GB
outcost           0.078GB
test              0.078GB
```

## Listagem das cole��es (passo 3)
```
> show collections
pokemons
system.indexes
```

## Cadastro dos pokemons (passo 4)
```
> db.pokemons.insert([{name: "Ivysaur",description: "Um pokemon com uma rosa em cima, bem viad�o", attack: 62, defense: 63, height: 10 },{name: "Poliwag",description: "Um pokemon loc�o com uma parada no meio da barriga, dahora mesmo", attack: 50, defense: 40, height: 6 },{name: "Girafarig",description: "Um pokemon que � uma girafa com outra parada a�", attack: 80, defense: 65, height: 15 },{name: "Linoone",description: "Parece um roedor...", attack: 70, defense: 61, height: 5 },{name: "Bibarel",description: "Biba...rel", attack: 85, defense: 60, height: 10 }]);
BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 5,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})
```

## Lista dos pokemons (passo 5)
```
> db.pokemons.find({})
{ "_id" : ObjectId("5643c6cf5da32f5fba3bf442"), "name" : "Ivysaur", "description" : "Um pokemon com uma rosa em cima, bem viad�o", "attack" : 62, "defense" : 63, "height" : 10 }
{ "_id" : ObjectId("5643c6cf5da32f5fba3bf443"), "name" : "Poliwag", "description" : "Um pokemon loc�o com uma parada no meio da barriga, dahora mesmo", "attack" : 50, "defense" : 40, "height" : 6 }
{ "_id" : ObjectId("5643c6cf5da32f5fba3bf444"), "name" : "Girafarig", "description" : "Um pokemon que � uma girafa com outra parada a�", "attack" : 80, "defense" : 65, "height" : 15 }
{ "_id" : ObjectId("5643c6cf5da32f5fba3bf445"), "name" : "Linoone", "description" : "Parece um roedor...", "attack" : 70, "defense" : 61, "height" : 5 }
{ "_id" : ObjectId("5643c6cf5da32f5fba3bf446"), "name" : "Bibarel", "description" : "Biba...rel", "attack" : 85, "defense" : 60, "height" : 10 }
```

## Atualiza��o do Pikachu (passo 6)
```
> var poke = db.pokemons.findOne({name: "Poliwag"});
> poke.description = "Mudei por que sim e acabou"
Mudei por que sim e acabou
> db.pokemons.save(poke)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
```