# Instalacao do Windows 2008

Novo > Nome: Windows Server 2008

Tipo: Microsoft Windows

Versão: Windows 2008 (64-bit)

Selecione memoria e processador

Monte a ISO do Windows Server 2008

Inicie a VM e pressione qualquer tecla para bootar pelo DVD

Siga o instalador

Selecione "Full Installation"

Ative a avaliação (ou use uma chave válida)

Aceite os termos

Formate o disco e instale

Defina uma senha de administrador

Reinicie após a instalação

# Como Criar um domínio AD para gerenciar usuários.
Passo 1: No Windows Server 2008

Abra "Server Manager" → "Add Roles".

Selecione "Active Directory Domain Services".

Siga o assistente e promova o servidor a "Domain Controller".

Defina o nome do domínio (ex: meudominio.local).

Passo 2: Adicione o Windows 7 ao Domínio

No Windows 7:

Painel de Controle → Sistema → Alterar Configurações.

Clique em "Domain" e insira o nome do domínio.

Digite as credenciais de um usuário AD válido.
