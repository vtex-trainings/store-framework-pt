# CSS Handles e o poder da customização de blocos

**BRANCH:** csshandles

## Introdução

Dando uma rápida olhada na sua loja atual, você conseguirá perceber que todos os componentes possuem estilos parecidos, mesmo que nenhuma customização tenha sido feita por você.  

Todos eles, incluindo o Info Card recém configurado, compartilham **valores pré-estabelecidos** para fonte, cor de fundo, cor principal, formato dos botões, etc.

Isso se deve ao `style.json`,  arquivo responsável por declarar valores genéricos de customização para toda loja do Store Framework. 

![style](https://user-images.githubusercontent.com/52087100/69889933-60854400-12d2-11ea-8d11-97aef0f3bf83.png)

Para criar uma identidade própria para os componentes da sua loja, você pode sobrescrever esses valores por meio de **customizações de CSS**.  

Analisando a [recipe](https://vtex.io/docs/recipes/style/using-css-handles-for-store-customization) para customizações de loja por CSS, percebemos que alguns passos serão necessários para aplicar o estilo próprio desejado por você, como:

1.  Criar um novo arquivo dentro da pasta `CSS` com o nome `vtex.{AppName}.css`
2.  Usar o CSS Handle do componente que será customizado dentro deste arquivo seguindo o formato abaixo:

```
.{CSSHandle} {  
{PropriedadeDeCSS}: {ValorDesejado};
{PropriedadeDeCSS}: {ValorDesejado};  
}
```
3. Na falta de CSS Handles, aplicar CSS Selectors permitidos, como é o caso do `:global(vtex-{AppName})`. 

4. Para aplicar CSS em um bloco específico e não a todos os blocos daquele tipo, usa-se o recurso de blockClass, que aparece ao lado dos handles de css ao inspecionar seu código. As blockClass devem ser declaradas como uma prop no bloco em questão, e então referenciado no arquivo de estilo como mostrado abaixo:

```
.{CSSHandle}--{blockClass} {  
{PropriedadeDeCSS}: {ValorDesejado};
{PropriedadeDeCSS}: {Val
orDesejado};  
}
```

## Customizando o Info Card 

Para descobrir os CSS Handles de um componente, como o Info Card, basta acessar a sessão `Customization` da sua [documentação](https://vtex.io/docs/components/all/vtex.store-components/info-card). 

De acordo com a descrição dos CSS Handles, conseguimos implementar um exemplo de Info Card customizado, alterando seu título e as configurações do botão call to action:

```
.infoCardHeadline {
    font-family: serif;
    font-size: 2.25rem;
    font-weight: normal;
    color: gray;
    border: 2px solid black;
    padding: 24px;
}

.infoCardContainer--vintage {
    background-color: #EDCFD1;
}

.infoCardCallActionContainer :global(.vtex-button) {
color: white;
background-color: gray;
border: transparent;
}

.infoCardCallActionContainer :global(.vtex-button):hover {
color: gray;
background-color: blue;
border: transparent;
}
```
Você pode conferir o efeito das mudanças feitas por você executando o comando `vtex link`.

Em seguida, vamos adicionar um estilo específico para o infocard Vintage.  Para começar, adicione a prop `blockClass` no `info-card#button-right` como mostrado abaixo:

  ```
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
        "textAlignment": "center",
        "blockClass": "vintage"     //  <------------
      }
    }
```
E então declare uma `background-color` para este infocard específico no seu arquivo de css:

```
  .infoCardContainer--vintage {
    background-color: #EDCFD1
}
```
Observe o efeito atingido linkando sua app.

## Atividade

1. Copie o código acima para usá-lo no arquivo CSS do seu tema, seguindo a [recipe](https://vtex.io/docs/recipes/style/using-css-handles-for-store-customization) sobre customizações de loja por CSS;
2. Com base nos Handles do [**Info Card**](https://vtex.io/docs/components/all/vtex.store-components/info-card), defina a largura máxima (`max-width`) de todo componente para `1260px`, a margin para `0 auto` e o padding para `0`.
3. Mude a cor do título do componente para `black`; 
4. Coloque o título em negrito (`bold`);
5. Mude a cor de fundo do botão durante o hover para `white`.
6. Paralelamente ao blockClass `vintage`, aplique um novo block class chamado `metal` no infocard `info-card#button-left` e aplique a cor de fundo `#e1e1e1`nele.


