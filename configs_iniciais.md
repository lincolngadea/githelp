# Configuração Inicial do Git

Este guia descreve os passos essenciais para configurar o Git corretamente em um novo ambiente.

## 1. Verificar Instalação do Git
```sh
git --version
```
Caso o Git não esteja instalado, faça o download e instale-o a partir do site oficial:
[Download Git](https://git-scm.com/downloads)

## 2. Configurar Nome de Usuário e E-mail
O Git usa essas informações para associar commits ao autor correto.
```sh
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```
Verificar configurações:
```sh
git config --global --list
```

## 3. Configurar o Editor Padrão (Opcional)
Se desejar definir um editor específico para mensagens de commit:
```sh
git config --global core.editor "code --wait"  # VS Code
git config --global core.editor "vim"         # Vim
```

## 4. Definir o Branch Padrão como `main`
A partir do Git 2.28, pode definir o branch inicial como `main`:
```sh
git config --global init.defaultBranch main
```

## 5. Gerar e Adicionar uma Chave SSH ao GitHub/GitLab (Opcional)
Se for usar GitHub ou GitLab via SSH:
```sh
ssh-keygen -t rsa -b 4096 -C "seu@email.com"
```
Adicionar a chave ao SSH-Agent:
```sh
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```
Exibir a chave pública para adicioná-la ao GitHub/GitLab:
```sh
cat ~/.ssh/id_rsa.pub
```

## 6. Configurar Cache de Credenciais (Opcional)
Se for usar HTTPS e não quiser digitar a senha toda vez:
```sh
git config --global credential.helper cache
```
Ou usar o gerenciador de credenciais do sistema:
```sh
git config --global credential.helper store
```

## 7. Criar um Repositório Local ou Clonar um Existente
Para iniciar um novo repositório:
```sh
git init
```
Para clonar um repositório remoto:
```sh
git clone <URL_DO_REPOSITORIO>
```

## 8. Criar um Arquivo `.gitignore` (Opcional)
Criar um arquivo `.gitignore` para ignorar arquivos desnecessários, por exemplo:
```
*.log
node_modules/
venv/
target/
.DS_Store
.idea/
```

## 9. Fazer o Primeiro Commit
Se iniciou um repositório do zero:
```sh
echo "# Meu Projeto" > README.md
git add .
git commit -m "Primeiro commit"
```

## 10. Vincular ao Repositório Remoto e Enviar o Código
Se ainda não vinculou ao GitHub/GitLab:
```sh
git remote add origin <URL_DO_REPOSITORIO>
git push -u origin main
```

Agora seu ambiente Git está configurado e pronto para uso! 🚀
