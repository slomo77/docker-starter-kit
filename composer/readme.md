# Use ```composer install``` without having composer installed on local machine
## Build image (replace example/tag with e.g. username/composer)
```
docker build -t example/tag .
```

## Run following command in folder with composer.json:
```
docker run --rm -i --tty -v $(pwd):/app example/tag composer install
```

## You can also use this container to execute php commands, e.g.:
```
docker run --rm -i --tty -v $(pwd):/app example/tag php artisan key:generate
```