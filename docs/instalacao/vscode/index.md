# Instalação do VS Code

> *"Um bom editor não faz o programador, mas faz toda a diferença."*

---

## Passo 1 — Baixar o VS Code

Acesse o site oficial:

```
https://code.visualstudio.com/
```

Baixe a versão para seu sistema:

| Sistema  | Ação                                    |
|----------|-----------------------------------------|
| Windows  | Clique em **Download for Windows**      |
| Linux    | Baixe `.deb` (Debian/Ubuntu) ou `.rpm` (Fedora) |
| macOS    | Clique em **Download for macOS**        |

---

## Passo 2 — Instalar

### Windows

```
1. Execute o arquivo VSCodeUserSetup-x64-*.exe
2. Aceite os termos
3. Clique em Next → Next → Install
4. Marque as opções:
   ☑ Add "Open with Code" to file context menu
   ☑ Add "Open with Code" to directory context menu
5. Clique em Finish
```

### Linux (Debian/Ubuntu)

```bash
# Download via terminal
wget -O vscode.deb "https://code.visualstudio.com/sha/download?build=stable&os=linux-deb-x64"

# Instalar
sudo dpkg -i vscode.deb

# Se houver dependências faltando:
sudo apt install -f -y

# Verificar instalação
code --version
```

### Linux (Fedora)

```bash
# Download via terminal
wget -O vscode.rpm "https://code.visualstudio.com/sha/download?build=stable&os=linux-rpm-x64"

# Instalar
sudo dnf install vscode.rpm

# Verificar instalação
code --version
```

---

## Passo 3 — Abrir o VS Code

```bash
# Via terminal (funciona em todos os sistemas se estiver no PATH)
code

# Ou abra pelo menu de aplicativos do sistema
```

---

## Passo 4 — Instalar a Extensão Python

### Via Interface

```
1. Abra o VS Code
2. Pressione Ctrl + Shift + X (ou Cmd + Shift + X no Mac)
3. Pesquise por: Python
4. Instale a extensão publicada pela Microsoft
```

### Via Terminal (atalho)

```bash
# Instalar extensão Python diretamente pelo terminal
code --install-extension ms-python.python

# Instalar extensão Pylance (intellisense avançado)
code --install-extension ms-python.vscode-pylance
```

**Saída esperada:**

```bash
$ code --install-extension ms-python.python
Extension 'ms-python.python' v2024.6.0 was successfully installed.
```

---

## Passo 5 — Configurar o Interpretador Python

```
1. Abra um arquivo .py
2. Pressione Ctrl + Shift + P
3. Digite: Python: Select Interpreter
4. Escolha a versão instalada
```

**Ou clique no canto inferior direito:**

```
┌─────────────────────────────────────────┐
│  Python 3.12.3 ('.venv': venv)     🔽   │
└─────────────────────────────────────────┘
```

Clique na seta e selecione o interpretador correto.

---

## Passo 6 — Executar Código

Crie um arquivo `teste.py`:

```python
nome = input("Digite seu nome: ")
print(f"Olá, {nome}!")

for i in range(3):
    print(f"Contagem: {i + 1}")
```

### Opção 1 — Botão Play

```
Clique no ▶ (canto superior direito do editor)
```

### Opção 2 — Terminal Integrado

```bash
# Abrir terminal integrado: Ctrl + J
# Executar:
python teste.py
```

**Saída:**

```bash
$ python teste.py
Digite seu nome: Ana
Olá, Ana!
Contagem: 1
Contagem: 2
Contagem: 3
```

### Opção 3 — Menu de Contexto

```
Clique com botão direito no arquivo → Run Python File in Terminal
```

---

## Extensões Recomendadas

| Extensão                      | ID                                   | Função                          |
|-------------------------------|--------------------------------------|---------------------------------|
| Python                        | `ms-python.python`                   | Suporte à linguagem Python      |
| Pylance                       | `ms-python.vscode-pylance`           | IntelliSense avançado           |
| Python Indent                 | `KevinRose.vsc-python-indent`        | Indentação inteligente          |
| Material Icon Theme           | `PKief.material-icon-theme`          | Ícones bonitos para arquivos    |
| GitLens                       | `eamodio.gitlens`                    | Histórico do Git no editor      |

### Instalar Todas de Uma Vez

```bash
code --install-extension ms-python.python
code --install-extension ms-python.vscode-pylance
code --install-extension KevinRose.vsc-python-indent
code --install-extension PKief.material-icon-theme
code --install-extension eamodio.gitlens
```

---

## Configurações Úteis (settings.json)

Abra as configurações:

```
Ctrl + ,  →  Clique no ícone "{}" (canto superior direito)
```

Adicione:

```json
{
    "editor.fontSize": 16,
    "editor.fontFamily": "'JetBrains Mono', 'Fira Code', 'Cascadia Code', monospace",
    "editor.fontLigatures": true,
    "editor.minimap.enabled": false,
    "editor.formatOnSave": true,
    "editor.wordWrap": "on",
    "terminal.integrated.fontSize": 14,
    "files.autoSave": "afterDelay",
    "files.autoSaveDelay": 1000,
    "python.defaultInterpreterPath": "python3",
    "[python]": {
        "editor.tabSize": 4,
        "editor.defaultFormatter": "ms-python.python"
    },
    "workbench.iconTheme": "material-icon-theme",
    "workbench.colorTheme": "Default Dark Modern"
}
```

---

## Atalhos Essenciais

| Ação                          | Windows/Linux        | macOS               |
|-------------------------------|----------------------|---------------------|
| Abrir arquivo                 | `Ctrl + O`           | `Cmd + O`           |
| Salvar                        | `Ctrl + S`           | `Cmd + S`           |
| Salvar tudo                   | `Ctrl + Shift + S`   | `Cmd + Shift + S`   |
| Desfazer                      | `Ctrl + Z`           | `Cmd + Z`           |
| Refazer                       | `Ctrl + Shift + Z`   | `Cmd + Shift + Z`   |
| Localizar                     | `Ctrl + F`           | `Cmd + F`           |
| Localizar e substituir        | `Ctrl + H`           | `Cmd + Option + F`  |
| Ir para linha                 | `Ctrl + G`           | `Cmd + G`           |
| Terminal integrado            | `Ctrl + J`           | `Cmd + J`           |
| Paleta de comandos            | `Ctrl + Shift + P`   | `Cmd + Shift + P`   |
| Commentar linha               | `Ctrl + /`           | `Cmd + /`           |
| Duplicar linha                | `Shift + Alt + ↓`    | `Shift + Option + ↓`|
| Mover linha                   | `Alt + ↑/↓`          | `Option + ↑/↓`      |
| Multi-cursor                  | `Alt + Clique`       | `Option + Clique`   |
| Formatar documento            | `Shift + Alt + F`    | `Shift + Option + F`|
| Explorador de arquivos        | `Ctrl + Shift + E`   | `Cmd + Shift + E`   |

---