<script setup lang="ts">
const name = ref('');
const type = ref(1);

function navigate() {
  return navigateTo({
    path: '/gsagsagsagasga',
    query: {
      name: name.value,
      type: type.value,
    },
  });
}
</script>
<template>
  <NuxtLink to="/mast/idgaaf">Child</NuxtLink>
  <p>sirko</p>
</template>
