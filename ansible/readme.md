
# Começando com Ansible

O Ansible é uma ferramenta que garante o estado de todos os seus servidores controlados. Podemos resumi-lo como uma serie de scripts que garantem que os servidores controlados fiquem em determinado estado. 
Na máquina de controle temos o servidor o ansible será executado, e os hosts que são as máquinas que serão controladas. A comunicação entre elas é normalmente feita com ssh e o ansible permite que a partir da máquina de controle, alteremos os estados nos hosts. 


### Estrutura do Ansible
- Inventory – Arquivo de inventário no qual serão declarados quais os hosts que serão gerenciados pelo Ansible.
- Módulos – Controlam as atividades dos hosts remotos, são os responsáveis por executar as tarefas nas máquinas.
- Playbook – Lista as tarefas que serão executadas nos hosts.
- Roles – Arquivo para modularizar o código. 

Algo interessante a se ressaltar é que no arquivo de inventario podemos ter quantas máquinas quisermos configurar, e distribuir em grupos, onde não necessariamente o mesmo arquivo de configuração se aplique para todos os grupos, podemos rodar diferentes arquivos de configuração para diferentes grupos a depender da demanda a ser seguida. 
O gerenciamento de configuração permite rastrear itens em sua infraestrutura e acompanhar o que eles fazem, como devem ser e o que está envolvido na criação. O tipo de informação que isso inclui são os serviços que eles executam, as versões dos aplicativos que estão sendo executados, como eles são configuradas e sua localização na rede.

___

### Sistemas suportados
Você pode usar praticamente qualquer máquina do tipo UNIX com o Python 3.8 ou mais recente instalado. Isso inclui Red Hat, Debian, Ubuntu, macOS, BSDs e Windows em uma distribuição Windows Subsystem for Linux (WSL.

Links: 

RedHat - https://developers.redhat.com/blog/2016/08/15/install-ansible-on-rhel#via_yum

Debian - https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-debian

Ubuntu - https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-ubuntu

Fedora or CentOS - https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-fedora-or-centos

macOs - https://www.ansiblepilot.com/articles/how-to-install-ansible-in-macos-ansible-install/

Windows - https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-windows 

___
No link a seguir estarei demonstrando como fazer a instalação do Ansible usando a distro linux Ubuntu 20.04.4 LTS, usando o subsistema do Windows para o Linux. 

Você pode conferir as instruções para instalação aqui:  [Instalação no Ubuntu wsl](https://github.com/matiassingers/awesome-readme)
