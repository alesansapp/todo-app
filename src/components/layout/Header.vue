<template>
  <header class="header">
    <h1>ADD YOUR TODOS</h1>
  </header>
</template>

<script>
export default {
  name: 'Header',
};
</script>

<style scoped>
.header {
  background: royalblue;
  color: white;
  text-align: center;
  padding: 1rem;
  -webkit-box-shadow: 0px 0px 6px 3px rgba(0, 0, 0, 0.2);
  -moz-box-shadow: 0px 0px 6px 3px rgba(0, 0, 0, 0.2);
  box-shadow: 0px 0px 6px 3px rgba(0, 0, 0, 0.2);
  margin-bottom: 2rem;
}

.header a {
  color: white;
  padding-right: 0.5rem;
}
</style>
