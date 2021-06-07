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
 
  props: ['post'],
}
</script>
