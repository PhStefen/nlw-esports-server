# NLW eSports - Server
## Criação de Projeto
Execute no `PowerShell`:
```
npm init -y
```

## Typescript
### Instalação
Execute no `PowerShell`:
```
npm i typescript -D
npx tsc --init
```
### Configuração
Edite `tsconfig.json`
```
{
    "rootDir": "./src",
    "moduleResolution": "node",  
    "outDir": "./build" 
}
```

## Express - Gerenciador de Rotas
### Instalação
Execute no `PowerShell`:
```
npm i express
npm i @types/express -D
```

## TS-NODE-DEV - Conversor de TS pra JS
### Instalação
Execute no `PowerShell`:
```
npm i ts-node-dev -D
```
### Configuração
Ajuste o `package.json`:
```
"scripts": {
    "build": "tsc",
    "dev": "tsnd src/server.ts"
}
```

## Primas - ORM
### Instalação
Execute no `PowerShell`
```
npm i prisma -D
npx prisma init --datasource-provider SQLite
npm i @prisma/client
```
Instale as extensões 
* `Prisma.prisma`
* `alexcvzz.vscode-sqlite`

### Configurações
Adicione a flag `--exit-child` no scirpt `dev` em `package.json` para reiniciar a conexão toda vez que o arquivo é salvo
```
"scripts": {
    "dev": "tsnd --exit-child src/server.ts"
}
```
## CORS - Segurança da API
### Instalação
Execute no `PowerShell`:
```
npm i cors
npm i @types/cors -D
```

### Configuração
Faça o `express` usar o `cors`:
```
import express from "express";
import cors from "cors";

const app = express();
app.use(express.json());
app.use(cors({
    origin: '*' //  Trocar para um domínio para limitar quem pode fazer a requisição
}));
```
