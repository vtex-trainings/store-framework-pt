# Tornando seu conteúdo responsivo

## :sparkles: **Branch:** responsiveimage

## Introdução

A página inicial de um e-commerce é sempre o primeiro contato do cliente com a marca. Por isso, é comum que o lojista queira estabelecer uma **comunicação direta** com os seus usuários nesse momento estratégico da navegação. 

No Store Framework, existem alguns componentes que atendem a esse cenário, como o [Info Card](https://vtex.io/docs/components/all/vtex.store-components/info-card) visto nos passos anteriores e o [**Rich Text**](https://vtex.io/docs/components/all/vtex.rich-text/). 

Como vimos no [terceiro passo](https://github.com/{{ user.username }}/store-framework/issues/3), o Rich Text é responsável por transformar textos em elementos HTML, com a grande vantagem de ler em [**Markdown**](https://www.markdownguide.org/). Isso dá ao componente a flexibilidade de aceitar diferentes estruturas de texto, permitindo ao lojista construir sua comunicação de forma mais clara e direta. 

## Configurando o Rich Text

Assim como a sua funcionalidade, a configuração do Rich Text também é simples. 

Da mesma forma que o "**Hello, world!**" foi feito, podemos montar um exemplo de implementação do bloco usando texto escrito em markdown. Por exemplo:

```
"rich-text": {
  "props": {
    "text": "# Your Coffee, Your Way \n ### New Coffee Makers Collection",
    "textPosition": "CENTER",
    "textAlignment": "CENTER"
  }
},
```

Como falado anteriormente, o uso de Markdown permite flexibilidade ao componente. Mas, por outro lado, também pode fazer com que a sua renderização sofra alterações de acordo com o dispositivo usado pelo usuário. 

Por exemplo: a frase acima ( `# Your Coffee, Your Way \n ### New Coffee Makers Collection` ) pode usar um markdown adequado para desktop, mas não necessariamente para mobile (cujo tamanho de tela é menor). 

Para resolver esse cenário e tornar o componente mais adaptável a outros dispositivos, devemos usar o [**Responsive Layout**](https://vtex.io/docs/components/layout/vtex.responsive-layout).

Primeiramente devemos delcarar os blocos dentro do template de home `store.home`:
`"responsive-layout.desktop#desktop",
 "responsive-layout.mobile#mobile"`

Em seguida devemos declarar esses blocos da seguinte forma:

```
"responsive-layout.desktop#desktop": {
  "children": ["rich-text#desktop"]
},

"responsive-layout.mobile#mobile": {
  "children": ["rich-text#mobile"]
},

"rich-text#desktop": {
  "props": {
    "text": "# Your Coffee, Your Way /n ### New Coffee Makers Collection",
    "textPosition": "CENTER",
    "textAlignment": "CENTER"
  }
},

"rich-text#mobile": {
  "props": {
    "text": "# Your Coffee, Your Way /n ### New Coffee Makers Collection",
    "textPosition": "CENTER",
    "textAlignment": "CENTER"
  }
}
```

Ao interpretar o código acima, perceba como duas configurações de Rich Text são construídas a partir do uso de `responsive-layout.desktop#desktop` e `responsive-layout.mobile#mobile`. 

## Atividade

Nessa tarefa, vamos brincar um pouco com o markdown do [Rich Text](https://vtex.io/docs/components/all/vtex.rich-text/) e aprender a usá-lo com o componente [Image](https://vtex.io/docs/components/all/vtex.store-components/image). Tudo isso usando o Responsive Layout, é claro!

### Desktop:

![image](https://user-images.githubusercontent.com/12139385/70152049-414c3500-168b-11ea-8da3-4f4ce0f5fee6.png)


### Mobile:

![image](https://user-images.githubusercontent.com/12139385/70152185-84a6a380-168b-11ea-861e-9282ac024936.png)


1. Copie o código acima para usá-lo na página inicial do seu tema;
2. No Rich Text mobile, mude o markdown da primeira frase para `h3` e da segunda para `h4`;
3. Adicione `image#desktop` como children de `responsive-layout.desktop#desktop`. Faça o mesmo com `image#mobile`  em `responsive-layout.mobile#mobile`;
4. Declare os seguintes blocos de Image depois de `rich-text#mobile`: 

```
"image#desktop": {
  "props": {
    "src": "https://appliancetheme.vteximg.com.br/arquivos/Responsive-Image-Desktop.jpg?q=1",
    "link": {
      "url": "/small-appliances/coffee-makers"
    } ,
    "alt": "Coffee Makers Collection",
  }
},

"image#mobile": {
  "props": {
  "src": "https://appliancetheme.vteximg.com.br/arquivos/Responsive-Image-Mobile.jpg?q=1",
  "link": {
    "url": "/small-appliances/coffee-makers"
  } ,
  "alt": "Coffee Makers Collection"
}
},

```

5. Analisando as props do componente Image, defina a largura máxima das duas imagens como `100%`.
