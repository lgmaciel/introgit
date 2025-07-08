# Introdução ao GIT

## Inicializar um repositório

Para inicalizar um novo repositório do git:

```bash
mkdir nome_projeto
cd nome_projeto
git init
```
Configurar dados do usuário do repositório:

```bash
Sintaxe:
git config --local user.name [usuario]
git config --local user.email [email]
Exemplo:

git config --local user.name lgmaciel
git config --local user.email lgmaciel@email
```
> **Obs. 1** Não utilize seu email verdadeiro pois ele será enviado junto com seus commits para o repositório remoto e ficará visível a spammers e outros tipos de abusos.
>
> **Obs 2** `[ ]` significa que o parâmetro é opcional

Após estes comandos você terá um repositório vazio e um diretório de trabalho contendo apenas o diretório `.git`. Ele não é visível, a não com o comando:

```bash
no Linux e MacOS
ls -la

Resposta:
drwxr-xr-x 1 lgmaciel 4096    0 Jul  8 09:44 ./       
drwxr-xr-x 1 lgmaciel 4096    0 Jul  8 09:34 ../      
drwxr-xr-x 1 lgmaciel 4096    0 Jul  8 09:43 .git/   


no Windows
dir /a

Resposta:
Pasta de D:\introgit

08/07/2025  09:44    <DIR>          .
08/07/2025  09:44    <DIR>          ..
08/07/2025  09:43    <DIR>          .git
               0 arquivo(s)            0 bytes
               1 pasta(s)   999.583.449.088 bytes disponíveis
```

## Fazer um commit

Para fazer um commit precisamos ter alguma modificação feita no diretório do projeto. 

> Commits registram no repositório modificações feitas nos arquivos do projeto.

Vamos acrescentar um arquivo novo. Essa será nossa modificação.

no Linux:
```bash
$ echo "# Novo projeto" > README.md
```

no Windows:
```cmd
> echo "# Novo projeto" > README.md
```

### Verificar modificações 

Verificamos as modificações feitas no repositório usando `git status`.

```bash
$ git status
```

O resultado será algo como:

```
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

nothing added to commit but untracked files present (use "git add" to track)
```

### Adicionar arquivo ao `STAGE`

`Stage` é uma área virtual onde ficam "empilhados" os arquivos e modificações que entrarão *no próximo commit*. Uma espécie de "fila de espera" ou "preparação para o commit".

Para adicionar um arquivo aos que entrarão no próximo commit:

```bash
$ git add <arquivo>

Exemplo:

$ git add README.md
```

Se conferirmos o status do repositório agora, veremos que o arquivo `README.md` tem *status* de **New**

```bash
$ git status


```