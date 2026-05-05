# Instalação do Python — Windows

> *"No Windows, o segredo é marcar a opção certa na instalação."*

---

## Passo 1 — Baixar o Python

Acesse o site oficial:

```
https://www.python.org/downloads/
```

O site detecta seu sistema automaticamente. Clique no botão **"Download Python"**.

> Sempre baixe do site oficial. Evite repositórios de terceiros.

---

## Passo 2 — Abrir o Instalador

Encontre o arquivo baixado (geralmente em `Downloads`) e execute:

```
python-3.x.x-amd64.exe
```

---

## Passo 3 — Configurar a Instalação

!!! danger "ATENÇÃO — Passo Mais Importante"

    Na tela de instalação, **MARQUE** a opção:

    ```
    ☑ Add python.exe to PATH
    ```

    Sem isso, o Python não funcionará no terminal.

**Tela do instalador:**

```
┌─────────────────────────────────────────────────┐
│         Install Python 3.x.x (64-bit)           │
├─────────────────────────────────────────────────┤
│                                                 │
│  ☑ Add python.exe to PATH    ← MARQUE ISSO!    │
│                                                 │
│  [Install Now]     [Customize installation]     │
│                                                 │
└─────────────────────────────────────────────────┘
```

Clique em **Install Now**.

---

## Passo 4 — Aguardar a Instalação

O instalador vai:

```
Installing Python 3.x.x (64-bit)
████████████████████████████████ 100%

Setting up Python
Installing pip
Installing documentation
Installing test suite
```

Clique em **Close** quando terminar.

---

## Passo 5 — Verificar a Instalação

Abra o **PowerShell** ou **CMD**:

```
# Abrir pelo menu Iniciar
# Digite: PowerShell
# Pressione Enter
```

Verifique a instalação:

```powershell
python --version
pip --version
```

**Saída esperada:**

```powershell
PS C:\Users\usuario> python --version
Python 3.12.3

PS C:\Users\usuario> pip --version
pip 24.0 from C:\Users\usuario\AppData\Local\Python312\Lib\site-packages\pip (python 3.12)
```

---

## Passo 6 — Criar e Executar o Primeiro Programa

```powershell
# Criar uma pasta para o projeto
mkdir projetos-python
cd projetos-python

# Criar o arquivo
New-Item -Path "ola.py" -ItemType File
```

Edite o arquivo `ola.py` com seu editor de texto e adicione:

```python
nome = input("Digite seu nome: ")
print(f"Olá, {nome}! Bem-vindo à Monitoria!")
```

Execute:

```powershell
python ola.py
```

**Saída:**

```powershell
PS C:\Users\usuario\projetos-python> python ola.py
Digite seu nome: João
Olá, João! Bem-vindo à Monitoria!
```

---

## (Opcional) — Criar Ambiente Virtual

```powershell
# Criar ambiente virtual
python -m venv .venv

# Ativar
.venv\Scripts\Activate.ps1

# Verificar que está ativo
where python
```

**Saída:**

```powershell
PS C:\Users\usuario\projetos-python> python -m venv .venv
PS C:\Users\usuario\projetos-python> .venv\Scripts\Activate.ps1
(.venv) PS C:\Users\usuario\projetos-python> where python
C:\Users\usuario\projetos-python\.venv\Scripts\python.exe
```

> O prefixo `(.venv)` indica que o ambiente está ativo.

**Para desativar:**

```powershell
deactivate
```

---

## Comandos Úteis do PowerShell

| Comando                              | Descrição                            |
|--------------------------------------|--------------------------------------|
| `Get-Location` / `pwd`               | Mostra diretório atual               |
| `Get-ChildItem` / `dir` / `ls`       | Lista arquivos e pastas              |
| `Set-Location caminho` / `cd caminho`| Entra em um diretório                |
| `cd ..`                              | Volta um diretório                   |
| `New-Item -ItemType Directory -Path nome` | Cria diretório              |
| `New-Item -Path arquivo.py -ItemType File` | Cria arquivo vazio         |
| `Remove-Item arquivo.py`             | Remove arquivo                       |
| `Remove-Item -Recurse pasta/`        | Remove diretório e conteúdo          |
| `Copy-Item origem destino`           | Copia arquivo                        |
| `Move-Item origem destino`           | Move/renomeia arquivo                |
| `Get-Content arquivo.py` / `cat`     | Mostra conteúdo do arquivo           |
| `Clear-Host` / `cls`                 | Limpa a tela                         |

--- 