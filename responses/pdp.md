# Página de produto

**BRANCH:** pdp1

## Introdução

Terminada a página inicial da nossa loja, começamos um novo template da loja: a página de produto. Páginas de produto são provavelmente o template que mais possuem blocos diferentes, o que as torna extremamente customizáveis e flexíveis. 

## MVP

Vamos então construir uma página de produto mínima, em que tenhamos somente o essencial: 

 - **imagens;**
 - **preço;**
 - **nome;**
 - **botão de comprar**

![image](https://user-images.githubusercontent.com/18701182/69375575-6b632780-0c87-11ea-85d2-41e1e858a33e.png)

## Blocos de produto

A maioria dos blocos de produto, diferentemente dos de conteúdo, possuem um contexto ao qual estão inseridos. Tudo isso faz com que esses blocos sejam um pouco "plug-n-play": colocar um `product-images` na página de produto, automaticamente redenrizará as imagens do produto da página, da mesma forma se faz com o preço e o nome. 

Nada disso quer dizer, no entanto, que esses blocos são pouco customizáveis, conforme veremos adiante.

## Atividade

Construa uma página de produto usando os blocos `product-images`, `product-price`, `product-name` e `buy-button`. Esperamos que na estrutura tenhamos:  

1. Uma **linha** na `store.product`;
```
{
 "store.product": {
    "children": [
      "flex-layout.row#main"
    ]
  }
}
```
2. Dentro da **linha** devem haver **duas colunas**;
```
"flex-layout.row#main": { 
  "props": { 
    "marginTop": 6
  },
  "children": [
    "flex-layout.col#left",
    "flex-layout.col#right"
  ]
}
```
3. Dentro da coluna da esquerda deve haver um [`product-images`](https://vtex.io/docs/components/all/vtex.store-components/product-images); 
```
"flex-layout.col#left": { 
  "children": [ 
    "product-images"
  ]
}
```
4. Dentro da coluna da direita deve haver o [`product-name`](https://vtex.io/docs/components/all/vtex.store-components/product-name), [`product-price`](https://vtex.io/docs/components/all/vtex.store-components/product-price) e o `buy-button`;

Além disso, queremos que:

1. A coluna da direita esteja verticalmente alinhada ao centro (veja as props `verticalAlign` e `preventVerticalStrech` na [documentação de Flex Layout Column](https://vtex.io/docs/app/vtex.flex-layout#flex-layoutcol))
2. O [`product-price`](https://vtex.io/docs/components/all/vtex.store-components/product-price#configuration) mostre o total de economia e o preço de listagem (`showSavings` e `showListPrice`)

----

Se ainda tiver dúvida sobre como enviar sua resposta, você pode rever [aqui](https://github.com/{{ user.username }}/store-framework/issues/2).