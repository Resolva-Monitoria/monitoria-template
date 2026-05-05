# Instalação do Python — Linux

> *"No Linux, tudo começa pelo terminal."*

---

## Passo 1 — Abrir o Terminal

```bash
# Atalho padrão
CTRL + ALT + T

# Ou busque por "Terminal" no menu de aplicativos
```

---

## Passo 2 — Verificar se o Python Já Está Instalado

```bash
python3 --version
```

**Se aparecer algo como:**

```bash
$ python3 --version
Python 3.12.3
```

Você já tem Python instalado. Pule para o **Passo 5**.

**Se aparecer erro:**

```bash
$ python3 --version
bash: python3: comando não encontrado
```

Continue para o próximo passo.

---

## Passo 3 — Atualizar o Sistema

```bash
sudo apt update && sudo apt upgrade -y
```

**O que este comando faz:**

| Parte                          | Função                                      |
|--------------------------------|---------------------------------------------|
| `sudo`                         | Executa como administrador (root)            |
| `apt update`                   | Atualiza a lista de pacotes disponíveis      |
| `apt upgrade -y`               | Instala as atualizações automaticamente      |

**Saída esperada:**

```bash
$ sudo apt update && sudo apt upgrade -y
[sudo] senha para usuario:
Hit:1 http://archive.ubuntu.com/ubuntu noble InRelease
Hit:2 http://security.ubuntu.com/ubuntu noble-security InRelease
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
All packages are up to date.
Reading package lists... Done
Building dependency tree... Done
The following packages will be upgraded:
  base-files curl libcurl4t64 linux-firmware
4 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
```

---

## Passo 4 — Instalar Python e pip

```bash
sudo apt install python3 python3-pip python3-venv -y
```

**O que cada pacote faz:**

| Pacote           | Função                                        |
|------------------|-----------------------------------------------|
| `python3`        | Interpretador Python                          |
| `python3-pip`    | Gerenciador de pacotes (instala bibliotecas)  |
| `python3-venv`   | Cria ambientes virtuais isolados              |

**Saída esperada:**

```bash
$ sudo apt install python3 python3-pip python3-venv -y
Reading package lists... Done
Building dependency tree... Done
The following additional packages will be installed:
  python3-dev python3-wheel
The following NEW packages will be installed:
  python3-pip python3-venv
0 upgraded, 5 newly installed, 0 to remove and 0 not upgraded.
Setting up python3-pip (24.0+ubuntu1)...
Setting up python3-venv (3.12.3-0ubuntu2)...
```

---

## Passo 5 — Verificar a Instalação

```bash
python3 --version
pip3 --version
```

**Saída esperada:**

```bash
$ python3 --version
Python 3.12.3

$ pip3 --version
pip 24.0 from /usr/lib/python3/dist-packages/pip (python 3.12)
```

---

## Passo 6 — Criar um Ambiente Virtual (Recomendado)

Ambientes virtuais isolam as dependências de cada projeto.

```bash
# Criar o ambiente virtual
python3 -m venv .venv

# Ativar o ambiente
source .venv/bin/activate

# Verificar que está ativo
which python3
```

**Saída esperada:**

```bash
$ python3 -m venv .venv
$ source .venv/bin/activate
(.venv) $ which python3
/home/usuario/projeto/.venv/bin/python3
```

> O prefixo `(.venv)` no terminal indica que o ambiente está ativo.

**Para desativar:**

```bash
deactivate
```

---

## Passo 7 — Criar e Executar o Primeiro Programa

```bash
# Criar arquivo
nano ola.py
```

Digite o conteúdo:

```python
nome = input("Digite seu nome: ")
print(f"Olá, {nome}! Bem-vindo à Monitoria!")
```

Salve e saia do nano:

```
CTRL + O  → Enter  (salva)
CTRL + X           (sai)
```

Execute:

```bash
python3 ola.py
```

**Saída:**

```bash
$ python3 ola.py
Digite seu nome: Maria
Olá, Maria! Bem-vindo à Monitoria!
```

---

## (Opcional) — Usar `python` em vez de `python3`

No Linux, o comando padrão é `python3`. Se quiser usar apenas `python`:

```bash
# Instalar o pacote python-is-python3
sudo apt install python-is-python3 -y

# Verificar
python --version
```

**Saída:**

```bash
$ python --version
Python 3.12.3
```

---

## (Opcional) — Instalar Versão Mais Recente do Python

Se sua distribuição não tem a versão mais recente:

```bash
# Adicionar repositório deadsnakes (Ubuntu)
sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo apt update

# Instalar versão específica (ex: 3.13)
sudo apt install python3.13 python3.13-venv python3.13-pip -y

# Verificar
python3.13 --version
```

---

## Comandos Úteis do Terminal

| Comando                          | Descrição                            |
|----------------------------------|--------------------------------------|
| `pwd`                            | Mostra o diretório atual             |
| `ls`                             | Lista arquivos e pastas              |
| `ls -la`                         | Lista com detalhes (ocultos também)  |
| `cd caminho`                     | Entra em um diretório                |
| `cd ..`                          | Volta um diretório                   |
| `mkdir nome`                     | Cria um diretório                    |
| `touch arquivo.py`               | Cria um arquivo vazio                |
| `rm arquivo.py`                  | Remove um arquivo                    |
| `rm -rf pasta/`                  | Remove um diretório e seu conteúdo   |
| `cp origem destino`              | Copia arquivo                        |
| `mv origem destino`              | Move/renomeia arquivo                |
| `cat arquivo.py`                 | Mostra conteúdo do arquivo           |
| `clear`                          | Limpa a tela do terminal             |
| `history`                        | Mostra comandos anteriores           |
| `which python3`                  | Mostra onde o Python está instalado  |

---
