# Use ```npm install``` and similar without having node.js installed on local machine

## Build image (replace example/tag with e.g. username/nodejs)
```docker build -t example/tag .```

## Run following command in folder with package.json:
```docker run --rm -i --tty -v $(pwd):/app example/tag npm i```