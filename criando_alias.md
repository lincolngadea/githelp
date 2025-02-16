# Criando Aliases no Git

Os aliases no Git permitem encurtar comandos longos, tornando o uso do Git mais rápido e eficiente. Abaixo estão alguns exemplos úteis.

## 1. Criar um Alias
A sintaxe para criar um alias é:
```sh
git config --global alias.<alias> '<comando>'
```
Exemplo:
```sh
git config --global alias.co 'checkout'
```
Agora, ao invés de digitar `git checkout`, você pode simplesmente usar:
```sh
git co <branch>
```

## 2. Aliases Úteis

### 2.1. Status e Log
```sh
git config --global alias.s 'status -sb'  # Status curto
git config --global alias.lg 'log --oneline --graph --decorate --all'  # Histórico visual
```
Uso:
```sh
git s   # Exibe status simplificado
git lg  # Exibe histórico de commits em formato gráfico
```

### 2.2. Commit e Push
```sh
git config --global alias.cm 'commit -m'
git config --global alias.ac 'commit -a -m'
git config --global alias.p 'push'
git config --global alias.pu 'pull'
```
Uso:
```sh
git cm "Mensagem do commit"  # Commit rápido
git ac "Commit de todas as alterações"  # Adiciona e commita tudo
git p  # Faz push do código
git pu # Faz pull do repositório remoto
```

### 2.3. Branches e Merges
```sh
git config --global alias.br 'branch'
git config --global alias.sw 'switch'
git config --global alias.rb 'rebase'
git config --global alias.m 'merge'
```
Uso:
```sh
git br  # Lista branches
git sw <branch>  # Muda para outra branch
git rb main  # Faz rebase com a branch main
git m feature  # Faz merge da branch feature
```

### 2.4. Reset e Revert
```sh
git config --global alias.unstage 'reset HEAD'
git config --global alias.rst 'reset --hard'
git config --global alias.rv 'revert'
```
Uso:
```sh
git unstage <arquivo>  # Remove do staging
git rst  # Reseta hard para último commit
git rv <commit>  # Reverte um commit
```

### 2.5. Stash
```sh
git config --global alias.st 'stash'
git config --global alias.stp 'stash pop'
git config --global alias.stl 'stash list'
```
Uso:
```sh
git st  # Guarda alterações sem commit
git stp  # Aplica a stash mais recente
git stl  # Lista stashes salvas
```

## 3. Listar Aliases Configurados
Para ver todos os aliases configurados:
```sh
git config --global --list | grep alias
```

Esses aliases ajudam a reduzir o tempo digitando comandos longos no Git, tornando o fluxo de trabalho mais eficiente. 🚀
