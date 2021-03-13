<template>
  <input type="text" v-model="newTodo" @keypress.enter="addTodo"/>
  <button @click="addTodo">Add Todo</button>
  <div v-for="todo in todoList" :key="todo.id">
    <p>{{ todo.title }}</p>
    <button @click="deleteTodo(todo)">Delete Todo</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todoList: [
        {
          id: 1,
          title: "Watch Constantine",
        },
        {
          id: 2,
          title: "Make a Todo List",
        },
      ],
      newTodo: "",
    };
  },
  methods: {
    addTodo() {
      this.todoList.push({ id: this.todoList.length + 1, title: this.newTodo });
      this.newTodo = "";
    },
    deleteTodo(closeTodo) {
      this.todoList.splice(this.todoList.indexOf(closeTodo), 1);
    }
  },
};
</script>

<style>
</style>