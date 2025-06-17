# Aula 1 - Introdução aos Sistemas Web

Esta aula apresenta os conceitos básicos de uma aplicação web utilizando Node.js. O objetivo é iniciar um projeto simples e testar um endpoint HTTP local.

## Passos

1. **Inicializar o projeto Node**
   ```bash
   npm init -y
   ```
   Este comando cria o arquivo `package.json` com as configurações padrão do projeto.

2. **Instalar o Express**
   ```bash
   npm install express
   ```
   O Express é o framework que iremos utilizar para criar o servidor HTTP.

3. **Criar o `server.js`**
   No arquivo `server.js`, adicione o código abaixo:
   ```javascript
   const express = require('express');
   const app = express();
   const port = process.env.PORT || 3000;

   app.get('/', (req, res) => {
     res.send('Hello, World!');
   });

   app.listen(port, () => {
     console.log(`Server running on http://localhost:${port}`);
   });
   ```
   Esse servidor expõe um endpoint raiz (`/`) que retorna **Hello, World!**.

4. **Testar o endpoint com a extensão REST Client**
   Crie um arquivo `rest.http` com o conteúdo:
   ```http
   ### Test the root endpoint
   GET http://localhost:3000/
   ```
   Com a extensão [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client), é possível enviar a requisição e visualizar a resposta diretamente no editor.

Para iniciar o servidor execute:
```bash
node server.js
```
Em seguida, use o arquivo `rest.http` para testar a rota raiz.

