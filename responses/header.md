# Header

**BRANCH:** header

## Introdução

Neste passo, aprenderemos a configurar o primeiro componente da página inicial de toda loja: o Header

O Header tem um papel fundamental, pois ele é responsável por abrigar outros componentes essenciais para a navegação do usuário, como a barra de busca e o menu. 

FOTO Header (galc)

## Configurando o Header

O bloco do Header é responsivo, ou seja, ele pode ser configurado para se adaptar a diferentes dispositivos, como desktop e mobile. 

Abaixo, podemos conferir um exemplo de implementação responsiva do Header:

```
{
"header.full": {
"blocks": [
"header-layout.desktop",
"header-layout.mobile"
]
},

"header-layout.desktop": {
"children": [
"header-row#notification",
"header-row#main"
]
},

"header-layout.mobile": {
"children": [
"header-row#notification",
"header-row#main-mobile",
"header-row#search"
]
},

```

## Atividade

Agora, vamos configurar do zero um Header para a página inicial da sua loja, levando em consideração o código exemplo apresentado acima para desktop e mobile.  

O Menu não será implementado nesse momento no Header, pois trabalharemos com ele mais a fundo na próxima atividade. 

1. Copie o código acima para usá-lo no seu tema;
2. Declare o seguinte bloco em seguida:

```
"header-row#notification": {
"children": [
"header-spacer",
"rich-text#header",
"header-spacer"
]
},
```
3. Com base no bloco acima, construa o `header-row#main` com as seguintes children: `logo`, `header-spacer`, `search-bar`, `minicart` e `login`. 
4. Ainda no bloco `header-row#main`, declare as props `inverted`, `sticky` e `fullWidth` com os valores `true`, `true` e `false`, respectivamente. 
5. Copie e cole o código abaixo para configurar o bloco header para mobile, da mesma forma que fizemos para o desktop anteriormente:

```
"header-row#main-mobile": {
"children": [
"logo",
"header-spacer",
"minicart",
"login"
],

"props": {
"sticky": true,
"inverted":true
}
},

"header-row#search": {
"children": [
"search-bar"
],
"props": {
"sticky": true
}
},

```

6.  Declare o bloco responsável por definir o login e o logo da loja, usando o código apresentado abaixo. Eles serão usados pelo Header dos dois dispositivos. 

```
"login":{
"props": {
"showIconProfile": true,
"iconLabel": "Login"
}
},

"logo":{
"props": {
"url": "https://appliancetheme.vteximg.com.br/assets/vtex.file-manager-graphql/images/flatflat___6081e50402943bcb11bc45a8e613aa72.png"
}
},
```

7.  Por último, precisamos declarar o componente principal da linha do Header de notificação (`"header-row#notification"`): o Rich Text. 

```
"rich-text#header": {
"props": {
"text": "**Free Shipping on orders over $50**",
"textPosition": "CENTER"
}
}
}
```


