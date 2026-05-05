# Tutorial de Utilização do GitHub

> *"Controle de versão é a rede de segurança de todo programador."*

---

## 1. Instalar e Configurar o Git

### Linux

```bash
# Debian/Ubuntu
sudo apt update && sudo apt install git -y

# Fedora
sudo dnf install git -y

# Arch Linux
sudo pacman -S git
```

### macOS

```bash
# Com Homebrew
brew install git

# Ou instale o Xcode Command Line Tools
xcode-select --install
```

### Windows

```
Baixe em: https://git-scm.com/download/win
Execute o instalador com as opções padrão
```

### Configuração Inicial

```bash
# Configurar nome e email (use os mesmos do GitHub)
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@exemplo.com"

# Configurar editor padrão
git config --global core.editor "code --wait"

# Verificar configuração
git config --global --list
```

**Saída esperada:**

```bash
$ git config --global --list
user.name=Paulo Artur
user.email=paulo@exemplo.com
core.editor=code --wait
```

---

## 2. Clonar um Repositório

### Via HTTPS (Recomendado)

```bash
git clone https://github.com/Resolva-Monitoria/monitoria-template.git
cd monitoria-template
```

### Via SSH (Se tiver chave configurada)

```bash
# Gerar chave SSH (se não tiver)
ssh-keygen -t ed25519 -C "seu-email@exemplo.com"

# Copiar a chave pública
cat ~/.ssh/id_ed25519.pub

# Adicionar no GitHub: Settings → SSH and GPG keys → New SSH key

# Clonar
git clone git@github.com:Resolva-Monitoria/monitoria-template.git
cd monitoria-template
```

### Verificar Conexão com o Remoto

```bash
git remote -v
```

**Saída:**

```bash
$ git remote -v
origin  https://github.com/Resolva-Monitoria/monitoria-template.git (fetch)
origin  https://github.com/Resolva-Monitoria/monitoria-template.git (push)
```

---

## 3. Migrar/Alterar o Remote

Se você clonou de outro lugar e quer apontar para este repositório:

```bash
# Verificar remotes atuais
git remote -v

# Remover remote antigo
git remote remove origin

# Adicionar novo remote
git remote add origin https://github.com/Resolva-Monitoria/monitoria-template.git

# Ou apenas alterar a URL
git remote set-url origin https://github.com/Resolva-Monitoria/monitoria-template.git

# Verificar alteração
git remote -v
```

### Adicionar Múltiplos Remotes

```bash
# Adicionar um segundo remote (ex: fork pessoal)
git remote add meu-fork https://github.com/seu-usuario/monitoria-template.git

# Ver todos os remotes
git remote -v
```

**Saída:**

```bash
$ git remote -v
origin      https://github.com/Resolva-Monitoria/monitoria-template.git (fetch)
origin      https://github.com/Resolva-Monitoria/monitoria-template.git (push)
meu-fork    https://github.com/seu-usuario/monitoria-template.git (fetch)
meu-fork    https://github.com/seu-usuario/monitoria-template.git (push)
```

---

## 4. Branches (Ramos)

### Branches Disponíveis neste Projeto

| Branch        | Descrição                               |
|---------------|-----------------------------------------|
| `main`        | Branch principal — versão estável       |
| `dev`         | Branch de desenvolvimento               |
| `gh-pages`    | Site publicado (GitHub Pages)           |
| `Loops`       | Conteúdo sobre loops                    |
| `Pages`       | Funcionalidades de páginas              |
| `dicionarios` | Conteúdo sobre dicionários              |

### Listar Branches

```bash
# Branches locais
git branch

# Branches remotos
git branch -r

# Todos os branches
git branch -a
```

**Saída:**

```bash
$ git branch -a
* main
  dev
  remotes/origin/main
  remotes/origin/dev
  remotes/origin/gh-pages
  remotes/origin/Loops
```

### Criar e Trocar de Branch

```bash
# Criar e entrar em um novo branch
git checkout -b minha-feature

# Ou usando o comando moderno
git switch -c minha-feature

# Trocar para branch existente
git checkout dev
git switch dev

# Voltar ao branch anterior
git checkout -
```

### Deletar Branch

