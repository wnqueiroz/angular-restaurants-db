# Base de dados da aplicação [MEAT](https://angular-restaurants.herokuapp.com/) com `json-server` no **Heroku** 

* [Deploy no **Heroku**](#deploy-no-heroku)
* [Instalando e configurando **Heroku**](#instalando-e-configurando-o-heroku)
* [Como funciona?](#como-funciona)


## Deploy no **Heroku**

<img align="right" width="100px" height="auto" src="https://cdn.worldvectorlogo.com/logos/heroku.svg" alt="Heroku">

Heroku é um serviço de hosting gratuito (até certo ponto hehe) para hospedar pequenos projetos.

###### Prós:

* Fácil configuração
* Gratuito

###### Contras:

* A aplicação, caso não acessada, "dorme" durante 1 hora, todos os dias.
* As aplicações são "derrubadas" durante 30 minutos. Caso acessada, ela "sobe" porém leva uns segundos extras. Isso pode ser resolvido com essa aplicação: [**Kaffeine**](http://kaffeine.herokuapp.com/)

---

### Instalando e Configurando o Heroku

1 . Crie um conta em: [https://heroku.com](https://heroku.com)

2 . Instale o Heroku CLI no seu computador: <br/>[https://devcenter.heroku.com/articles/heroku-cli](https://devcenter.heroku.com/articles/heroku-cli)

3 . Logue-se no Heroku CLI com sua conta, escreva os seguintes comandos no terminal e siga as instruções nas linhas de comando:
```bash
heroku login
```
4 . Em seguida crie o seu projeto no heroku, é como criar um repositório no GitHub. Isso vai criar um projeto com um nome aleatório no Heroku. Caso queira um nome específico para o projeto, utilize algo como `heroku create project-name`:
```bash
heroku create my-cool-project
```

5 . Suba seu projeto para o __Heroku__ 
```bash
git push heroku master
```

6 . Você pode acessá-lo com o comando:
```bash
heroku open
```

7 . Para verificar os logs de erro:
```bash
heroku logs --tail
```

---

### Como funciona?

O Heroku procurará o script de inicialização, por padrão `npm start` então, certifique-se que tenha o seguinte trecho em seu `package.json` (supondo que o script execute `server.js`):
```json
 "scripts": {
    "start" : "node server.js"
 }
```

Você também precisa fazer alterações na porta, você não pode codificar um dev-port. Mas você pode fazer referência a porta do heroku. Então, o código ficará assim:
```js
const port = process.env.PORT || 4000;
```
