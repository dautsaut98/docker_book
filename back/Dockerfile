# Utiliser une image de base PostgreSQL
FROM postgres:latest

# Variables d'environnement pour définir l'utilisateur, le mot de passe et le nom de la base de données
ENV POSTGRES_USER postgres
ENV POSTGRES_PASSWORD root
ENV POSTGRES_DB bookDataBase

# Installation des outils nécessaires pour le développement
RUN apt-get update && \
    apt-get install -y \
        git \
        openjdk-17-jdk \
        maven \
        supervisor && \
    rm -rf /var/lib/apt/lists/*

# Désactivation de la vérification des certificats pour Git
RUN git config --global http.sslVerify false

# Clonage du dépôt Git contenant l'application
RUN git clone https://github.com/dautsaut98/back_spring_boot_book.git /usr/src/projets/back_spring_boot_book

# Définition du répertoire de travail
WORKDIR /usr/src/projets/back_spring_boot_book

# Construction de l'application avec Maven
RUN mvn clean install -Dmaven.wagon.http.ssl.insecure=true

# Exposition des ports utilisés par l'application
EXPOSE 8080

# Copier le fichier de configuration supervisord
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

# Commande par défaut pour exécuter l'application
CMD ["supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]