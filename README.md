# intro-prog-cmp24-I-versionamento-I
Versionamento de Códigos | Turma I 2024

### [Conteúdo - 19/08/2024](#conteúdo)

### Resumo
Nessa aula veremos? 
* [O que Terminal e linha de comando](#O-que-é-terminal-e-linha-de-comando)
* [O que é versionamento e Git](#versionamento)

## Conteúdo

### O que é Terminal e linha de comando
Terminal é uma interface que interpreta linhas de comando, para o git usamos o terminal *bash*.
Existem outros terminais como: cmd, PowerShell.
A linha de comando é uma interface baseada em *texto* por meio da qual é possível navegar, criar, executar e atuar nos arquivos e diretórios de um computador com precisão, inclusive o versionamento do seu código. O git é sempre utilizado através da linha de comando.

###Comandos básicos no bash

identifica usuário que esta logado. tradução: "quem sou eu" 
```sh
$ whoami
```

mostra o caminho da pasta atual no seu usuário, ex: C:/Users/tabita/documentos/dev. tradução: print working directory - mostre o diretório de trabalho
```sh
$ pwd  
```

lista arquivos ou pastas presentes na pasta que você esta. tradução: list - lista 
```sh
$ ls 
```

muda a pasta, entra em outra pasta com o nome passado. tradução change directory - mude o diretório
```sh
$ cd nome-da-pasta 
```

volta a pasta raiz/usuário
```sh
$ cd ~
```

volta uma pasta atrás
```sh
$ cd ..
```

o echo pede o que o texto entre as aspas seja inserido no arquivo que iremos criar com o nome que é dado depois do > , nesse caso um arquivo de text (.txt) com o nome tabita
```sh
$ echo "texto para o arquivo" > tabita.txt
```

criar uma pasta. tradução: make directory - crie diretório
```sh
$ mkdir nome-da-pasta 
```

deleta um pasta. traduão: remove directory - remova diretório
```sh
$ rmdir nome-do-arquivo
```

deleta um arquivo. traduão: remove
```sh
$ rm nome-do-arquivo
```

deleta uma pasta. tradução: remove directory - remova diretório
```sh
$ rmdir nome-da-pasta
```
____

### Versionamento

É o processo de controlar versões, utiliza um conjunto de ferramentas para ajudar a controlar a criação e manutenção de códigos. 

Existem dois tipos de versionamento: Centralizado e Distribuido.
Ambos funcionam com um repositório e área de trabalho. A comunicação entre elas se dá através de operações de commit e update.

**Modelo Distribuido (DVCS)**
O repositório armazena o código e cada pessoa desenvolvedora cria uma cópia deste repositório em sua área de trabalho. Na área de trabalho - seu pc com sua branch - ela é independente de alterações externas.
A desenvolvedora escreve seu código, na sua cópia, e envia para o repositório centralizado com um pedido de inclusão do seu código.
Podemos utilizar alguns comandos offline, não há impacto local se o servidor com o repositório central cair. 

**Modelo centralizado (CVCS)**
Existe um repositório central que é modificado diretamente pelos desenvolvedores. Cada dev não terá uma cópia, e sim a versão principal.
Pode gerar falhas caso o servidor central caia, depende de conexão com a internet para executar todos os comandos.



### Git

>Git é um sistema de controle de versão para rastrear alterações em arquivos e coordenar o trabalho nesses arquivos modificados entre várias pessoas. Ele é usado principalmente para gerenciamento de código-fonte no desenvolvimento de programas, mas pode ser usado para controlar as alterações em qualquer conjunto de arquivos. Git foi criado por Linus Torvalds em 2005 para o desenvolvimento do kernel Linux e é um software de código aberto e gratuito.

Repositórios git públicos e privados gratuitos estão disponíveis em:

Bitbucket
GitHub
GitLab

**Git: Comandos iniciais**
Você encontrará mais sobre todos os comandos na documentação oficial [aqui](https://git-scm.com/docs). 

configura usuário do git local
```sh
$ git config --global user.name "Tabita"
$ git config --global user.email "tabita@email.com"

```

listar todas as configurações do git: 
```sh
$ git config --list
```

criar um repositório local:
```sh
$ git init
```

verificar e mostrar os arquivos modificados:
```sh
$ git status
```

adicionar um arquivo ao olhar do git:
```sh
$ git add arquivo.txt
```

adicionar todos os arquivos que estão na pasta. todos os comandos fazer a mesma coisa:
```sh
$ git add  --all
$ git add  --A
$ git add  .
```

salvar e rastrear uma alteração. usar frase no imperativo:
```sh
$ git commit -m "Frase curta explicando a modificação realizada"

```

verificar diferenças entre arquivos:
```sh
$ git diff arquivo.txt

```

verificar diferenças na área de "preparação":
```sh
$ git diff --cached arquivo.txt
$ git diff --staged arquivo.txt
```

verificar históricos de alterações:
```sh
$ git log
$ git log --oneline
```

desfazer alterações:
```sh
$ git checkout arquivo.txt
```

listar branchs:
```sh
$ git branch
```

criar branch: 
```sh
$ git checkout -b nome-da-branch
$ git switch -c nova-branch
```

trocar de branch:
```sh
$ git checkout nome-da-branch
$ git switch nova-branch
```

deletar branch local:
```sh
$ git branch -D nome-da-branch
```

deletar branch remota:
```sh
$ git push origin --delete nome-da-branch
```

