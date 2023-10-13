<!-- <script lang="ts">
import { defineNuxtComponent } from 'nuxt/app';

type TodoType = {
  id: string;
  title: string;
  completed: boolean;
};

type PhotoType = {
  albumId: string;
  thumbnailUrl: string;
};

export default defineNuxtComponent({
  data: () => ({
    todoList: [] as TodoType[],
    photos: [] as PhotoType[],
  }),

  methods: {
    fetchTodoList() {
      fetch('https://jsonplaceholder.typicode.com/todos/')
        .then((response) => response.json())
        .then((json) => (this.todoList = json));
    },

    async fetchPhotos() {
      const res = await fetch('https://jsonplaceholder.typicode.com/photos');
      const data = await res.json();
      this.photos = data;
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

    <ul>
      <button @click="fetchPhotos">Fetch photos</button>
      <li v-for="photo in photos" :key="`photo-id-${photo.albumId}`">
        <img :src="photo.thumbnailUrl" />
      </li>
    </ul>
  </div>
</template> -->

<script setup lang="ts"></script>
<template>
  <NuxtLayout>
    <nav>
      <ul>
        <li><NuxtLink to="dashboard">Dashboard</NuxtLink></li>
        <li><NuxtLink to="/">Home</NuxtLink></li>
        <li><NuxtLink to="/mast">Mast</NuxtLink></li>
      </ul>
    </nav>

    <NuxtPage />
  </NuxtLayout>
</template>
