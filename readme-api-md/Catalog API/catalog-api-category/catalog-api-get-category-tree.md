---
title: "Get Category Tree"
slug: "catalog-api-get-category-tree"
excerpt: "Retrieves the Category Tree of your store. Get all the category levels registered in the Catalog or define the level up to which you want to get.  \r\n> 📘 Onboarding guide \r\n>\r\n> Check the new [Catalog onboarding guide](https://developers.vtex.com/vtex-rest-api/docs/catalog-overview). We created this guide to improve the onboarding experience for developers at VTEX. It assembles all documentation on our Developer Portal about Catalog and is organized by focusing on the developer's journey. \r\n## Response body example\r\n\r\n```json\r\n[\r\n    {\r\n        \"id\": 1,\r\n        \"name\": \"Alimentação\",\r\n        \"hasChildren\": true,\r\n        \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao\",\r\n        \"children\": [\r\n            {\r\n                \"id\": 6,\r\n                \"name\": \"Bebedouro\",\r\n                \"hasChildren\": false,\r\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao/bebedouro\",\r\n                \"children\": [],\r\n                \"Title\": \"Bebedouro para Gatos\",\r\n                \"MetaTagDescription\": \"\"\r\n            },\r\n            {\r\n                \"id\": 7,\r\n                \"name\": \"Comedouro\",\r\n                \"hasChildren\": false,\r\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao/comedouro\",\r\n                \"children\": [],\r\n                \"Title\": \"Comedouro para Gatos\",\r\n                \"MetaTagDescription\": \"\"\r\n            },\r\n            {\r\n                \"id\": 8,\r\n                \"name\": \"Biscoitos\",\r\n                \"hasChildren\": false,\r\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao/biscoitos\",\r\n                \"children\": [],\r\n                \"Title\": \"Biscoitos para Gatos\",\r\n                \"MetaTagDescription\": \"\"\r\n            },\r\n            {\r\n                \"id\": 9,\r\n                \"name\": \"Petiscos\",\r\n                \"hasChildren\": false,\r\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao/petiscos\",\r\n                \"children\": [],\r\n                \"Title\": \"Petiscos para Gatos\",\r\n                \"MetaTagDescription\": \"\"\r\n            },\r\n            {\r\n                \"id\": 10,\r\n                \"name\": \"Ração Seca\",\r\n                \"hasChildren\": false,\r\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao/racao-seca\",\r\n                \"children\": [],\r\n                \"Title\": \"Ração Seca para Gatos\",\r\n                \"MetaTagDescription\": \"\"\r\n            },\r\n            {\r\n                \"id\": 11,\r\n                \"name\": \"Ração Úmida\",\r\n                \"hasChildren\": false,\r\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao/racao-umida\",\r\n                \"children\": [],\r\n                \"Title\": \"Ração Úmida para Gatos\",\r\n                \"MetaTagDescription\": \"\"\r\n            }\r\n        ],\r\n        \"Title\": \"Alimentação para Gatos\",\r\n        \"MetaTagDescription\": \"\"\r\n    },\r\n    {\r\n        \"id\": 2,\r\n        \"name\": \"Brinquedos\",\r\n        \"hasChildren\": true,\r\n        \"url\": \"https://lojadobreno.vtexcommercestable.com.br/brinquedos\",\r\n        \"children\": [\r\n            {\r\n                \"id\": 12,\r\n                \"name\": \"Bolinhas\",\r\n                \"hasChildren\": false,\r\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/brinquedos/bolinhas\",\r\n                \"children\": [],\r\n                \"Title\": \"Bolinhas para Gatos\",\r\n                \"MetaTagDescription\": \"\"\r\n            },\r\n            {\r\n                \"id\": 13,\r\n                \"name\": \"Ratinhos\",\r\n                \"hasChildren\": false,\r\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/brinquedos/ratinhos\",\r\n                \"children\": [],\r\n                \"Title\": \"Ratinhos\",\r\n                \"MetaTagDescription\": \"\"\r\n            },\r\n            {\r\n                \"id\": 19,\r\n                \"name\": \"Arranhador para gato\",\r\n                \"hasChildren\": false,\r\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/brinquedos/arranhador-para-gato\",\r\n                \"children\": [],\r\n                \"Title\": \"Brinquedo Arranhador para gatos\",\r\n                \"MetaTagDescription\": \"Arranhador gatos é indispensável no lar com felinos. Ideais para afiar as unhas e garantir a diversão\"\r\n            }\r\n        ],\r\n        \"Title\": \"Brinquedos para Gatos\",\r\n        \"MetaTagDescription\": \"\"\r\n    }\r\n]\r\n```"
hidden: false
createdAt: "2020-02-05T23:07:29.210Z"
updatedAt: "2022-09-09T19:28:13.796Z"
---
## Response body has the following properties:


