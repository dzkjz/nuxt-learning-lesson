<template>
  <div>
    <h2>Making API request - the Vue way</h2>
    <div class="container row">
      <Card class="ml-auto mr-auto" v-for="post in posts" :key="post.id" :post="post"></Card>
      <button class="btn btn-danger" v-scroll-to="'body'">Back to Top</button>
    </div>
  </div>
</template>

<script>
  import axios from 'axios';
  import Card from "../../components/Card";

  import {mapGetters} from 'vuex';

  export default {
    name: "index.vue",
    components: {
      Card,
    },
    // data() {
    //   return {
    //     posts: [],
    //   }
    // },
    computed: {
      ...mapGetters(['posts']),
      // allPosts() {
      //   return this.$store.getters.posts;
      // }
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
    // async asyncData(context) {
    //   let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts');
    //   return {posts: data};
    // },

    // async asyncData({store}) {
    //   let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts');
    //   store.dispatch('setPosts', data);
    // },
    // async fetch({store}) {
    //   let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts');
    //   store.dispatch('setPosts', data);
    // },
    head: {
      title: 'List of posts',
    }
  }
</script>

<style scoped>

</style>
