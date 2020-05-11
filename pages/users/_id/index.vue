<template>
  <div>
    <h2>This is first nested page</h2>
    <input type="text" v-model="id">
    <button @click="loadUser">Load user</button>
  </div>
</template>

<script>
  export default {
    name: "index.vue",
    data() {
      return {
        id: '',
      }
    },
    methods: {
      loadUser() {
        this.$router.push(`/users/1/${this.id}`);
      },
    }
  }
</script>

<style scoped>

</style>
