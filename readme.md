# Dockerfile that spins up nginx, php, mysql for Laravel

remove the file in /src/.remove

add ssl certs to nginx/certs

start docker
```
docker-compose up --build
docker-compose run --rm composer create-project laravel/laravel .
```

run : want to run a command and exit
--rm : destroy container after finish
composer : docker service name from .yml

npm install
```docker-compose run --rm npm install```

compile assets
```docker-compose run --rm npm run dev```

update .env file in laravel files
```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_PASSWORD=secret
```

run initial migration
```docker-compose run -rm artisan migrate```

run any artisan commands
```docker-compose run --rm artisan make:model Post --migration```