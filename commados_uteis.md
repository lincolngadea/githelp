# Comandos Úteis do Git no Dia a Dia

## 1. Configuração do Git
```sh
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
git config --global core.editor "code --wait"  # Define o editor padrão (VS Code)
```

## 2. Inicializar e Clonar Repositórios
```sh
git init  # Inicializa um novo repositório

git clone <URL_DO_REPOSITORIO>  # Clona um repositório remoto
```

## 3. Status e Histórico
```sh
git status  # Verifica o status do repositório
git log  # Exibe o histórico de commits
git log --oneline --graph --all  # Exibe um histórico mais compacto e visual
```

## 4. Adicionar e Confirmar Alterações
```sh
git add .  # Adiciona todas as alterações ao staging
git commit -m "Mensagem do commit"  # Faz o commit das alterações
git commit --amend -m "Nova mensagem"  # Modifica a mensagem do último commit
```

## 5. Trabalhando com Branches
```sh
git branch  # Lista todas as branches
git branch <nome-da-branch>  # Cria uma nova branch
git checkout <nome-da-branch>  # Alterna para uma branch específica
git switch <nome-da-branch>  # Alterna de forma moderna para outra branch
git checkout -b <nome-da-branch>  # Cria e muda para uma nova branch
git merge <branch>  # Mescla uma branch na branch atual
git branch -d <nome-da-branch>  # Exclui uma branch local
```

## 6. Trabalhando com Repositórios Remotos
```sh
git remote -v  # Lista os repositórios remotos configurados
git remote add origin <URL_DO_REPOSITORIO>  # Adiciona um repositório remoto
git push -u origin main  # Envia as alterações para o repositório remoto
git push origin --delete <branch>  # Deleta uma branch remota
git pull origin main  # Baixa e mescla as mudanças do repositório remoto
```

## 7. Reverter Alterações
```sh
git reset --soft HEAD~1  # Desfaz o último commit mantendo as alterações no staging
git reset --hard HEAD~1  # Desfaz o último commit apagando as alterações
git revert <commit>  # Cria um novo commit revertendo um commit específico
```

## 8. Stash (Salvar Alterações Temporárias)
```sh
git stash  # Guarda as alterações sem fazer commit
git stash list  # Lista os stashes salvos
git stash pop  # Recupera o stash mais recente e remove da lista
git stash apply  # Aplica o stash mais recente sem removê-lo
git stash drop  # Remove um stash específico
```

## 9. Rebasing
```sh
git rebase main  # Reaplica commits da branch atual sobre a branch main
git rebase --interactive HEAD~3  # Permite reordenar, modificar ou excluir commits
```

## 10. Tags
```sh
git tag  # Lista todas as tags
git tag -a v1.0 -m "Versão 1.0"  # Cria uma tag anotada
git push origin --tags  # Envia as tags para o repositório remoto
git tag -d v1.0  # Deleta uma tag local
git push origin --delete v1.0  # Deleta uma tag remota
```

Esses comandos cobrem os cenários mais comuns no desenvolvimento diário com Git. 🚀
