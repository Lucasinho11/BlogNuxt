<template>
  <div>
    <h1 v-if="error.statusCode === 404">Page introuvable</h1>
    <h1 v-else>An error occurred</h1>
    <NuxtLink to="/">Home page</NuxtLink>
  </div>
</template>

<script>
  export default {
      head() {
    return {
      title: "Page Introuvable"
    }
  },
    props: ['error'],
    layout: 'error' 
  }
</script>
<style scoped>
div{
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 35vh;

}
</style>