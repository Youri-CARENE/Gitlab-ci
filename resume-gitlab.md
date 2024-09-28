
# GitLab CI

## Introduction à GitLab CI
- **GitLab CI/CD** est un outil d'intégration et de déploiement continu intégré à GitLab.
- **CI** : Intégration continue pour automatiser le build et les tests.
- **CD** : Déploiement continu pour automatiser le déploiement après les tests.

## Concepts Clés
- **Pipeline** : Ensemble de jobs qui s'exécutent pour effectuer des builds, tests, ou déploiements.
- **Jobs** : Tâches individuelles exécutées dans un pipeline.
- **Stages** : Phases du pipeline (ex. : `build`, `test`, `deploy`).
- **Runners** : Serveurs qui exécutent les jobs (peuvent être partagés ou spécifiques).
- **Artifacts** : Fichiers générés par un job qui peuvent être partagés.
- **Cache** : Stockage de fichiers ou dépendances pour accélérer les pipelines.

## Fichier `.gitlab-ci.yml` Exemple
```yaml
stages:
  - build
  - test
  - deploy

build_job:
  stage: build
  script:
    - echo "Building the project"
    - make build
  artifacts:
    paths:
      - build/

test_job:
  stage: test
  script:
    - echo "Running tests"
    - make test

deploy_job:
  stage: deploy
  script:
    - echo "Deploying to production"
    - make deploy
  only:
    - main