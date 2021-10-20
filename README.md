## MERN Stack

* MongoDB - document database
* Express(.js) - Node.js web framework
* React(.js) - a client-side JavaScript framework
* Node(.js) - the premier JavaScript web server

## Install Node

Using nvm

## Create Project

* npm init
* accept all defaults

## Install Express

```sh
npm install express --save
```

### Express Gen

https://expressjs.com/en/starter/generator.html

### Root '/'

Free up routing for '/' in app.js
```diff
- app.use('/', indexRouter);
+ app.use('/home', indexRouter);
```
## Setup React


### Create React app

```sh
npx create-react-app reactapp --template redux
```

### Do cleanup

[Follow Steps](https://makeall.dev/notepad/reactjs-spring-boot-scaffold/)

### Install MUI

* [Instructions](https://mui.com/getting-started/installation/)
* Setup theme

### Routing 

```sh
npm install react-router-dom --save
```

### Setup Build

package.json

```json
  "scripts": {
    "build": "react-scripts build && rm -rf ../expressapp/public/ && mv build ../expressapp/public/",
  },
```

## MongoDB

### wsl2 Install

https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database

https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/

```sh
wget -qO - https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add -
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list
sudo apt-get update
sudo apt-get install -y mongodb-org
mongod --version
sudo service mongod start
mongo --eval 'db.runCommand({ connectionStatus: 1 })'
```

init Script Setup

```sh
curl https://raw.githubusercontent.com/mongodb/mongo/master/debian/init.d | sudo tee /etc/init.d/mongodb >/dev/null
sudo chmod +x /etc/init.d/mongodb
sudo service mongodb status/start/stop
```

### VS Code Connect

https://code.visualstudio.com/docs/azure/mongodb

Connection locahost instance
```sh
localhost
27017
noauth
```

## Test Run

```sh
cd reactapp
npm run build
```


```sh
cd expresapp
npm start
```

## Dockerize