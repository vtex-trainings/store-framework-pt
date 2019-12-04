# Inserindo um Iframe na nossa página institucional

## :sparkles: **Branch:** iframe

## Introdução

Um *iframe* é um elemento HTML que permite a incorporação de uma outra página HTML à atual. Dessa forma, é possível embutir conteúdos de outras URLs para serem exibidos em nossa página. É importante lembrar que que as URLs renderizadas pelo iframe possuem um contexto próprio, tendo histórico de sessão e DOM independentes da sua página customizada.

**ATENÇÃO**: iframes só são permitidos dentro de templates de custom pages

O bloco `iframe` tem propriedades bem simples:

- `src`: indica qual URL o iframe deve renderizar
- `width`: largura do elemento iframe em pixels
- `height`: altura do elemento iframe

Abaixo, vemos um exemplo de implementação do bloco `iframe`:

```json
"store.custom#about-us": {
   "blocks": [
     "flex-layout.row#about-us",
     "iframe"
   ]
 },

"iframe": {
  "props": {
    "src": "http://someURL.com/resource",
    "width": 100,
    "heigth": 200,
  }
}
```

## Tarefa

Vamos exibir um post de Instagram em nossa loja:

1. Troque a label da aba "Electronics" para "Instagram"
2. No conteúdo da aba Instagram, apague o `rich-text` e inclua um bloco `iframe`
3. Nas props do `iframe`, exiba o conteúdo do link `https://www.instagram.com/p/B37Zfd6FobU/embed` num container de 800px de largura por 1000px de altura