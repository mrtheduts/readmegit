# [Link para trabalho aqui](http://www.google.com.br)

Links:
- [Git - The Simple Guide](http://rogerdudler.github.io/git-guide/).
- [blog do Git](https://git-scm.com/blog).

## Começar a trabalhar:

Há duas maneiras de configurar uma pasta de um repositório git:

1. Criar uma pasta vazia e entrar nela
2. Inicializar o git : `$ git init`
3. Realizar o pull request: `$ git pull https://github.com/usuario/repositorio`
4. Ir até a pasta e criar um branch pra você: `$ git checkout -b Nome`
5. Dar push no branch: `$ git push origin Nome`
6. Codar hardmente

ou

1. Clonar: `$ git clone https://github.com/usuario/repositorio`
2. Ir até a pasta e criar um branch pra você: `$ git checkout -b Nome`
3. Dar push no branch: `$ git push origin Nome`
4. Codar hardmente

## Comandos

### Coisas básicas
 - Verificar status: `$ git status`
 - Adicionar arquivos no repositório: `$ git add <arquivos>`
 - Registrar suas mudanças: `$ git commit -m "Sua mensagem aqui"`
 - Fazer upload: `$ git push origin <branch>` (De preferência, no seu branch)

## Lidar com branches
 - Ver os branches existentes e em qual está: `$ git branch`
 - Criar novo branch: `$ git branch <nome>`
 - Mudar de branch: `$ git checkout <nome>`
 - Criar (caso não exista) e mudar de branch: `$ git checkout -b <nome>`
 
### Atualizar o arquivo compartilhado
 
Links:
 - [How to merge changes to a single file](http://stackoverflow.com/questions/10784523/how-do-i-merge-changes-to-a-single-file-rather-than-merging-commits)
 
Basicamente,você está no branch *Seu* e mudou certo arquivo que precisa ser atualizado no master. Faça o seguinte:
 
 1. Mude para o branch *master*: `$ git checkout master`
 2. Una os dois arquivos: `$ git checkout --patch Gustavo <arquivo>`
 3. Gerencie as mudanças (pode aceitar parte por parte com 'y' ou tudo com 'a' ou editar o arquivo final com 'e')
 4. Atualize a tag: `$ git tag -a vx.y.z -m "Mudança"`
 
    >Sendo: x = 0 ou 1 (projeto completo ou não), y += 1 a cada função adicionada e z += 1 quando bugs são corrigidos

 5. Registre as mudanças com commit: `$ git commit -m "Texto aqui"`
 6. Dê o upload dos arquivos: `$ git push`
 7. Dê o upload das tags: `$ git push --tags`
 
## Cuidados

- Adicione cuidados aqui

##Tarefas:
- [X] Ler esse readme.
