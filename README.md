# LOGS-Apache
Quête sur les logs

## Installation et configuration du service Apache2  

Je suis parti d'une machine virtuelle Ubuntu 24.04 sur virtual box. J'ai configuré le réseau en accès par pont.
Sur la VM, je commence par faire une petit

    sudo apt-get update && sudo apt-get upgrade -y  
    
Ensuite j'installe le servive apache 2 :  

    sudo apt-get install apache2 -y  

Je regarde l'ip de mon serveur apache :

    ip a  

Je constate relève l'IP et je me connecte dessus depuis ma machine hôte :  

<P><IMG SRC="https://github.com/julien-Nmd/LOGS-Apache/blob/main/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-02%2010-25-19.png" ALIGN=CENTER Width=600></P>

