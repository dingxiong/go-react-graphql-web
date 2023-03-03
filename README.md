# React App with golang and graphql backend
This tutorial aims to list the steps of creating a React website with a golang
+ Graphql backend.


## Steps

### Repo initialization

```bash
mkdir go-react-graphql-web
export REPO_PATH=$(cd go-react-graphql-web && pwd)
git init
touch .gitignore
git add -A && git commit -m "init setup"
```
Add below content to `.gitignore`. We can add more later.
```
# Ignore all
*
# Unignore all with extensions
!*.*
# Unignore all dirs
!*/

### Above combination will ignore all files without extension ###

# Yarn
.pnp.*
.yarn/*
!.yarn/patches
!.yarn/plugins
!.yarn/releases
!.yarn/sdks
!.yarn/versions
node_modules
```

### Create the skeleton of a React app

```bash
yarn init -2
```
