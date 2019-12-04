# Info Card: o call to action do Store Framework

## :sparkles: **Branch:** infocard

## Introdução

Uma loja precisa de uma boa *home page* para manter a atenção do usuário, aumentando o tempo de sessão e, portanto, aumentando as chances de conversão. Para que isso seja possível, vários elementos podem ser usados, como: banners promocionais, prateleiras de destaque, conteúdos institucionais.

Criaremos o próximo bloco na *home page* usando um *Call to Action*. No Store Framework, temos um bloco que serve para esse propósito chamado **Info Card**.

## Info Card

![image](https://user-images.githubusercontent.com/18701182/68480411-7b085800-0213-11ea-9426-31dcb0d0aa7d.png)

Com o [Info Card](https://vtex.io/docs/app/vtex.store-components/Info-Card#blocks-api) é possível criar imagens que, no topo ou ao lado, existam links ou botões que direcionem o fluxo do usuário (*Call to Action*).

Olhando a [documentação](https://vtex.io/docs/app/vtex.store-components/info-card#blocks-api) é possível ver que:

- `isFullModeStyle` define se o *Call to Action (CTA)* deve estar acima do banner;
- `textPosition` definirá a posição do texto;
- `textAlignment` definirá o alinhamento do texto;
- `imageUrl` definirá qual imagem será usada como banner;
- `headline` determinará qual o texto que será usado de título;
- `callToActionMode` possibilitará a escolha do *CTA* como sendo um link ou um botão;
- `callToActionText` definirá o texto do *CTA*;
- `callToActionUrl` determinará o link ao qual será redirecionado;

Ficamos, assim, com as seguintes props:

```json
  {
    "store.home": {
      "blocks": [
        "rich-text",
        "info-card",
      ]
    },
    "rich-text": {
      "props": {
        "text": "*Hello, World!*",
        "textPosition": "RIGHT"
      }
    },
    "info-card": {
      "props": {
      "isFullModeStyle": false,
      "textPosition": "right",
      "imageUrl": "https://appliancetheme.vteximg.com.br/arquivos/cozinha-rosa-min.png",
      "headline": "Vintage Pink",
      "subhead": "Give your kitchen a boho style adding vintage apparels.<br>Available until January 2020.",
      "callToActionMode": "button",
      "callToActionText": "Explore",
      "callToActionUrl": "/sale/d",
      "textAlignment": "center"
      }
    }
  }
```

## Instanciando blocos

Pode ser que você tenha se perguntado: 
> "E se eu quiser ter dois Info Cards com aparências diferentes?" 

Isso é possível através da **instanciação de blocos**.

Todos os blocos têm nomes preestabelecidos, mas você pode criar instâncias deles e definir aparências diferentes para um mesmo tipo de bloco. Para fazer isso, basta colocar um `#` com um nome **arbitrário** e que faça sentido depois da definição de cada bloco, por exemplo:

```json
  {
    "store.home": {
      "blocks": [
        "rich-text"
        "info-card#button-right",
      ]
    },
    ...
    "info-card#button-right": {
      "props": {
        "isFullModeStyle": false,
        "textPosition": "right",
        "imageUrl": "https://appliancetheme.vteximg.com.br/arquivos/cozinha-rosa-min.png",
        "headline": "Vintage Pink",
        "subhead": "Give your kitchen a boho style adding vintage apparels.<br>Available until January 2020.",
        "callToActionMode": "button",
        "callToActionText": "Explore",
        "callToActionUrl": "/sale/d",
        "textAlignment": "center"
      }
    }
  }
```

> **ATENÇÃO:** Durante o curso serão vistos vários `...`, essa parte não deve ser copiada e representa o progresso de steps anteriores

## Atividade

Copie o código acima, crie um `info-card#button-left` depois do `info-card#button-right`, que tenha um botão e seja exibido como a imagem abaixo:

![image](https://appliancetheme.vteximg.com.br/arquivos/info-card-activity.png)

**DICA**: Utilize a imagem a seguir para compor o seu `info-card#button-left`: 

`https://appliancetheme.vteximg.com.br/arquivos/cozinha-cinza-min.png`

----

Se ainda tiver dúvida sobre como enviar sua resposta, você pode rever [aqui](https://github.com/{{ user.username }}/store-framework/issues/2).