<h1 align="center" display="flex" flexDirection="column">
  <img alt="GoBarber" title="GoBarber" src="https://play-lh.googleusercontent.com/KXeyZCwYdhmXATiNH5UzwkweYesVpsGacL6PQEddho5jOsbu1fX-PFvXtJwKrRQ3TdU" width="112px" />
</h1>

<span align="center">
  Trata-se de uma aplicação back-end densevolvida com NodeJs afim de gerenciar agendamentos de serviços prestados por barbearias.
</span>

# Instruções para executar a aplicação.

Faça o download do repositório e siga as instruções:

## Ambiente 

Este procedimento foi testado usando o Windows 10.

Para criação das bases de dados foi utilizado o docker. No ternal, rode os seguintes comandos: 

```
  docker run --name goBarberDataBase -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres
```

Após está conectado ao goBarberDataBase, crie uma base de dados com nome gobarber.

Agora vamos criar a base redis para tarefas de envio de emails:

```
  docker run --name redisBarber -p 6379:6379 -d -t redis:alpine 
```

Agora vamos criar a base mongoDb para lidar com mensagens de notificação:

```
  docker run --name mongoBarber -p 27017:27017 -d -t mongo
```

## Backend

duplique o arquivo .env.example que se encontra na raiz da pasta backend, salve com o nome .env e preencha as variáveis de acordo com a configuração utilizada na preparaçÃo do ambiente.

utilizando o terminal acesse a pasta backend e rode o seguinte comando para instalar as dependências do projeto.

```
  yarn
```
Para criação das tabelas utilize o comando:

```
yarn sequelize db:migrate
```

Todo pronto, é hora de subir o servidor: rode o seguinte comando na raiz da pasta backend:
```
yarn dev
```

Agora vamos subir o servidor responsável pelo gerenciamento de filas de envio de emails. Abra uma nova janela do terminal e na raiz da pasta backend rode:

```
yarn queue
```

<h3 align="center">Se todos os passos foram seguidos corretamente, o servidor já deve está funcionando.</h3>

### tecnologias aprendidas e aplicadas

- Node
- Express
- Sequelize
- Docker
- Redis
- Bequeue
- MongoDb
- Mongoose
- Nodemailer
- Handlebars
- Eslint
- Prettier
- Nodemon
- Date-fns

## Backend

https://github.com/JRCouto4D/Bootcamp-api_GoBarber

## Mobile

https://github.com/JRCouto4D/BootCamp-GoBarber_mobile
