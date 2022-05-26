

<div align="center">
 <h1> Monorepo and Micro-Front Boilerplate 👋  </h1>
 <img  src="/documentation/frontend/example-monorepo.jpg" width="50%">
</div>
<br>

<div align="center">
 <h1> 🏗️ ARCHITECTURE </h1>
 <img src="/documentation/frontend/example-architecture.png" width="50%">
</div>

- [🤷🏼‍♂️ PREREQUISITE TO RUN MONOREPO](#️-prerequisite-to-run-monorepo)
	- [📜 RUN MONOREPO - LERNA](#-run-monorepo---lerna)
	- [🐳 RUN MONOREPO - DOCKER](#-run-monorepo---docker)
	- [🧹 OTHER HELPFULL COMMANDS](#-other-helpfull-commands)
	- [📦 REGISTRIES INFORMATION - MONOREPO LOGIN (OPTIONAL)](#-registries-information---monorepo-login-optional)
	- [📜 DOCUMENTATION KUBERNETES](#-documentation-kubernetes)
	- [🌸 SERVICE/SYSTEM/REGISTRIES DOCUMENTATION](#-servicesystemregistries-documentation)
	- [👤 AUTHOR](#-author)
	- [📝 LICENSE](#-license)
	- [🛳 PORTS](#-ports)

### 🤷🏼‍♂️ PREREQUISITE DEPENDENCIES

- yarn
- lerna
- docker
- react

### 🚀 SERVICES REQUIRED INFORMATION

micro-front ends can work as standalone and is only dependent of the ***xotomicro-front-hook-system*** and the ***xotomicro-front-shell-system*** service

- xotomicro-front-hook-system
  - the system that ***encapsulates components and renders them on a specific section app/page.

- xotomicro-front-shell-system
  - the system that hosts all data passed by the ***global event distributor*** and shells all services independently

### 🎭 MONOREPO MODE CLONE

```sh

# git submodules
git clone --recurse-submodules https://github.com/xotomicro/xotomicro-front.git > /dev/null # to import all micro services into the monorepo

```

## 🤷🏼‍♂️ PREREQUISITE TO RUN MONOREPO

```shell

# register packages - yarn (ask owner for token)
export GITHUB_TOKEN=${ASK_GITHUB_TOKEN} # first set accessibility rules for your team and add your github token like so 
npm set "//npm.pkg.github.com/:_authToken=${GITHUB_TOKEN}" # you will need to tell npm to authenticate yourself to install registries

```

### 📜 RUN MONOREPO - LERNA

```sh

yarn boot # bootstraps packages and cleans all node_modules with lerna
yarn start # to run [all] services
yarn start:{service} # run single front service example with lerna -> (or yarn start:{service})

```

### 🐳 RUN MONOREPO - DOCKER

```sh

docker-compose --env-file=.env up --build -d

```

### 🧹 OTHER HELPFULL COMMANDS

```sh

yarn lint:eslint # lint checks and fixes for all files
yarn lint:stylelint # lint for styles for all files
yarn format:prettify # fixes format issues across all micro-front ends and keeps your team in sync with formatting issues
yarn test:all # tell learna to run all tests

```

### 📦 REGISTRIES INFORMATION - MONOREPO LOGIN (OPTIONAL)

- [REGISTRIES](./documentation/registries.md)

### 📜 DOCUMENTATION KUBERNETES

- [KUBERNETES](./kubernetes/README.md) : main readme for front kubernetes (local kubectl & minikube)

### 🌸 SERVICE/SYSTEM/REGISTRIES DOCUMENTATION

1. SERVICE APPS

- [SERVICE-APP SERVICEAUTH](./packages/service/xotomicro-front-auth-service/README.md) documentation/frontend - xotomicro-front-auth-service service
- [SERVICE-APP SERVICEEVENT](./packages/service/xotomicro-front-event-service/README.md) documentation/frontend - xotomicro-front-event-service service
- [SERVICE-APP SERVICEORDER](./packages/service/xotomicro-front-order-service/README.md) documentation/frontend - xotomicro-front-order-service service
- [SERVICE-APP SERVICEPRODUCT](./packages/service/xotomicro-front-product-service/README.md) documentation/frontend - xotomicro-front-product-service service
- [SERVICE-APP SERVICEUSER](./packages/service/xotomicro-front-user-service/README.md) documentation/frontend - xotomicro-front-user-service service

2. SYSTEM APPS

- [SYSTEM-APP xotomicro-front-hook-system](./packages/system/xotomicro-front-hook-system/README.md) documentation/frontend - xotomicro-front-hook-system system
- [SYSTEM-APP xotomicro-front-shell-system](./packages/system/xotomicro-front-shell-system/README.md) documentation/frontend - xotomicro-front-shell-system system

3. REGISTRIES

- [REGISTRIES xotomicro-front-design-registry](./registries/xotomicro-front-design-registry/README.md) documentation/frontend - xotomicro-front-design-registry registry
- [REGISTRIES xotomicro-front-common-registry](./registries/xotomicro-front-common-registry/README.md) documentation/frontend - xotomicro-front-common-registry registry
- [REGISTRIES xotomicro-front-utility-registry](./registries/xotomicro-front-utility-registry/README.md) documentation/frontend - xotomicro-front-utility-registry registry

### 👤 AUTHOR

 **xotosphere organization**

- Github: [@xotosphere](https://github.com/xotosphere)

### 📝 LICENSE

Copyright © 2021 [XOTOSPHERE](https://github.com/xotosphere).<br/>
This project is [ISC](https://raw.githubusercontent.com/xotomicro/xotomicro-front/development/LICENSE) licensed.

### 🛳 PORTS

| ROOTSHELL | SERVICEEVENT | SERVICEORDER | SERVICEPRODUCT | SERVICEUSER | SERVICEAUTH | xotomicro-front-hook-system |
|-----------|--------------|--------------|----------------|-------------|-------------|-----------------------------|
| 7070      | 7071         | 7072         | 7073           | 7074        | 7075        | 7076                        |
