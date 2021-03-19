<template>
  <input type="text" v-model="newTodo" @keypress.enter="addTodo" />
  <button @click="addTodo">Add Todo</button>
  <div v-for="todo in todoList" :key="todo.id">
    <p>{{ todo.title }}</p>
    <button @click="deleteTodo(todo)">Delete Todo</button>
  </div>
</template>

<script>
import { reactive, ref } from "@vue/reactivity";
export default {
  setup() {
    let todoList = reactive([
      {
        id: 1,
        title: "Watch Constantine",
      },
      {
        id: 2,
        title: "Make a Todo List",
      },
    ]);
    let newTodo = ref("");

    const addTodo = () => {
      todoList.push({id: todoList.length + 1, title: newTodo.value});
      newTodo.value = "";
    }

    const deleteTodo = closeTodo => {
      todoList.splice(todoList.indexOf(closeTodo), 1);
    }

    return {
      todoList,
      addTodo,
      newTodo,
      deleteTodo
    }
  },
};
</script>

<style>
</style>