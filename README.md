# FBCS architecture

**for building service oriented scalable next/react application**
Feature Based Component and Service architecture

\*This architecture is still in evolution to support implementations of full backend apis. Currently it is focused on building and consuming gateways alone.

# folder structure goals

This folder structure is developed based on separation of responsibilities
Each folder shares a single responsibility. The application will be located in the `src/` directory so that we can separate the testing related directory from the project structure.

## 1. `page/`

> routing and default starting point

It is a next js defined directory to handle routes and apis. A page is actually constructed with the features from the respective feature directory.
the folder will contain the following directories

1. `api` - The gate way APIs will be defined here
2. `feature-x`

## 2. features/

> individual independent features

One feature may be constructed with the components. Features are more likely to invoke any services associated with that feature. It uses the components and widgets from the components to implement the business logic aof that particular feature.

1. `core` - The shared features across pages.
2. `feature-x` - The page specific features.

_There will be one single export per an feature_

## 3. components/

> The smallest reusable and immutable pieces of the application

A component doesn't specify any business logic inside it. It purely handles only UI related actions such as interactivity and

## 4. services/

> The services consists api consumers and respective state handlers hooks

1. `api/` - It exports the axios functions that makes the gateway requests and passes response to the `react-query`
2. `hooks/` -

## 5. utils/

> essential javascript functions and redux store

This folder holds all additional functions and implementations other than theme and services. Let's say you are trying to add CRM like prisma to the project it could be placed in the utils folder.

## 6. config/

> any configuration files

Exports config files, variables and objects to the app.

## 7. theme/ and styles/

> theming related configurations and styles

`styles/` is a next defined directory

## `core`

Core is the most reused independent items in eact sections

> The core folder in most of the section is actually targeted to be moved to the libs when mono-repo is requested
