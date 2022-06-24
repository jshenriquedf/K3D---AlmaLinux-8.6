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




## Comando HISTCONTROL:
Difinição: No Linux, o comando history pode ser usado para mostrar a lista de comandos que foram executados recentemente. A variável HISTCONTROL é uma lista separada por dois pontos de valores que controlam como os comandos são salvos na lista de histórico. A variável HISTCONTROL nos permite armazenar o histórico do bash com mais eficiência. Ele pode ser usado para ignorar os comandos duplicados ou comandos com espaço em branco à esquerda ou ambos.
Algumas opções:

    HISTFILE=/dev/null      # Desvia o histórico para o /dev/null.
    HISTSIZE=0              # Armazena zero comandos no histórico.
    HISTFILESIZE=200000     # Tamanho máximo em bytes (B) que o arquivo será permitido atingir.
    unset HISTFILE          # Desabilita a variável de controle do histórico.
    history -c              # Limpa o conteúdo do histórico na sessão corrente:
    CTRL + r                # Pesquisa no histório.

ignoredups: Faz com que as linhas correspondentes à entrada anterior do histórico não sejam incluídas. Não adiciona um comando ao histórico se for igual ao comando anterior imediato. Ele não olha mais para trás na lista de histórico.
ignorespace: Faz com que as linhas que começam com um caractere de espaço em branco não sejam incluídas na lista de histórico. Se não quisermos que um comando seja incluído no histórico, podemos usar caracteres de espaço em branco antes do comando para evitar sua inclusão na lista de histórico.
ignoreboth: é usado quando queremos usar tanto ignorespace quanto ignoreups.

    HISTCONTROL=ignoreboth      # O mesmo que: HISTCONTROL=ignorespace:ignoredups


* Para uma configuração sistemática
Adicione as alterações no final do arquivo /etc/profile ou do arquivo /etc/bashrc.

    export HISTSIZE=1000
    export HISTFILESIZE=200000
    export HISTCONTROL=ignoreboth

* Para configurar por perfil:
Adicione as alterações no final de um dos arquivos ~/.bashrc, ou ~/.profile, ou ~/.bash_profile, localizados no path, /home/<user>/<filename>, no perfil do usuário desejado, usando seu editor de texto preferido.

    HISTCONTROL=ignoreboth
    HISTSIZE=1000
    HISTFILESIZE=2000 
  
    
   
    
