# vue-todo-list

Una aplicación simple de una lista de recordatorios con *Vue.js*

## Instalar vue-cli
Vue CLI ofrece una herramienta que no requiere configuración que te permite empezar a desarrollar apps y componentes sin esfuerzo.


`$ npm install --global vue-cli`

Crear la aplicación

`$ vue init webpack vue-todo-list`

Daremos `no` a las preguntas referentes a:

 - Vue-router
 - eslint
 - Unit test
 - e2e testing

Correr el proyecto

`$ npm run dev`

Ir a [http://localhost:8080/](http://localhost:8080/)

## Agregar estilo

Agregaremos semantic para darle estilo a nuestra aplicacion [semantic](https://semantic-ui.com/) y [SweetAlert](https://sweetalert.js.org/) para manejar los cuadros de alerta.

## Crear componentes

En esta aplicación habra dos componentes principales:

  - Main app -> `src/App.vue`
  - Todo list -> `src/components/TodoList.vue`

`App` sera un contenedor para nuestro componente `TodoList`

Un componente se compone de tres partes:

  - template
  - component class
  - styles sections

**template**: es la parte visual de un componente.

**component class**: aquí se manejan los comportamientos, eventos y almacenamiento de información del template.

**styles section**: para mejorar la apariencia del template.

## Agregar información a los componentes


Nuestros *todos* tendrán 3 componentes:

  - title
  - project
  - done (para indicar si esta completo o no)

Para pasar la información de nuestro componente principal a **TodoList** usaremos la directiva `v-bind`.

Para hacer render de los items en **TodoList** usaremos la directiva `v-for="item in items"`.
