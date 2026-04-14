# Instalação do Python no Ubuntu

> *"A melhor forma de aprender programação é colocando a mão no código."*

---

## Sobre esta página

Este guia mostra **passo a passo completo** como instalar o Python no Ubuntu usando o terminal.

Você vai aprender:

- Verificar se já tem Python instalado  
- Instalar Python e pip  
- Criar e executar seu primeiro programa  
- Preparar seu ambiente corretamente  

---

## Abrindo o terminal

!!! tip "Abrindo o terminal"
    Você pode abrir o terminal usando:

- Atalho: `CTRL + ALT + T`  
- Ou pesquisando por **Terminal** no sistema  

---

## Verificando se o Python já está instalado

!!! info "Passo 1"
    Vamos verificar se o Python já existe no sistema.

Digite no terminal:

```bash
python3 --version
```

Saída esperada (print simulado):

```bash
paulo@ubuntu:~$ python3 --version
Python 3.10.12
```

✔️ Se aparecer algo assim, você já tem Python instalado!  
❗ Se aparecer erro, continue para a instalação.

---

## Atualizando o sistema

!!! warning "Passo 2"
    Antes de instalar qualquer coisa, atualize o sistema.

```bash
sudo apt update && sudo apt upgrade -y
```

Print simulado:

```bash
paulo@ubuntu:~$ sudo apt update && sudo apt upgrade -y
[sudo] senha for paulo:
Hit:1 http://archive.ubuntu.com/ubuntu jammy InRelease
Reading package lists... Done
Building dependency tree... Done
```

---

## Instalando Python e pip

!!! warning "Passo 3"
    Agora vamos instalar o Python e o gerenciador de pacotes pip.

```bash
sudo apt install python3 python3-pip -y
```

Print simulado:

```bash
paulo@ubuntu:~$ sudo apt install python3 python3-pip -y
Reading package lists... Done
Building dependency tree... Done
Installing:
python3
python3-pip
Done.
```

---

## Confirmando a instalação

!!! success "Passo 4"
    Verifique se tudo foi instalado corretamente.

```bash
python3 --version
pip3 --version
```

Print simulado:

```bash
paulo@ubuntu:~$ python3 --version
Python 3.10.12

paulo@ubuntu:~$ pip3 --version
pip 22.0.2 from /usr/lib/python3/dist-packages/pip (python 3.10)
```

---

## Criando seu primeiro programa

!!! tip "Passo 5"
    Vamos criar um arquivo Python simples.

```bash
nano teste.py
```

Digite dentro do arquivo:

```python
print("Olá, mundo!")
```

Agora salve:

```
CTRL + O → Enter
CTRL + X
```

---

## Executando o programa

```bash
python3 teste.py
```

Print simulado:

```bash
paulo@ubuntu:~$ python3 teste.py
Olá, mundo!
```

Parabéns! Seu primeiro programa rodou com sucesso.

---

## (Opcional) Usar comando python

!!! note "Passo 6"
    Por padrão usamos python3, mas você pode ativar o comando python.

```bash
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 1
```

Agora funciona assim:

```bash
python teste.py
```
Print simulado:

```bash
paulo@ubuntu:~$ python teste.py
Olá, mundo!
```

---

## Conclusão

!!! success "Você concluiu!"
    Agora você está pronto para programar 

Você tem:

-  Python instalado  
-  pip funcionando  
-  Terminal configurado  
-  Primeiro programa executado  