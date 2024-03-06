# docker_book_back
utiliser la commande "docker build -t book_back_docker ." pour build l'image
puis pour lancer le container "winpty docker run --name book_back_docker_conteneur -p 8080:8080 -d book_back_docker"

# docker_book_front
utiliser la commande "docker build -t book_front_docker ." pour build l'image
puis pour lancer le container "winpty docker run -p 4200:4200 book_front_docker"
