# dio-geekapi

<h2>Projeto Dio Portifólio: Aplicação básica de uma API REST com Spring Boot para o gerenciamento de pessoas GEEKs</h2>

Nessa aplicação podemos cadastrar um GEEK com seus jogos, heróis e filmes prediletos através de uma API REST, criada com o Spring Boot.

A aplicação roda o schema.sql toda vez na inicialização somente para facilitar qualquer teste. Foi feito um deploy local com h2 e com postgres. Outro deploy completo na Heroku com postgres.

Sessão aberta na heroku:

```
https://dio-geekapi.herokuapp.com/api/v1/geek
```


Conceitos utilizados:

* Criação de modelo de dados para o mapeamento de entidades em bancos de dados.
* Desenvolvimento de operações de gerenciamento (Cadastro, leitura, atualização e remoção).
* Relação de cada uma das operações acima com o padrão arquitetural REST.

Segue um json modelo para inclusão:

<h3>Exemplo método POST para criar</h3>

```
{
    "geekName": "olaf_tnt",
    "realName": "Olaf",
    "favoriteGame": [
        {
            "name": "Fortnite",
            "gameStyle" : "FREEFIRE",
            "price": 480.00
        }
    ],
    "favoriteSuperHero": [
        {
            "name": "IronMan"
        },
        {
            "name": "Hulk"
        }
    ],
    "favoriteFilm" : [
        {
            "name": "Matrix"
        },
        {
            "name": "StarTrek"
        }
    ],
    "hasGlasses": "true",
    "favoriteLanguage": "JAVA",
    "birthDate": "30-03-1910",
    "email": "geek@gmail.com"
}
```

<h3>Exemplo método GET</h3>

* Busca todos
```
https://dio-geekapi.herokuapp.com/api/v1/geek
```

* Busca por Id
```
https://dio-geekapi.herokuapp.com/api/v1/geek/{id}
```

* Busca versão do app
```
https://dio-geekapi.herokuapp.com/api/v1/geek/about
```


<h3>Exemplo método PUT para atualizar</h3>

```
{    
    "id": 1,
    "geekName": "olaf_tnt",
    "realName": "Olaf",
    "favoriteGame": [
        {
            "id": 1,
            "name": "Fortnite",
            "gameStyle" : "FREEFIRE",
            "price": 480.00
        },
        {
            "id":2,
            "name": "Call Of Duty",
            "gameStyle" : "FREEFIRE",
            "price": 550.00
        }
    ],
    "favoriteSuperHero": [
        {
            "id": 1,
            "name": "IronMan"
        },
        {
            "id": 2,
            "name": "Hulk"
        }
    ],
    "favoriteFilm" : [
        {
            "id": 1,
            "name": "Matrix"
        },
        {
            "id": 2,
            "name": "StarWars"
        }
    ],
    "hasGlasses": "true",
    "favoriteLanguage": "JAVA",
    "birthDate": "25-03-1910",
    "email": "olaf@gmail.com"
}
```

<h3>Exemplo método DELETE</h3>

* Delete por Id
```
https://dio-geekapi.herokuapp.com/api/v1/geek/{id}
```


Versões e ferramentas usados no projeto:

* Java 11.0.11
* Maven 3.8.1
* Spring Boot 2.5.4
* Intellj IDEA Community Edition.
* Postgre 13.4
* Heroku para o deploy.