# Laravel Dev Environment
Based on Andrew Schmelyun's Youtube Tutorial [Part 1](https://www.youtube.com/watch?v=5N6gTVCG_rw) and [Part 2](https://www.youtube.com/watch?v=I980aPL-NRM)

## Getting started
- Copy Folder "_docker" and file "docker-compose.yml" into your Laravel project folder.

- Run `docker-compose build` in that folder to create the images. This may take a while.
- Run `docker-compose up -d` to start the containers
- Visit [http://localhost:8081] to view your homepage
- Visit [http://localhost:8082] for Adminer (access the MariaDB database).

  Login with following credentials:
    - Server: mariadb
    - User: test
    - Password: test

  You can edit these credentials in docker-compose.yml

## Composer
You can run Composer in your project folder without having Composer installed. It is installed in the Dockerfile of the container "webserver". Just run
```
docker-compose exec webserver composer
```

## npm
You can run npm in your project folder without having npm installed. It is installed in the Dockerfile of the container "webserver". Just run
```
docker-compose exec webserver npm -v
```
For Laravel Mix with Live-Reload edit your `webpack.mix.js`:
```js
mix.js('resources/js/app.js', 'public/js')
  .sass('resources/sass/app.scss', 'public/css')
  .browserSync({
    proxy: 'localhost:80',
    open: false,
  });
```

## Artisan
There is also a container for Laravel's Artisan Commands. Just run
```
docker-compose exec webserver php artisan
```

## Recommended Aliases
If you don't have the above tools installed on your host machine you may want to create shortcuts for these commands (in your ~/.bashrc or ~/.bash_aliases):
```
alias composer='docker-compose exec webserver composer'
alias npm='docker-compose exec webserver npm'
alias artisan='docker-compose exec webserver php artisan'
```