```bash
# Deletar branch local
git branch -d minha-feature

# Forçar deleção (se não foi mergeado)
git branch -D minha-feature

# Deletar branch remoto
git push origin --delete minha-feature
```

### Trazer Branch Remoto para Local

```bash
# Baixar e criar branch local baseado no remoto
git checkout -b Loops origin/Loops

# Ou com switch
git switch Loops
```

---

## 5. Pull — Atualizar seu Repositório

### Comandos Básicos

```bash
# Baixar e aplicar atualizações do branch atual
git pull

# Baixar de um remote e branch específicos
git pull origin main

# Baixar sem aplicar (apenas baixa informações)
git fetch origin

# Baixar e rebase (evita commits de merge desnecessários)
git pull --rebase origin main
```

### Fluxo Recomendado de Atualização

```bash
# 1. Vá para o branch principal
git checkout main

# 2. Atualize com o remoto
git pull origin main

# 3. Volte para seu branch de trabalho
git checkout minha-feature

# 4. Traga as atualizações do main
git merge main
# ou (preferível):
git rebase main
```

### Verificar Diferenças entre Local e Remoto

```bash
# Ver o que mudou no remoto
git fetch origin
git log HEAD..origin/main --oneline

# Ver diferenças de conteúdo
git diff HEAD..origin/main
```

---

## 6. Trabalhando com Arquivos

### Verificar Status

```bash
# Status completo
git status

# Status resumido
git status -s
```

**Saída:**

```bash
$ git status -s
 M docs/index.md       ← Modificado (não staged)
A  docs/novo.md        ← Adicionado (staged)
?? docs/rascunho.md    ← Não rastreado
```

### Adicionar Arquivos

```bash
# Adicionar arquivo específico
git add docs/github/index.md

# Adicionar todos os arquivos modificados e novos
git add .

# Adicionar todos os arquivos de um diretório
git add docs/conteudo/

# Adicionar apenas arquivos modificados (ignora novos)
git add -u

# Adicionar interativamente (escolher partes de um arquivo)
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

# Ver resumo das mudanças
git diff --stat
```

**Saída:**

```bash
$ git diff docs/index.md
diff --git a/docs/index.md b/docs/index.md
--- a/docs/index.md
+++ b/docs/index.md
@@ -1,5 +1,5 @@
-# Título Antigo
+# Título Novo

 Conteúdo atualizado...
```

---

## 7. Commits — Salvar Alterações

### Fazer um Commit

```bash
# Commit com mensagem inline
git commit -m "feat: Adiciona tutorial de GitHub"

# Commit com título e descrição
git commit -m "fix: Corrige link do exercício" -m "O link apontava para a página errada. Agora aponta para a unidade correta."

# Commit pulando o stage (arquivos já rastreados)
git commit -am "docs: Atualiza documentação"
```

### Editar o Último Commit

```bash
# Alterar apenas a mensagem
git commit --amend -m "nova mensagem"

# Adicionar arquivo esquecido ao último commit
git add arquivo-esquecido.md
git commit --amend --no-edit

# Alterar mensagem e adicionar arquivo
git add arquivo-esquecido.md
git commit --amend -m "feat: Adiciona tutorial e arquivo extra"
```

### Conventional Commits

Este projeto segue o padrão **Conventional Commits**:

| Prefixo       | Quando Usar                           | Exemplo                                        |
|---------------|---------------------------------------|------------------------------------------------|
| `feat:`       | Nova funcionalidade                   | `feat: Adiciona exercícios sobre condicionais` |
| `fix:`        | Correção de bug                       | `fix: Corrige erro de digitação na unidade 1`  |
| `docs:`       | Alteração na documentação             | `docs: Atualiza README com novas instruções`   |
| `style:`      | Formatação, espaços, sem mudar lógica | `style: Remove espaços em branco`              |
| `refactor:`   | Refatoração de código                 | `refactor: Simplifica função de validação`     |
| `test:`       | Testes                                | `test: Adiciona testes para entrada de dados`  |
| `chore:`      | Build, configurações                  | `chore: Atualiza dependências do MkDocs`       |

---

## 8. Push — Enviar para o Remoto

### Enviar Commits

```bash
# Enviar branch atual (se já configurado)
git push

# Enviar e configurar upstream (primeira vez)
git push -u origin minha-feature

# Enviar para branch específico
git push origin dev

# Enviar todos os branches
git push --all origin
```

