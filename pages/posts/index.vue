<template>
  <div>
    <h2>Making API request - the Vue way</h2>
    <div class="container row">
      <Card class="ml-auto mr-auto" v-for="post in posts" :key="post.id" :post="post"></Card>
    </div>
  </div>
</template>

<script>
  import axios from 'axios';
  import Card from "../../components/Card";

  export default {
    name: "index.vue",
    components: {
      Card,
    },
    data() {
      return {
        posts: [],
      }
    },
    // mounted() {
    //   axios.get('https://jsonplaceholder.typicode.com/todos')
    //     .then(response => {
    //       console.log(response);
    //       this.posts = response.data;
    //     })
    //     .catch(function (error) {
    //       console.log(error);
    //     })
    // },
    async asyncData(context) {
      let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts');
      return {posts: data};
    },
    head: {
      title: 'List of posts',
    }
  }
</script>

<style scoped>

</style>
