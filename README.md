# RDIG-LEGACY-DOCKER
# Install


```
git clone https://github.com/bnza/rdig-legacy-docker.git rdig-docker
cd rdig-docker
git clone https://github.com/bnza/rdig.git app
``` 
Copy the rDig database plain dump inside ```db/initdb.d``` folder
Edit the docker-compose ,```.env``` file, build and start the container

```
docker-compose up --build --remove-orphans
```
Install the app inside the ```php``` container using
```
docker exec -it php /bin/bash
$ composer install
```

Edit the ```.env``` file inside the ```app``` folder
```
$ bin/console doctrine:schema:create --em=jobs
```
Install the frontend inside the ```node``` container using
```
docker exec -it node /bin/sh
$ yarn install
$ yarn run encore dev
``



