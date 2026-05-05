# Visão Geral — Ambiente de Programação

> *"Antes de escrever código, entenda as ferramentas que você vai usar."*

---

## O Que Você Precisa

Para programar em Python, você precisa de três componentes:

| Componente        | Função                                    |
|-------------------|-------------------------------------------|
| **Python**        | Interpretador — executa seu código `.py`  |
| **VS Code**       | Editor — onde você escreve e organiza código |
| **Terminal**      | Interface — roda programas e instala pacotes |

---

## Como Tudo Funciona

```
┌─────────────────────────────────────────────┐
│           Fluxo de Desenvolvimento           │
├─────────────────────────────────────────────┤
│                                             │
│  1. Você escreve código  →  VS Code         │
│           ↓                                 │
│  2. Salva como arquivo   →  .py             │
│           ↓                                 │
│  3. Executa no terminal  →  python app.py   │
│           ↓                                 │
│  4. Python interpreta    →  Resultado       │
│                                             │
└─────────────────────────────────────────────┘
```

---

## Verificando se Tudo Está Instalado

Abra o terminal e rode:

```bash
# Verificar Python
python3 --version
# ou no Windows:
python --version

# Verificar pip (gerenciador de pacotes)
pip3 --version

# Verificar VS Code (se estiver no PATH)
code --version
```

**Saída esperada:**

```bash
$ python3 --version
Python 3.12.3

$ pip3 --version
pip 24.0 from /usr/lib/python3/dist-packages/pip (python 3.12)

$ code --version
1.89.0
```

---

## Ordem de Instalação

Siga esta sequência:

| Passo | Ação                          | Guia                                  |
|-------|-------------------------------|---------------------------------------|
| 1     | Instalar Python               | [Linux](linux/index.md) / [Windows](windows/index.md) |
| 2     | Instalar VS Code              | [VS Code](vscode/index.md)            |
| 3     | Configurar extensões          | [VS Code](vscode/index.md)            |
| 4     | Clone este repositório        | [GitHub](../github/index.md)          |

---

## Terminal — Comandos Básicos

| Ação                  | Linux/macOS         | Windows             |
|-----------------------|---------------------|---------------------|
| Listar arquivos       | `ls`                | `dir`               |
| Entrar em pasta       | `cd nome-da-pasta`  | `cd nome-da-pasta`  |
| Voltar uma pasta      | `cd ..`             | `cd ..`             |
| Criar pasta           | `mkdir nome`        | `mkdir nome`        |
| Criar arquivo         | `touch arquivo.py`  | `type nul > arquivo.py` |
| Limpar tela           | `clear`             | `cls`               |
| Executar Python       | `python3 arquivo.py`| `python arquivo.py` |
