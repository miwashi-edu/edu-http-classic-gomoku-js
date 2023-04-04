# edu-http-classic-gomoku-js

## Expected time 6:30 minutest

## Info

[serve-favicon](https://expressjs.com/en/resources/middleware/serve-favicon.html)  
[path](https://www.npmjs.com/package/path)  
[express](https://www.npmjs.com/package/express)  
[uuid](https://www.npmjs.com/package/uuid)  
[nodemon](https://www.npmjs.com/package/nodemon)  
[jest](https://www.npmjs.com/package/jest)  
[jest-runner-groups](https://www.npmjs.com/package/@euklios/jest-runner-groups)  
[supertest](https://www.npmjs.com/package/supertest)  
[faker](https://www.npmjs.com/package/@faker-js/faker)

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
npm install uuid
npm install -D nodemon 
curl https://raw.githubusercontent.com/miwashi-edu/edu-http-classic-gomoku-js/main/resources/favicon.ico -o ./public/favicon.ico
```

### Add static frontend

```bash
mkdir public
mkdir public/img
touch ./public/{index.html,index.js,index.css}
curl https://raw.githubusercontent.com/miwashi-edu/edu-http-classic-gomoku-js/main/resources/black.png -o ./public/img/black.png
curl https://raw.githubusercontent.com/miwashi-edu/edu-http-classic-gomoku-js/main/resources/white.png -o ./public/img/white.png
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
npm install -D @faker-js/faker
npm pkg set scripts.test="jest  --group=-component --group=-integration"
npm pkg set scripts.test:watch="jest --watchAll=true --group=-component --group=-integration"
npm pkg set scripts.test:component="jest --group=component"
npm pkg set scripts.test:integration="jest --group=integration"
npm pkg set jest.runner="groups"
```
### Create repository

```bash
git init
curl -L https://gist.github.com/miwashiab/3378fc2e4ab5d2691fa5978822721796/raw/.gitignore -o .gitignore
git add .
git commit -m "Initial Commit"
```
