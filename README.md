# Testes de API - ServeRest

Projeto voltado para validação dos endpoints da API **ServeRest** utilizando **Postman**.

O objetivo deste repositório é registrar os testes realizados na API, organizar a collection utilizada e documentar a cobertura dos endpoints da ServeRest para compor portfólio de QA.

## Objetivo

Validar o comportamento dos endpoints da API ServeRest por meio de testes manuais no Postman, cobrindo cenários positivos, negativos e validações das respostas da API.

## Ferramentas utilizadas

- Postman
- GitHub
- ServeRest

## Documentação da API

- Swagger UI: `https://serverest.dev/`
- Swagger JSON: `https://serverest.dev/swagger.json?lang=pt-BR`

## Base URL da API pública

```bash
https://serverest.dev

## Executando a API localmente

A API ServeRest também pode ser executada localmente em localhost, usando npm ou Docker.

Subindo com npm
```bash
npx serverest@latest

Observação: versões mais recentes do ServeRest podem exigir Node.js mais atual.

Subindo com Docker
```bash
docker run -p 3000:3000 serverest/serverest:latest