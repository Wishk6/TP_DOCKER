2
```shell
docker run hello-world
docker run -it ubuntu bash
docker images
docker ps -a
docker run -p 80:80 nginx et docker run -p -d 80:80 nginx
```

5.a
```shell
wishk@wishk-virtual-machine:~$ sudo docker pull nginx
Using default tag: latest
latest: Pulling from library/nginx
025c56f98b67: Pull complete 
ca9c7f45d396: Pull complete 
ed6bd111fc08: Pull complete 
e25b13a5f70d: Pull complete 
9bbabac55ab6: Pull complete 
e5c9ba265ded: Pull complete 
Digest: sha256:ab589a3c466e347b1c0573be23356676df90cd7ce2dbf6ec332a5f0a8b5e59db
Status: Downloaded newer image for nginx:latest
docker.io/library/nginx:latest
```
5.b
```shell
wishk@wishk-virtual-machine:~$ sudo docker image ls
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
nginx         latest    ac8efec875ce   11 hours ago    142MB
hello-world   latest    feb5d9fea6a5   14 hours ago   13.3kB
```
5.c
```shell
wishk@wishk-virtual-machine:~/Documents$ echo > index.html
wishk@wishk-virtual-machine:~/Documents$ ls
index.html
```
Après avoir crée un fichier index.html dans le dossier siteWeb, je lance la commande suivante:
```shell
5.d
```shell
wishk@wishk-virtual-machine:~$ sudo docker run -it --rm -d -p 8080:80 --name testPageNginx -v ~/siteWeb:/usr/share/nginx/html nginx

aa0d351efde863cb469a99293ef444bde5400a4c0581aa71d79d14a21de18795
```
Cette commande nous permet de monter notre repository dans le container nginx.
<br>
Nous avons donc accès à notre fichier index.html depuis le container nginx. 
![img_1.png](img_1.png)

6.a
```shell

```

6.b
```shell

```

6.c
```shell

```