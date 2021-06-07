<template>
  <ul id="example-1">
        <li v-for="post in posts" :key="post.id">
            <nuxt-link :to="`/posts/${post.id}`">{{ post.title }}</nuxt-link>
        </li>
    </ul>
</template>

<script>
export default {
  data(){
    return{
      posts: []
    }
  },
  async fetch() {
      this.posts = await fetch(
        'https://jsonplaceholder.typicode.com/posts'
      ).then(res => res.json())
    }
}
</script>
