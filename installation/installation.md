# Guide d'installation GitLab CI/CD

Ce guide vous aide à configurer GitLab CI/CD pour automatiser vos pipelines de build, de test et de déploiement.

## Étape 1 : Créer un Projet GitLab
1. Connectez-vous à GitLab.
2. Créez un nouveau projet ou utilisez un projet existant.
3. Assurez-vous d'avoir un fichier `.gitlab-ci.yml` à la racine de votre projet.

## Étape 2 : Installer GitLab Runner
GitLab Runner est l'outil qui exécute vos jobs de pipeline. Suivez les étapes suivantes pour l'installer sur votre machine.

### Installation sur Linux
```bash
# Télécharger et ajouter le repo officiel GitLab
curl -L --output /usr/local/bin/gitlab-runner https://gitlab-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-runner-linux-amd64
chmod +x /usr/local/bin/gitlab-runner

# Enregistrer le Runner
sudo gitlab-runner register
