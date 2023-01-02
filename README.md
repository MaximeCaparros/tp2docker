# tp2docker

## Mise en pratique - Docker Application Express JS

### 1. Récuperer le zip TP-2-Docker.zip sur Moodle

### 2. Compléter le Dokcerfile afin de builder correctement l'application contenu dans src/
 * a. Une option de npm vous permet de n'installer que ce qui est nécessaire. Quelle est cette option ? Quelle bonne pratique Docker permet t-elle de respecter? *

 Pour n'installer que les modules nécessaires à l'application, vous pouvez utiliser l'option  `--production` de npm lors de l'installation des modules.

Voici comment cela pourrait être intégré dans le Dockerfile :
```
FROM node:12-alpine3.9

# Copier les fichiers de l'application dans le conteneur
COPY . .

# Installer les modules nécessaires à l'application
RUN npm install --production

# Lancer l'application
CMD ["node", "src/index.js"]
```
En utilisant cette option, seuls les modules listés dans le fichier package.json dans la section dependencies seront installés, ce qui permet de respecter la bonne pratique Docker consistant à inclure uniquement les éléments nécessaires pour exécuter l'application dans le conteneur. Cela permet de limiter la taille du conteneur et d'améliorer les performances de l'application.
### 3. A l'aide de la commande docker build, créer l'image ma_super_app

Pour créer l'image ma_super_app on fait :
` docker build -f Dockerfile -t ma_super_app . `

Ensuite pour démarrer l'image on fait : `docker run ma_super_app`
### 4. Compléter le fichier docker-compose.yml afin d'éxécuter ma_super_app avec sa base de données
##### /!\ Utiliser correctement les variables d'environement afin de configurer base de données et l'application /!\ 


   