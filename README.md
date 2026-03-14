# Desafio Ignite - Database Queries

Projeto de desafio da trilha Ignite (Node.js) com foco em consultas com TypeORM e PostgreSQL.

O objetivo principal e implementar metodos de repositorio usando:

- ORM (relacoes e carregamento de dados)
- Query Builder
- Raw Query

As validações de comportamento estão em testes automatizados com Jest.

## Tecnologias

- Node.js
- TypeScript
- TypeORM
- PostgreSQL
- Jest

## Estrutura principal

```text
src/
	__tests__/Repositories.spec.ts
	database/migrations/
	modules/
		games/
		users/
```

## Pre-requisitos

- Node.js 14+
- PostgreSQL em execucao
- npm ou yarn

## Configuracao do banco

O projeto usa o arquivo `ormconfig.json` com a conexao padrao:

- host: `localhost`
- port: `5432`
- username: `postgres`
- password: `docker`
- database: `queries_challenge`

Se necessario, ajuste os valores no `ormconfig.json` para o seu ambiente.

## Como executar

1. Instale as dependencias:

```bash
npm install
```

2. Crie o banco de dados no PostgreSQL com o nome `queries_challenge`.

3. Rode as migracoes:

```bash
npx ts-node ./node_modules/typeorm/cli.js migration:run
```

4. Execute os testes:

```bash
npm test
```

## O que e validado nos testes

Os testes em `src/__tests__/Repositories.spec.ts` validam, entre outros pontos:

- Busca de usuario com lista de jogos por ID
- Listagem de usuarios ordenados por primeiro nome
- Busca de usuario por nome completo sem diferenca entre maiusculas e minusculas
- Busca de jogo por titulo parcial
- Contagem total de jogos
- Listagem de usuarios que possuem um jogo especifico

## Script disponivel

- `npm test`: executa os testes com Jest

## Observacoes

- O teste prepara os dados automaticamente (drop de tabelas, migracoes e seed em memoria de teste).
- Em caso de erro de conexao, revise credenciais e se o PostgreSQL esta ativo.
