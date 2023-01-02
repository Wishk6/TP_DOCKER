# TP 2 Docker
## Alexandre ORTUNO / SAURIN Guillaume 
#
2.a
```text
FROM node:latest

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD [ "node", "app.js" ]
```

```text
    L'option de npm qui permet d'installer uniquement ce qui est nécessaire est --production. Elle permet d'exclure les paquets qui ne sont pas utilisés en production, comme les outils de développement et les dépendances de test.

    Utiliser l'option --production permet de respecter la bonne pratique Docker de créer des images légères et de ne pas inclure dans l'image des éléments inutiles. Cela peut réduire la taille de l'image et améliorer les performances de l'application.
```
