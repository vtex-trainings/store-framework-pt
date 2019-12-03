# Flex Layout: crie layouts utilizando o poder do Flexbox

**BRANCH:** flexlayout

## Introdução

O Flex Layout é um paradigma de estruturação de layout criado no Store Framework para permitir a construção de layouts complexos. Esse paradigma usa o conceito de **linhas** e **colunas** para definir a estrutura e o posicionamento desejados dos componentes em uma determinada página.

Existem dois blocos de construção básicos de cada Flex Layout:

- `flex-layout.row`
- `flex-layout.col`

Se você já está familiarizado com o Flexbox utilizado no CSS, o Flex Layout deve ser simples de entender, já que o Flexbox está sendo utilizar "por debaixo dos panos" pelo flex-layout.row e flex-layout.col.

## Flex Layout

Com o [Flex Layout](https://vtex.io/docs/components/layout/vtex.flex-layout) é possível criar layouts personalizados, utilizando a estrutura de linhas e colunas do Flexbox.

Analisando a [documentação](https://vtex.io/docs/components/layout/vtex.flex-layout), vemos que você pode utilizar qualquer *array* de blocos como `children` do Flex Layout. Além disso, você deve sempre usar `flex-layout.row` e `flex-layout.col`, **NUNCA** `flex-layout` de forma isolada.


Abaixo, temos um exemplo de implementação do `flex-layout.row` com dois *childrens*: um `info-card` e um `rich-text`:

```
{
  "store.home": {
    "blocks": [
      "flex-layout.row"
    ]
  },
  "flex-layout.row":{
    "children": [
      "info-card",
      "rich-text"
    ]
  },
  "info-card": {
    "props": {
      "imageUrl": "https://images.unsplash.com/photo-1524185962737-ea7c028a12cd?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80",
      "isFullModeStyle": true,
      "headline": "Black Friday",
      "callToActionText": "Subscribe",
      "textPosition": "center"

    }
  },
  "rich-text": {
    "props": {
      "text": "I'll be deleted soon"
    }
  }
}
```

## Atividade

1. Copie o código acima;
2. Faça com que o `rich-text` não apareça mais como componente do `flex-layout.row`;
3. Adicione um `flex-layout.col` como *children* do `flex-layout.row`;
4. Dentro do `flex-layout.col`, declare dois componentes `image` como `image#electronics` e `image#major-appliance`
5. Declare as seguintes props abaixo do objeto do `flex-layout.col`:

```
"image#electronics": {
    "props": {
      "src": "https://appliancetheme.vteximg.com.br/assets/vtex.file-manager-graphql/images/electronics_banner___25d69b49f8224b369375e68513b4d593.png",
      "maxWidth": "100%"
    }
  },
  "image#major-appliance": {
    "props": {
      "src": "https://appliancetheme.vteximg.com.br/assets/vtex.file-manager-graphql/images/major_appliance_banner___bb10093866a127345ddfbcca3efa5022.png",
      "maxWidth": "100%"
    }
  }
```

----

Se ainda tiver dúvida sobre como enviar sua resposta, você pode rever [aqui](https://github.com/{{ user.username }}/store-framework/issues/2).