<template>
  <h1>Todo List Using Vue</h1>
  <Todo />
</template>

<script>
import Todo from './components/Todo';

export default {
  name: 'App',
  setup() {
    return {
      Todo,
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
