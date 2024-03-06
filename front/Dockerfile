# Utilisation de l'image Node.js officielle avec une version spécifique
FROM node:16.14.0

# Définition du répertoire de travail
WORKDIR /usr/src/projets

# Installation de Git
RUN apt-get update && apt-get install -y git

# Configuration pour désactiver la vérification des certificats pour npm
RUN npm config set strict-ssl false

# Installation d'Angular CLI avec une version spécifique
RUN npm install -g @angular/cli@16.2.0

# Désactivation de la vérification des certificats pour Git
RUN git config --global http.sslVerify false

# Clonage du dépôt Git
RUN git clone https://github.com/dautsaut98/front_angular_book.git .

# Accéder au répertoire du projet
WORKDIR /usr/src/projets/front_angular_book

# Installation des dépendances du projet
RUN npm install

# Demarrer le serveur
CMD ["ng", "serve", "--host", "0.0.0.0"]
