# Redaction-du-DOCKERFILE
Seconde étape de maîtrise de Docker

le build d'une image docker vous permet de la mettre sous forme de repositorie sur Dockerhub.
Voici la manip:


Vous créez dans le répertoire de votre projet un fichier Dockerfile ou DOCKERFILE 
(au minimum le D majuscule et pas d'extension)
écrivez ceci:

FROM mattrayner/lamp:latest-1804

//ici viendra vos déclarations

CMD ["/run.sh"]

- FROM signifie qu'on appelle l'image lamp sur le dockerhub de mattrayner
- CMD lance le serveur déclaré
- entre ces deux bornes vous allez utiliser la commande COPY

COPY .  /var/www/html

Le . signifie:  copie tout ce qui se trouve au niveau du fichier Dockerfile dans ...
Le reste de la déclaration est le chemin de la racine du serveur apache du conteneur

- ensuite vous sauvegardez votre fichier Dockerfile
- et dans le terminal vous vous rendez là où se trouve votre fichier Dockerfile
  Dans votre répertoire de projet si vous avez bien suivi
- puis vous tapez :     docker build .
- N'oubliez pas le .
