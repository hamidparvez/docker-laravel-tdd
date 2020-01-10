# Resturant API Demo

#### Downloading and configuring the project
 - Git Clone
 - sudo docker-compose build
 - sudo docker-compose up
 - sudo nano /etc/hosts (Add 127.0.0.1 test.local)

#### Installing the dependencies
- sudo docker exec resturant-demo /bin/bash -c "cd /public_html/demo && composer install"

#### Setting Up Database and Inserting CSV values
- sudo docker exec resturant-demo /bin/bash -c "cd /public_html/demo && php artisan migrate"
- sudo docker exec resturant-demo /bin/bash -c "cd /public_html/demo && php artisan db:seed" 

 #### Running The Application
 - API Endpoint (test.local:8080/api/resturants)
 - You can modify the endpoint from docker/vhost.conf
 - You can configure the nginx & mysql port as well from docker-compose.yaml

## Sorting and Searching

- test.local:8080/api/resturants?search='resturant-name'&sort='best-match'
- You need to add dash (-) in the sorting value like best match will be best-match.
- test.local:8080/api/resturants will be sorted on opening state 

## Running Test Cases

 - sudo docker exec resturant-demo /bin/bash -c "cd /public_html/demo && ./vendor/bin/phpunit"

## Note

 - I have not added .env in the .gitignore
 - Not added any auth middleware. So all the endpoints are public now.

### TODO:

 - API Authtentication/Authorization
 - Adding .env in .gitignore
 - API Versioning

