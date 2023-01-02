FROM node:12-alpine3.9

# Copier les fichiers de l'application dans le conteneur
COPY . .

# Installer les modules nécessaires à l'application
RUN npm install --production

# Lancer l'application
CMD ["node", "src/index.js"]