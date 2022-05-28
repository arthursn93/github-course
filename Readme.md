# Git Course

Este é um repositório de teste para aprender comandos do Git.

Configura usuário no git:
$ git config --global user.name "Arthur Nunes"

Configura o email do usuario no git:
$ git config --global user.email "arthur_sn_@hotmail.com"

Configura por padrão o editor de texto pra Codar. Ex: Visual Studio Code
git config --global core.editor 'code --wait'

Mostra o usuario e/ou email
$ git config user.name
$ git config user.email

Mostra tudo
$ git config --list

Cria uma pasta
$ mkdir git-course

Acessa uma pasta
$ cd git-course/

Limpa o terminal mantendo os comandos anteriores
$ reset

Inicializa repositorio
$ git init

Valida repositorio git todo
$ ls -la

Valida informações listadas em um repositorio específico
$ ls

Retorna ao diretório anterior de um repositorio
$ cd ..

Abre editor de texto VI
$ vi Readme.md
- Clicar I = INSERT
- Com I ativado, você consegue escrever qualquer coisa dentro
- Para sair dessa ativação, clicar no botão ESC
- Depois disso, seguir o comando logo abaixo:
->	 :wq       -> Apertar Enter

: (adicionar comando)
w (escrever/salvar)
q (sair)

Mostra o status do seu repositorio
$ git status

Salva seu arquivo no repositorio (para reconhecer na branch)
$ git add .

Lista as alterações feitas na Hash do Autor
$ git show 2f8aa0094fad046598df1dbdebda80beb30cbfb5

Commitar ou versionar o arquivo pra branch
$ git commit -m "first commit"

Mostra a Hash do ultimo Commit com as informações da Data e Autor
$ git log

A mesma coisa que o git log, com a adição de mostrar pra qual branch ele estará acessando
$ git log --decorate

Lista todas as logs com o nome "Arthur"
$ git log --author="Arthur"

Lista em ordem alfabetica o Autor, Numero de Commits e Arquivos commitados na log
$ git shortlog

Lista o Autores e Commits de cada um
$ git shortlog -sn

Lista em forma gráfica seus versionamentos
$ git log --graph

Lista alterações realizadas no editor VI
$ git diff

Lista alterações apenas do arquivo realizadas no editor VI
$ git diff --name-only

Volta pro ponteiro anterior, tirando da fase Staged do git, ficando Unstaged.
Ex: se você der (git add .) sem querer num arquivo errado, e quiser voltar atrás
$ git reset HEAD Readme.md

Checa ultima alteração do arquivo
$ git checkout

Gerar uma nova chave SSH
https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

Lista diretorio onde fica as chaves SSH
$ cd ~/.ssh/

Gera Key SSH \ Lista \ Pega HashCode do SSH \ Mostra HashCode no Editor VI
$ ssh-keygen -C "arthur_sn_@hotmail.com"
$ ls
$ cat id_rsa.pub
$ vi id_rsa.pub

Liga o repositorio remoto com o local
$ git remote add origin git@github.com:arthursn93/github-course.git

Mostra informações do repositorio
$ git remote
$ git remote -v

Pega todos os arquivos do seu repositorio local e envia pro repositorio remoto (Github) 1x
$ git push -u origin master
  comando + arquivo de origem + branch
Na 2x
$ git push


Clonando um repositorio para outro
$ git clone git@github.com:arthursn93/github-course.git github-course-clone

Criar branch
$ git checkout -b testing

Lista as branchs
$ git branch

Acessar branch
$ git checkout testing (ou master)

Deletar uma branch específica
$ git branch -D testing (ou qualquer outra branch)

Junta arquivos de branchs diferentes, porém em linhas diferentes da feature (Ex: master e test)
$ git merge test

Obs: num cenário onde tenho 3 arquivos, sendo que 2 estão na branch master e 1 na branch test:

vim foo  (master)
vim bar  (test)
vim buzz (master)

Obs: validar as branchs pelo (git log) e/ou (git log --graph)

Junta arquivos de branchs diferentes, porém na mesma linha da feature (Ex: apenas master)
$ git rebase test2

Ignora arquivos específicos de repositorio
$ vi .gitignore
- Ex: db.xls

Salva seu arquivo e deixa em WIP (Working in Progress) dentro da branch.
Obs: Não será utilizado no commit, apenas irá guardar aquelas modificações na branch
$ git stash

Você volta a mexer com o arquivo que foi alterado em estado WIP
$ git stash apply

Lista todos os arquivos em estado WIP (Working in Progress)
$ git stash list

Limpa todos os arquivos em estado WIP (Working in Progress)
$ git stash clear

Alias em comandos git (Ex: git status -------> git s)
$ git config --global alias.s status
$ git status -------------> $ git s
