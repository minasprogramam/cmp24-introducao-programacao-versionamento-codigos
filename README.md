# cmp24-introducao-programacao-versionamento-codigos
Versionamento de Códigos | Turma I 2024

### Resumo
Nessa aula veremos? 
* [O que Terminal e linha de comando](#O-que-é-terminal-e-linha-de-comando)
* [O que é versionamento e Git](#versionamento)
* [Passo a passo](#Passo-a-passo)

### O que é Terminal e linha de comando
Terminal é uma interface que interpreta linhas de comando, para o git usamos o terminal *bash*.
Existem outros terminais como: cmd, PowerShell.
A linha de comando é uma interface baseada em *texto* por meio da qual é possível navegar, criar, executar e atuar nos arquivos e diretórios de um computador com precisão, inclusive o versionamento do seu código. O git é sempre utilizado através da linha de comando.

### Comandos básicos no bash

identifica usuário que esta logado. tradução: "quem sou eu" 
```sh
$ whoami
```
batatai
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
$ cd
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

deleta um pasta. tradução: remove directory - remova diretório
```sh
$ rmdir nome-do-arquivo
```

deleta um arquivo. tradução: remove
```sh
$ rm nome-do-arquivo
```

deleta uma pasta. tradução: remove directory - remova diretório
```sh
$ rmdir nome-da-pasta
```

_____________

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

clonar repositório:
```sh
$ git clone url-do-repositorio
```
atualizar repositório local com informações do repositório do clone:
```sh
$ git pull origin nome-da-branch
```

conectar repositório externo a pasta local:
```sh
$ git remote add origin url-do-repositorio
```
editar repositorio externo conectado a pasta local:
```sh
$ git remote set-url origin url-do-repositorio
```

adicionar repositorio do fork original como atualizador:
```sh
$ git remote add upstream url-do-repositorio
```
editar repositorio do fork original como atualizador:
```sh
$ git remote set-url upstream url-do-repositorio
```
atualizar repositório local com informações do repositório do fork:
```sh
$ git pull upstream nome-da-branch
```

enviar alterações para repositório externo:
```sh
$ git push origin nome-da-branch
```

**Fork** -> é uma cópia de um repositório atráves do Github, criando um reposiório clone no nosso perfil que estará atrelado aquele original que foi 'forkado'(copiado).

**Pull Request** -> é um pedido de inclusão de alterações ao código de uma branch, quando nossas alterações são aceitas na branch principal temos o merge.

**Merge** -> mesclagem do código de uma branch com o código de outra. Exemplo em aula: quando pedimos para incluir nossas alterações - do polvo com oculos e do polvo com chapeu - a branch principal.

_____________


### Passo a passo

Criar um repositório local, no seu computador:
- abrir a pasta do seu projeto no git bash, para inicializar: **git init**

Adicionar um repositório de origem (github) ao seu local:
- criar um repositório no seu Github e copiar o link
- no bash, dentro da pasta do seu projeto: **git remote add origin link-do-repositório-no-github**
- caso digitar o nome errado do repositório, pode corrigir com: **git remote set-url origin link-do-repositório-original**

Adicionar arquivos ao git: 
- verificar as alterações a ser comitadas: **git status**
- adicionar ao olhar do git: **git add .**
- criar o commit para marcar as alterações: **git commit -m "adiciona X e Y arquivos"**

Enviar alterações para o repositório no git:
- fazer commit antes de enviar! 
- para enviar as alterações: **git push origin branch-que-quer-mandar**

Para clonar um repositório:
- com o link do repositório abrir o git bash onde você quer criar a cópia do repositório
- no git bash: **git clone url-do-repositorio**

Para atualizar seu repositório local com informações do clone original no github
- verificar se há atualizações: **git fetch origin branch-que-quer-pegar**
- puxar as atualizações para sua máquina: **git pull origin branch-que-quer-pegar**
- para enviar as atualizações para a sua branch no github: **git push origin sua-branch**

Para criar um fork:
- entrar no repositório do github, clicar no botão "Fork"
- automaticamente cria uma cópia no seu próprio github. se o repositório original tiver atualizações você precisa puxar as atualizações na mão

Adicionar o repositório original do fork como atualizador do seu
- adiciona ele como repositório para puxar atualizações: **git remote add upstream link-do-repositório-original**
- verificar que ele foi adicionado, listando repositórios de origem: **git remote -v**
- caso digitar o nome errado do repositório, pode corrigir com: **git remote set-url upstream link-do-repositório-original**

Atualizar seu repositório local com o fork original
- verificar se há atualizações: **git fetch upstream branch-do-repositório**
- puxar atualizações para seu repositório local: **git pull upstream branch-do-repositório**
- para enviar as atualizações para a sua cópia do fork: **git push origin sua-branch**


No dia a dia do curso vocês usarão bastante o fluxo de:
**clonar, alterar, salvar, commitar, enviar alterações e puxar alterações/atualizações**
- git clone -> cria cópia local para um repositório
- git add . -> prepara as alterações para commitar
- git commit -m "sua mensagem" -> commita, cria "etiqueta" temporal para sua alteração
- git push origin sua-branch -> envia para o github
- git pull origin branch-da-prof -> atualiza

_____________

Observações:

caso seu bash entre no modo editor após puxar alterações - acontece quando aparecem diversas linhas iniciadas com ~ no bash - inserir " :wq " ou clicar na tecla " esc "

se não entender o erro no bash busque no google! sua dúvida com certeza já foi a dúvida de alguém!
