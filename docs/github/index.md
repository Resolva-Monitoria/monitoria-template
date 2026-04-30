# Tutorial de Utilização do GitHub

Guia completo para colaborar no projeto **Monitoria IFC Araquari** usando Git e GitHub via terminal.

---

## 1. Pré-requisitos

Antes de começar, certifique-se de ter o Git instalado:

```bash
git --version
```

Se não estiver instalado:

```bash
# Linux (Debian/Ubuntu)
sudo apt update && sudo apt install git -y

# Linux (Fedora)
sudo dnf install git -y

# macOS (com Homebrew)
brew install git

# Windows (baixe o instalador)
# https://git-scm.com/download/win
```

Configure seu usuário global:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@exemplo.com"
```

Verifique a configuração:

```bash
git config --global --list
```

---

## 2. Clonando o Repositório

Clone o repositório para sua máquina local:

```bash
git clone https://github.com/Resolva-Monitoria/monitoria-template.git

```

Acesse o diretório clonado:

```bash
cd monitoria-template
```

---

## 3. Configurando o Remote (Migração)

Se você clonou de outro lugar e quer apontar para este repositório:

```bash
# Verificar remotes atuais
git remote -v

# Adicionar um novo remote
git remote add origin https://github.com/Resolva-Monitoria/monitoria-template.git

# Remover um remote existente
git remote remove origin

# Renomear um remote
git remote rename old-name origin

# Alterar a URL de um remote
git remote set-url origin https://github.com/Resolva-Monitoria/monitoria-template.git
```

---

## 4. Branches (Ramos)

### Visualizar Branches

```bash
# Listar branches locais
git branch

# Listar branches remotos
git branch -r

# Listar todos os branches (locais e remotos)
git branch -a

# Ver branch atual com detalhes
git status
```

### Criar e Trocar de Branch

```bash
# Criar um novo branch
git branch minha-feature

# Criar e já entrar no branch (atalho)
git checkout -b minha-feature

# Trocar para um branch existente
git checkout dev

# Trocar para o branch main
git checkout main

# Voltar ao branch anterior (atalho)
git checkout -
```

---

## 5. Pull (Atualizar seu Repositório Local)

Mantenha seu código atualizado com o repositório remoto:

```bash
# Baixar e aplicar atualizações do branch atual
git pull

# Baixar e aplicar de um branch específico
git pull origin dev

# Baixar atualizações sem aplicar (apenas baixa)
git fetch origin

# Baixar atualizações e rebase (evita commits de merge)
git pull --rebase origin main
```

### Fluxo Recomendado de Atualização

```bash
# 1. Vá para o branch main
git checkout main

# 2. Atualize com o remoto
git pull origin main

# 3. Vá para seu branch de trabalho
git checkout minha-feature

# 4. Traga as atualizações do main para seu branch
git merge main
# ou
git rebase main
```

---

## 6. Trabalhando com Arquivos

### Verificar Status

```bash
# Ver status dos arquivos
git status

# Ver status de forma resumida
git status -s
```

### Adicionar Arquivos

```bash
# Adicionar um arquivo específico
git add docs/github/index.md

# Adicionar todos os arquivos modificados e novos
git add .

# Adicionar todos os arquivos de um diretório
git add docs/conteudo/

# Adicionar apenas arquivos modificados (ignora novos)
git add -u

# Adicionar interativamente (escolher arquivos)
git add -p
```

### Verificar Diferenças

```bash
# Ver diferenças não staged
git diff

# Ver diferenças staged (prontas para commit)
git diff --staged

# Ver diferenças de um arquivo específico
git diff docs/index.md

# Ver diferenças entre branches
git diff main..dev
```

---

## 7. Commits (Salvar Alterações)

### Fazer um Commit

```bash
# Commit simples com mensagem
git commit -m "feat: Adiciona tutorial de GitHub"

# Commit com título e descrição
git commit -m "fix: Corrige link do exercício" -m "Descrição detalhada da correção"

# Commit pulando o stage (para arquivos já rastreados)
git commit -am "docs: Atualiza documentação"

# Editar o último commit (sem alterar mensagem)
git commit --amend --no-edit

# Editar o último commit (com nova mensagem)
git commit --amend -m "nova mensagem"
```

### Convenção de Commits

Este projeto segue o **Conventional Commits**:

| Prefixo      | Descrição                                    |
|--------------|----------------------------------------------|
| `feat:`      | Nova funcionalidade                          |
| `fix:`       | Correção de bug                              |
| `docs:`      | Alteração na documentação                    |
| `style:`     | Formatação, ponto e vírgula, etc             |
| `refactor:`  | Refatoração de código                        |
| `test:`      | Adição ou correção de testes                 |
| `chore:`     | Tarefas de build/configuração                |

**Exemplos:**

```bash
git commit -m "feat: Adiciona exercícios sobre condicionais"
git commit -m "fix: Corrige erro de digitação na unidade 1"
git commit -m "docs: Atualiza README com novas instruções"
git commit -m "refactor: Reorganiza estrutura de navegação"
```

---

## 8. Push (Enviar para o Remoto)

### Enviar Commits

```bash
# Enviar branch atual para o remoto
git push

# Enviar branch atual e configurar upstream
git push -u origin minha-feature

# Enviar para um branch específico
git push origin dev

# Forçar push (CUIDADO - sobrescreve histórico)
git push --force origin minha-feature

# Forçar push com segurança (não sobrescreve se houver novos commits)
git push --force-with-lease origin minha-feature
```

### Primeiro Push de um Novo Branch

```bash
# Criar, fazer commit e enviar
git checkout -b minha-feature
# ... faça alterações ...
git add .
git commit -m "feat: Minha nova feature"
git push -u origin minha-feature
```

---

## 9. Comandos Úteis


### Desfazer Alterações

```bash
# Descartar alterações em um arquivo (não staged)
git checkout -- arquivo.md
# ou
git restore arquivo.md

# Descartar todas alterações não staged
git restore .

# Remover arquivo do stage (mantém alterações)
git reset HEAD arquivo.md
# ou
git restore --staged arquivo.md

# Desfazer último commit (mantém alterações)
git reset --soft HEAD~1

# Desfazer último commit (descarta alterações)
git reset --hard HEAD~1
```

---

## 10. Dicas Finais

- **Sempre faça `git pull` antes de começar a trabalhar**
- **Use branches para cada feature/correção**
- **Commits frequentes e pequenos são melhores que um commit gigante**
- **Use mensagens de commit claras e no padrão Conventional Commits**
- **Nunca force push no `main` ou `dev`**
- **Revise suas alterações com `git diff` antes de commitar**
