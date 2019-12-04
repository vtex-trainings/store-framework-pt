# Hello, World!

## :sparkles: **Branch:** richtext

## Introdução

Começamos nossa jornada pelo clássico **"Hello, World!"**. Para criar algo do tipo, precisamos conhecer os blocos do Store Framework e usar um que nos possibilite a criação de textos. Este bloco se chama **Rich Text**. 

## Rich Text

<img src="https://user-images.githubusercontent.com/18701182/68885337-be6f3480-06f3-11ea-99dd-7d33ad3777cb.png" width="150" />

O Rich Text é somente um das dezenas de blocos disponíveis no Store Framework. É um bloco que parece simples, mas que possibilita uma série de customizações para criar textos. Para começar, todo texto escrito no Rich Text suporta [linguagem Markdown](https://www.markdownguide.org/cheat-sheet/), isso faz com que a estilização do texto seja muito mais fácil. 

Olhando a [documentação](https://vtex.io/docs/app/vtex.rich-text#blocks-api) do bloco é possível encontrar a especificação técnica. Uma das seções presentes é a de **Blocks API** nela é vista toda a lista de **propriedades *(props)*** que o Rich Text possui. As propriedades são o principal **ponto de customização** de um bloco, são elas que garantem que um mesmo bloco possa ter visual e comportamento completamente diferente, dependendo de como for configurado.

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

Vamos então incluir o Rich Text em seu corpo:

```
  {
    "store.home": {
      "blocks": [
        "rich-text"
      ]
    }
    ...
  }
```

Dessa forma, o `store.home` agora sabe que precisará renderizar um Rich Text. Todavia, ainda não especificamos qual o visual desse Rich Text. Para isso, precisamos fazer uma **definição de bloco**.

## Definição de blocos

A definição de blocos deve ser sempre feita fora de qualquer outro bloco, no nível da raiz do arquivo JSON.

```
  {
    "store.home": { 
      "blocks": [
        "rich-text" <----- Aqui o bloco está dentro de outro 
      ]
    },
    "rich-text": { <----- Aqui estamos na raiz
    }
  }
```

Na definição é possível determinar o comportamento e visual de um bloco. Para tal devem ser usados **pontos de customização**, começaremos usando as `props` do Rich Text:

```
  {
    "store.home": { 
      "blocks": [
        "rich-text"
      ]
    },
    "rich-text": {
      "props": { 

      }
    }
  }
```

Observe novamente a [documentação](https://vtex.io/docs/app/vtex.rich-text#blocks-api) do Rich Text e vamos, então, definir as props que usaremos para customizá-lo. 

Queremos fazer um simples "Hello, World!", olhando nas props vemos uma que se chama: `text` [(Text written in markdown language to be displayed)](https://vtex.io/docs/app/vtex.rich-text#blocks-api). Essa é, então, a prop que determinará qual o texto que será exibido. 

Incluindo essa prop temos, então:

```
  {
    "store.home": { 
      "blocks": [
        "rich-text"
      ]
    },
    "rich-text": {
      "props": { 
        "text": "Hello, World!"
      }
    }
  }
```

Olhando a [documentação do Markdown](https://www.markdownguide.org/cheat-sheet/) vemos que para deixar *itálico* basta colocar `*` antes e depois do texto: 

```
  {
    "store.home": { 
      "blocks": [
        "rich-text"
      ]
    },
    "rich-text": {
      "props": { 
        "text": "*Hello, World!*"
      }
    }
  }
```

Para posicioná-lo ao centro, podemos adicionar `textPosition` [(*Choose in which position of the component text will be displayed, left, center or right. Default: "LEFT"*)](https://vtex.io/docs/app/vtex.rich-text#blocks-api) e atribuí-lo `CENTER`:

```
  {
    "store.home": { 
      "blocks": [
        "rich-text"
      ]
    },
    "rich-text": {
      "props": { 
        "text": "*Hello, World!*",
        "textPosition": "CENTER"
      }
    }
  }
```


## Atividade

Defina um `rich-text` na sua home e crie um texto "Hello, World!" em **negrito** e **posicionado à direita**. 

<img src="https://user-images.githubusercontent.com/18701182/68888503-d77ae400-06f9-11ea-967b-662fe1dac644.png" width="150" />

----

Se ainda tiver dúvida sobre como enviar sua resposta, você pode rever [aqui](https://github.com/{{ user.username }}/store-framework/issues/2).
