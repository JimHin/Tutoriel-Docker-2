# Redaction-du-DOCKERFILE
Seconde étape de maîtrise de Docker
docker ps -a       (pour visualiser les conteneurs crées avec leur ID , noms etc...)
docker start ID du conteneur    (les 3 premiers caractères de l'ID suffisent d'ailleurs)
docker stop ID du conteneur    (pareil les 3 premiers caractères de l'ID suffisent)
Par la suite il faut apprendre à build une image avec un DOCKERFILE
Je posterai un tuto sous peu le temps que vous testiez cela
le build d'une image docker vous permet de la mettre sous forme de repositorie sur Dockerhub
donc voici la manip
Vous créez dans le répertoire de votre projet un fichier Dockerfile ou DOCKERFILE (au minimum le D majuscule et pas d'extension)
écrivez ceci:

FROM mattrayner/lamp:latest-1804

//ici viendra vos déclarations

CMD ["/run.sh"]

- FROM signifie qu'on appelle l'image lamp sur le dockerhub de mattrayner
- CMD lance le serveur déclaré
- entre ces deux bornes vous allez utiliser la commande COPY

COPY .  /var/www/html

-le . signifie:  copie tout ce qui se trouve au niveau du fichier Dockerfile
                                                              Sous entendu "votre projet"
-puis vous indiquez le chemin de la racine du serveur apache du conteneur
-ensuite vous sauvegardez votre fichier Dockerfile
-et dans le terminal vous vous rendez là où se trouve votre fichier Dockerfile
  Dans votre répertoire de projet si vous avez bien suivi
- puis vous tapez :     docker build .
- N'oubliez pas le .
