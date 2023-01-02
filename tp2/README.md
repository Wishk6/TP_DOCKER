# TP 2 Docker
## Alexandre ORTUNO / SAURIN Guillaume 
#
2.a
Le DockerFile 
```text
FROM node:latest

WORKDIR /app

COPY ["package.json","./"]

RUN npm install --production

COPY . .

EXPOSE 3000

CMD [ "node", "index.js" ]
```

```text
    L'option de npm qui permet d'installer uniquement ce qui est nécessaire est --production. Elle permet d'exclure les paquets qui ne sont pas utilisés en production, comme les outils de développement et les dépendances de test.

    Utiliser l'option --production permet de respecter la bonne pratique Docker de créer des images légères et de ne pas inclure dans l'image des éléments inutiles. Cela peut réduire la taille de l'image et améliorer les performances de l'application.
```
3.
````text
On peut donc executer la commande suivante après avoir écrit notre Dockerfile, en étant dans le dossier du projet :
````
````shell
docker build -t ma_super_app .
````
````text
Sending build context to Docker daemon  362.6MB
Step 1/7 : FROM node:latest
latest: Pulling from library/node
32de3c850997: Pull complete 
fa1d4c8d85a4: Pull complete 
.......
Step 2/8 : ENV NODE_ENV=production
 ---> Using cache
 ---> b47523d0a52a
Step 3/8 : WORKDIR /app
 ---> Using cache
 ---> 9dc9014aaf89
Step 4/8 : COPY ["package.json","./"]
 ---> Using cache
 ---> 94f580b5dc30
Step 5/8 : RUN npm install --production
 ---> Running in 981213c94d1c
.......
Removing intermediate container 547bbaceed6e
 ---> 58b896dfff4e
Step 6/8 : COPY . .
 ---> 40c0a29e5bf4
Step 7/8 : EXPOSE 3000
 ---> Running in 49424f3e9cc4
Removing intermediate container 49424f3e9cc4
 ---> 222da3ba45d1
Step 8/8 : CMD [ "node", "index.js" ]
 ---> Running in 9ecdc0439c42
Removing intermediate container 9ecdc0439c42
 ---> 99f3ef943d45
Successfully built 99f3ef943d45
Successfully tagged ma_super_app:latest
````
4.

[docke-compose.yml](docke-compose.yml)
````text
Après avoir réécrit le docker-compose.yml, on peut lancer la commande suivante en spécifiant les variables d'environnement :
````

````shell
docker-compose up -d -e DATABASE_PORT=3306 -e DATABASE_NAME=mydatabase -e DATABASE_USERNAME=myuser -e DATABASE_PASSWORD=mypassword  ....
````

