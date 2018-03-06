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

## Abstraer los *todo*(s) a su propio componente

Para mantener el código mas limpio y fácil de entender moveremos lo que es un todo de `TodoList` a su propio documento `Todo`

## Agregar funcionalidad de editar

Añadiremos una propiedad `isEditing` al componente Todo. Esta se encargara de determinar si el Todo esta en modo editable o no. Tendremos un controlador de eventos en el span del edit que nos ayudara a desencadenar el método `showForm` cuando se le de click. (Cambiando le propiedad `isEditing` a true).

Ademas del `showForm` también tendremos un `hideForm` que cerrara el form cuando demos click al botón cancel.

Como hemos hecho un link entre los valores del form y los valores del todo, editar los valores del form editara inmediatamente los valores del todo. (Permitido por la directiva ***v-model***)


```
        <div class='field'>
          <label>Title</label>
          <input type='text' v-model="todo.title" >
        </div>
        <div class='field'>
          <label>Project</label>
          <input type='text' v-model="todo.project" >
        </div>
```

## Borrar un Todo


Añadiremos un span con el icono de borrar en Todo. Después un método a dicho span que emita un evento `delete-todo` para el padre (TodoList) y pase el Todo (seleccionado) para borrarlo.

El padre necesitara un controlador de eventos para manejar el delete.

## Añadir un Todo

Crearemos un nuevo componente `CreateTodo` (sera el encargado de mostrar un botón + para añadir `Todos`)

Después de crear el nuevo componente lo importaremos en `App.vue`. También añadiremos un método `addTodo` para agregar todos en `App`. CreateTodo sera el encargado de emitir un evento create-todo para accionar `addTodo` en el padre.
