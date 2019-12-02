# Footer

**BRANCH:** footer

## Introdução

Neste passo, iremos aprender como criar um componente que é comumente visto como pouco relevante, mas que é fundamental para dar uma boa experiência ao buyer: o footer.

Poucos usuários chegam a scrollar até o footer. Porém, essa parcela que chega pode estar procurando informações que usualmente são abrigadas neste bloco, como links para mídias sociais e meios de pagamento aceitos pela loja. Ele também pode abrigar páginas customizadas que direcionam ao site de vagas da empresa, suporte ao cliente e menus de categorias.

FOTO Footer

## Configurando o Footer

O bloco do Footer assim como o do header é responsivo, ou seja, ele pode ser configurado para se adaptar a diferentes dispositivos, como desktop e mobile.

Abaixo, podemos conferir um exemplo de implementação somente desktop do Footer:

```json
{
  "footer": {
    "blocks": ["footer-layout.desktop"]
  },
  "footer-layout.desktop": {
    "children": [
      "flex-layout.row#footer-1-desktop"
    ]
  }
}
```

## Atividade

Agora, vamos configurar um footer para a página inicial da sua loja, levando em consideração o código exemplo apresentado acima para desktop e mobile.

Não implementaremos o menu nessa atividade, pois ele já foi visto no contexto do Header. Iremos cobrir os casos de meios de pagamento aceitos e redes sociais da loja.

1. Copie o código acima para usá-lo no seu tema;
2. Declare o seguinte bloco em seguida:

```json
  "flex-layout.row#footer-1-desktop": {
    "children": [
      "flex-layout.col#footer-left-desktop",
      "flex-layout.col#footer-right-desktop"
    ],
    "props": {
      "blockClass": "footer-row",
      "paddingTop": 7,
      "paddingBottom": 7
    }
  }
```

1. Com base no bloco acima, construa o `flex-layout.col#footer-left-desktop` com a seguinte children: `accepted-payment-methods`.

2. Agora construa o bloco `accepted-payment-methods` com os seguintes meios de pagamento: `MasterCard`, `Visa` e `Diners Club`. Se precisar, consulte a documentação.

3. Copie e cole o código abaixo para configurar o bloco header para mobile, da mesma forma que fizemos para o desktop anteriormente:

