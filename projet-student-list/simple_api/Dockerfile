#Image de base
FROM python:2.7-stretch

#Meta données sur le mainteneur de l'image
LABEL maintainer="ttoure05@gmail.com"

#Installation des prérequis en 2 layer
RUN	apt-get update -y && apt-get install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y
RUN	pip install flask==1.1.2 flask_httpauth==4.1.0 flask_simpleldap python-dotenv==0.14.0

#Copier le fichier de l'application sur la racine / du conteneur
COPY student_age.py /

#creation du dossier data sur la racine / du conteneur
VOLUME /data/

#Indique le port d'exposition de l'application du conteneur
EXPOSE 5000

#Commande lancer au demarrage du conteneur pour le demarrage de l'appli
CMD [ "python", "./student_age.py" ]
