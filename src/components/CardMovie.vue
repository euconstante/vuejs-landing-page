<script lang="ts">
import { defineComponent } from 'vue'

import '../assets/styles/components/CardMovie.css'

export default defineComponent({
  props: {
    image: String,
    title: String,
    description: String,
  },
})
</script>

<template>
  <div class="card">
    <img :src="image" alt="Card Image" class="card-image" width="170" />
  </div>
</template>

<style></style>
