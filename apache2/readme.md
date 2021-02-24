# Simple Apache Server with PHP

## Build image
```
docker-compose build
```

## Run following command (omit the "-d" for verbose log):
```
docker-compose up -d
```

## "ssh" into container:
```
docker exec -it foldername_php_1 bash
```
Now you can run commands like `php -v` from within the container.