# K3D - AlmaLinux-8.6
Para esse ambiente de teste, foi utilizado o VirtualBox com redirecionamento de portas:
* SSH: 127.0.0.1:2222 -> 10.0.2.15:22

## Configurações básicas após intalação
### Atualização dos pacotes dos sistema
Acessando a máquina via SSH:

    ssh ceberus@127.0.0.1 -p 2222
    
###Adicionao o usuário "cerberus" ao grupo :
Logue como root:

    su - # sdfsdfs

Verificando os grupos pertencentes ao usuário "Cerberus":
    
    groups cerberus
