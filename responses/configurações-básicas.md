# Configurações básicas

O **Toolbelt** é a **linha de comando** do VTEX IO. É ele quem permite a realização de qualquer atividade na plataforma, como criar um novo workspace de desenvolvimento, fazer login em uma conta VTEX, desenvolver novas apps, gerenciar as já existentes, etc.

Uma vez que o Toolbelt é quem estabelece a comunicação entre o desenvolvedor e a plataforma, você precisará dele para conseguir realizar todas as tarefas propostas durante o curso do Store Framework. 

Por isso, o seu primeiro passo é instalar a linha de comando do VTEX IO no seu computador.   

## Instalando o Toolbelt

1. Instale o [**Node.js**](https://nodejs.org/) e o [**Yarn**](https://yarnpkg.com/) no seu computador;
2. Execute o comando `yarn global add vtex` no seu terminal;

```
$ yarn global add vtex
```

Você pode executar o comando `vtex` para confirmar se a instalação do Toolbelt ocorreu como esperado. 

3. Execute `vtex use {workspace}`, substituindo `{workspace}` pelo nome desejado por você.

Workspaces nada mais são do que espaços de trabalho na plataforma. O último passo irá fazer com que um workspace de desenvolvimento seja criado para você, permitindo que as suas configurações não alterem a versão final pública da loja. 

Você conseguirá acessar a sua versão de loja em desenvolvimento a partir do link `https://{workspace}--{conta}.myvtex.com`, em que `{workspace}` é o nome do workspace de desenvolvimento já criado e `{conta}` o nome da conta em que você está trabalhando. 

Com o Toolbelt instalado e um workspace de desenvolvimento criado, você está pronto pra começar o curso! 
