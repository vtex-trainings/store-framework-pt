# Evoluindo sua página de produto (pdp)

**BRANCH:** pdp2

## Introdução

No último passo aprendemos como fazer uma página de produto simples com seus itens mínimos, mas sabemos que o que fizemos está longe de ser uma página de produto ideal, colocaremos outros elementos que vemos com frequência nas páginas de produto de várias lojas.

![image](https://user-images.githubusercontent.com/18701182/69391258-002e4b00-0cb1-11ea-901f-f69d9c0b3062.png)

## Mais de 30 blocos de produto

Na [nossa documentação](https://vtex.io/docs/components/product-related) é possível encontrar mais 30 blocos relacionados a produto. No começo do curso falamos sobre Shelf e seus blocos relacionados, além de na última seção termos visto outros 4 blocos. Neste passo veremos mais 4: 

- Breadcrumb
- Product Identifier
- Product Quantity
- SKU Selector

É importante que ao fim do curso, você tome um tempo para explorar nossos componentes, bem como as possibilidades de customização que se tem com estes. 

## Atividade

Evolua a página de produto adicionando os outros 4 blocos listados acima da seguinte forma:

1. Defina um `breadcrumb` logo no início antes da **linha principal** do produto

```
"store.product": {
  "children": [
    "breadcrumb",
    "flex-layout.row#main"
  ]
}
```

2. Defina o `product-identifier.product` logo abaixo do `product-name`

3. Crie uma **linha** logo abaixo do preço com o `sku-selector` e o `product-quantity` como filhos

```
{
  ...
    "children": [ 
      "product-price",
      "flex-layout.row#qty-sku"
    ]
  },
  "flex-layout.row#qty-sku": { 
    "children": [
      "sku-selector",
      "product-quantity"
    ]
  },
  ...
}


```

4. Defina `shipping-simulator` logo abaixo da linha com o SKU Selector e o Product Quantity

----

Se ainda tiver dúvida sobre como enviar sua resposta, você pode rever [aqui](https://github.com/{{ user.username }}/store-framework/issues/2).