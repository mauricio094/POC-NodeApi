# POC-NodeApi
Poc de estudos de uma API com Node e GraphQL
* Node
* Hapi
* MongoDb
* GraphQL
* Swagger

# Iniciando
para baixar as dependencias do projeto utilizar o comando
```
npm install
```
Logo em seguida subir o projeto com o comando
```
npm run start
```
## Utilizando os Endpoints Rest
Existem alguns endpoints rests para utizar sendo eles:
* GET /api/v1/paintings - Retorna todas as pinturas 
* GET /api/v1/paintings/{id} - Retorna apenas a pintura do ID correspondente
* POST /api/v1/paintings - salva uma nova pintura, passando o payload corretamente, Exemplo:
```
{
  "name": "Mona Lisa",
  "url": "https://en.wikipedia.org/wiki/Mona_Lisa#/media/File:Mona_Lisa,_by_Leonardo_da_Vinci,_from_C2RMF_retouched.jpg",
  "techniques": "Portrait"
}
```
é possivel acessar o Swaagger atrevés do endpoint /documentation

## Trabalhando com o GraphQL
GraphQL nos permite trabalharmos apenas com a informação que realmente desejamos, sendo um diferencial se comparado ao rest que não nós permite trabalhar assim, consequentemente sempre temos um response com diversas informações que nem sempre serão necessárias, já com GraphQL podemos passar na query qual informação iremos utilizar, para evitar recebermos informações a mais.

query de exemplo:
```
{
  painting(id:"5b09bfd602a5e247ab203641"){
    name,url
  }
}
```
response de exemplo:
```
{
  "data": {
    "painting": {
      "name": "Mona Lisa",
      "url": "https://en.wikipedia.org/wiki/Mona_Lisa#/media/File:Mona_Lisa,_by_Leonardo_da_Vinci,_from_C2RMF_retouched.jpg"
    }
  }
}
```

através do endpoint /graphiql é possivel acessar uma IDE para trabalharmos com algumas querys de GraphQL que inclusive ja tem uma documentação.




