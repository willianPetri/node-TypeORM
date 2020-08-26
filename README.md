<h1 align="center">Node-TypeORM</h1>

---

## 🚀 Technologies

This project was developed at the Rocketseat GoStack Bootcamp with the following technologies:

- [Node](https://nodejs.org/en/)
- [Typescript](https://www.typescriptlang.org/)
- [Express](https://expressjs.com/)
- [Cors](https://www.npmjs.com/package/cors)
- [Multer](https://www.npmjs.com/package/multer)
- [Docker Postgres](https://hub.docker.com/_/postgres)
- [TypeORM](https://typeorm.io/#/)
- [VS Code](https://code.visualstudio.com/) with [EditorConfig](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig) and [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

---

## ⚙️ How To Use

```bash

  # Clone this repository
  $ git clone https://github.com/willianPetri/node-TypeORM.git

  # Go into the repository
  $ cd node-TypeORM

  # Install dependecies
  $ yarn install

  #Run Postgres on docker port 5434 and change the host to localhost on the file ormconfig.json
  #Create a database with the name "gostack_desafio06" then
  #Run migration
  $ yarn typeorm migration:run

  #Run the project
  $ yarn dev:server
```
## 📬 HTTP Request

<details>
  <summary>Transaction {METHOD}/transaction </summary>

<!--START_SECTION:activity-->
<details>

<summary>GET</summary>

   ### Response

  ```json
    {
      "transactions": [
        {
          "id": "34135792-e455-41e9-aa24-10bf64a8ffa0",
          "title": "Salário",
          "type": "income",
          "value": "5000",
          "category_id": "7bb3a552-91d0-4f11-ad31-b9ecb400b2c7",
          "created_at": "2020-08-24T04:43:35.696Z",
          "updated_at": "2020-08-24T04:43:35.696Z"
        }
      ],
      "balance": {
        "income": 5000,
        "outcome": 0,
        "total": 5000
      }
    }
  ```
</details>

<details>
  <summary>POST</summary>

  ### Request Body

  ```bash
    {
      title: string
      type: string  (income | outcome)
      value: number
      category: string
    }
  ```


  ### Example

  ```json
  {
    "title": "Comida",
    "type": "outcome",
    "value": 150.59,
    "category": "Alimentos"
  }
  ```

  <h3> Response 200 </h3>

  ```json
    {
      "title": "Comida",
      "type": "outcome",
      "value": 150.59,
      "category_id": "85e4b9ec-b0ca-4bd5-be88-74462d609629",
      "category": {
        "id": "85e4b9ec-b0ca-4bd5-be88-74462d609629",
        "title": "Alimentos",
        "created_at": "2020-08-24T04:45:55.671Z",
        "updated_at": "2020-08-24T04:45:55.671Z"
      },
      "id": "956ff629-88f4-42c8-81c1-1bcac29bfd6a",
      "created_at": "2020-08-24T04:45:55.685Z",
      "updated_at": "2020-08-24T04:45:55.685Z"
    }
  ```

<h3> Response 500 Internal Server Error </h3>

  ```json
    {
      "status": "error",
      "message": "Internal server error"
    }
  ```
</details>

<details>
  <summary><span>DELETE </span>/{id}</summary>

  <h3> Response 204 No content </h3>
</details>

<!--END_SECTION:activity-->
</details>

---

Made with ❤ by Willian Petri  [✌ Get in touch!](https://www.linkedin.com/in/willian-petri-84a935135/)
