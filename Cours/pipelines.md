# Les Pipelines dans GitLab CI/CD

Un pipeline dans GitLab CI/CD est une série de jobs configurés pour s'exécuter dans un ordre défini, permettant d'automatiser les tests, la construction et le déploiement de logiciels. Les pipelines sont définis dans un fichier `.gitlab-ci.yml`.

## Structure d'un Pipeline

Un pipeline est composé de plusieurs **stages** (étapes) qui regroupent des **jobs**. Chaque stage peut contenir un ou plusieurs jobs qui s'exécutent en parallèle. Les stages s'exécutent dans un ordre séquentiel.

### Exemple d'un pipeline simple :
```yaml
stages:
  - build
  - test
  - deploy

build_job:
  stage: build
  script:
    - echo "Building the project"

test_job:
  stage: test
  script:
    - echo "Running tests"

deploy_job:
  stage: deploy
  script:
    - echo "Deploying the application"
