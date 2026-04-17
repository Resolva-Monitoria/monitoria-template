# Instalação do Python no Windows

> *"Todo programador começou com um simples print."*

---

## Sobre esta página

Este guia ensina como instalar o **Python no Windows** de forma correta e sem erros comuns.

Você aprenderá:

- Baixar o Python  
- Instalar corretamente  
- Configurar o PATH  
- Executar programas  

---

## Download do Python

!!! info "Site oficial"
    Sempre baixe o Python do site oficial:

```
https://www.python.org/downloads/
```

---

## Etapa mais importante

!!! danger "ATENÇÃO"
    Durante a instalação, marque a opção:

```
Add Python to PATH
```

Sem isso, o Python pode não funcionar no terminal.

---

## Instalação

!!! tip "Instalando"
    Após marcar a opção, clique em:

```
Install Now
```

---

## Verificação

!!! success "Testando instalação"
    Abra o CMD ou PowerShell:

```bash
python --version
pip --version
```

Saída esperada (print simulado):

```bash
C:\Users\paulo> python --version
Python 3.12.0

C:\Users\paulo> pip --version
pip 23.2.1 from ...
```

Se aparecer a versão, está, tudo certo ✅

---

## Primeiro programa

!!! info "Criando arquivo"
    Crie um arquivo chamado:

```
teste.py
```

Conteúdo:

```python
print("Olá, mundo!")
```

Execute:

```bash
python teste.py
```

💻 Print simulado:

```bash
C:\Users\paulo> python teste.py
Olá, mundo!
```

---

## Problemas comuns

!!! warning "Erro comum"
    Se aparecer:

```
python não é reconhecido como um comando interno ou externo
```

### Solução:

- Reinstalar o Python  
- Marcar **Add Python to PATH**  
- Ou configurar o PATH manualmente  

---

## Dica

!!! tip "Terminal"
    Use o **Windows Terminal** ou **PowerShell** para melhor experiência.

---

## Conclusão

!!! success "Resultado"
    Agora você tem:

- Python instalado no Windows  
- Terminal funcionando  
- Ambiente pronto para programar  