# edu-http-classic-gomoku-js

## Förväntad tid 6:30 minuter, inklusive skriva server.js utantill.

## Info

[serve-favicon](https://expressjs.com/en/resources/middleware/serve-favicon.html)  
[nodemon](https://www.npmjs.com/package/nodemon)
[jest](https://www.npmjs.com/package/jest)
[path](https://www.npmjs.com/package/path)
[express](https://www.npmjs.com/package/express)

## Instructions

### Initialize project

```bash
cd ~
cd ws
rm -rf edu-http-classic-gomoku-js #Om den finns
mkdir edu-http-classic-gomoku-js
cd edu-http-classic-gomoku-js
npm init -y
touch {service.js,server.js}
touch .env
npm pkg set main="service.js"
npm pkg set scripts.dev="nodemon service.js"
npm install express
npm install path
npm install serve-favicon
npm install -D nodemon 
curl https://gomokuonline.com/favicon.ico -o ./public/favicon.ico
```

### Add static frontend

```bash
mkdir public
touch ./public/{index.html,index.js,index.css}
```

### Add backend

```bash
mkdir {routes,controllers,domain}
touch ./routes/gomoku_routes.js
touch ./controllers/gomoku_controller.js
touch ./routes/gomoku_routes.js
touch ./domain/gomoku.js
```

### Add testing

```bash
mkdir __tests__
touch ./__tests__/{unit_tests.js,component_tests.js,integration_tests.js}
touch service.js
touch .env.test
npm install -D jest
npm install -D jest-runner-groups
npm install -D supertest
npm pkg set scripts.test="jest  --group=-component --group=-integration"
npm pkg set scripts.test:component="jest --group=component"
npm pkg set scripts.test:integration="jest --group=integration"
npm pkg set jest.runner="groups"
```
### Create repository

```bash
curl -L https://gist.github.com/miwashiab/3378fc2e4ab5d2691fa5978822721796/raw/.gitignore -o .gitignore
```

### Get code

```bash
curl https://www.jensenyh.se/favicon.ico -o ./public/favicon.ico
curl -L https://gist.github.com/miwashiab/f58042d997beb7983f91152c7b555529/raw/server.js -o server.js
curl -L https://gist.github.com/miwashiab/44bb4bc1d82f0952ffbf6c55fbd63ec8/raw/index.html -o  ./public/index.html
```

