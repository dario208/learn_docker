# Writing the Docker Swarm command list to a Markdown file

content = """

# Commandes Essentielles Docker Swarm pour les DevOps

## 1. Commandes de base pour initier et gérer le Swarm

- **`docker swarm init`**Initialise un cluster Swarm sur le nœud actuel.
- **`docker swarm join --token <TOKEN> <IP:PORT>`**Permet à un nœud de rejoindre un cluster Swarm existant.
- **`docker swarm leave`**Quitte le cluster Swarm (avec `--force` pour forcer un manager à quitter).
- **`docker swarm update`**
  Met à jour la configuration du Swarm (par exemple, les délais ou le quorum).

## 2. Gestion des nœuds (Nodes)

- **`docker node ls`**Affiche la liste des nœuds dans le cluster Swarm.
- **`docker node inspect <NODE_ID>`**Donne des informations détaillées sur un nœud.
- **`docker node update --availability <active|pause|drain> <NODE_ID>`**Change l'état d'un nœud (drain = n'accepte plus de tâches).
- **`docker node rm <NODE_ID>`**
  Supprime un nœud du cluster.

## 3. Gestion des services

- **`docker service create --name <NAME> <IMAGE>`**Crée un nouveau service dans le Swarm.
- **`docker service ls`**Liste tous les services actifs.
- **`docker service inspect <SERVICE_NAME>`**Fournit des détails complets sur un service.
- **`docker service scale <SERVICE_NAME>=<NUMBER>`**Redimensionne un service (modifie le nombre de réplicas).
- **`docker service update <OPTIONS> <SERVICE_NAME>`**Met à jour les paramètres d’un service (ex: image, ressources).
- **`docker service rm <SERVICE_NAME>`**
  Supprime un service.

## 4. Gestion des tâches (Tasks)

- **`docker service ps <SERVICE_NAME>`**Montre les tâches (containers) associées à un service.
- **`docker inspect <TASK_ID>`**
  Donne des informations sur une tâche spécifique.

## 5. Gestion des réseaux

- **`docker network create --driver overlay <NETWORK_NAME>`**Crée un réseau Swarm en mode overlay.
- **`docker network ls`**Liste tous les réseaux disponibles.
- **`docker network inspect <NETWORK_NAME>`**Fournit des détails sur un réseau.
- **`docker network rm <NETWORK_NAME>`**
  Supprime un réseau.

## 6. Stack Management

- **`docker stack deploy -c <COMPOSE_FILE> <STACK_NAME>`**Déploie une stack (pile) basée sur un fichier `docker-compose`.
- **`docker stack ls`**Liste les stacks actives.
- **`docker stack ps <STACK_NAME>`**Montre les tâches pour une stack spécifique.
- **`docker stack rm <STACK_NAME>`**
  Supprime une stack.

## 7. Monitoring et Debugging

- **`docker service logs <SERVICE_NAME>`**Affiche les logs d’un service.
- **`docker service events`**Montre les événements en temps réel du Swarm.
- **`docker node ps <NODE_ID>`**
  Affiche les conteneurs en cours sur un nœud donné.

## 8. Commandes utiles pour les managers

- **`docker node promote <NODE_ID>`**Promeut un nœud en manager.
- **`docker node demote <NODE_ID>`**
  Rétrograde un nœud en worker.

## 9. Sauvegarde et restauration

- **`docker swarm unlock`**Débloque un cluster protégé.
- **`docker swarm unlock-key`**Montre la clé de déblocage.
- **`docker service rollback <SERVICE_NAME>`**
  Revenir à la version précédente d'un service après une mise à jour.

## 10. Commandes avancées

- **`docker service create --constraint <key=value>`**Crée un service avec des contraintes spécifiques, par ex. placement (`node.role == worker`).
- **`docker service create --limit-cpu <VALUE>` et `--limit-memory <VALUE>`**Définit des limites de ressources pour un service.
- **`docker service update --force <SERVICE_NAME>`**
  Force le redémarrage des tâches d’un service.

---

Ces commandes couvrent l’essentiel pour gérer un environnement **Docker Swarm**. Chaque commande peut être approfondie avec `--help` pour plus de détails.
"""

# Save the content to a Markdown file

file_path = "/mnt/data/docker_swarm_commands.md"

with open(file_path, "w") as file:
    file.write(content)

file_path
