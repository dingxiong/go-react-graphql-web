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

## Step 2: Install frontend dependencies

```bash
# initialize yarn
yarn init -2

# add dependencies
yarn add esbuild react react-dom styled-components
yarn add -D typescript @types/react @types/react-dom @types/styled-components
```

Also create `tsconfig.json` file.
```
{
  "compilerOptions": {
    "target": "ES2020",
    "jsx": "react",
    "module": "es2020",
    "rootDir": "./",
    "moduleResolution": "node",
    "baseUrl": "./",
    "sourceMap": true,
    "allowJs": true,
    "checkJs": true,
    "declaration": true,
    "declarationMap": true,
    "outDir": "./dist/",
    "allowSyntheticDefaultImports": true,
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true,
    "strict": true,
    "skipLibCheck": true
  },
  "exclude": ["frontend/generated-types/index.ts"],
  "include": ["frontend/**/*", "**/*.ts", "**/*.tsx"]
}
```
We can come back to `tsconfig.json` later.

Add esbuild config
```
```
Install eslint and its config.
```

```

Install prettier and its config.
```
```

Add script section inside `package.json`
```
  "scripts": {
    "eslint": "eslint .",
    "eslint-fix": "eslint --fix .",
    "format": "prettier --write '.'",
    "ts-check": "yarn run clean-static && tsc",
    "clean-static": "rimraf ./static && mkdir static",
    "prebuild": "yarn run clean-static",
    "build": "yarn prebuild && NODE_ENV=production webpack --config ./webpack.config.js --mode production",
    "build-dev": "NODE_ENV=development webpack --config ./webpack.config.js --mode development",
    "codegen": "graphql-codegen --config codegen.yml"
  },
```

## Step 3: create the skeleton of a React app
```bash
mkdir $REPO_PATH/frontend
cd $REPO_PATH/frontend
touch app.tsx
```
Put below content inside `app.tsx`. We definitely will add more content to it
later.
```
import React from 'react';

import ReactDOM from 'react-dom/client';
import { BrowserRouter, Route, Routes } from 'react-router-dom';

const Home = () => {
  return (
    <div>
      <H3> Hello world </H3>
    </div>
  );

const App = () => {
  return (
    <div>
      <Routes>
        <Route path="/" element={<Home />} />
      </Routes>
    </div>
  );
};

const root = ReactDOM.createRoot(
  document.getElementById('main-app') as HTMLElement
);

root.render(
    <BrowserRouter>
      <App />
    </BrowserRouter>
);
```
