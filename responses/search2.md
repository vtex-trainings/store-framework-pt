# Ajustando layout da página de busca

**BRANCH:** search2

## Introdução  

No último step conhecemos a página de busca e seus principais componentes. Também aprendemos que o layout de search funciona como qualquer outro bloco tendo, portanto, toda a flexibilidade ao seu alcance. Nesse step criaremos algumas linhas e colunas para melhorar a aparência da busca criada. 

## Atividade

![image](https://user-images.githubusercontent.com/18701182/69843559-db088200-1246-11ea-8873-8651dd973be9.png)

1. Remova `total-products.v2` e `order-by.v2` do `search-result-layout.desktop`. 

2. Substitua ambos acima por uma linha de topo que inclua os blocos removidos:
  ```
  "flex-layout.row#top": { 
      "children": [
        "total-products.v2",
        "order-by.v2"
      ]
  }
  ```
3. Remova o `search-content` e o `filter-navigator.v3` do `search-result-layout.desktop` e crie uma linha de resultados 

4. Na linha de resultado coloque outras duas colunas:
```
{
  ...
  "search-result-layout.desktop": {
    "children": [
      "breadcrumb.search",
      "search-title.v2",
      "flex-layout.row#top",
      "search-fetch-previous",
      "flex-layout.row#results",
      "search-fetch-more"
    ],
    "props": {
      "pagination": "show-more"
    }
  },
  "flex-layout.row#results": { 
    "children": [ 
      "flex-layout.col#filter",
      "flex-layout.col#search"
    ]
  },
  ...
}
```

5. Na coluna da esquerda inclua o `filter-navigator.v3` novamente e, na da direita, inclua o `search-content`  

Para finalizar, vamos usar o mesmo **Resumo de Produto**(`product-summary`) que usamos na shelf para exibir os resultados de busca.

6. Defina seu `search-content` com os blocos `gallery` e `not-found`:

```
{
  ...
  "search-content": { 
    "blocks": ["gallery", "not-found"]
  }
  ...
}
```

7. Use o `product-summary.shelf` nas props da Gallery:
```
{
  ...
  "search-content": { 
    "blocks": ["gallery", "not-found"]
  },
  "gallery": {
    "blocks": ["product-summary.shelf"]
  }
  ...
}
```

----

Se ainda tiver dúvida sobre como enviar sua resposta, você pode rever [aqui](https://github.com/{{ user.username }}/store-framework/issues/2).


