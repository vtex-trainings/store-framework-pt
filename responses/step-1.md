# First block: Info Card

**BRANCH:** infocard

## Introdução

Nosso percurso de montagem começa pela página principal. Uma loja precisa de uma boa *home page* para manter a atenção do usuário, aumentando o tempo de sessão e, portanto, aumentando as chances de conversão. Para que isso seja possível, vários elementos podem ser usados, como: banners promocionais, prateleiras de destaque, conteúdos institucionais.  

Criaremos o primeiro bloco na *home page* usando um *Call to Action*. No Store Framework, temos um bloco que serve para esse propósito chamado **Info Card**. 

## Info Card

![image](https://user-images.githubusercontent.com/18701182/68480411-7b085800-0213-11ea-9426-31dcb0d0aa7d.png)

O Info Card é somente um das dezenas de blocos disponíveis no Store Framework. Com ele é possível criar imagens que, no topo ou ao lado, existam links ou botões que direcionem o fluxo do usuário (*Call to Action*). 

Olhando a [documentação](https://vtex.io/docs/app/vtex.store-components/info-card#blocks-api) do bloco é possível encontrar a especificação técnica. Uma das seções presentes é a de **Blocks API** nela é vista toda a lista de **propriedades *(props)*** que o Info Card possui. As propriedades são o principal **argumento de customização** de um componente, são elas que garantem que um mesmo bloco possa ter visual e comportamento completamente diferente, dependendo de como for configurado.

## Começando

Vamos então começar a personalizar a *home page*. No seu tema é possível encontrar um arquivo chamado `blocks.jsonc` na pasta `store/`. Neste arquivo é determinada a organização dos blocos que se deseja usar. A linguagem para composição do layout é simples e baseada em [JSON](http://www.json.org/json-pt.html).

No `blocks.jsonc` se ver um bloco que é padrão em todos os temas: `store.home`. Este bloco determina os blocos filhos que estarão expostos na *home page*. 

```
  {
    "store.home": {
      blocks: [

      ]
    }
    ...
  }
```

Vamos então incluir o Info Card em seu corpo:

```
  {
    "store.home": {
      "blocks": [
        "info-card"
      ]
    }
    ...
  }
```

Dessa forma, o `store.home` agora sabe que precisará renderizar um Info Card. Todavia, ainda não especificamos qual o visual desse Info Card. Para isso, precisamos fazer uma **definição de bloco**.

## Definição de blocos

A definição de blocos deve ser sempre feita fora de qualquer outro bloco, no nível da raiz do arquivo JSON.

```
  {
    "store.home": { 
      "blocks": [
        "info-card" <----- Aqui o bloco está dentro de outro 
      ]
    },
    "info-card": { <----- Aqui estamos na raiz
    }
  }
```

Na definição é possível determinar o comportamento e visual de um bloco. Para tal devem ser usados **argumentos de customização**, começaremos usando as `props` do Info Card:

```
  {
    "store.home": { 
      "blocks": [
        "info-card"
      ]
    },
    "info-card": {
      "props": { 

      }
    }
  }
```

Observe novamente a [documentação](https://vtex.io/docs/app/vtex.store-components/info-card#blocks-api) do Info Card e vamos, então, definir as props que usaremos para customizá-lo, queremos chegar a este:

![image](https://user-images.githubusercontent.com/18701182/68485077-57e2a600-021d-11ea-8e34-650d82f4adbc.png)

Olhando na [documentação](https://vtex.io/docs/app/vtex.store-components/info-card#blocks-api) vê-se que: 
- `isFullModeStyle` define que o *Call to Action* deve estar acima do banner;
- `textPosition` alinhará o texto a esquerda;
- `imageUrl` definirá qual imagem será usada como banner;
- `headline` determinará qual o texto que será usado;
- `callToActionMode` possibilitará a escolha de *Call to Action* como sendo um link;
- `callToActionText` definirá o texto do link;
- `callToActionUrl` determinará o link ao qual será redirecionado;
- `textAlignment` definirá a formatação do texto

Ficamos, assim, com as seguintes props:

```
  {
    "store.home": { 
      "blocks": [
        "info-card"
      ]
    },
    "info-card": {
      "props": { 
        "isFullModeStyle": ...,
        "textPosition": ...,
        "imageUrl": ...,
        "headline": ...,
        "callToActionMode": ...,
        "callToActionText": ...,
        "callToActionUrl": ...,
        "textAlignment": ...
      }
    }
  }
```

## Ação

Defina os `...` no código acima e submeta sua solução para que possamos seguir para o próximo passo. 

Se ainda tiver dúvida sobre como enviar sua resposta, você pode rever [aqui]().