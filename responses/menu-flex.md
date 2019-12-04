# Menu avançado com Flex Layout

## :sparkles: **Branch:** menuflex

## Introdução 

Como vimos no último passo, um Submenu aceita como *children* qualquer bloco do Store Framework.  

A partir desse entendimento, podemos melhorar a configuração do Menu feita na atividade anterior, incrementando seu conteúdo com o uso do [**Flex Layout**](https://vtex.io/docs/components/layout/vtex.flex-layout). 

## Atividade

De acordo com o que foi praticado na atividade anterior e o que foi aprendido sobre Flex Layout na atividade pipipipopopo, vamos aplicar o Flex Layout no Submenu de *Major Appliance*. 

1. Substitua `vtex.menu@2.x:menu#major` por `flex-layout.row#major` na lista de *children* do bloco `vtex.menu@2.x:submenu#major`;
2. Defina em seguida o bloco `flex-layout.row#major`: 

```
"flex-layout.row#major": {
  "children": [
    "flex-layout.col#menu",
    "flex-layout.col#img"
  ]
},
```
3. Agora temos que declarar os blocos definidos em  `flex-layout.row#major`. Para começar, declare o bloco `flex-layout.col#menu` com `vtex.menu@2.x:menu#major` como *children*;
4. Faça o mesmo para o bloco `flex-layout.col#img`, o declarando com `image#menu` e `rich-text#header` como *children* e as seguintes props:

```
"props":{
  "paddingRight": 4,
  "horizontalAlign": "right"
 }
```

5. Por último, vamos declarar o `image#menu` passado como *children* no último passo. Para isso, use o código abaixo: 

```
"image#menu": {
  "props": {
    "src": "https://appliancetheme.vteximg.com.br/arquivos/menu-washer.jpg",
    "link": {
      "url": "/small-appliances/coffee-makers"
    },
    "alt": "Coffee Makers Collection",
    "maxWidth": "200px"
  }
}
```
