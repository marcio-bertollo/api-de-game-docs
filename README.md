# API de Games
Esta API é utilizada para cadastrar Games.
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parâmetros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.

Exemplo de resposta:
```
  [
    {
      "id": 5,
      "title": "GTA V",
      "year": 2013,
      "price": "80.00",
      "createdAt": "2021-06-10T00:26:53.000Z",
      "updatedAt": "2021-06-10T00:26:53.000Z"
    },
    {
      "id": 6,
      "title": "FIFA",
      "year": 2020,
      "price": "120.00",
      "createdAt": "2021-06-10T00:40:11.000Z",
      "updatedAt": "2021-06-10T01:23:08.000Z"
    },
    {
      "id": 7,
      "title": "PES",
      "year": 2022,
      "price": "200.00",
      "createdAt": "2021-06-10T00:40:31.000Z",
      "updatedAt": "2021-06-10T00:40:31.000Z"
    }
  ]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado.

Exemplo de resposta:
```
{
  "err": "Token inválido!"
}
```

### POST /auth
Esse endpoint é responsável por fazer o processo de login.
#### Parâmetros
email: E-mail do usuário cadastrado no sistema.

password: Senha do usuário cadastrado no sistema.

Exemplo:
```
  {
    "email": "user@user.com",
    "password": "123"
  }
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de resposta:
```
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MiwiZW1haWwiOiJtb25hbGl6YWRhbGxhYnJpZGFAZ21haWwuY29tIiwiaWF0IjoxNjIzNzk4MTU1LCJleHAiOjE2MjM4ODQ1NTV9.EdtEorgum_iZcCYlKaeRAqSYhggKzghVCjysRZHXpNE"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou e-mail incorretos.

Exemplo de resposta:
```
{
  "err": "Credenciais inválidas!"
}
```
