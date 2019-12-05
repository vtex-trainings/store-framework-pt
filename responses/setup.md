# Configurações básicas

O **Toolbelt** é a ferramenta de **linha de comando** do VTEX IO. É ele quem permite a realização de qualquer atividade na plataforma, como criar um novo workspace de desenvolvimento, fazer login em uma conta VTEX, desenvolver novas apps, gerenciar as já existentes, etc.

Uma vez que o Toolbelt é quem estabelece a comunicação entre o desenvolvedor e a plataforma, você precisará dele para conseguir realizar todas as atividades propostas durante o curso do Store Framework. 

Por isso, o seu primeiro passo é instalar a linha de comando do VTEX IO no seu computador.   

## Instalando o Toolbelt

1. Instale o [**Node.js**](https://nodejs.org/) e o [**Yarn**](https://yarnpkg.com/) no seu computador;
2. Execute o comando `yarn global add vtex` no seu terminal;

```
$ yarn global add vtex
```

Você pode executar o comando `vtex` para confirmar se a instalação do Toolbelt ocorreu como esperado. 

Com a instalação concluída, o seu próximo passo deve ser *logar* em uma conta VTEX. 

## Fazendo login 

1. Execute o comando `vtex login contaVTEX` no seu terminal, substituindo `contaVTEX` pelo nome real da conta em que você deseja trabalhar. Por exemplo, `vtex login appliancetheme`.

2. Uma vez *logado*, execute o comando `vtex whoami` para confirmar em qual conta e workspace você está. 

Workspaces nada mais são do que espaços de trabalho. Na plataforma do VTEX IO, as contas possuem três tipos principais de workspaces: [master](https://vtex.io/docs/recipes/store/promoting-a-workspace-to-master), de [produção](https://vtex.io/docs/recipes/store/creating-a-production-workspace) e desenvolvimento. 

O próximo passo irá fazer com que um workspace de desenvolvimento seja criado para você, permitindo que as configurações feitas nas atividades do curso não alterem a versão final pública da loja. 

## Criando um workspace de desenvolvimento

1. Execute `vtex use nome-do-workspace`, substituindo `nome-do-workspace` pelo nome desejado. Por exemplo, `vtex use devworkspace`.

### Visualizando seu workspace

Depois que seu workspace foi criado, você conseguirá acessá-lo a partir do link `https://{workspace}--{conta}.myvtex.com`, substituindo `{workspace}` e `{conta}` pelo workspace criado anteriormente e pelo nome da conta, respectivamente. Por exemplo, `https://devworkspace--appliancetheme.myvtex.com`

## Linkando seus arquivos locais

Ao executar `vtex link` a partir da pasta onde estão os arquivos do seu tema, eles passarão a ser automaticamente sincronizados com a plataforma do VTEX IO. Isso significa que qualquer alteração feita e salva por você será refletida no workspace e na conta em que você está *logado*, e poderá ser visualizada através do endereço descrito acima.

---

Com todas as configurações básicas concluídas, você está pronto pra começar o curso! 

## Para continuar clique em Close Issue
