
# Primeiros passos após a instalação

O primeiro passo após a instalação do Ansible, é a configuração do arquivo de inventario, que contém informações sobre os hosts que você irá gerenciar com o Ansible. Você pode incluir qualquer lugar, de um a centenas de servidores no seu arquivo de inventário. Além disso, hosts podem ser organizados em grupos e subgrupos.

Para editar o conteúdo do seu inventário padrão, abra o arquivo /etc/ansible/hosts usando seu editor de texto preferido: 

```bash
sudo nano /etc/ansible/hosts
```

![Screenshot hosts](https://user-images.githubusercontent.com/87887130/201476117-3282fcbd-5014-4957-9236-f1a83d7da56b.png)

Como você pode observar, no meu arquivo de exemplo tenho 5 grupos de servidores onde posso selecionar no meu arquivo de roles a que grupo quero que aquela “ação” seja executada. Posso definir meus servidores com os seus endereços IP ou DNS. 

O subgrupo **all:vars** define o parâmetro de host ansible_python_interpreter que será válido para todos os hosts incluídos neste inventário. Este parâmetro garante que o servidor remoto utilize o executável do Python 3 /usr/bin/python3 ao invés do /usr/bin/python (Python 2.7), que não está presente em versões recentes do Ubuntu.

---
Você pode conferir como ficou a sua própria infraestrutura de servidor definida no seu arquivo de inventário com o seguinte comando: 

```bash
ansible-inventory --list -y
```

___

Após configurar o arquivo de inventário para incluir seus servidores, é hora de verificar se o Ansible é capaz de se conectar a esses servidores e executar comandos através do SSH.

Este comando usará o módulo ping interno do Ansible para executar um teste de conexão em todos os nós do seu inventário padrão, conectando como root. 

O módulo ping irá testar:

- Se os hosts estão acessiveis?
- Se as credenciais ssh estão validas?
- Se os hosts conseguem executar módulos do Ansible usando Python.

O Ansible vem com um utilitário chamado ansible-doc. Nele é possível consultar todos os módulos disponíveis numa instalação padrão do Ansible:

```bash
ansible-doc -l
```
Com o nome do módulo escolhido, é possível ver a documentação do módulo através do comando:

```bash
ansible-doc <nomedomodulo>
```

### Comando ad hoc

Com o Ad-hoc você consegue executar comandos direto na linha de comando, sem a necessidade de um playbook.
O uso mais básico dos comandos Ansible-Adhoc é executar ping em um host ou grupo de hosts.

```bash
ansible -m ping all
```

Saiba mais em:
https://docs.ansible.com/ansible/latest/user_guide/intro_adhoc.html

### Ansible playbook

Os comandos Ad-Hoc executam apenas um módulo por vez. Mas e se a gente quiser criar uma sequência de tarefas com os módulos disponíveis? Aí que entram as playbooks.

Utilizando um arquivo no formato YAML (veja sintaxe YAML), todas as tarefas podem ser definidas em sequência e chamadas através de um único comando:


```bash
ansible-playbook -i <nome_inventario> <nome_playbook>
```
Um playbook basicamente é composto por “hosts” e “tasks”. Um “host” é análogo a uma jogada ensaiada de basquete. Define-se quais jogadores participarão (Hosts alvo) e quais passos (tasks) serão executados. 

Num contexto mais prático, uma “task” nada mais é do que uma chamada aos módulos do Ansible.

Veja abaixo o exemplo básico de um script playbook:

![Exemplo de playbook](https://user-images.githubusercontent.com/87887130/201477047-1e36fffa-35b3-425e-9867-e2ebc007ba68.png)

Essa é a saída esperada: 

![Saída frist playbook](https://user-images.githubusercontent.com/87887130/201477157-f18345d6-d56d-4ef2-a7be-f0857e8caf75.png)

Nesse caso em específico, eu iniciei o script playbook com o comando: 

```bash
ansible-playbook <nome do playbook> -K 
```

Existem vários argumentos que podem ser passados na inicialização do playbook, você pode conferir com o seguinte comando: 

```bash
ansible-playbook -h 
```

![argumentos playbook](https://user-images.githubusercontent.com/87887130/201477287-c7f5af52-f201-4e7e-ab16-d52aeb04e234.png)

___
Este é o fim do nosso guia de primeiros passos com o Ansible, você pode continuar seus estudos consultando a extensa documentação do ansible, através deste [link](https://www.ansible.com/resources/get-started)