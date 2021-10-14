<template>
  <div class="read-more-button">
    <v-btn class="primary" small>
      <nuxt-link :to="`/${id}`" class=" white--text text-decoration-none">Read More</nuxt-link>
    </v-btn>
  </div>
</template>

<script>
  export default {
    name: "ReadMoreButton",

    props: ["id"]
  }
</script>

<style scoped>

</style>
