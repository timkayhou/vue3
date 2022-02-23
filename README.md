# [vue3](https://vuejs.org/guide/introduction.html)

Vue3 project.

## Build development environment

Install [Visual Studio Code](https://code.visualstudio.com/Download), [Node.js](https://nodejs.org/zh-cn/download/), [Git](https://git-scm.com/downloads), [[TortoiseGit](https://tortoisegit.org/download/)]

## Create a new repository in [GitHub](https://github.com/new)

### Repository template

No template

### Owner / Repository name

my-id/my-repo-name

### Description

Vue3 project.

### Public · Private

◉ Public

☉ Private

### Initialize this repository with

☑ Add a README file

☑ Add .gitignore

.gitignore template: Node ▾

☑ Choose a license

License: GNU General Public License v3.0 ▾

### Create repository

## Clone repository from GitHub

```PowerShell / Git Bash
# PowerShell / Git Bash
git clone https://github.com/my-id/my-repo-name.git
```

## Create project

### Install [yarn](https://classic.yarnpkg.com/lang/en/docs/)

```PowerShell
# PowerShell
npm install --global yarn
```

### [Scaffolding Vite project](https://vitejs.dev/guide/#scaffolding-your-first-vite-project)

```PowerShell
# PowerShell
yarn create @vitejs/app <project-name> --template vue-ts
```

### Install [extensions for Visual Studio Code](https://marketplace.visualstudio.com/vscode)

Install [Volar](https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.volar), [[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)], [[git-commit-plugin](https://marketplace.visualstudio.com/items?itemName=redjue.git-commit-plugin)]

### Install packages

```PowerShell
# PowerShell
yarn install
```

### Complication project

```PowerShell
# PowerShell
yarn run build
```

#### Vue [SFC](https://vuejs.org/guide/scaling-up/sfc.html)(Single File Component)

> Vue Single-File Components (aka *.vue files, abbreviated as SFC) is a special file format that allows us to encapsulate the template, logic, and styling of a Vue component in a single file.

- PowerShell

```PowerShell
npm i -D vite-plugin-singlefile
```

- vite.config.ts

```TypeScript
import { defineConfig } from "vite"
import vue from "@vitejs/plugin-vue"
import { viteSingleFile } from "vite-plugin-singlefile"

export default defineConfig({
 plugins: [vue(), viteSingleFile()],
 build: {
  target: "esnext",
  assetsInlineLimit: 100000000,
  chunkSizeWarningLimit: 100000000,
  cssCodeSplit: false,
  brotliSize: false,
  rollupOptions: {
   inlineDynamicImports: true,
   output: {
    manualChunks: () => "everything.js",
   },
  },
 },
})
```
