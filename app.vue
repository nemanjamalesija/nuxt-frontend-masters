<script lang="ts">
import { defineNuxtComponent } from 'nuxt/app';

type TodoType = {
  id: string;
  title: string;
  completed: boolean;
};

export default defineNuxtComponent({
  data: () => ({
    todoList: [] as TodoType[],
  }),

  methods: {
    fetchTodoList() {
      fetch('https://jsonplaceholder.typicode.com/todos/')
        .then((response) => response.json())
        .then((json) => (this.todoList = json));
    },
  },
});
</script>

<template>
  <div>
    <img src="/todo.avif" alt="Todo photo" height="400px" />
    <button @click="fetchTodoList">Fetch list</button>
    <ul>
      <li v-for="todo in todoList" :key="`todo-id-${todo.id}`">
        <input type="checkbox" :checked="todo.completed" />
        {{ todo.title }}
      </li>
    </ul>
  </div>
</template>
