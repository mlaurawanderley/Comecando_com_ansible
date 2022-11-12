### Instalando Ansible no ubuntu 20.04 (WSL)

Antes de instalar verifique se você já possui o Python 3 instalado:
```bash
python3 --version
```

Caso você ainda não possua o Python instalado, pode baixar através do [link](https://www.python.org/downloads/).

Verifique também se o pip está disponível:
```bash
python3 -m pip -V
```


Caso não possua você deve instalar o pip com os seguintes comandos:
```bash
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py --user
```
---
### Podemos instalar o Ansible de 2 maneiras, através do pip ou do apt-get. 
### Confira abaixo o passo a passo com as duas opções:

**Instalar usando o modulo pip**
```bash
sudo apt update
python3 -m pip install --user ansible
```

**Instalar usando o apt-get**
```bash
sudo apt update
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update -y && sudo apt-get install -y ansible
```
---
Os proximos passos são os mesmos, independente da forma de instalação previamente escolhida. 

**Gerar um par de chaves SSH**

```bash
ssh-keygen
```

**Copie a chave pública para os servidores do seu cluster.**

```bash
ssh-copy-id -i /root/.ssh/id_rsa.pub <user>@<ip>
```

**Realize o teste de acesso SSH.**

```bash
ssh -i /root/.ssh/id_rsa.pub <user>@<ip
```

Após cumprir todas essas etapas você está pronto para dar os [Primeiros passos com Ansible](https://github.com/mlaurawanderley/Comecando_com_ansible/blob/main/ansible/primeiros-passos.md)

