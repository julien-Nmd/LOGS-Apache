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

<P ALIGN=CENTER><IMG SRC="https://github.com/julien-Nmd/LOGS-Apache/blob/main/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-02%2010-25-19.png" Width=600></P>

Je me connecte aussi d'une autre VM afin d'avoir plusieurs IPs dans le fichier journal d'accès su serveur HTTP.  
Je rajoute un sous dossier qui n'existe pas à mon IP de serveur afin d'y enregistrer des erreurs d'accès. Je le fait aussi de ma VM et de ma machine hôte.
Sur mon serveur HTTP je vais vérifier les fichiers log du serveur, ils se situent dans /var/log/apache2/. Le fichier qui va nus intéresser ici est le fichier acces.log.   
Si on regarde son contenu on peut y voir les ip qui se sont connectés le plus souvent :  

<P ALIGN=CENTER><IMG SRC="https://github.com/julien-Nmd/LOGS-Apache/blob/main/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-02%2011-04-09.png" Width=600></P>
Dans notre cas 10.8.2.136 (ma machine hôte) et 10.8.2.137 (ma 2e VM windows server), on peut d'ailleurs aussi retrouver d'autres infos telles que l'OS ou le navigateur utilisé.  

On va afficher aussi son contenu en filtrant :  

- Les requêtes réussies (code 200)
 <P ALIGN=CENTER><IMG SRC="https://github.com/julien-Nmd/LOGS-Apache/blob/main/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-02%2014-02-36.png" Width=600></P>
- Les pages non trouvées (code 404)
<P ALIGN=CENTER><IMG SRC="https://github.com/julien-Nmd/LOGS-Apache/blob/main/Capture%20d%E2%80%99%C3%A9cran%20du%202025-01-02%2014-03-40.png" Width=600></P>
