# K3D - AlmaLinux-8.6
Para esse ambiente de teste, foi utilizado o VirtualBox com redirecionamento de portas:
* SSH: 127.0.0.1:2222 -> 10.0.2.15:22
* Usuário: Cerberus

## Configurações básicas após intalação
### Atualização dos pacotes dos sistema
Acessando a máquina via SSH:

    ssh ceberus@127.0.0.1 -p 2222
    
## Adicionao o usuário "cerberus" ao grupo sudoes:
Logue como root:

    su - 

Verificando os grupos pertencentes ao usuário "Cerberus":
    
    groups cerberus
    # ou
    id -nG cerberus

Teste:

    su - username
    sudo ls -la /root
    
## Configurando o HISTCONTROL
HISTCONTROL=ignorespace:ignoredups
HISTSIZE=1000  
HISTFILESIZE=2000 

HISTCONTROL=ignoredups:erasedups  # no duplicate entries
HISTSIZE=1000                     # custom history size
HISTFILESIZE=100000                 # custom history file size
shopt -s histappend                      # append to history, don't overwrite it


// Para uma configuração sistemática
// Adicione as alterações no final do arquivo /etc/profile ou do arquivo /etc/bashrc.

export HISTSIZE=100000
export HISTFILESIZE=200000
export HISTCONTROL=ignoredups:ignorespace

Para configurar por perfil 
Adicione as alterações no final de um dos arquivos ~/.bashrc, ou ~/.profile, ou ~/.bash_profile, localizados no path, /home/<user>/<filename>, no perfil do usuário desejado, usando seu editor de texto preferido.
    
HISTCONTROL=ignoredups:erasedup
HISTSIZE=1000
HISTFILESIZE=2000 
    
    
    
   
    
