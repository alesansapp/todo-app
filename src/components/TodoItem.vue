<template>
  <div class="todo-item" v-bind:class="{ 'is-complete': todo.completed }">
    <div class="content">
      <p class="text">
        <input type="checkbox" v-on:change="markComplete" class="checkbox" />
        {{ todo.title }}
      </p>
      <div>
        <button @click="$emit('del-todo', todo.id)" class="deleted">X</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['todo'],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 5rem 1rem;
  border-bottom: 1px #ccc dotted;
  -webkit-box-shadow: 0px 10px 22px -10px rgba(0, 0, 0, 0.48);
  -moz-box-shadow: 0px 10px 22px -10px rgba(0, 0, 0, 0.48);
  box-shadow: 0px 10px 22px -10px rgba(0, 0, 0, 0.48);
}

.content {
  display: grid;
  justify-items: center;
}

.is-complete {
  text-decoration: line-through;
}
.deleted {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 0.5rem 2rem;
  border-radius: 4px;
  cursor: pointer;
  transition: 0.2s;
}

.deleted:hover {
  opacity: 0.8;
}

.text {
  text-align: center;
  margin-bottom: 2rem;
}

.checkbox {
  background-color: MediumSeaGreen;
  border-color: MediumSeaGreen;
  color: #fff;
}
</style>
