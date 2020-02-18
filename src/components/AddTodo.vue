<template>
  <div class="Container">
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Create your awesome todo here" />
      <input type="submit" value="ADD NEW" class="btn" />
    </form>
  </div>
</template>

<script>
import uuid from 'uuid';

export default {
  name: 'AddTodo',
  data() {
    return {
      title: '',
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        id: uuid.v4(),
        title: this.title,
        completed: false,
      };
      this.$emit('add-todo', newTodo);
      this.title = '';
    },
  },
};
</script>

<style scoped>
.Container {
  display: grid;
  justify-items: center;
  margin-left: 5%;
  margin-right: 5%;
}

.form {
  display: flex;
}

input[type='text'] {
  flex: 10;
  width: 100%;
  border: 0;
  border-bottom: 2px solid royalblue;
  padding: 0.5rem 0.1rem;
  margin-right: 1px;
  outline: none;
  font-size: inherit;
  font-family: inherit;
  text-align: center;
}
</style>
