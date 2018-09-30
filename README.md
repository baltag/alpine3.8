#Build container

docker build -t alpine3.8 .

#Run container

docker run -d --name alpine3.8 -p 8080:80 -v $(pwd)/html:/var/www/html alpine3.8:latest

#Console container

docker exec -it alpine3.8 sh

cd /var/www/html

#Install Laravel 5.7

docker exec -it alpine3.8 /var/init_laravel.sh

#Browser

http://localhost:8080# alpine3.8
