<template>
  <div class="container">
    <div>
      <h1 class="title">
        Post#{{post.id}}
      </h1>
      <div>
        <h2>{{ post.title}}</h2>
        <p>{{ post.body}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: this.post.title
    }
  },
  data() {
    return {
      post: {}
    }
  },
  async asyncData({ params, $http }) {
    const post = await $http.$get(`https://jsonplaceholder.typicode.com/posts/${params.id}`);
    return { post }
  }
}
</script>