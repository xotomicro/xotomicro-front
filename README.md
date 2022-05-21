<div align="center">
 <h1> Monorepo and Micro-Front Boilerplate 👋  </h1>
 <img  src="/documentation/frontend/example-monorepo.jpg" width="50%">
</div>
<br>

### 🏗️ ARCHITECTURE

<img src="/documentation/frontend/example-architecture.png" width="800">

### 🤷🏼‍♂️ PREREQUISITE

- yarn
- lerna
- docker
- react

### 🚀 SERVICES REQUIREMENT

micro-front ends can work as standalone and is only dependent of the ***xotomicro-front-hook-system*** and the ***xotomicro-front-shell-system*** service

- xotomicro-front-hook-system
  - the system that encapsulates components and renders them on a specific section app/page.
 
- xotomicro-front-shell-system
  - the system that hosts all data passed by the ***global event distributor*** and shells all services independently

### 🎭 MONOREPO STRUCTURE

```sh
# git submodules
git clone --recurse-submodules https://github.com/xotomicro/xotomicro-front.git > /dev/null # to import all micro services into the monorepo
```

### 🐳 COMMAND

```sh

# starting monorepo - yarn
npm i lerna -g # make sure you first have lerna as a global dependencie
yarn boot # bootstraps packages and cleans all node_modules with lerna

# run single front service example with lerna : 
yarn start:user # if you want to run independent services -> (or yarn start:{service})

# run all front services with lerna : 
export GITHUB_TOKEN={add-token-here} # first set accessibility rules for your team and add your github token like so 
npm set "//npm.pkg.github.com/:_authToken=$GITHUB_TOKEN" # you will need to tell npm to authenticate yourself to install registries
yarn start # if you want to run all services

# run all front services with docker :
export GITHUB_TOKEN={GITHUB_TOKEN} # first set accessibility rules for your team and add your github token like so 
docker-compose --env-file=.env up --build -d
```

```sh
# lints and more
yarn lint:eslint # lint checks and fixes for all files
yarn lint:stylelint # lint for styles for all files
yarn format:prettify # fixes format issues across all micro-front ends and keeps your team in sync with formatting issues
```

```sh
# tests
yarn test:all # tell learna to run all tests
```

### REGISTRIES - MONOREPO

1. lerna.json contains the global registry url

``` json
{
  "command": {
    "publish": {
      "ignoreChanges": ["ignored-file", "*.md"],
      "message": "chore(release): publish",
      "registry": "https://npm.pkg.github.com"
    }
  },
}
```

2. complete checklist for registry - design :

- [DESIGN-REGISTRY](./registries/xotomicro-front-design-registry/documentation/registries.md)

3. complete checklist for registry - utility :

- [UTILITY-REGISTRY](./registries/xotomicro-front-utility-registry/documentation/registries.md)

4. complete checklist for registry - common :

- [COMMON-REGISTRY](./registries/xotomicro-front-common-registry/documentation/registries.md)

-

### 📜 DOCUMENTATION KUBERNETES

- [KUBERNETES](./kubernetes/README.md) : main readme for front kubernetes (local kubectl & minikube)

### 🌸 SERVICE APP DOCUMENTATION

1. SERVICE APPS

- [SERVICE-APP SERVICEAUTH](./packages/service/xotomicro-front-auth-service/README.md) documentation/backend - xotomicro-front-auth-service service
- [SERVICE-APP SERVICEEVENT](./packages/service/xotomicro-front-event-service/README.md) documentation/backend - xotomicro-front-event-service service
- [SERVICE-APP SERVICEORDER](./packages/service/xotomicro-front-order-service/README.md) documentation/backend - xotomicro-front-order-service service
- [SERVICE-APP SERVICEPRODUCT](./packages/service/xotomicro-front-product-service/README.md) documentation/backend - xotomicro-front-product-service service
- [SERVICE-APP SERVICEUSER](./packages/service/xotomicro-front-user-service/README.md) documentation/backend - xotomicro-front-user-service service

2. SYSTEM APPS

- [SYSTEM-APP xotomicro-front-hook-system](./packages/system/xotomicro-front-hook-system/README.md) documentation/backend - xotomicro-front-hook-system service
- [SYSTEM-APP xotomicro-front-shell-system](./packages/system/xotomicro-front-shell-system/README.md) documentation/backend - xotomicro-front-shell-system service

### 👤 AUTHOR

 **xotosphere organization**

- Github: [@xotosphere](https://github.com/xotosphere)

### 📝 LICENSE

Copyright © 2021 [XOTOSPHERE](https://github.com/xotosphere).<br/>
This project is [ISC](https://raw.githubusercontent.com/xotomicro/xotomicro-front/development/LICENSE) licensed.

### 🛳 PORTS

| ROOTSHELL | SERVICEEVENT | SERVICEORDER | SERVICEPRODUCT | SERVICEUSER | SERVICEAUTH | xotomicro-front-hook-system |
| --------- | -------- | -------- | ---------- | ------- | ------- | ---------- |
| 7070      | 7071     | 7072     | 7073       | 7074    | 7075    | 7076       |
