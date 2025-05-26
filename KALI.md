# Instalacao do Kali
Novo > Nome: Kali Linux

Tipo: Linux

Versão: Debian (64-bit)

Selecione processador e memoria

Monte a ISO do Kali no "Armazenamento".

Inicie a VM e escolha "Graphical Install".

Siga os passos (similar ao Debian):

Idioma: Português (Brasil).

Hostname: kali

Domínio: deixe em branco.

Senha do root e usuário padrão.

Particionamento: "Guided - usar disco inteiro".

Instale o GRUB.

Reinicie e faça login.

# Configuracao do Kali:
Clique no menu de aplicativos e procure pelo terminal Xfcee abra-o

Coloque o seguinte comando: 

"sudo apt update && sudo apt install dnsmasq -y"

Edite o arquivo com a seguinte configuracao: 

"sudo nano /etc/dnsmasq.conf"

E adcione as seguintes linhas:

"interface=eth0  

dhcp-range=192.168.1.100,192.168.1.200,255.255.255.0,24h 

dhcp-option=3,192.168.1.1  # Gateway padrão  

server=8.8.8.8             # Servidor DNS externo (Google)"

Reinicie o servico:

"sudo systemctl restart dnsmasq"

Para ver se esta funcionado:

"sudo systemctl status dnsmasq"

Se aparecer "active(running), esta ok


# Instalacao do Ansible:
Instale o Ansible:

"sudo apt update && sudo apt install ansible -y"

Edite o arquivo:

"sudo nano /etc/ansible/hosts"

Adicione os IP's:

"[linux_servers]

192.168.1.10  # Debian

192.168.1.20  # Kali"

Teste a conxao:

"ansible linux_servers -m ping -u seu_usuario --ask-pass"
Crie um playbook simples. Exemplo (update_system.yml)
"- hosts: linux_servers
  tasks:
    - name: Atualizar todos os pacotes
      apt:
        update_cache: yes
        upgrade: dist"
				
Execute:
"ansible-playbook update_system.yml -u seu_usuario --ask-pass"
