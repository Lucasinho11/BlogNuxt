<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        Posts
      </h1>
      <nuxt-link to="/about">ABOUT</nuxt-link>
      <ul id="example-1">
        <li v-for="post in posts" :key="post.id">
            <nuxt-link :to="{path: '/posts', params: {id: post.id} }">{{post.title}}</nuxt-link>
        </li>
      </ul>

      </div>
  </div>
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

