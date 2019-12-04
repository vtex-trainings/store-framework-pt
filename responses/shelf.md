# Prateleira de produtos

## :sparkles: **Branch:** shelf

## Introdução

O próximo bloco que vamos utilizar é a Shelf, a nossa prateleira para uma coleção de produtos. Nessa sessão vamos aprender a renderizar e configurar essa prateleira na home da nossa loja.

## Shelf

Analisando a documentação da [Shelf](https://vtex.io/docs/app/vtex.shelf), vemos que é possível configurar qual coleção de produtos queremos mostrar através das props `category`, `specificationFilters` ou `collection`, de acordo com os produtos cadastrados no catálogo.

As demais props são para configuração na maneira com que os items são mostrados. É importante notar que o componente `shelf` sempre pede que block do tipo `product-summary` faça parte da sua composição.

Abaixo, temos o exemplo da implementação de uma Shelf:

```json
{
  "store.home": {
    "blocks": [
      ...
      "shelf"
    ]
  },
  ...
  "shelf": {
    "blocks": ["product-summary.shelf"],
    "props": {
      "category": 1,
      "orderBy": "OrderByTopSaleDESC",
      "paginationDotsVisibility": "desktopOnly",
      "productList": {
        "maxItems": 10,
        "itemsPerPage": 5,
        "minItemsPerPage": 1,
        "scroll": "BY_PAGE",
        "arrows": true,
        "titleText": "Top sellers"
      }
    }
  },
  "product-summary.shelf": {
    "children": [
      "product-summary-image",
      "product-summary-add-to-list-button",
      "product-summary-name",
      "product-rating-inline",
      "product-summary-space",
      "product-summary-price",
      "product-identifier.summary",
      "product-summary-buy-button"
    ]
  }
}
```

## Atividade

1. Declare um componente `shelf` no `store.home`
2. Dentro da pasta blocks, crie um arquivo `shelf.jsonc`
3. No arquivo `shelf.jsonc`, defina o objeto `shelf` conforme o exemplo acima
4. Altere o número máximo de itens exibidos para `8`
5. Altere o número de itens por página para `4`

----

Se ainda tiver dúvida sobre como enviar sua resposta, você pode rever [aqui](https://github.com/{{ user.username }}/store-framework/issues/2).