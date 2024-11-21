# Writing the essential Docker commands to a Markdown file

docker_commands_content = """

# Commandes Essentielles Docker pour les DevOps

## 1. Commandes de base

- **`docker --version`**Affiche la version de Docker installée.
- **`docker info`**Donne des informations détaillées sur l'installation de Docker et le système.
- **`docker help`**
  Liste toutes les commandes Docker avec une brève description.

## 2. Gestion des images

- **`docker images`**Liste toutes les images locales.
- **`docker pull <IMAGE>`**Télécharge une image depuis Docker Hub ou un registre privé.
- **`docker build -t <NAME:TAG> <PATH>`**Construit une image à partir d'un fichier Dockerfile.
- **`docker rmi <IMAGE>`**
  Supprime une image locale.

## 3. Gestion des conteneurs

- **`docker ps`**Liste tous les conteneurs en cours d'exécution.
- **`docker ps -a`**Liste tous les conteneurs (actifs et stoppés).
- **`docker run <OPTIONS> <IMAGE>`**Crée et exécute un nouveau conteneur basé sur une image.
- **`docker stop <CONTAINER>`**Arrête un conteneur en cours d'exécution.
- **`docker start <CONTAINER>`**Démarre un conteneur arrêté.
- **`docker restart <CONTAINER>`**Redémarre un conteneur.
- **`docker rm <CONTAINER>`**Supprime un conteneur (arrêté).
- **`docker exec -it <CONTAINER> <COMMAND>`**
  Exécute une commande dans un conteneur en cours d'exécution (par exemple, accès bash).

## 4. Gestion des volumes

- **`docker volume create <VOLUME_NAME>`**Crée un volume Docker.
- **`docker volume ls`**Liste tous les volumes Docker.
- **`docker volume rm <VOLUME_NAME>`**
  Supprime un volume Docker.

## 5. Gestion des réseaux

- **`docker network ls`**Liste tous les réseaux Docker.
- **`docker network create <NETWORK_NAME>`**Crée un nouveau réseau.
- **`docker network rm <NETWORK_NAME>`**Supprime un réseau.
- **`docker network inspect <NETWORK_NAME>`**
  Affiche les détails d'un réseau.

## 6. Gestion des logs et diagnostics

- **`docker logs <CONTAINER>`**Affiche les logs d'un conteneur.
- **`docker stats`**Montre en temps réel les métriques d'utilisation des ressources des conteneurs.
- **`docker inspect <RESOURCE>`**Donne des détails JSON sur un conteneur, une image, un volume ou un réseau.
- **`docker events`**
  Montre les événements en temps réel du démon Docker.

## 7. Gestion des registres

- **`docker login`**Connecte Docker à un registre (Docker Hub ou privé).
- **`docker tag <SOURCE_IMAGE> <TARGET_IMAGE>`**Ajoute un tag à une image.
- **`docker push <IMAGE>`**
  Pousse une image vers un registre.

## 8. Commandes avancées

- **`docker-compose up`**Démarre des conteneurs définis dans un fichier `docker-compose.yml`.
- **`docker-compose down`**Arrête et supprime les conteneurs, réseaux et volumes créés avec `docker-compose`.
- **`docker prune`**
  Supprime tous les objets inutilisés (conteneurs arrêtés, images non référencées, volumes non utilisés).

---

Ces commandes couvrent les bases pour une gestion efficace de Docker. Utilisez `--help` pour explorer les options supplémentaires de chaque commande.
"""

# Save the content to a Markdown file

docker_file_path = "/mnt/data/docker_commands.md"

with open(docker_file_path, "w") as file:
    file.write(docker_commands_content)

docker_file_path
