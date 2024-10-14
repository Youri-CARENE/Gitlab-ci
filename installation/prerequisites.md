# Prérequis pour GitLab CI/CD

Avant de configurer GitLab CI/CD, assurez-vous que votre environnement de développement remplit les prérequis suivants :

## Systèmes d'exploitation supportés
- Linux (Ubuntu, CentOS, etc.)
- macOS
- Windows (via WSL pour utiliser Linux)

## Outils requis
- **Git** : Assurez-vous d'avoir Git installé et configuré. Vérifiez avec la commande `git --version`.
- **Docker** : Pour l'exécution de jobs dans des conteneurs, Docker doit être installé. Vérifiez avec `docker --version`.
- **GitLab Runner** : Installez et configurez un GitLab Runner pour exécuter vos jobs. Vous pouvez suivre la documentation officielle : https://docs.gitlab.com/runner/install/
- **Accès à un dépôt GitLab** : Avoir un projet sur GitLab avec un fichier `.gitlab-ci.yml` pour configurer vos pipelines.

## Configuration matérielle recommandée
- **Processeur** : 4 cœurs minimum.
- **RAM** : 8 GB minimum (16 GB recommandé pour des projets complexes).
- **Stockage** : 50 GB
