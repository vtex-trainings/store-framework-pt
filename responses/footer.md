# Rodapé

## :sparkles: **Branch:** footer

## Introdução

Neste passo, iremos aprender como criar um componente que é comumente visto como pouco relevante, mas que é fundamental para dar uma boa experiência ao usuário: o [footer](https://vtex.io/docs/components/all/vtex.store-footer/).

Poucos usuários chegam a scrollar até o footer. Porém, essa parcela que chega pode estar procurando informações que usualmente são abrigadas neste bloco, como links para mídias sociais e meios de pagamento aceitos pela loja. Ele também pode abrigar páginas customizadas que direcionam ao site de vagas da empresa, suporte ao cliente e menus de categorias.

FOTO Footer

## Configurando o Footer

O bloco do Footer, assim como o do header, é responsivo. Isso significa que ele pode ser configurado para se adaptar a diferentes dispositivos, como desktop e mobile.

Abaixo, podemos conferir um exemplo de implementação do Footer para desktop:

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

3. Com base no bloco acima, construa o `flex-layout.col#footer-left-desktop` com a seguinte children: `accepted-payment-methods`;

4. Agora construa o bloco `accepted-payment-methods` com os seguintes meios de pagamento: `MasterCard`, `Visa` e `Diners Club`. Só para mostrar um pouco mais de conhecimento, descubra também como mostrar os meios de pagamento em cores;

5. No próximo passo iremos usar o bloco `social-networks` para mostrar as redes sociais da nossa loja. Veja na documentação como fazer isso. E implemente como children do bloco `flex-layout.col#footer-right-desktop`. Nós queremos mostrar `Facebook`, `Instagram` e `Twitter`.

:information_source: Lembre-se de acessar a [documentação](https://vtex.io/docs/components/all/vtex.store-footer/) do Footer caso tenha alguma dúvida durante a atividade. 

Resultado esperado:
![](https://appliancetheme.vteximg.com.br/arquivos/imagem-footer.png)

----

Se ainda tiver dúvida sobre como enviar sua resposta, você pode rever [aqui](https://github.com/{{ user.username }}/store-framework/issues/3).
