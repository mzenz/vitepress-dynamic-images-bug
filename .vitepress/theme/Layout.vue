<style scoped>
.thumbnail {
  position: relative;
  max-width: 250px;
}
</style>

<script setup lang="ts">
import { useData } from 'vitepress'

const { frontmatter } = useData()

const img = frontmatter.value.thumbnail
const imgPath = `/${img}`
const imgUrl = new URL(imgPath, import.meta.url).href
</script>

<template>
  <p>Thumbnail name: {{ img }}, Thumbnail url: {{ imgUrl }}</p>
  <img class="thumbnail" :src="imgUrl" alt="blog post thumbnail" />
  <Content />
</template>
