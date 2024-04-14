<script setup>
  import {ref} from 'vue'
  const portfolioItems=ref([
      {
        title: 'Portfolio Item 1',
        description: 'This is a profolio item 1',
        id: 1,
        image: "https://via.placeholder.com/150",
        link: "https://www.google.com",
        category: "web"
      },
      {
        title: 'Portfolio Item 2',
        description: 'This is a profolio item 2',
        id: 2,
        category: "design"
      }
    ]) //dynamic
</script>


<template>
  <main>
    <h1 class="text-3xl font-bold underline">
  </h1>
  <div v-for="portfolioItem in portfolioItems" :key="portfolioItem" class="card">
    <h2 :class="portfolioItem.category">{{ portfolioItem.title }}</h2>
    <h2>{{ portfolioItem.description }}</h2>
    <h2>{{ portfolioItem.id }}</h2>
    <img :src="portfolioItem.image" alt="">
    <div v-if="portfolioItem.link">
      <a :href="portfolioItem.link">link</a>
    </div>
    <div v-else></div>
  </div>
  </main>
</template>


<style>
.card{
  border: 1px solid #000;
  padding: 1rem;
  margin: 1rem;
  border-radius: 0.5rem;
  background-color: #fff;
  color: #000;
}
.web{
  background-color: aqua;
}
.design{
  background-color: blueviolet;
}

</style>
