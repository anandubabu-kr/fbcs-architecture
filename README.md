# FBCS architecture

Feature Based Component and Service architecture

_for building service oriented scalable next/react application_

Read from [Documentation](https://fbcs-architecture.netlify.app/) with illustration.

\*_This architecture is still in evolution to support implementations of full backend apis. Currently it is focused on building and consuming gateways alone._

# Prerequisites

1. Knowledge in ReactJS and NextJS.
2. Build application with intense api interactions.
3. Basic understanding of Component Based Architecture and Modular architecture.

# Folder structure goals

This folder structure is developed based on separation of responsibilities.

Since we are using a component library such as antd/material-ui for the ui components, it could act as shared-ui as well as at some degree widgets.
Each folder shares a single **responsibility**. The application will be located in the `src/` directory so that we can separate the testing related directory from the project structure.

Outside of this `src` there can be framework(next-js)/library(react) specific configuration files and test directories.

\*_For a mono repo the approach could be much different._

## 1. `page/`

> routing and default starting point

It is a next js defined directory to handle routes and apis. A page is actually constructed with the features from the respective feature directory. The export could be a combination of ui/layouts from components and features.

- From each route there will be only a **single** file and export.
- The page will import respective features and combine them to form the page.

Page will contain the following directories

### Sub directories

1. `api/` - The gate way APIs will be defined here
2. `page-x/` - This will be the routes

```
└── page/
      ├── api/
      └── page-x/
```

## 2. features/

> individual independent features

One feature may be constructed with the components. Features are more likely to invoke any services associated with that feature. It uses the components and widgets from the components to implement the business logic aof that particular feature.

1. `core` - The shared features across pages.
2. `feature-x` - The page specific features.

```
└── features/
      ├── core/
      |      └── shared-a/
      └── feature-x/
```

_There will be one single export per an feature_

## 3. components/

> The smallest reusable and immutable pieces of the application

A component doesn't specify any business logic inside it. It purely handles only UI related actions such as interactivity and

```
└── components/
      ├── core/
      └── feature-x/
```

## 4. services/

> The services consists api consumers and respective state handlers hooks

1. `api/` - It exports the axios functions that makes the gateway requests and passes response to the `react-query`
2. `hooks/` -

```
└── services/
      ├── core/
      |     ├─── hooks/
      |     └─── api/
      |
      └── feature-x/
            ├─── hooks/
            └─── api/
```

## 5. utils/

> essential javascript functions and redux store

This folder holds all additional functions and implementations other than theme and services. Let's say you are trying to add CRM like prisma to the project it could be placed in the utils folder.

```
└── utils/
      ├── core/
      └── util-x/
```

## 6. config/

> any configuration files

Exports config files, variables and objects to the app.

```
└── config/
      ├── config-a.ts
      ├── config-x/
      └── config-b.ts
```

## 7. theme/ and styles/

> theming related configurations and styles

`styles/` is a next defined directory

# Nomenclatures

## `core`

Core is the most reused independent items in eact sections

> The core folder in most of the section is actually targeted to be moved to the libs when mono-repo is requested

# Quality tips

1.  typescript
2.  prettier
3.  ES Lint
4.  Pre-commit hooks
5.  Pre-commit peer review
