# Finalizando a página de produto

**BRANCH:** pdp3

## Introdução

Neste passo vamos terminar de montar a nossa página de produto. Aprenderemos como empilhar blocos usando o **Stack Layout**, como sugerir produtos similares e como customizar melhor o SKU Selector para produtos com imagem de SKU. 

![image](https://user-images.githubusercontent.com/18701182/69393219-50a8a700-0cb7-11ea-8718-c5ec0536cbe2.png)


## Stack Layout

O `stack-layout` é um tipo layout que possibilita que blocos possam ser empilhados sobre outros. É muito útil quando se deseja colocar algum badge em cima de uma imagem ou produto. Também é útil para compor textos compostos sobre imagens (usando um `rich-text` e uma `image`). 

![image](https://user-images.githubusercontent.com/18701182/69392819-0a9f1380-0cb6-11ea-8238-1e2e75b9eee9.png)

(Na imagem, uma shelf empilhada sobre um carrossel :point_up_2:)

Neste passo, usaremos o `stack-layout` para colocar a marca sobre as imagens de produto. 

## Atividade

1. Declare um `shelf.relatedProducts` abaixo da **linha principal** de produto

```
"store.product": {
  "children": [
    "breadcrumb",
    "flex-layout.row#main",
    "shelf.relatedProducts"
  ]
}
```

2. Troque `product-images` na coluna da esquerda por uma declaração de `stack-layout`

```
"flex-layout.col#left": { 
  "children": [ 
    "stack-layout#brand"
  ]
}
```

3. Defina o `stack-layout` e coloque como filhos o `product-images` e `product-brand`

```
"stack-layout#brand": { 
  "children": [
    "product-images",
    "product-brand"
  ]
}
```

4. Consulte a [documentação](https://vtex.io/docs/components/product/vtex.store-components/product-brand#configuration) para mudar a forma que o `product-brand` é exibido. Você deve fazer o logo aparecer e com altura de **30**. 

5. Consulte a [documentação](https://vtex.io/docs/components/product/vtex.store-components/sku-selector) para fazer com que o `sku-selector`: 
- comece sem nenhum SKU selecionado, 
- mostre o nome por variação de sku, 
- mostre erro se nenhuma variação de sku for selecionada

----

Se ainda tiver dúvida sobre como enviar sua resposta, você pode rever [aqui](https://github.com/{{ user.username }}/store-framework/issues/2).
