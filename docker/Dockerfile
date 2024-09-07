# Utiliser une image Node.js officielle comme image de base
FROM node:16-alpine

# Définir le répertoire de travail à l'intérieur du conteneur
WORKDIR /app

# Copier package.json et package-lock.json pour installer les dépendances
COPY package*.json ./

# Installer les dépendances
RUN npm install --production

# Copier le reste des fichiers de l'application dans le conteneur
COPY . .

# Exposer le port 3000 pour accéder à l'application
EXPOSE 3000

# Définir la commande par défaut pour démarrer l'application
CMD ["npm", "start"]
