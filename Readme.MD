* Important Point about MySQL user:

* MySQL containers start as root only to initialize the database, but the actual MySQL process (mysqld) runs as the internal mysql user. This is the default, secure behavior of the official image, so you don’t need to force a non-root user yourself.                                                                                              
* ✔ MySQL image is secure by default
* ✔ mysqld does not run as root
* ❌ Do not override USER
* ✔ Focus non-root on Nginx & Node.js
* 👉 MySQL internally runs as mysql user, even though the container starts as root. You are already secure by default.


* Docker best practices should be followed for docker images.

# Installing Roboshop Docker:
* creating docker images

```
for i in mysql backend frontend debug ; do cd $i ; docker build -t $i:v1.1 . ; cd ..; done
```

```
docker build -t mysql:v1.1 .
```

```
docker build -t backend:v1.1 .
```

```
docker build -t frontend:v1.1 .
```

```
docker build -t debug:v1.1 .
```

```
docker images

```

* running docker images
```
docker run -d -p 3306:3306 --name mysql --network expense mysql:v1.1
```

```
docker run -d -p 8080:8080 --name backend --network expense backend:v1.1
```

```
docker run -d -p 80:80 --name frontend --network expense frontend:v1.1
```

```
docker run -d -p 81:81 --name debug --network expense debug:v1.1
```

```
docker ps -a

```



