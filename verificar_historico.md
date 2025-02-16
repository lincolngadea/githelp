# Comandos para Analisar o Histórico de Commits no Git

Este documento lista comandos úteis para visualizar e analisar o histórico de commits no Git.

## 1. Exibir o Histórico de Commits
```sh
git log  # Exibe a lista completa de commits
```

### 1.1. Exibir Histórico Compacto
```sh
git log --oneline  # Mostra o histórico em uma linha por commit (hash + mensagem)
```

### 1.2. Exibir Histórico com Gráfico
```sh
git log --oneline --graph --decorate --all  # Mostra um gráfico visual dos branches e merges
```

### 1.3. Exibir Commits de um Arquivo Específico
```sh
git log -- <arquivo>  # Exibe apenas os commits que modificaram um arquivo específico
```

### 1.4. Exibir Commits com Diferentes Formatos
```sh
git log --pretty=short   # Mostra commits com mensagens curtas
git log --pretty=full    # Exibe autor, e-mail e data de cada commit
git log --pretty=format:"%h - %an: %s"  # Personaliza a saída
```

### 1.5. Exibir Commits de um Autor Específico
```sh
git log --author="Nome do Autor"
```

## 2. Filtrar Commits por Data
```sh
git log --since="2 weeks ago"  # Exibe commits feitos nas últimas 2 semanas
git log --until="2024-01-01"  # Exibe commits até uma data específica
```

## 3. Exibir Commits com Alterações (Diff)
```sh
git log -p  # Exibe os commits junto com as alterações feitas
```

## 4. Contar Número de Commits
```sh
git rev-list --count HEAD  # Conta o número total de commits no repositório
```

## 5. Identificar Quem Modificou uma Linha Específica
```sh
git blame <arquivo>  # Mostra quem alterou cada linha do arquivo e em qual commit
```

## 6. Exibir a Última Modificação de Cada Arquivo
```sh
git log --name-only  # Lista arquivos modificados em cada commit
git log --stat  # Exibe estatísticas de cada commit
```

## 7. Buscar Commits por Palavra-chave
```sh
git log --grep="bugfix"  # Mostra commits cuja mensagem contém "bugfix"
```

## 8. Reverter para um Commit Anterior
```sh
git checkout <commit_hash>  # Move para um commit específico (modo detached head)
git reset --hard <commit_hash>  # Retorna ao estado de um commit específico, descartando alterações posteriores
```

Esses comandos ajudam a visualizar e analisar o histórico de commits no Git de maneira eficiente. 🚀