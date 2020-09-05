
<a href="https://xkcd.com/1597/" a="https://xkcd.com/1597/">
 <img align = "right" src=https://imgs.xkcd.com/comics/git.png  hspace="20" vspace="5">
</a>

# [Readmegit](https://www.github.com/mrtheduts/readmegit) 

## Índice:
1. [Inicializando o repositório](#inicializando-o-repositório)
2. [Comandos](#comandos)
   - [Gerenciar Mudanças](#gerenciar-mudanças) 
   - [Lidar com `$ git branch` e `$ git checkout`](#lidar-com-%24-git-branch-e-%24-git-checkout)
   - [Lidando com `$ git merge`](#lidando-com-%24-git-merge)
   - [Lidar com `$ git remote`](#lidar-com-%24-git-remote)
   - [Lidar com `$ git tag`](#lidar-com-%24-git-tag)
3. [Dicas](#dicas)
4. [Links para referência](#links-para-referência)
    - [Guias](#guias)
    - [Documentação](#documentação)
    - [Diversos](#diversos)

## Inicializando o repositório
Há duas maneiras de configurar uma pasta como um repositório git:
#### 1. Através de `$ git init`
1. Crie uma pasta vazia ou aproveite uma pasta já existente
2. Entre nela e inicialize o repositório com o comando: `$ git init`
3. Configure o endereço remoto do repositório:
   - Com https: `$ git remote add origin https://github.com/user/repo.git`
   - Com ssh: `$ git remote add origin ssh:git@github.com/user/repo.git`
   > Mais informações sobre o uso de `$ git remote` na seção [Lidar com `$ git remote`](#lidar-com-%24-git-remote)
4. Realize o _pull_: `$ git pull origin master`
5. **Comece a trabalhar!**

#### 2. Ou de `$ git clone`
1. Clone o repositório:
   - Com https: `$ git clone https://github.com/user/repo`
   - Com ssh: `$ git clone ssh:git@github.com/user/repo.git`
2. **Comece a trabalhar!**

## Comandos

### Gerenciar mudanças
 - Atualizar repositório local com as mudanças carregadas ao remoto: `$ git pull`
 - Verificar os arquivos que foram modificados, adicionados e removidos: `$ git status`
 - Verificar as mudanças feitas após o último _commit_: `$ git diff`
 - Incluir adição ou mudança a ser registrada: `$ git add <caminho/para/arquivos>`
 - Incluir remoção de arquivo a ser registrada: `$ git rm <caminho/para/arquivos>`
 - Registrar suas mudanças: `$ git commit [-a] [-m "Mensagem"]`
     >As _flags_ são opcionais.<br />
     >`-a` Adiciona automaticamente as mudanças realizadas nos arquivos que já estavam sendo rastreados nesse _commit_;<br />
     >`-m` Pula a etapa de abertura do editor de texto para a criação da mensagem de _commit_, utilizando diretamente a mensagem entre aspas;
 - Carregar as mudanças registradas ao repositório remoto: `$ git push origin <branch>`
    >\<branch\> é o _branch_ que está sendo modificado, como, por exemplo, o _master_.<br />
    > Para maiores explicações, veja a seção [Lidar com `$ git branch` e `$ git checkout`](#lidar-com-%24-git-branch-e-%24-git-checkout)
 - Verificar os _commits_ feitos em ordem cronológica: `$ git log [--oneline] [--graph]`
    >As flags são opcionais.<br />
    >`--graph` mostra os _commits_ em estilo de grafo, com cada _branch_ de uma cor;<br />
    >`--oneline` Deixa de lado algumas informações e mostra apenas o ID e o comentário do _commit_;<br />
    >No quadrinho abaixo há uma representação parecida com resultado do uso das duas _flags_ acima.
 - Ver informações sobre um _commit_: `$ git show <ID do commit>`

<br />
<p align="center"> 
 <a href=https://xkcd.com/1296/><img src=https://imgs.xkcd.com/comics/git_commit.png a=https://xkcd.com/1296/></a>
</p>

### Lidar com `$ git branch` e `$ git checkout`
_Branches_ são ramos de _commits_ que divergiram do "tronco" principal do repositório - ou até mesmo de outros _branches_. São muito úteis para o desenvolvimento paralelo de recursos, gerenciando mudanças de uma forma organizada, podendo ser integrados ao ramo principal quando estiverem prontos. O ramo azul no quadrinho acima é um exemplo de _branch_.
 - Listar o _branches_ existentes, indicando o atual: `$ git branch [--all]`
    > A flag é opcional.<br />
    >`--all` Lista todos os _branches_ presentes no repositório local e no remoto;
 - Criar um novo _branch_ a partir do _commit_ atual: `$ git branch <nome>`
 - Mudar o _branch_ atual: `$ git checkout <nome>`
    > O par de comandos acima pode ser substituído por `$ git checkout -b <nome>`, caso deseje criar um novo _branch_ e fazer dele seu atual.
 - Deletar _branch_:
    - Local: `$ git branch -d <nome>`
    - Remoto: `$ git push origin --delete <nome>`
 
### Lidando com `$ git merge`
Dada a forma que o git gerencia as mudanças nos arquivos, é relativamente fácil unir duas versões de um ou vários arquivos, em _branches_ separados, por exemplo. No quadrinho acima, o ramo azul foi fundido no ramo verde. O passo-a-passo abaixo instrui como realizar um _merge_ entre dois _branches_.
1. Mude para o _branch_ que receberá as mudanças: `$ git checkout <branch1>`
2. Realize o _merge_ de `<branch2>` em `<branch1>`: `$ git merge [--no-ff] <branch2>`
    > A flag é opcional.<br />
    > `--no-ff` Impede que os _commits_ de `<branch2>` sejam incorporados à árvore de `<branch1>`, apagando a existência de `<branch2>` do _log_ do repositório;<br />
    > Para mais informações, veja [differences between `git merge` and `git merge --no-ff`](http://stackoverflow.com/questions/9069061/what-is-the-difference-between-git-merge-and-git-merge-no-ff)
3. Resolva os possíveis conflitos, editando o que for necessário
4. Adicione, registre e carregue as mudanças no repositório remoto normalmente

### Lidar com `$ git remote`
 - Listar os repositórios remotos registrados: `$ git remote show`
 - Verificar qual o endereço do repositório remoto: `$ git remote get-url <nome>`
 - Adicionar um novo repositório remoto:
   - Com https: `$ git remote add <nome> https://github.com/user/repo.git`
   - Com ssh: `$ git remote add <nome> ssh:git@github.com/user/repo.git`
 - Remover o endereço do repositório: `$ git remote remove origin`

### Lidar com `$ git tag`

 - Listar todas as _tags_ do repositório local: `$ git tag [-nX]`
    > A _flag_ é opcional.<br />
    > `-nX` Mostra as X primeiras linhas da mensagem da _tag_ ou do _commit_ correspondente.
 - Criar uma _tag_ no _commit_ atual: `$ git tag <nome> [-a [-m "Mensagem"]]`
    > As _flags_ são opcionais.<br />
    > `-a` Cria uma flag _annotated_, isto é, uma _flag_ com informações sobre o usuário, a data e a hora de criação, assim como uma mensagem.<br />
    >`-m` Pula a etapa de abertura do editor de texto para a criação da mensagem, utilizando diretamente a mensagem entre aspas;
 - Ver informações de uma _tag_: `$ git show <nome>`
 - Carregar as _tags_ ao repositório remoto: `$ git push --tags`

## Dicas

 - Configure seu editor de texto padrão:
 `$ git config --global core.editor "seu_editor"`
 - Para não precisar inserir as informações de login no repositório remoto a cada _push_:<br />
 `$ git config credential.helper 'cache --timeout=<nºsegundos>'`
 - Se utiliza verificação em duas etapas, use uma [chave ssh](https://docs.github.com/pt/github/authenticating-to-github/connecting-to-github-with-ssh) para se conectar.

## Links para referência
<a href="https://xkcd.com/979/" a="https://xkcd.com/979/">
 <img align = "right" src=https://imgs.xkcd.com/comics/wisdom_of_the_ancients.png  hspace="20" vspace="5">
</a>

### Guias
- [Git - The Simple Guide](http://rogerdudler.github.io/git-guide/)
- [Learn Git branching](https://learngitbranching.js.org/?locale=pt_BR)
- [Git Rebase](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase)
### Documentação
- [Git Docs](https://git-scm.com/documentation)
### Diversos
- [A Successful Git Branching Model](https://nvie.com/posts/a-successful-git-branching-model/)
- [Merging vs. Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)

## Tarefas:
- [X] Ler esse readme.
- [ ] Terminar esse readme.

_Autor: [@mrtheduts](https://github.com/mrtheduts/)_<br />
_Esse readme é de uso livre._ <br />
_Sugestões são bem-vindas._

<p align="center"> 
 <a href=https://xkcd.com/292/><img src=https://imgs.xkcd.com/comics/goto.png></a>
</p>
