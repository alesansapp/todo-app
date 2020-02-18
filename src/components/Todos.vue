<template>
  <div class="Container">
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  name: 'Todos',
  components: {
    TodoItem,
  },
  props: ['todos'],
};
</script>

<style scoped>
.Container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  align-items: center;
  grid-gap: 2rem;
  margin-left: 2%;
  margin-right: 2%;
}

@media (max-width: 1000px) {
  .Container {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 600px) {
  .Container {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 450px) {
  .Container {
    grid-template-columns: repeat(1, 1fr);
  }
}
</style>
