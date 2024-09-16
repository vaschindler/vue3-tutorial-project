# vue3-example-project


Vue 3 tutorial project with differences in Composition API, Options API and Class API.

## Vue 3 Overview

Vue 3 consists of Single file components. An SFC is a reusable self-contained block of code that encapsulates HTML, CSS and JavaScript that belong together, written inside a .vue file.
The core feature of Vue 3 is declarative rendering. Vue 3 uses a template syntax that allows you to declaratively render data to the DOM. This means that you can write your templates in a way that describes the structure of the DOM and Vue will take care of updating the DOM when the data changes.:
When the state changes the html will be updated automatically.
State can trigger updates in the DOM, when changes are considered reactive.

- mustache syntax: {{}} only for text interpolation
- v-bind: for attribute binding


## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
npm run test:unit
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
