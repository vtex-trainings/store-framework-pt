# Rich Text 

**BRANCH:** rich-text-image

## Introdução

A página inicial de um e-commerce é sempre o primeiro contato do cliente com a marca. Por isso, é comum que o lojista queira estabelecer uma comunicação direta com os seus usuários nesse momento estratégico da navegação. 

No Store Framework, existem alguns componentes que atendem a esse cenário, como o [Info Card](https://vtex.io/docs/components/all/vtex.store-components/info-card) visto nos passos anteriores e o [Rich Text](https://vtex.io/docs/components/all/vtex.rich-text/). 

Como vimos no [terceiro passo](https://github.com/{{ user.username }}/store-framework/issues/3), o Rich Text é responsável por transformar textos em elementos HTML, com a grande vantagem de ler em [Markdown](https://www.markdownguide.org/). Isso dá ao componente a flexibilidade de aceitar diferentes estruturas de texto, permitindo ao lojista construir sua comunicação de forma mais clara e direta. 

## Configurando o Rich Text

Assim como a sua funcionalidade, a configuração do Rich Text também é simples. 

Da mesma forma que o "*Hello, world!*" foi feito, podemos montar um exemplo de implementação do bloco usando texto escrito em markdown. Por exemplo:

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

Por exemplo: a frase acima ( `# Your Coffee, Your Way \n ### New Coffee Makers Collection` ) pode usar um markdown adequado para desktop, mas não necessariamente para mobile cujo tamanho de tela é menor. 

Para resolver esse cenário e tornar o componente mais adaptável a outros dispositivos, vamos usar o [Responsive Layout](https://vtex.io/docs/components/layout/vtex.responsive-layout):

```
{
"store.home": {
"responsive-layout.desktop#testing",
"responsive-layout.mobile#testing"
]
},

"responsive-layout.desktop#testing": {
"children": ["rich-text#desktop"]
},
"responsive-layout.mobile#testing": {
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
},
```

## Atividade

Nessa tarefa, vamos brincar um pouco com o markdown do [Rich Text](https://vtex.io/docs/components/all/vtex.rich-text/) e aprender a usá-lo com o componente [Image](https://vtex.io/docs/components/all/vtex.store-components/image).

IMAGEM QUE QUEREMOS  (GALC)

1. Copie o código acima para usá-lo no seu tema;
2. No Rich Text mobile, mude o markdown da primeira frase para `h3` e da segunda para `h4`. 
3. Adicione `image#desktop` como children de `responsive-layout.desktop#testing`. Faça o mesmo com `image#mobile`  em `responsive-layout.mobile#testing`. 
4. Declare os seguintes blocos de Image depois de `rich-text#mobile`: 

```
"image#desktop": {
"props": {
"src": "https://images.unsplash.com/photo-1442512595331-e89e73853f31?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2250&q=80",
"link": {
"url": "/small-appliances/coffee-makers"
} ,
"alt": "Coffee Makers Collection",
}
},

"image#mobile": {
"props": {
"src": "https://images.unsplash.com/photo-1560108878-8147b6c871d6?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1600&q=80",
"link": {
"url": "/small-appliances/coffee-makers"
} ,

"alt": "Coffee Makers Collection",
}
},
```

5. Analisando as props do componente Image, defina a largura máxima das duas imagens como `100%`