### Force Push (Cuidado!)

```bash
# Forçar push (sobrescreve histórico remoto)
git push --force origin minha-feature

# Forçar push com segurança (não sobrescreve se houver novos commits)
git push --force-with-lease origin minha-feature
```

> Nunca use `--force` no `main` ou `dev`. Use apenas em branches pessoais.

### Verificar Status Após Push

```bash
git status
```

**Se tudo está sincronizado:**

```bash
$ git status
On branch minha-feature
Your branch is up to date with 'origin/minha-feature'.
nothing to commit, working tree clean
```

---

## 9. Pull Requests (PRs)

### Via GitHub CLI (`gh`)

```bash
# Instalar o GitHub CLI
# Linux (Debian/Ubuntu)
sudo apt install gh -y

# macOS
brew install gh

# Windows
winget install GitHub.cli
```

### Autenticar

```bash
gh auth login
```

Siga as instruções no terminal para autenticar via navegador ou token.

### Criar um Pull Request

```bash
# Criar PR do branch atual para main
gh pr create --base main --title "feat: Adiciona tutorial de GitHub" --body "Descrição das mudanças realizadas."

# Criar PR de forma interativa
gh pr create

# Abrir navegador para criar PR
gh pr create --web
```

### Gerenciar PRs

```bash
# Listar PRs abertos
gh pr list

# Ver detalhes de um PR
gh pr view 123

# Fazer checkout de um PR
gh pr checkout 123

# Aprovar um PR
gh pr review --approve

# Comentar em um PR
gh pr comment --body "Ótimo trabalho!"
```

### Via GitHub Web

```
1. Acesse: https://github.com/Resolva-Monitoria/monitoria-template
2. Clique em "Compare & pull request"
3. Selecione:
   - base: main (ou dev)
   - compare: sua-feature
4. Adicione título e descrição
5. Clique em "Create pull request"
```

---

## 10. Resolução de Conflitos

Quando o Git não consegue mesclar automaticamente:

```bash
# Tentar merge
git merge main
```

**Se houver conflito:**

```bash
$ git merge main
Auto-merging docs/index.md
CONFLICT (content): Merge conflict in docs/index.md
Automatic merge failed; fix conflicts and then commit the result.
```

### Resolver o Conflito

```bash
# Ver arquivos em conflito
git status

# Abrir o arquivo conflitante
code docs/index.md
```

O arquivo terá marcadores assim:

```markdown
<<<<<<< HEAD
# Meu Título
=======
# Título Atualizado
>>>>>>> main
```

**Resolva manualmente:**

```markdown
# Título Atualizado
```

### Finalizar

```bash
# Marcar como resolvido
git add docs/index.md

# Completar o merge
git commit -m "merge: Resolve conflito em docs/index.md"
```

### Abortar um Merge

```bash
git merge --abort
```

---

## 11. Comandos Úteis

### Histórico

```bash
# Histórico completo
git log

# Histórico resumido
git log --oneline

# Histórico com gráfico
git log --oneline --graph --all --decorate

# Histórico de um arquivo
git log --follow docs/index.md

# Últimos 10 commits
git log --oneline -10

# Histórico com autor e data
git log --oneline --format="%h %an %ar %s"
```

**Saída:**

```bash
$ git log --oneline -5
87bb2de (HEAD -> main, origin/main) Merge pull request #8
e953dc1 fix: Atualiza links de exercícios
9b331d6 feat: Atualiza navegação da Unidade 2
47c9a9c feat: Adiciona material de prática para condicionais
e64ce03 fix: Corrige enunciados de entradas e saídas
```

### Desfazer Alterações

```bash
# Descartar alterações em um arquivo (não staged)
git restore docs/index.md

# Descartar todas alterações não staged
git restore .

# Remover arquivo do stage (mantém alterações)
git restore --staged docs/index.md

# Desfazer último commit (mantém alterações no stage)
git reset --soft HEAD~1

# Desfazer último commit (mantém alterações, remove do stage)
git reset HEAD~1

# Desfazer último commit (DESCARTA todas alterações — CUIDADO!)
git reset --hard HEAD~1
```

### Stash (Guardar Alterações Temporariamente)

