# FBCS architecture

**for building service oriented scalable next/react application**
Feature Based Component and Service architecture

\*This architecture is still in evolution to support implementations of full backend apis. Currently it is focused on building and consuming gateways alone.

# folder structure goals

This folder structure is developed based on separation of responsibilities
Each folder shares a single responsibility.

## 1. page

> routing and default starting point

It is a next js defined directory to handle routes and apis. A page is actually constructed with the features from the respective feature directory.
the folder will contain the following directories

1. `api` - The gate way APIs will be defined here
2. `feature-x`

## 2. features

> individual independent features

One feature may be constructed with the components. Features are more likely to invoke any services associated with that feature

1. `core` - The shared features across pages.
2. `feature-x` - The page specific features.

## 3. components

> The smallest reusable and immutable pieces of the application

## 4. services

> The services consists api consumers and respective state handlers hooks

1. `api`
2. `hooks`

## 5. utils

> essential javascript functions and redux store

This folder holds all

## 6. config

> any configuration files

## 7. theme and styles

> theming related configurations and styles

`styles ` is a next defined directory

## `core`

Core is the most reused independent items in eact sections

> The core folder in most of the section is actually targeted to be moved to the libs when mono-repo is requested
