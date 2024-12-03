
# Étapes pour Créer un Pipeline sur GitLab

---

## **Étape 1 : Configurer un dépôt GitLab**
1. **Créer un nouveau dépôt** :
   - Accédez à l’interface GitLab.
   - Cliquez sur **"New Project"** ou **"Create Blank Project"**.
   - Nommez votre projet et configurez les paramètres de visibilité (privé ou public).

2. **Cloner le dépôt sur votre machine locale** :
   ```bash
   git clone <URL_du_dépôt>
   ```

---

## **Étape 2 : Ajouter un fichier `.gitlab-ci.yml`**
1. **Créer un fichier `.gitlab-ci.yml` dans la racine de votre projet** :
   - Ce fichier définit les étapes (jobs) et les scripts à exécuter.

2. **Exemple de structure simple** :
   ```yaml
   stages:
     - build
     - test
     - deploy

   build-job:
     stage: build
     script:
       - echo "Compilation du projet..."
       - make

   test-job:
     stage: test
     script:
       - echo "Exécution des tests..."
       - make test

   deploy-job:
     stage: deploy
     script:
       - echo "Déploiement de l'application..."
       - ./deploy.sh
   ```

3. **Ajouter et pousser le fichier vers GitLab** :
   ```bash
   git add .gitlab-ci.yml
   git commit -m "Ajout du pipeline GitLab CI"
   git push origin main
   ```

---

## **Étape 3 : Vérifier le pipeline dans GitLab**
1. Accédez à votre projet dans GitLab.
2. Allez dans l'onglet **"CI/CD" > "Pipelines"**.
3. Vérifiez si un pipeline a été déclenché automatiquement après le push.

---

## **Étape 4 : Ajouter des runners GitLab**
Un runner est une machine qui exécute les jobs définis dans votre pipeline.

1. **Installer un runner** (si vous n’en avez pas déjà un) :
   - Suivez [la documentation officielle](https://docs.gitlab.com/runner/) pour installer un runner GitLab.
   - Enregistrez le runner avec la commande :
     ```bash
     gitlab-runner register
     ```
   - Fournissez l'URL du projet et le token disponible dans **"Settings" > "CI/CD" > "Runners"**.

2. Vérifiez que le runner est actif dans **"Settings" > "CI/CD" > "Runners"**.

---

## **Étape 5 : Étendre le pipeline avec des configurations avancées**
1. **Définir des environnements** :
   ```yaml
   deploy-job:
     stage: deploy
     script:
       - echo "Déploiement sur production"
     environment:
       name: production
       url: https://mon-app-production.com
   ```

2. **Configurer des conditions pour les jobs** :
   - Exécuter un job uniquement sur une branche spécifique :
     ```yaml
     deploy-job:
       stage: deploy
       script:
         - echo "Déploiement en production"
       only:
         - main
     ```

3. **Utiliser des artefacts pour partager des fichiers entre les jobs** :
   ```yaml
   build-job:
     stage: build
     script:
       - make
     artifacts:
       paths:
         - dist/
   ```

---

## **Étape 6 : Debug et optimisation**
1. Si un job échoue, accédez à l’onglet **"CI/CD" > "Jobs"** pour voir les logs et comprendre l’erreur.
2. Ajoutez des variables d’environnement dans **"Settings" > "CI/CD" > "Variables"** pour gérer des secrets ou des configurations dynamiques.

---

Avec ces étapes, vous aurez un pipeline GitLab CI/CD fonctionnel, prêt à automatiser vos processus de développement et de déploiement. 🚀
