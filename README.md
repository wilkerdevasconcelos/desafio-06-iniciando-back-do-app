### :rocket: Desafio 06: Banco de dados e upload de arquivos no Node.js - GoStack 11.0
Neste desafio foi solicitada a criação de uma aplicação com node.js e typescript para
registrar entradas e saídas financeiras. Também foi solicitado um endpoint para
importação de arquivos CSV com lançamentos de transações financeiras.


### Tecnologias utilizadas

- [Node.js](https://nodejs.org/en/)
- [TypeScript](https://www.typescriptlang.org/)
- [Jest](https://www.npmjs.com/package/jest)
- [Postgres](https://www.postgresql.org/)

Também foram utilizadas tecnologias para padronização de código, são elas:
prettier, eslint e editorconfig.

### Executando a aplicação

```js
yarn
yarn dev:server
```

**Para executar os testes:**

```js
yarn test
```

### :muscle: Endpoints


[GET] *http://localhost:3333/transactions*
```json
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Salário",
      "value": 4000,
      "type": "income",
      "category": {
        "id": "uuid",
        "title": "Salary"
      }
    },
    {
      "id": "uuid",
      "title": "Freela",
      "value": 2000,
      "type": "income",
      "category": {
        "id": "uuid",
        "title": "Others"
      }
    },
    {
      "id": "uuid",
      "title": "Pagamento da fatura",
      "value": 4000,
      "type": "outcome",
      "category": {
        "id": "uuid",
        "title": "Others"
      }
    },
    {
      "id": "uuid",
      "title": "Cadeira Gamer",
      "value": 1200,
      "type": "outcome",
      "category": {
        "id": "uuid",
        "title": "Recreation"
      }
    }
  ],
  "balance": {
    "income": 6000,
    "outcome": 5200,
    "total": 800
  }
}
```

Para o cadastro de transações é necessário informar a categoria. Caso ela
já exista, não será cadastrada novamente, apenas será relacionada com a
categoria já cadastrada.

[POST] *http://localhost:3333/transactions*
```json
{
  "id": "uuid",
  "title": "Salário",
  "value": 3000,
  "type": "income",
  "category": "Alimentação"
}
```

[DELETE] *http://localhost:3333/transactions/:id*

[POST] *http://localhost:3333/transactions/import*

Body: Multipart
file csv [Modelo](https://github.com/adrianoluisalmeida/desafio-06-gostack11/blob/master/src/__tests__/import_template.csv)


### :memo: Licença

Esse projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE.md) para mais detalhes.

---

<p align="center">Feito  por <strong>Adriano Almeida</p>
