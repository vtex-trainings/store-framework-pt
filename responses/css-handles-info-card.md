# CSS Handles e o poder da customização de blocos

**BRANCH:** css-handles

## Introdução

Dando uma rápida olhada na sua loja atual, você conseguirá perceber que todos os componentes possuem estilos parecidos, mesmo que nenhuma customização tenha sido feita por você.  

Todos eles, incluindo o Info Card recém configurado, compartilham valores pré-estabelecidos para os blocos quanto à fonte, cor de fundo, cor principal, ao formato dos botões, etc.

Isso se deve ao `style.json`,  arquivo responsável por declarar valores genéricos de customização para toda loja do Store Framework. 

![style](https://user-images.githubusercontent.com/52087100/69889933-60854400-12d2-11ea-8d11-97aef0f3bf83.png)

Para criar uma identidade própria para os blocos da sua loja, você pode sobrescrever esses valores por meio de **customizações de CSS**.  

Analisando a [recipe](https://vtex.io/docs/recipes/style/using-css-handles-for-store-customization) para customizações de loja por CSS, percebemos que alguns passos serão necessários para aplicar o estilo próprio desejado por você, como:

1.  Criar um novo arquivo dentro da pasta `CSS` com o nome `vtex.{AppName}.css`
2.  Usar o CSS Handle do componente que será customizado dentro deste arquivo seguindo o formato abaixo:

```css
.{CSSHandle} {  
{ClasseDeCSS1}: {ValorDesejado};
{ClasseDeCSS2}: {ValorDesejado};  
}
```
3. Na falta de CSS Handles, aplicar CSS Selectors permitidos, como é o caso do `:global(vtex-{AppName})`. 

## Customizando o Info Card 

Para descobrir os CSS Handles de um bloco, como o Info Card, basta acessar a sessão `Customization` da sua [documentação](https://vtex.io/docs/components/all/vtex.store-components/info-card). 

De acordo com a descrição dos CSS Handles, conseguimos implementar um exemplo de Info Card customizado, alterando seu título e as configurações do botão call to action:

```
.infoCardHeadline {
color: gray;
border: 2px solid gray;
font-size: 50px;
font-weight: 500;
background-color:#d7db8f;
padding: 10px;
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

## Atividade

1. Copie o código acima para usá-lo no arquivo CSS do seu tema, seguindo a [recipe](https://vtex.io/docs/recipes/style/using-css-handles-for-store-customization) sobre customizações de loja por CSS;
2. Com base nos Handles do [Info Card](https://vtex.io/docs/components/all/vtex.store-components/info-card), defina a altura (`height`) do bloco para `450px`;
3. Mude a cor do título do componente para `black`; 
4. Tirar o negrito do título, diminuindo o peso da sua fonte para `200`;
5. Mude a cor de fundo do botão durante o hover para `white`. 


