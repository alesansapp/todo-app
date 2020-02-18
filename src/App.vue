<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import AddTodo from './components/AddTodo';
import Todos from './components/Todos';

export default {
  name: 'App',
  components: {
    Header,
    AddTodo,
    Todos,
  },
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    },
  },
};
</script>

<style>
* {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  line-height: 1.5;
}

.Container {
  margin-bottom: 2rem;
}

.btn {
  display: inline-block;
  border: none;
  outline: none;
  width: 100%;
  cursor: pointer;
  border-radius: 4px;
  transition: 0.3s;
  margin-top: 1rem;
  background: royalblue;
  color: white;
  padding: 1rem 2rem;
  font-weight: bold;
  font-family: inherit;
}

.btn:hover {
  opacity: 0.8;
}
</style>
