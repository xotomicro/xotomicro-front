<h1 align="center">Microservices Frontend Monorepo 👋</h1>

<div align="center">
 <h3> Monorepo and Micro-Front Boilerplate 👋  </h3>
 <img  src="/documentation/frontend/example-monorepo.jpg" width="70%">
</div>

<br>

<div align="center">
 <h3> 🏗️ ARCHITECTURE </h3>
 <img src="/documentation/frontend/example-architecture.png" width="70%">
</div>

<br>

- [🤷🏼‍♂️ PREREQUISITE DEPENDENCIES](#️-prerequisite-dependencies)
- [🚀 SERVICES REQUIRED INFORMATION](#-services-required-information)
- [🎭 MONOREPO MODE CLONE](#-monorepo-mode-clone)
- [🏗️ SETUP - ENVIRONMENT](#️-setup---environment)
- [📜 RUN MONOREPO - TURBO](#-run-monorepo---turbo)
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
- node v16+
- turbo
- docker
- react
- vue
- angular

### 🚀 SERVICES REQUIRED INFORMATION

micro-front ends can work as standalone and is only dependent of the **_xotomicro-front-hook-system_** and the **_xotomicro-front-shell-system_** service

- xotomicro-front-hook-system

  - the system that \*\*\*encapsulates components and renders them on a specific section app/page.

- xotomicro-front-shell-system
  - the system that hosts all data passed by the **_global event distributor_** and shells all services independently

### 🎭 MONOREPO MODE CLONE

```sh

# git submodules
git clone --recurse-submodules https://github.com/xotomicro/xotomicro-front.git > /dev/null # to import all micro services into the monorepo

```

### 🏗️ SETUP - ENVIRONMENT

```sh
# Ask for a GITHUB_TOKEN from the owner

# register packages - yarn (ask owner for token)
npm set "//npm.pkg.github.com/:_authToken=${GITHUB_TOKEN}" # you will need to tell npm to authenticate yourself to install registries

# set the GITHUB_TOKEN in the .env files variable
GITHUB_TOKEN=${GITHUB_TOKEN}

```

### 📜 RUN MONOREPO - TURBO

```sh

yarn boot # bootstraps packages and cleans all node_modules with lerna
yarn start # to run [all] services
yarn start:{service} # run single front service example with lerna -> (or yarn start:{service})

```

### 🐳 RUN MONOREPO - DOCKER

```sh

docker-compose --env-file=monorepo.env up --build -d --force-recreate

```

### 🧹 OTHER HELPFULL COMMANDS

```sh

yarn lint:eslint # lint checks and fixes for all files
yarn lint:stylelint # lint for styles for all files
yarn lint:prettify # fixes format issues across all micro-front ends and keeps your team in sync with formatting issues
yarn test:all # tell learna to run all tests

```

### 📦 REGISTRIES INFORMATION - MONOREPO LOGIN (OPTIONAL)

- [REGISTRIES](./documentation/registries.md)

### 📜 DOCUMENTATION KUBERNETES

- [KUBERNETES](https://github.com/xotomicro/xotomicro-front/blob/development/kubernetes/README.md) : main readme for front kubernetes (local kubectl & minikube)

### 🌸 SERVICE/SYSTEM/REGISTRIES DOCUMENTATION

1. SERVICE APPS

- [SERVICE-APP SERVICE AUTH](https://github.com/xotomicro/xotomicro-front-auth-service/blob/development/README.md) documentation/frontend - xotomicro-front-auth-service service
- [SERVICE-APP SERVICE EVENT](https://github.com/xotomicro/xotomicro-front-event-service/blob/development/README.md) documentation/frontend - xotomicro-front-event-service service
- [SERVICE-APP SERVICE ORDER](https://github.com/xotomicro/xotomicro-front-order-service/blob/development/README.md) documentation/frontend - xotomicro-front-order-service service
- [SERVICE-APP SERVICE PRODUCT](https://github.com/xotomicro/xotomicro-front-product-service/blob/development/README.md) documentation/frontend - xotomicro-front-product-service service
- [SERVICE-APP SERVICE USER](https://github.com/xotomicro/xotomicro-front-user-service/blob/development/README.md) documentation/frontend - xotomicro-front-user-service service

2. SYSTEM APPS

- [SYSTEM-APP HOOK](https://github.com/xotomicro/xotomicro-front-hook-system/blob/development/README.md) documentation/frontend - xotomicro-front-hook-system system
- [SYSTEM-APP SHELL](https://github.com/xotomicro/xotomicro-front-shell-system/blob/development/README.md) documentation/frontend - xotomicro-front-shell-system system

3. REGISTRIES

- [REGISTRIES DESIGN](https://github.com/xotomicro/xotomicro-front-design-registry/blob/development/README.md) documentation/frontend - xotomicro-front-design-registry registry
- [REGISTRIES COMMON](https://github.com/xotomicro/xotomicro-front-common-registry/blob/development/README.md) documentation/frontend - xotomicro-front-common-registry registry
- [REGISTRIES UTILITY](https://github.com/xotomicro/xotomicro-front-utility-registry/blob/development/README.md) documentation/frontend - xotomicro-front-utility-registry registry

### 👤 AUTHOR

**xotosphere organization**

- Github: [@xotosphere](https://github.com/xotosphere)

### 📝 LICENSE

Copyright © 2021 [XOTOSPHERE](https://github.com/xotosphere).<br/>
This project is [ISC](https://raw.githubusercontent.com/xotomicro/xotomicro-front/development/LICENSE) licensed.

### 🛳 PORTS

| SHELLSYSTEM | SERVICEEVENT | SERVICEORDER | SERVICEPRODUCT | SERVICEUSER | SERVICEAUTH | HOOKSYSTEM |
| ----------- | ------------ | ------------ | -------------- | ----------- | ----------- | ---------- |
| 7070        | 7071         | 7072         | 7073           | 7074        | 7075        | 7076       |
