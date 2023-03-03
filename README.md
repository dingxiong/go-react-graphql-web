# React App with golang and graphql backend
This tutorial aims to list the steps of creating a React website with golang and Graphql backend.

## Step 1: Repo initialization

```bash
mkdir go-react-graphql-web
export REPO_PATH=$(cd go-react-graphql-web && pwd)
git init
touch .gitignore
git add -A && git commit -m "init setup"
gh repo create
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

## Step 2: create the skeleton of a React app

```bash
# initialize yarn
yarn init -2

# add dependencies
yarn add esbuild react react-dom styled-components
yarn add --dev typescript @types/react @types/react-dom @types/styled-components @types/node serve-handler @types/serve-handler
```
