<script lang="ts">
import { defineNuxtComponent } from 'nuxt/app';

type PhotoType = {
  albumId: string;
  thumbnailUrl: string;
};

export default defineNuxtComponent({
  data: () => ({
    photos: [] as PhotoType[],
  }),

  methods: {
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
    <ul>
      <button @click="fetchPhotos">Fetch photos</button>
      <li v-for="photo in photos" :key="`photo-id-${photo.albumId}`">
        <img :src="photo.thumbnailUrl" />
      </li>
    </ul>
  </div>
</template>
