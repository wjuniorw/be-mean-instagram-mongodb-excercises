# MongoDB - Aula 01 - Exercício
autor: Marco Tanaka

## Importando os restaurantes

```
$ mongoimport --db be-mean --collection restaurantes --host=127.0.0.1 --drop --file ~/Downloads/restaurantes.json
2015-11-14T01:04:54.547-0200    connected to: 127.0.0.1
2015-11-14T01:04:54.548-0200    dropping: be-mean.restaurantes
2015-11-14T01:04:57.268-0200    imported 25359 documents
```

## Contando os restaurantes

```
> use be-mean
switched to db be-mean
> db.restaurantes.find({}).count()
25359
```
