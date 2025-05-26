# Instalacao do pfSense
Baixe a ISO do pfsense

Crie uma nova VM no VirtualBox

Configure colocando duas placas de rede, sendo uma para Wan(tipo Bridge) e outra para Lan(Rede Interna)

acesse-o

Configure a Wan como 0 e a Lan como 1

Atribua as interfaces:

WAN (Internet): vtnet0 (geralmente a primeira)

LAN (Rede Interna): vtnet1 (segunda placa)

Confirme pressionando Enter

Configure o IP da LAN:

Escolha "2" para configurar a LAN.

Digite o IP da LAN (ex: 192.168.1.1)

Máscara: 24 (equivale a 255.255.255.0)

Acesse o painel web:

Conecte outra VM na rede intnet
Acesse no navegador:
"http://192.168.1.1"

Login padrão:

Usuário: admin

Senha: pfsense
