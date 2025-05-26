# Instalacao:
Abra o VirtualBox e clique em "Novo"
Selecione a imagem ISO do Debian
Colouque nome, o tipo, quantidade de memoria e processadores
Apos isso, inicie a maquina clicando nela
Configure-a com idioma e localizacao
Coloque a senha root, particionamento de disco e instale o GRUB
Na configuracao do terminal, retire o Gnome e selecione o Xfce e os ultimos 3

# Configuracao do Debian:
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
