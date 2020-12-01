# VUE JS

## Configuración TypeScript

![VUE%20JS%209e0a199cec8a44cc90060c994f9cd51d/Untitled.png](VUE%20JS%209e0a199cec8a44cc90060c994f9cd51d/Untitled.png)

## Auxiliares

[https://youtu.be/CQAQkHuulTU](https://youtu.be/CQAQkHuulTU)

[kaorun343/vue-property-decorator](https://github.com/kaorun343/vue-property-decorator)

[Class Component | Vue Class Component](https://class-component.vuejs.org/guide/class-component.html)

## API REST FREE

[Jsonfy, Fake Online REST API for Testing and Prototyping](https://jsonfy.com/)

[JSONPlaceholder](https://jsonplaceholder.typicode.com/)

## Instalación.

```
npm install -g @vue/cli
# OR
yarn global add @vue/cli
```

## Creación de un proyecto.

```jsx
vue create project-name
```

## Instalación de bootstrap

```jsx
# With npm
npm install vue bootstrap-vue bootstrap

# With yarn
yarn add vue bootstrap-vue bootstrap
```

## Importaciones que se deben hacer en el archivo main.ts

```
import Vue from 'vue'
import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'

// Install BootstrapVue
Vue.use(BootstrapVue)
// Optionally install the BootstrapVue icon components plugin
Vue.use(IconsPlugin)

import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

import 'node_modules/bootstrap/scss/bootstrap.scss';
import 'node_modules/bootstrap-vue/src/index.scss';

```