```bash
# Guardar alterações atuais
git stash

# Guardar com mensagem
git stash push -m "WIP: trabalhando na feature X"

# Listar stashes
git stash list

# Aplicar último stash e removê-lo
git stash pop

# Aplicar stash específico sem removê-lo
git stash apply stash@{0}

# Remover stash
git stash drop stash@{0}

# Limpar todos os stashes
git stash clear
```

**Saída:**

```bash
$ git stash list
stash@{0}: WIP: trabalhando na feature X
stash@{1}: On main: alterações temporárias
```

### Tags

```bash
# Listar tags
git tag

# Criar tag anotada
git tag -a v1.0.0 -m "Versão 1.0.0"

# Enviar tags para o remoto
git push origin --tags

# Criar tag em commit específico
git tag -a v1.1.0 87bb2de -m "Versão 1.1.0"
```

### Limpeza

```bash
# Remover arquivos não rastreados (simulação)
git clean -n

# Remover arquivos não rastreados (real)
git clean -f

# Remover arquivos e diretórios não rastreados
git clean -fd
```

---

## 12. Fluxo de Trabalho Completo

### Cenário: Contribuir com Novo Conteúdo

```bash
# 1. Clonar (primeira vez)
git clone https://github.com/Resolva-Monitoria/monitoria-template.git
cd monitoria-template

# 2. Criar branch para sua tarefa
git checkout -b feat/unidade-loops

# 3. Fazer alterações
# ... edite arquivos no VS Code ...

# 4. Verificar o que mudou
git status
git diff

# 5. Adicionar e commite
git add docs/conteudo/unidade-3/
git commit -m "feat: Adiciona conteúdo sobre loops"

# 6. Continuar trabalhando
# ... mais alterações ...
git add .
git commit -m "feat: Adiciona exercícios resolvidos de for/while"

# 7. Atualizar com o main mais recente
git fetch origin
git rebase origin/main

# 8. Enviar para o GitHub
git push -u origin feat/unidade-loops

# 9. Criar Pull Request
gh pr create --base main --title "feat: Unidade 3 - Loops" --body "Conteúdo completo sobre for e while."
```

---

## 13. Publicando o Site (GitHub Pages)

Este projeto usa **MkDocs** para gerar o site.

### Instalar MkDocs

```bash
pip install mkdocs mkdocs-material mkdocs-minify-plugin
```

### Build Local

```bash
# Gerar o site estático
mkdocs build

# O site será gerado na pasta site/
ls site/
```

### Servir Localmente

```bash
# Iniciar servidor de desenvolvimento
mkdocs serve

# O site estará em: http://localhost:8000
```

### Deploy para GitHub Pages

```bash
# Deploy automático
mkdocs gh-deploy

# Deploy com mensagem customizada
mkdocs gh-deploy --message "Atualiza site com novo conteúdo sobre loops"
```

**Saída:**

```bash
$ mkdocs gh-deploy
INFO    -  Building documentation...
INFO    -  Documentation built in 2.34 seconds
INFO    -  Copying 'site' to 'gh-pages' branch...
INFO    -  Deploying to GitHub...
Your documentation should be available shortly at:
https://resolva-monitoria.github.io/monitoria-template/
```

---

## 14. Git Hooks (Automatizações)

### Pre-commit Hook — Verificar Antes de Commitar

```bash
# Criar arquivo de hook
cat > .git/hooks/pre-commit << 'EOF'
#!/bin/bash
echo "Verificando arquivos antes do commit..."
# Adicione verificações aqui
echo "OK!"
EOF

# Tornar executável
chmod +x .git/hooks/pre-commit
```

---

## 15. Dicas Finais

| Dica                                    | Por que Fazer                               |
|-----------------------------------------|---------------------------------------------|
| Sempre `git pull` antes de começar      | Evita conflitos com mudanças recentes       |
| Use branches para cada feature/correção | Mantém o main limpo e estável               |
| Commits pequenos e frequentes           | Facilita rastrear e reverter mudanças       |
| Use mensagens no padrão Conventional    | Padroniza o histórico do projeto            |
| Nunca force push no main/dev            | Pode apagar trabalho de outros colaboradores |
| Revise com `git diff` antes de commitar | Evita enviar código com erros               |
| Use `git stash` para trocar de branch   | Guarda trabalho em andamento sem commitar   |