| Attribute    | Type        | Description |
| --------------- |:---------:| -------------------------------------------------------------------------------------------:|
| `id` | integer | Category ID|
| `name` | string      |  Category Name |
| `hasChildren` | boolean    | If the Category has a Category Child  |
| `url`  | integer | Category URL |
| `children` | array of object  | Category Child Object |
| `Title` | string | Category page Meta Title |
| `MetaTagDescription` | string | Category page Meta Description |


## Response body example:
[block:code]
{
  "codes": [
    {
      "code": "[\n    {\n        \"id\": 1,\n        \"name\": \"Alimentação\",\n        \"hasChildren\": true,\n        \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao\",\n        \"children\": [\n            {\n                \"id\": 6,\n                \"name\": \"Bebedouro\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao/bebedouro\",\n                \"children\": [],\n                \"Title\": \"Bebedouro para Gatos\",\n                \"MetaTagDescription\": \"\"\n            },\n            {\n                \"id\": 7,\n                \"name\": \"Comedouro\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao/comedouro\",\n                \"children\": [],\n                \"Title\": \"Comedouro para Gatos\",\n                \"MetaTagDescription\": \"\"\n            },\n            {\n                \"id\": 8,\n                \"name\": \"Biscoitos\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao/biscoitos\",\n                \"children\": [],\n                \"Title\": \"Biscoitos para Gatos\",\n                \"MetaTagDescription\": \"\"\n            },\n            {\n                \"id\": 9,\n                \"name\": \"Petiscos\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao/petiscos\",\n                \"children\": [],\n                \"Title\": \"Petiscos para Gatos\",\n                \"MetaTagDescription\": \"\"\n            },\n            {\n                \"id\": 10,\n                \"name\": \"Ração Seca\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao/racao-seca\",\n                \"children\": [],\n                \"Title\": \"Ração Seca para Gatos\",\n                \"MetaTagDescription\": \"\"\n            },\n            {\n                \"id\": 11,\n                \"name\": \"Ração Úmida\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/alimentacao/racao-umida\",\n                \"children\": [],\n                \"Title\": \"Ração Úmida para Gatos\",\n                \"MetaTagDescription\": \"\"\n            }\n        ],\n        \"Title\": \"Alimentação para Gatos\",\n        \"MetaTagDescription\": \"\"\n    },\n    {\n        \"id\": 2,\n        \"name\": \"Brinquedos\",\n        \"hasChildren\": true,\n        \"url\": \"https://lojadobreno.vtexcommercestable.com.br/brinquedos\",\n        \"children\": [\n            {\n                \"id\": 12,\n                \"name\": \"Bolinhas\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/brinquedos/bolinhas\",\n                \"children\": [],\n                \"Title\": \"Bolinhas para Gatos\",\n                \"MetaTagDescription\": \"\"\n            },\n            {\n                \"id\": 13,\n                \"name\": \"Ratinhos\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/brinquedos/ratinhos\",\n                \"children\": [],\n                \"Title\": \"Ratinhos\",\n                \"MetaTagDescription\": \"\"\n            },\n            {\n                \"id\": 19,\n                \"name\": \"Arranhador para gato\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/brinquedos/arranhador-para-gato\",\n                \"children\": [],\n                \"Title\": \"Brinquedo Arranhador para gatos\",\n                \"MetaTagDescription\": \"Arranhador gatos é indispensável no lar com felinos. Ideais para afiar as unhas e garantir a diversão\"\n            }\n        ],\n        \"Title\": \"Brinquedos para Gatos\",\n        \"MetaTagDescription\": \"\"\n    },\n    {\n        \"id\": 3,\n        \"name\": \"Higiene\",\n        \"hasChildren\": true,\n        \"url\": \"https://lojadobreno.vtexcommercestable.com.br/higiene\",\n        \"children\": [\n            {\n                \"id\": 14,\n                \"name\": \"Areia\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/higiene/areia\",\n                \"children\": [],\n                \"Title\": \"Areia para Gatos\",\n                \"MetaTagDescription\": \"\"\n            },\n            {\n                \"id\": 15,\n                \"name\": \"Caixa de Areia\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/higiene/caixa-de-areia\",\n                \"children\": [],\n                \"Title\": \"Caixa de Areia para Gatos\",\n                \"MetaTagDescription\": \"\"\n            },\n            {\n                \"id\": 16,\n                \"name\": \"Pá Higiênica\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/higiene/pa-higienica\",\n                \"children\": [],\n                \"Title\": \"Pá Higiênica para Gatos\",\n                \"MetaTagDescription\": \"\"\n            },\n            {\n                \"id\": 17,\n                \"name\": \"Tesoura de Unhas\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/higiene/tesoura-de-unhas\",\n                \"children\": [],\n                \"Title\": \"Tesoura de Unhas para Gatos\",\n                \"MetaTagDescription\": \"\"\n            },\n            {\n                \"id\": 18,\n                \"name\": \"Escova\",\n                \"hasChildren\": false,\n                \"url\": \"https://lojadobreno.vtexcommercestable.com.br/higiene/escova\",\n                \"children\": [],\n                \"Title\": \"Escova para Gatos\",\n                \"MetaTagDescription\": \"\"\n            }\n        ],\n        \"Title\": \"Higiene para Gatos\",\n        \"MetaTagDescription\": \"\"\n    },\n    {\n        \"id\": 4,\n        \"name\": \"Arranhadores\",\n        \"hasChildren\": false,\n        \"url\": \"https://lojadobreno.vtexcommercestable.com.br/arranhadores\",\n        \"children\": [],\n        \"Title\": \"Arranhadores para Gatos\",\n        \"MetaTagDescription\": \"\"\n    },\n    {\n        \"id\": 5,\n        \"name\": \"Caixas de Transporte\",\n        \"hasChildren\": false,\n        \"url\": \"https://lojadobreno.vtexcommercestable.com.br/caixas-de-transporte\",\n        \"children\": [],\n        \"Title\": \"Caixas de Transporte de Gatos\",\n        \"MetaTagDescription\": \"\"\n    },\n    {\n        \"id\": 20,\n        \"name\": \"teste\",\n        \"hasChildren\": false,\n        \"url\": \"https://lojadobreno.vtexcommercestable.com.br/teste\",\n        \"children\": [],\n        \"Title\": null,\n        \"MetaTagDescription\": \"teste\"\n    },\n    {\n        \"id\": 21,\n        \"name\": \"teste\",\n        \"hasChildren\": false,\n        \"url\": \"https://lojadobreno.vtexcommercestable.com.br/teste\",\n        \"children\": [],\n        \"Title\": \"aaaa\",\n        \"MetaTagDescription\": \"teste\"\n    }\n]",
      "language": "json"
    }
  ]
}
[/block]
## Authentication

This is a public API, so it does not need credentials to access.