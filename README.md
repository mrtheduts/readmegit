# [Link para trabalho aqui](https://www.github.com/mrtheduts/readmegit)


 <img align = "left" src=https://octodex.github.com/images/baracktocat.jpg width="190" height="190"  hspace="20" vspace="5" alt="Octocat">

#### Links para referência:
- [Git Docs](https://git-scm.com/documentation)
- [Blog do Git](https://git-scm.com/blog).
- [Git - The Simple Guide](http://rogerdudler.github.io/git-guide/).

<br />
<br />
<br />

> ***“Talk is cheap. Show me the code.”** <br /> ― Linus Torvalds*



## Começar a trabalhar:

Há duas maneiras de configurar uma pasta de um repositório git:

1. Criar uma pasta vazia e entrar nela
2. Inicializar o git : `$ git init`
3. Realizar o pull request: `$ git pull https://github.com/usuario/repositorio`
4. Ir até a pasta e criar um branch pra você: `$ git checkout -b Nome`
    >Sugestão: Para organizar melhor o projeto, recomendo criar diferentes branches para diferentes implementações
5. Dar push no branch: `$ git push origin Nome`
6. **Codar hardmente**

ou

1. Clonar: `$ git clone https://github.com/usuario/repositorio`
2. Ir até a pasta e criar um branch pra você: `$ git checkout -b Nome`
    >Sugestão: Para organizar melhor o projeto, recomendo criar diferentes branches para diferentes implementações
3. Dar push no branch: `$ git push origin Nome`
4. **Codar hardmente**

<br />

 >***“A code is like love, it has created with clear intentions at the beginning, but it can get complicated.”** <br />― Gerry Geek, Ice Breakers for Project Managers: Jokes, Quotes, and Brainteasers*

<br />

## Comandos

### Coisas básicas

 - Verificar status: `$ git status`
 - Adicionar arquivos no repositório: `$ git add <arquivos>`
 - Registrar suas mudanças: `$ git commit -m "Sua mensagem aqui"`
     >Sugestão: Se quiser pular o `git add` e adicionar automaticamente os arquivos que foram modificados - dos quais o git mantém relatório - basta adicionar um `-a` no `git commit`
 - Fazer upload: `$ git push origin <branch>`
 - Verificar os commits feitos: `$ git log [--oneline] [--graph] [--decorate]`
    >`git log`, apenas, mostra os commits e seus autores, dentre outras informaçõe; `--oneline`, como o nome mostra, deixa de lado algumas informações e mostra apenas a hash e o comentario do commit; `--graph` imprime uma árvore do projeto e com `--decorate` ela é impressa de diferentes cores, baseadas em qual branch ela está.

### Usando Tags

Tags servem para manter um certo controle da versão "oficial" do programa, servindo de atalho para certos commits. Elas podem ser lightweight e annotated. As lightweight só contém informações do autor da tag, da data e do hash do commit. Já as annotated (adicionando as flags -a e -m) guardam informações extras como o que mudou no commit, o autor original do repositório e podem ser verificadas pelo Gnu Privacy Guard.

 - Atualize a tag: `$ git tag [-a] vx.y.z [-m "Mudança"]`
 
    >Sugestão: sendo x = 0 ou 1 (projeto completo ou não), y += 1 a cada função adicionada e z += 1 quando bugs são corrigidos
    
  - Dê o upload das tags: `$ git push --tags`

<br />

 >***“I'm not a great programmer; I'm just a good programmer with great habits.”** <br /> ― Kent Beck*
 
 <br />

## Branches

#### Links:
 - [Network Graph](https://github.com/blog/39-say-hello-to-the-network-graph-visualizer)

### Lidar com branches

 - Ver os branches existentes e em qual está: `$ git branch`
 - Criar novo branch: `$ git branch <nome>`
 - Mudar de branch: `$ git checkout <nome>`
 - Criar (caso não exista) e mudar de branch: `$ git checkout -b <nome>`
 
### Deletar branches

- Localmente: `$ git branch -d <nome>`
- Remotamente: `$ git push origin --delete <nome>`
 
### Fundir dois branches (merge)

1. Vá para o branch que continuará ativo
2. `$ git merge --no-ff <branch no qual mudanças foram feitas>`
    >Por que `--no-ff`? [`git merge` ou `git merge --no-ff`](http://stackoverflow.com/questions/9069061/what-is-the-difference-between-git-merge-and-git-merge-no-ff)
3. Resolva os conflitos
4. Adicione, commite e dê push nas mudanças
 
<br />
 
 > ***“Programming isn't about what you know; it's about what you can figure out.”** <br />― Chris Pine, Learn to Program*
 
<br />
 
## Cuidados

- Não confunda a ordem dos adds, commits e pushes
- Verifique se está no branch certo

<br />

 > ***“Always code as if the guy who ends up maintaining your code will be a violent psychopath who knows where you live”** <br />― John Woods*
 
<br />
 
## Dicas

 - Você não precisa mais de uma conta premium para criar um repositório privado
 - Configurar seu editor de texto padrão: `git config --global core.editor "seu_editor"`
 - Para não precisar dar login toda hora: `$ git config credential.helper 'cache --timeout=<nºsegundos>'`
 - [Oh My Zsh](https://github.com/robbyrussell/oh-my-zsh) - É um plugin para seu zsh (seu terminal pode ser bash ou zsh). Com o tema `ZSH_THEME="agnoster"` configurado no seu arquivo .zshrc e o plugin do git habilitado (por padrão) fica simples ver em qual branch está e se as mudanças foram commitadas. Vale a pena dar uma olhada.
 

#### Links específicos, mas possívelmente úteis:
 - [How to merge changes to a single file](http://stackoverflow.com/questions/10784523/how-do-i-merge-changes-to-a-single-file-rather-than-merging-commits)

<br />

 > ***“Think twice, code once.”** <br />― Waseem Latif*
 
 <br />

## Tarefas:
- [X] Ler esse readme.
- [ ] Modificar esse readme

<br />

<p align="center"> 
 <a href=https://imgs.xkcd.com/comics/new_bug.png><img src=https://imgs.xkcd.com/comics/new_bug.png a=https://imgs.xkcd.com/comics/new_bug.png></a>
</p>
