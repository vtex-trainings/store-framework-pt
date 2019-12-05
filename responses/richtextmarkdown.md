# Explorando o poder do rich text

## :sparkles: **Branch:** richtextmarkdown

## Introdução

Conforme já vimos, Markdown é uma linguagem de marcação amigável que pode ser convertida de maneira simples para HTML. Nesta lição, veremos como é possível utilizar esta linguagem em nosso componente de `rich-text` para criar textos interessantes.

## Rich Text com Markdown

Para incluir textos no componente de `rich-text`, é necessário utilizar a prop `text`:

```json
  "rich-text#home1": {
    "props": {
      "text": "Meu texto",
      "textPosition": "CENTER",
      "textAlignment": "CENTER"
    }
```

A prop `text` aceita o formato de markdown. Portanto, se você deseja escrever seu texto utilizando essa linguagem, seu código deve ficar semelhante a este:

```json
```json
  "rich-text#home1": {
    "props": {
      "text": "# Meu título h1 \n Escreva aqui um parágrafo \n ## Meu título h2 \n Escreva aqui seu segundo parágrafo \n Inclua aqui uma lista \n - Item 1 \n - Item 2 \n - Item3",
      "textPosition": "CENTER",
      "textAlignment": "CENTER"
    }
```

**DICA**: Sempre utilize o comando `\n` para pular linhas ao utilizar markdown na prop `text`

Outras propriedades do componente `rich-text` podem ser encontrados na [documentação oficial do Store Framework](https://vtex.io/docs/components/all/vtex.rich-text/)

## Atividade

1. Dentro do arquivo `about-us.jsonc`, troque o texto da `tab-list.item#home1` para que apareça um "Sobre" na primeira aba.

2. No conteúdo `rich-text` associado a essa aba, crie um texto que contenha um "Quem somos" como um título h2 e 3 parágrafos.

3. Coloque o título e os parágrafos em negrito.

**DICA**: você pode utilizar o texto abaixo como conteúdo dos três parágrafos:

```
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut nibh tellus, malesuada vel faucibus eu, laoreet nec lorem. Praesent lorem erat, tempus in malesuada eu, tincidunt vitae risus. Pellentesque vulputate neque vitae mollis mattis. Cras aliquet ac felis eget dictum. Nulla porttitor, ante in lobortis tincidunt, ipsum ligula bibendum turpis, in facilisis ligula velit ac tortor. Proin feugiat ultricies purus, et pretium lorem pulvinar ut. Donec blandit ipsum sit amet neque semper imperdiet. Cras maximus elementum ligula, a mollis risus hendrerit quis. Morbi gravida enim quis erat faucibus cursus.

Nullam ligula dolor, vehicula ut nulla ut, tempus lobortis arcu. Morbi id blandit nisl, non tempus urna. Phasellus lacus ante, dignissim a egestas at, pharetra in dui. Curabitur posuere sapien vitae lectus semper, fermentum fermentum tellus semper. Aenean ligula elit, elementum quis iaculis in, fringilla nec est. Vestibulum ex sapien, iaculis eget tortor id, porta tempor lorem. Aenean aliquam mi et nisi bibendum rhoncus. Sed viverra risus et nulla sodales, eget rutrum lectus fringilla. Quisque iaculis metus in dignissim pretium. Fusce sollicitudin et ipsum et varius.

Curabitur ac mauris sed tortor bibendum euismod. Cras eu volutpat neque. Maecenas at massa eu lacus maximus lacinia. Nunc vehicula diam ac lorem bibendum eleifend. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nunc vehicula vehicula nisi vel efficitur. Phasellus vitae pretium magna. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Etiam sodales nunc in libero congue condimentum. Mauris libero neque, cursus nec ipsum ut, gravida maximus libero. In rhoncus leo non ante porta mattis id sed erat. Etiam rhoncus sit amet mi sed gravida. Aliquam scelerisque accumsan malesuada. Praesent ante leo, gravida at tristique at, venenatis non purus. Proin elementum ante quis viverra maximus. Praesent lobortis scelerisque mauris, et eleifend nisi varius in.
```

Resultado esperado:
![](https://appliancetheme.vteximg.com.br/arquivos/rich-text-solution.png)
----

Se ainda tiver dúvida sobre como enviar sua resposta, você pode rever [aqui](https://github.com/{{ user.username }}/store-framework/issues/2).
