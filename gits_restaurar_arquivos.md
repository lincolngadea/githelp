# Recuperação de Arquivos Deletados no Git

Este documento lista os comandos Git para lidar com arquivos deletados, seja de forma intencional ou acidental.

## 1. Verificar Arquivos Deletados
Antes de restaurar, verifique quais arquivos foram removidos:
```sh
git status  # Exibe arquivos deletados e não rastreados
git ls-files --deleted  # Lista arquivos deletados que ainda estão no índice
```

## 2. Restaurar Arquivos Deletados Antes do Commit
Se um arquivo foi removido, mas o commit ainda não foi feito:
```sh
git checkout -- <arquivo>  # Restaura um arquivo deletado no working directory
```
Exemplo:
```sh
git checkout -- src/config.yaml  # Restaura config.yaml deletado
```

Alternativamente, em versões mais recentes do Git:
```sh
git restore <arquivo>
```

## 3. Restaurar Arquivos Deletados Após o Commit
Se um arquivo foi removido e o commit já foi feito, mas ainda não foi enviado ao repositório remoto:
```sh
git checkout HEAD~1 -- <arquivo>
```
Se deseja reverter toda a alteração:
```sh
git reset HEAD~1 --hard  # Volta ao estado anterior ao último commit
```

## 4. Restaurar Arquivos de um Commit Específico
Se deseja restaurar um arquivo específico de um commit anterior:
```sh
git checkout <commit_hash> -- <arquivo>
```
Para encontrar o hash do commit:
```sh
git log --oneline
```
Exemplo:
```sh
git checkout 3f2a1b7 -- src/config.yaml
```

## 5. Restaurar Arquivos Removidos do Staging
Se um arquivo foi deletado e já adicionado ao staging (`git add`), mas ainda não foi commitado:
```sh
git reset HEAD <arquivo>
git checkout -- <arquivo>
```

## 6. Recuperar Arquivos Deletados Após um `git push`
Se um arquivo foi deletado, commitado e enviado para o repositório remoto, use:
```sh
git revert <commit_hash>
```
Ou para restaurar o arquivo manualmente:
```sh
git checkout <commit_hash> -- <arquivo>
git add <arquivo>
git commit -m "Restaurando arquivo deletado"
git push origin main
```

## 7. Recuperar Arquivos que Não Estavam Rastreáveis pelo Git
Se um arquivo foi deletado antes de ser rastreado pelo Git (nunca foi adicionado com `git add`):
- **Não será possível restaurá-lo pelo Git.**
- Use ferramentas do sistema operacional como `Ctrl+Z`, `lixeira`, ou software de recuperação de arquivos.

---
Esses comandos cobrem as situações mais comuns ao lidar com arquivos deletados no Git. 🚀
