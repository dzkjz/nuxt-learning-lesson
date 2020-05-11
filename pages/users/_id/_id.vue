<template>
  <div>
    <h2>This is user's id: {{$route.params.id}} second nested page</h2>
  </div>
</template>

<script>
  export default {
    name: "_id.vue",
    validate(context) {
      return /^\d+$/.test(context.params.id);
    },
  }
</script>

<style scoped>

</style>
