<template>
  <div class="container">
    <h1>{{post.title}}</h1>
    <pre>{{post.body}}</pre>
    <nuxt-link to="/posts">Back to posts page</nuxt-link>
  </div>
</template>

<script>
  import axios from "axios";

  export default {
    name: "index.vue",

    // async asyncData(context) {
    //   let {data} = await axios.get(`https://jsonplaceholder.typicode.com/posts/${context.params.id}`);
    //   return {post: data};
    // },
    async asyncData({params}) {
      let {data} = await axios.get(`https://jsonplaceholder.typicode.com/posts/${params.id}`);
      return {post: data};
    },

    // head: {
    //   title: this.post.title,
    // }
    head() { //动态设置title
      return {
        title: this.post.title,
      }
    }
  }
</script>

<style scoped>

</style>
