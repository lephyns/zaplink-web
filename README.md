# Sumário 📚

- [**O projeto**](#o-projeto)
- [**Comandos**](#comandos)
  - [**Para utilizar a aplicação pela web**](#para-utilizar-a-aplicacao-pela-web)
  - [**Para executar os testes automatizados do front com o Cypress**](#para-executar-os-testes-automatizados-do-front-com-cypress)
  - [**Para executar os testes unitários do backend**](#para-executar-os-testes-unitarios-do-backend)
  - [**Para acessar o relatório de testes unitários do Mocha**](#para-acessar-o-relatorio-de-testes-unitarios-do-mocha)
- [**Dependêcias**](#dependencias)
  - [**Frontend**](#frontend)
  - [**Backend**](#backend)
- [**Observações**](#observacoes)
  - [**Pastas e arquivos**](#pastas-e-arquivos)
- [**Desenvolvimento do projeto**](#desenvolvimento-do-projeto)
  - [**Processo para criação do front**](#processo-para-criacao-do-front)
    - [**Vue**](#vue)
    - [**Core-js**](#core-js)
    - [**vue-router**](#vue-router)
    - [**vue/cli-plugin-babel**](#vue-cli-plugin-babel)
    - [**vue/cli-plugin-e2e-cypress**](#vue-cli-plugin-e2e-cypress)
    - [**vue/cli-plugin-router**](#vue-cli-plugin-router)
    - [**vue/cli-service**](#vue-cli-service)
    - [**vue-template-compiler**](#vue-template-compiler)
    - [**Buefy**](#buefy)
    - [**Axios**](#axios)
    - [**Mocha**](#mocha)
      - [**Mochawesome**](#mochawesome)
      - [**Mochawesome-merge**](#mochawesome-merge)
  - [**Processo para criação do backend**](#processo-para-criacao-do-backend)
    - [**Nodemon**](#nodemon)
    - [**Hapi**](#hapi)
      - [**hapi/hapi**](#hapi-hapi)
      - [**hapi/code**](#hapi-code)
      - [**hapi/lab**](#hapi-lab)
    - [**Mongoose**](#mongoose)
    - [**md5**](#md5)
  - [**Criar um banco de dados no MongoDB**](#criar-um-banco-de-dados-no-mongodb)

# O projeto ✨

Este aplicativo foi criado para suprir a necessidade do usuário que faz negociações de produtos com vários fornecedores. Ao cadastrar um contato o usuário poderá adicionar um assunto para que seja fácil identificar o que está sendo cotado. Os cards dos contatos possuem a funcionalidade de conversar (a qual redireciona o usuário para conversar com o fornecedor) e apagar (caso o usuário deseja apagar o contato criado).<br>

Foi desenvolvido o front com o framework Vue.js para as telas de login e dashboard. Também foi desenvolvido o backend da API que faz GET, POST e DELETE para as requisições do usuário. Implementado a autenticação para que cada usuário possa ter acesso ao seu próprio dashboard.<br>
Para salvar os registros da aplicação foi utilizado o banco de dados MongoDB.<br>
Para automatizar os testes do front foi utilizado o framework Cypress e para executar os testes unitários do backend foi utilizado o framework Hapi.dev e como o relatório é gerado pelo próprio terminal adicionamos o report do mocha o qual é muito mais amigável e que ficará salvo no nosso projeto ao invés de estar no terminal como é o caso do Hapi.dev.

# Comandos 🧙‍♂️

Abaixo descrevo os comandos que podem ser utilizados para:

* Acessar a aplicação pela web (Chrome, Edge, Firefox, etc);
* Executar os testes automatizados do front com o Cypress;
* Executar os testes unitários;
* Gerar o relatório do Mocha.

Existem algumas formas de colocar a aplicação no ar.

## Para utilizar a aplicação pela web

Para conseguir utilizar a aplicação através da web (Chrome, Edge, Firefox, etc) preciamos digitar os comandos abaixo em diretórios específicos:<br>

No diretório do frontend:<br>
`$ npm run serve`

No diretório do backend:<br>
`$ npm run dev`

Após colocar a aplicação no ar será exibido o link da porta 8080:

```
App running at:
 - Local: http://localhost:8080/
```

Ao clicar no link você será redirecionado para a tela de login.

## Para executar os testes automatizados do front com o Cypress

Para executar os testes automatizados do front com o Cypress preciamos digitar os comandos abaixo em diretórios específicos:<br>

Na pasta do frontend digitar o comando abaixo:<br>
`$ npm run test:e2e`

O Cypress será aberto.

Na pasta do backend digitar o comando abaixo:<br>
`$ npm run dev:cy`

Além de colocar a API no ar este comando também irá droppar o banco de dados para que não tenha registros duplicados durante os testes.

Para executar um ou todos os testes automatizados basta seleciona-los na interface gráfica do Cypress.

## Para executar os testes unitários do backend

Para executar os testes unitários automatizados da API preciamos digitar os comandos abaixo em diretórios específicos:

Na pasta do backend digitar o comando abaixo:

`$ npm run test`

Após executado será gerado o relatório de testes diretamente no terminal e, se você quiser ter um relatório mais amigável basta seguir os passos do próximo comando.

## Para acessar o relatório de testes unitários do Mocha

Este relatório é útil porque quando executamos os testes pelo terminal e sem querer limpamos a tela ou fechamos o terminal, acabamos perdendo o resultado dos testes. Ao criar o relatório com o Mocha isso não irá mais ocorrer já que será gerado um arquivo que poderá ser visualizado a qualquer momento.<br>

Para acessar o relatório de testes unitários do mocha preciamos digitar os comandos abaixo no diretório `backend`.<br>

Executar os testes em modo headless e depois executar o comando `test:report` que que faz o merge de todos os relatórios individuais gerados pelo mocha transformando eles em apenas 1 report, ele também muda o tipo do arquivo de `.json` para `.html` e por fim ele transfere a pasta `screenshots` que contém todas as imagens dos testes e coloca ela dentro da pasta `assets` a qual será usada no relatório html para exibir as imagens dos testes.

Primeiramente executar os testes no modo headless:

`$ npm run test:headless`

Executar o comando abaixo para gerar o relatório:

`$ npm run test:report`

Após o processo será gerado o arquivo html no local: `frontend > mochawesome-report > report.html`. Ao abri-lo será exibido o relatório dos testes unitários com o print do resultado.

# Dependêcias 💼

Abaixo estão todas as dependências do projeto e uma breve explicação sobre elas.

## Frontend

- [**Vue**](#vue)
- [**Core-js**](#core-js)
- [**vue-router**](#vue-router)
- [**vue/cli-plugin-babel**](#vue-cli-plugin-babel)
- [**vue/cli-plugin-e2e-cypress**](#vue-cli-plugin-e2e-cypress)
- [**vue/cli-plugin-router**](#vue-cli-plugin-router)
- [**vue/cli-service**](#vue-cli-service)
- [**vue-template-compiler**](#vue-template-compiler)
- [**Buefy**](#buefy)
- [**Axios**](#axios)
- [**Mocha**](#mocha)
  - [**Mochawesome**](#mochawesome)
  - [**Mochawesome-merge**](#mochawesome-merge)

## Backend

- [**Nodemon**](#nodemon)
- [**Hapi**](#hapi)
  - [**hapi/hapi**](#hapi-hapi)
  - [**hapi/code**](#hapi-code)
  - [**hapi/lab**](#hapi-lab)
- [**Mongoose**](#mongoose)
- [**md5**](#md5)


<!-- # Observações 

## Pastas e arquivos

backend: diretório principal do backend.
controllers:
models:
routes:
tests: testes unitários do backend.
server.js: 

frontend: diretório principal do frontend.
mochawesome-report: contém arquivos usados no relatório do mocha.
src:
assets: imagens e gifs utilizados no projeto.
components: 
router: contém as rotas do projeto.
views: são as páginas do projeto.
app.vue:
main.js:
tests: testes do frontend. -->

## Arquivos

**contact.controller.js**: é um controller que:
* list(): retorna a lista de contatos;
* create(): cria novos contatos

**contact.model.js**: exibe o modelo de dados (campos que vão ser utilizados).

**Exemplo:**
```
const contactSchema = new Schema({
    name: String,
    number: String,
    description: String
});
```

**contact.routes.js**: cria os métodos (GET, POST, etc) e o que será feito neles.
Exemplo: `method: 'GET'` faz uma requisição no endpoint (path) `/contacts` que lista os contatos no dashboard (handler).

**server.js**: 

# Desenvolvimento do projeto 👨‍💻

Abaixo resumo do processo de criação do frontend e do backend.

## Processo para criação do front 📝

### Vue

Primeiro criaremos o projeto padrão do frontend através do Vue CLI.<br>
Vue comand line (CLI), fornece recursos de linhas de comando para usarmos através do terminal. Além disso ele fornece um sistema completo para iniciarmos de forma rápida o desenvolvimento de aplicações vue.js, ou seja, ele faz muito do trabalho tedioso feito manualmente por nós e nos fornece recursos valiosos pronto para uso, como por exemplo a integração com o Cypress.

No diretório principal do projeto digitar o comando abaixo para criar a pasta do frontend:

`$ vue create frontend`

Utilizado o preset abaixo:

```
Preset:
? Please pick a preset: Manually select features
? Check the features needed for your project: Babel, Router, E2E
? Choose a version of Vue.js that you want to start the project with 2.x
? Use history mode for router? (Requires proper server setup for index fallback in production) No
? Pick an E2E testing solution: Cypress
? Where do you prefer placing config for Babel, ESLint, etc.? In package.json
? Save this as a preset for future projects? Yes
? Save preset as: DevTester (você pode escolher o nome que desejar)
```

No final da instalação será exibido nas dependências:<br>

```
  "dependencies": {
    "core-js": "^3.8.3",
    "vue": "^2.6.14",
    "vue-router": "^3.5.1"
  },
  "devDependencies": {
    "@vue/cli-plugin-babel": "~5.0.0",
    "@vue/cli-plugin-e2e-cypress": "~5.0.0",
    "@vue/cli-plugin-router": "~5.0.0",
    "@vue/cli-service": "~5.0.0",
    "cypress": "^9.7.0",
    "vue-template-compiler": "^2.6.14"
  },
```

#### Core-js

É uma biblioteca JavaScript que fornece funcionalidades que não estão presentes em algumas versões mais antigas dos navegadores e também adiciona novas funcionalidades que ainda não foram incluídas nas especificações ECMAScript. Ela é uma biblioteca de polyfill, que permite que os desenvolvedores escrevam código JavaScript usando as últimas funcionalidades da linguagem, independentemente do navegador ou ambiente em que está sendo executado.

#### vue-router

É um pacote que fornece roteamento de URLs para aplicativos Vue.js. Com ele é possível criar aplicativos Vue.js mais complexos e organizados, com várias páginas e URLs, tornando a navegação mais fácil para o usuário e permitindo que você construa aplicativos mais avançados e dinâmicos.<br>

Ele usa o sistema de componentes do Vue.js para definir as diferentes páginas do aplicativo e as rotas para elas. O vue-router também fornece recursos como navegação programática, passagem de parâmetros dinâmicos para as rotas e roteamento aninhado.

#### vue/cli-plugin-babel

É um plugin para o Vue CLI que permite a configuração do Babel em um projeto Vue.js. O Babel é uma ferramenta que permite aos desenvolvedores escreverem código JavaScript usando as últimas funcionalidades da linguagem, mesmo que essas funcionalidades ainda não estejam disponíveis em todos os navegadores ou ambientes.

O @vue/cli-plugin-babel configura o Babel para transpilar o código JavaScript do projeto Vue.js, convertendo as funcionalidades que não são suportadas por alguns navegadores em código JavaScript mais antigo que possa ser executado em qualquer ambiente. Isso significa que os desenvolvedores podem escrever código Vue.js usando as últimas funcionalidades do ECMAScript, como async/await, arrow functions e spread operators, sem se preocupar com a compatibilidade do navegador.

#### vue/cli-plugin-e2e-cypress

É um plugin para o Vue CLI que adiciona suporte para testes end-to-end usando a ferramenta Cypress em projetos Vue.js.

#### vue/cli-plugin-router

É um plugin para o Vue CLI que adiciona suporte para roteamento em projetos Vue.js. O roteamento em uma aplicação web é a capacidade de navegar entre diferentes páginas ou rotas em um aplicativo, sem precisar carregar a página novamente. Com o @vue/cli-plugin-router, é possível criar uma estrutura de roteamento em um projeto Vue.js de forma simples e eficiente, definindo rotas e seus respectivos componentes.

#### vue/cli-service

É uma ferramenta de linha de comando que faz parte do Vue CLI (Interface de linha de comando). É responsável por gerenciar e executar diversos recursos do projeto Vue.js durante o desenvolvimento, como compilação de arquivos .vue, transpilação de código JavaScript usando Babel, minificação de código, hot-reloading e muito mais.<br>

O @vue/cli-service é executado durante o desenvolvimento do projeto para processar e compilar o código Vue.js, transformando-o em arquivos HTML, CSS e JavaScript que podem ser interpretados pelo navegador. Também pode ser usado para gerar arquivos para a produção.

#### vue-template-compiler

A dependência vue-template-compiler é responsável por compilar templates Vue.js em funções de renderização JavaScript. O Vue.js utiliza uma sintaxe especial em seus templates para definir a estrutura e a lógica de renderização de componentes.

Durante o desenvolvimento, o código Vue.js é escrito em um arquivo .vue, que pode conter um template Vue.js em sua seção `<template>`. Esses templates são compilados em funções de renderização que são executadas pelo Vue.js no navegador.

### Buefy

Framework de CSS que fornece todos os recursos necessários para criar um padrão visual. O Buefy foi criado exclusivamente para trabalhar com o Vue.Js.<br>
No terminal digitar o comando abaixo na pasta `frontend`:

`$ npm install buefy`

Colocar os imports de todos os componentes no arquivo `main.js` da pasta `frontend`:

```
import Buefy from 'buefy'
import 'buefy/dist/buefy.css'

Vue.use(Buefy)
```

### Axios

O Axios é um framework que faz a integração do frontend com o backend.<br>
Devemos entrar no diretório do front e colocar a aplicação web no ar:

`$ npm run serve`

Abrir uma nova instância no terminal para deixar o servidor on e digitar o comando abaixo ainda no diretório `frontend` para instalar o framework Axios (que fará a integração com a API REST):

`$ npm install axios`

Agora precisamos fazer a configuração padrão do Axios no arquivo `main.js` do frontend:

```
window.axios = require('axios')

window.axios.defaults.baseURL = 'http://localhost:3000'
```

O arquivo ficará da seguinte maneira:

```
import Vue from 'vue'
import App from './App.vue'
import router from './router'

import Buefy from 'buefy'
import 'buefy/dist/buefy.css'

import axios from 'axios';

axios.defaults.baseURL = 'http://localhost:3000';

axios.interceptors.request.use((config) => { //Aqui estamos interceptando todas as requisições do axios e estamos adicionando o token de autorização dentro do headers
  const userToken = localStorage.getItem('user_token') //No arquivo Login.vue adicionamos o token do usuário dentro de localStorage e aqui estamos obtendo o token através do getItem
  
  if(userToken) {
    config.headers.Authorization = userToken //Adicionado o token de autorização dentro do headers
  }  
  return config //Retorna a nova configuração que faz a interceptação das chamadas na API e adiciona automaticamente o token dentro do autorization  
}, (error) => Promise.reject(error)) //Se o .use apresentar error será devolvido uma promessa

Vue.use(Buefy)

Vue.config.productionTip = false
new Vue({
  router,
  render: h => h(App)
}).$mount('#app')
```

No arquivo `Dashboard.vue` criar os métodos para fazerem chamadas na API.<br>
No arquivo `server.js` adicionar a constante server do Hapi para liberar o acesso da API para qualquer aplicação.

```
const server = Hapi.server({
    port: 3000,
    // host: 'localhost', //Apenas para acesso local
    host: '0.0.0.0', //Libera para acesso externo
    routes: {
        cors: {
            // origin: ['http://localhost:8080'] // Libera apenas para esta rota
            origin: ['*'] // Libera a porta 3000 para qualquer aplicação
        }
    }
});
```

### Mocha

O Mocha é um framework de teste para javaScript amplamente utilizado que fornece uma estrutura flexível e fácil de usar para escrever testes de unidade, integração e aceitação. Ele é executado em node.js e no navegador, permitindo que os desenvolvedores testem tanto o código do cliente quanto do servidor.<br>
O Cypress usa a estrutura do mocha para estruturar os testes por isso o relatório do mocha vai ter compatibilidade com o Cypress.

No terminal da pasta `frontend` digitar o comando abaixo para instalar o mocha:

`$ npm i mocha`

#### Mochawesome

O Mochawesome é uma biblioteca de relatórios gerada pelo Mocha que fornece uma representação visual atraente dos resultados dos testes. Ele inclui gráficos e tabelas que facilitam a identificação de testes falhados e bem-sucedidos, bem como a análise de tendências e a comparação de desempenho ao longo do tempo.

Quando executamos o Cypress no modo headless, é exibido um relatório dentro do terminal, se o usuário limpar o terminal, será perdido o relatório. O mochawesome cria um relatório em HTML para não ficar preso no terminal.

Para isso basta instalar o framework mochawesome no diretório `frontend`:

`$ npm install --save-dev mochawesome`

Agora precisamos fazer algumas configurações no arquivo `cypress.json` para definir o tipo de relatório:

```
{
  "pluginsFile": "tests/e2e/plugins/index.js",
  "reporter": "mochawesome",
  "reporterOptions": {
    "reportDir": "mochawesome-report",
    "overwrite": true,
    "html": false,
    "json": true,
    "timestamp": "mmddyyyy_HHMMss"
  }
}
```

Deixado o relatório html como false porque posteriormente será feito um merge para gerar um arquivo único em html.

#### Mochawesome-merge

O Mochawesome-merge é uma ferramenta que permite mesclar vários relatórios Mochawesome em um único relatório consolidado. Isso é útil para projetos maiores ou para equipes que trabalham em diferentes partes do mesmo projeto, pois permite consolidar os resultados dos testes em um só lugar e facilitar a análise e a tomada de decisões com base nesses resultados.

Ainda no diretório `frontend` adicionar o pacote mochawesome-merge:

`$ npm install mochawesome-merge --save-dev`

Criar os scripts abaixo dentro de `package.json` da pasta `frontend` com o comando que engloba todos os relatórios json em apenas 1 relatório json.

* test:merge
Engloba todos os relatórios json em apenas 1
* test:html
Transforma o relatório json englobado em um arquivo html
* test:report
Executa os comandos test:merge e test:html (produtividade)

```
  "scripts": {
    "start": "yarn serve",
    "serve": "vue-cli-service serve",
    "build": "vue-cli-service build",
    "test:e2e": "vue-cli-service test:e2e",
    "test:headless": "vue-cli-service test:e2e --headless",
    "test:report": "yarn test:merge & yarn test:html & yarn test:mv",
    "test:merge": "mochawesome-merge > mochawesome-report/report.json",
    "test:html": "marge mochawesome-report//\\report.json",
    "test:mv": "mv tests\\e2e\\screenshots mochawesome-report\\assets\\screenshots"
  },
```

Por fim digitar o comando abaixo no terminal no diretório `frontend` para gerar o relatório em html:

`$ npm run test:report`

Após completo um arquivo chamado report.html será criado.


## Processo para criação do backend 📝

### Iniciar um projeto Node

Criar uma outra pasta para o backend normalmente sem vue:

`$ mkdir backend`

Dentro da pasta `backend` iniciar um projeto node normalmente:

`$ npm init`

<!-- package name: (backend) zaplink-api
description: API REST do Zaplink
keywords: api, node.js, hapi.dev, hapi
license: (ISC) MIT -->

Será criado o arquivo `package.json`.

### Nodemon

O Nodemon é um utilitário de linha de comando que monitora o diretório raiz do projeto e reinicia o aplicativo Node.js sempre que um arquivo é alterado. Ele é útil durante o desenvolvimento de aplicativos Node.js, pois permite que você faça alterações no código e veja o resultado imediatamente, sem precisar reiniciar manualmente o aplicativo a cada vez que você fizer uma alteração.

Ainda no diretório `backend` digitar o comando abaixo no terminal:

`$ npm install -g nodemon`

Colocar o script para o nodemon ficar monitorando o projeto:

```
"scripts": {
  "dev": "nodemon server.js",
}
```

Basta digitar o comando abaixo na pasta `backend` para o nodemon ficar monitorando as alterações:

`$ npm run dev`

Ao abrir a porta <a href="http://localhost:3000">3000</a> pode ser notado que o conteúdo não está em json, então precisamos ajustar.<br>

No arquivo `server.js` alterar a rota para o código abaixo:

```
    server.route({
        method: 'GET',
        path: '/',
        handler: (request, h) => {

            return {message: "Welcome to ZapLink API", company: "QA Ninja", course: "DevTester"};
        }
    });
```

Após isso o conteúdo exibido será no formato json.


### Hapi

Hapi é um framework para desenvolvimento de aplicações web em Node.js. O Hapi fornece uma grande variedade de recursos para ajudar os desenvolvedores a criar APIs de alta qualidade de forma rápida e fácil.

#### hapi/hapi

É o módulo principal do Hapi.js, fornecendo o núcleo do framework para criar aplicativos da web. Ele fornece recursos como roteamento, manipulação de solicitações e respostas HTTP, gerenciamento de conexão do servidor e muito mais.

Para adicionar o hapi ao projeto. Basta digitar o comando no diretório `backend`:

`$ npm install @hapi/hapi`

Dentro da pasta `backend` criar um arquivo chamado `server.js` e colocar o código que irá subir a aplicação na porta 3000:

Adding Routes

```
'use strict';

const Hapi = require('@hapi/hapi');

const init = async () => {

    const server = Hapi.server({
        port: 3000,
        host: 'localhost'
    });

    server.route({
        method: 'GET',
        path: '/',
        handler: (request, h) => {

            return 'Hello World!';
        }
    });

    await server.start();
    console.log('Server running on %s', server.info.uri);
};

process.on('unhandledRejection', (err) => {

    console.log(err);
    process.exit(1);
});

init();
```

### Automatizar os testes unitários com o plugin Lab e code do hapi.dev

Para automatizar o teste na camada de teste unitário utilizarmos o plugin <a href="https://hapi.dev/module/lab/">lab</a> e o code do hapi.dev.

#### hapi/code

É uma biblioteca de suporte de teste para testes de unidade, que fornece uma API de asserção e outras utilidades para escrever testes para aplicativos Hapi.js. Ele é usado principalmente com o framework de teste de unidade Lab, mas também pode ser usado em conjunto com outros frameworks de teste.

#### hapi/lab

É um framework de teste de unidade para aplicativos Hapi.js, que fornece uma API de teste mais simples e intuitiva do que outras bibliotecas de teste de unidade. Ele inclui recursos como a capacidade de executar testes em paralelo, usar hooks de ciclo de vida para configurar e limpar o estado dos testes, e integração com o suporte de teste @hapi/code.

No terminal digitar os comandos abaixo no diretório `backend`:

`$ npm install @hapi/lab`
`$ npm install @hapi/code`

Dentro da pasta `backend` criar uma nova pasta chamada `tests` e dentro desta pasta criar um arquivo com o final `.test.js` o qual conterá os testes do backend.<br>
Exemplo `get.test.js`:

```
const Code = require('@hapi/code');
const Lab = require('@hapi/lab');

const { expect } = Code;
const { describe, it } = exports.lab = Lab.script();

it('returns true when 1 + 1 equals 2', () => {

    expect(1 + 1).to.equal(2);
});
```

Precisamos também modificar o arquivo `server.js` que ficará da seguinte maneira:

Adicionado o script abaixo para auxiliar no comando de teste para não ter que ficar digitando o comando acima a todo momento.<br> 
O comando `-v` descreve o nome de cada caso de teste:

```
  "scripts": {
    "dev": "nodemon server.js",
    "test": "lab -v tests -I resp"
  },
```

### Mongoose

Recomendado criar um banco antes desta etapa. Veja o tópico: [Criar um banco de dados no MongoDB](#criar-um-banco-de-dados-no-mongodb)
o Mongoose é um framework Node.js de conexão no banco de dados no MongoBD com o Node.Js com um esquema de modelagem de dados, então além de termos a conexão com o banco vamos conseguir modelar os dados da nossa aplicação. Essa modelagem será dos campos (name, number, etc). 

Para instalar o Mongoose digitar o comando abaixo no diretório `backend`:

`$ npm install mongoose`

Na pasta `backend` criar uma pasta chamada `models` e dentro dela criar um arquivo chamado `contact.model.js`. 
Neste arquivo iremos importar o mongoose:

```
const mongoose = require('mongoose');

const Schema = mongoose.Schema

const contactSchema = new Schema({
    name: String,
    number: String,
    description: String
});

module.exports = mongoose.model('Contact', contactSchema);
```

No arquivo `server.js` criar a conexão com o banco de dados. Após a importação do happy colocar a constante de importação do mongoose: 

```
const mongoose = require('mongoose');

const mongoUrl = "mongodb+srv://qaninja:qaninja@zaplinkcluster.fapnnxf.mongodb.net/?retryWrites=true&w=majority";

mongoose.connect(mongoUrl, { useNewUrlParser: true, useUnifiedTopology: true});

mongoose.connection.on('connected', () => {
    console.log('MongoDB connected');
    if (process.env.NODE_ENV === 'test') {
        mongoose.connection.db.dropDatabase();
        console.log('MongoDB test database dropped');
    }
});

mongoose.connection.on('error', (error) => {
    console.log('MongoDB error ' + error)
})
```

Para pegar a connection basta entrar no mongo, clicar em connect, selecionar a opção `Connect your application`. 
Passo 1, driver `Node.js`, version `4.1 or later`. 
Passo 2, copiar a conexão. Guardamos ela em uma constante (mongoURL) no código acima. **Atentar-se pois é necessário adicionar a senha manualmente no link**.

Adicionamos 2 listeners (connected e error) para saber quando a conexão é feita com sucesso ou quando tiver algum erro de conexão. 

Após isso podemos ver a aplicação rodando através do código abaixo:

`$ npm run dev`

Se tudo ocorrer bem, no terminal será apresentado a informação: "MongoBD connected".

### md5

O pacote "md5" do Node.js oferece a função md5(), que é usada para gerar o hash MD5 de uma string. O hash MD5 é frequentemente usado para verificar a integridade dos dados ou para armazenar senhas criptografadas.

No diretório do `backend` instalar o pacote do node MD5 para criptografar as senhas dos usuários:

`$ npm install md5`


## Criar um banco de dados no MongoDB 📝

A diferença de um banco de dados tradicional para o MongoDB é ao invés de você ter tabelas será collections. Em uma tabela de banco de dados tradicional é inserido registros, nas collections do MongoDB é inserido documentos.<br>

Deve-se criar uma conta no MongoBD.<br>
Criar um novo projeto com o nome `ZapLink` e clicar em `Create project`.<br>

Criar um cluster (aglomeração de banco de dados). Clicar em `Build a cluster`. Será criado um banco de dados na nuvem.<br>

Selecionar a opção free, provide AWS, escolher uma região Brasil (preferencialmente por conta da latência) e colocar o nome de do cluster `zaplinkCluster`. Clicar no botão `Create`.<br>

Na listagem ao lado esquerdo clicar em `Database` ´para ser exibido o Database Deployments. Clicar em `Connect`.<br>

No ponto 1, selecionar a opção `Allow Access from Anywhere`. Pode ser deixado o IP Address como está para ele deixar todo o range de IP acessível a este banco de dados, clicar em `Add ip address`.<br>

No ponto 2, Username e Password informar: qaninja. Clicar no botão `Create Database User`. Após isso clicar no botão `Choose a connection method`.<br>

Selecionar a opção `Connect using MongoDB Compass`. Copiar a string de conecção para usar no Robo 3T `Copy the connection string, then open MongoDB Compass.`<br>

MongoDB Compass é uma interface gráfica para explorar, consultar dados no MongoDB, inserir dados, etc. Mas ao invés de usarmos o MongoDB Compass usaremos o <a href="https://robomongo.org/">Robo 3T</a>.<br>

Baixar e instalar normalmente (Next, next, next..).<br>

Abrir o Studio 3T e aceitar os termos, manter a opção `Use Studio 3T's(..)`. Next, manter a opção `Easy data access(...)`. Cadastrar e depois que aberto no Quickstart clicar na opção `+ Create a new connection`. Na URI colar a connection string do MongoDB (para conectar via interface gráfica) porém atentar-se que nessa string existe a tag `<password>` que deverá ser substituída pela senha criada no MongoDB. Exemplo: `mongodb+srv://qaninja:qaninja@zaplinkcluster.fapnnxf.mongodb.net/test`. Clicar em next e dar OK na box que irá aparecer. Alterar o `Connection name:` para `ZapLink` e clicar no botão `save` e depois no botão `Connect`. Se tudo der certo será conectado ao banco de dados do MongoBD.<br>

Voltando para o MongoBD a janela de connect pode ser fechada.<br>

Clicar na opção `Browse Collections` não será listado nenhuma base de dados. Para criar uma clicar no botão `Add My Own Data`. No `DATABASE NAME` informar `zaplinkdb` e em `COLLECTION NAME` informar `contacts`, clicar no botão `Create`. Será criado o banco de dados e a collection.<br>

Se voltarmos ao Robo 3T e atualizarmos o banco ZapLink será exibido a collection `contacts` criada.<br>

Na collection `contacts` inserir um documento, **prestar atenção na formatação**. Para inserir basta selecionar a opção `Add document`através do ícone localizado na aba Result. Os documentos devem ser inseridos no formato json:

```
{
    "name" : "Rafael Rabelo da Silva",
    "number" : "48 996561401",
    "description" : "Solicitar consultoria em DevOps"
}
```

Neste caso não precisamos informar o ID já que ele será criado automaticamente.<br>

Clicar em `Add Document`. Fazer o mesmo processo para os demais:

```
{
    "name" : "João da Silva",
    "number" : "48 996561402",
    "description" : "Orçamento para aulas de inglês"
}
```

```
{
    "name" : "Maria da Silva",
    "number" : "48 996561403",
    "description" : "Orçamento para aulas de francês"
}
```

Para fazer um teste basta digitar a query abaixo no campo query, deverá retornar um registo:

```
{ name : "Rafael Rabelo da Silva" }
```

Agora nós temos a listagem de contatos armazenada no banco de dados porém o código da nossa API não sabe se comunicar com o banco faremos isso nos próximos passos.
<!-- 
## Minhas observações

### Como adicionar o loader na página

Adicionar a imagem dentro da tag `<template>`:

```
<div id="loader">
    <img src="../assets/loading.gif" alt="Loader">
</div>
```

Dentro da função `data()` adicionar um novo objeto que chamei de `isLoading: false,` que quando estiver carregando (buscando a informação) ficará como `true`.
```
  data() {
    return {
      isLoading: false,
      contactList: [],
```

Dentro da div que tem a imagem do loader colocar um `v-if="isLoading"`:

```
<div id="loader" v-if="isLoading === true"> //Se for igual a true irá mostrar esta lista
        <img src="../assets/loading.gif" alt="Loader">
      </div>
```

Agora na lista de contatos devemos adicionar um `v-if="isLoading"` para que ela só seja exibida se não estiver carregando nenhuma busca

```
<div class="contact-list columns is-multiline" v-if="isLoading === false"> //Só vai mostrar a lista de contatos se o loading for false
<div
```

Se após essas etapas o loader não estiver sendo exibido é porque você está no caminho certo.

Na função `list()` adicionar a condição `this.isLoading` para iniciar como `true` e finalizar como `false`, ou seja, ao iniciar a busca irá exibir o loader e ao finalizar a busca ele deixará de exibir o loader:

```
async list() {
this.isLoading = true; // Enquanto estiver fazendo a busca o isLoading vai ser true (mostra o loader mas não mostra a lista)
try {
const res = await axios.get("/contacts");
this.contactList = res.data;
console.log(res.data);
// continue with other instructions
} catch (error) {
console.log(error);
// handle the error
}
this.isLoading = false; //Quando terminou a busca o isLoading é alterado para falso para o loading não ser mais exibido
},
},
mounted() {
this.list();
},
};
```

### Como adicionar um snackbar

Utilizando do Bulma (componentes>message)

Na tag `<template>` do arquivo `Dashboard.vue`

## Como alterar o status code da requisição

O processo é feito no arquivo `contact.controller.js`. Nele é instanciamos o objeto e invocamos a função salvar. Na response adicionamos a função `code()` que define o status code como `200`.
O arquivo ficará da seguinte maneira:

```
const contactModel = require('../models/contact.model')

module.exports = {
    async create(request, h) {


        const contact = new contactModel({
            name: request.payload.name,
            number: request.payload.number,
            description: request.payload.description
        })

        let result = await contact.save()

        return h.response(result).code(200);
    },
    async list(request, h) {
        const contacts = await contactModel.find().exec();
        return contacts;
    }
}
```

## Try Catch

Eu tento executar um código e se por algum motivo este código não foi executado com sucesso é tratado uma exceção.
Tente executar o `contact.save()` e guardar o resultado na variável `result`, tente retornar o resultado da `result` e o status code 200 e se por ventura não funcionar (se entrou em algum outro caso que não foi mapeado) será tratado o erro de uma forma melhor.

```
try {
    let result = await contact.save() //Chamado o objeto contact e invocado a função salvar. Desta forma será salvo as informações no banco de dados através do Mongoose
    return h.response(result).code(200); //Na `response` estamos enviando o resultado esperado. Chamado a função `code()` colocando o status 200
} catch (error) {
    return h.response(error).code(500)
}
```

## Custom actions

Basta verificar o arquivo `add_contacts.cy.js` nele tem os casos de testes criados. No arquivo `commands.js` existem os comandos customizados que criamos (funções) que estão sendo usadas no arquivo `add_contacts.cy.js`. 

Observação: no arquivo commands não deve ser feito validações.

## Autenticação

Precisa ser criado uma rota, modelo de dados e uma controller para conter toda a funcionalidade de login rodando no backend

Foi criado nos arquivos
user.model.js
user.controller.js
user.routes.js
server.js

No diretório do `backend` instalar o pacote do node MD5 para criptografar as senhas:

`$ npm install md5`

Foi feito o import e o ajuste na const user dentro do arquivo `user.controller.js`

### Autenticação através da tela de login

Implementação feita dentro de `frontend>views>Login.vue`

## Logout

Feito no arquivo `navbar.vue` onde foi adicionada uma função com o nome logout() que ao ser acionada remove o token do usuário do localStorage e volta para a tela de login.

## HTTP response status code

No site da <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Status">Mozilla</a> tem uma documentação com vários status code da web para utilizar como base.

## Relatórios e Cobertura de Código

No diretório `backend` dentro de `package.json` criado os scrips de relatório test:ci e test:coverage. Estes relatórios só funcionam com o framework hapi.lab:

```
"scripts": {
    "dev": "nodemon server.js",
    "test": "lab -v tests -I resp",
    "test:ci": "lab -v tests -r junit -o logs/report.xml -I resp",
    "test:coverage": "lab -v tests -r html -o logs/report.html -I resp"
},
```

* dev
Coloca o servidor no ar.

* test
Executa os testes via linha de comando.
-I resp para ignorar a variável resp que é global em nosso projeto

* test:ci
Se quiser rodar esses testes em um projeto com lab em um servidor de continuos integration.
-r é o tipo de relatório que queremos, no caso Junit o qual é universal (irá funcionar no jenkins, no gitlab CI, Circle CI, em qualquer ferramenta de continuos integration).
-o é onde será gravado o relatório de testes automatizados.
Após executado o arquivo `XML` estará dentro de `backend>logs>report.xml` no formato do Junit (para continuos integration)

* test:coverage
Após executado o arquivo `HTML` estará dentro de `backend>logs>report.html` no formato do Junit (para continuos integration).
Ao abri-lo, que irá exibir todos os testes que foram executados, duração e o code coverage report que analisa os arquivos (cobertura de código) e exibe quais regras de negócio não tem testes.
 -->
