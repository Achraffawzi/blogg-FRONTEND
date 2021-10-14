<template>
  <div class="post-details py-16">
    <span class="capture text-center d-inline-block mb-5">
      <nuxt-link to="/">&lt;- go back</nuxt-link>
    </span>
    <v-img :src="`http://localhost:3001/uploads/images/${post.image}`"></v-img>
    <h2 class="text-h2 text-center mb-4">{{ post.title }}</h2>
    <p class="text-center">{{ post.content }}</p>
  </div>
</template>

<script>
export default {
  name: "id",

  asyncData({ $axios, route }) {
    return $axios.$get(`/posts/${route.params.id}`).then(post => {
      return {
        post
      };
    });
  },

  data() {
    return {
      post: null
    };
  }
};
</script>

<style scoped>
.post-details {
  width: 600px;
  max-width: 90vw;
  margin: auto;
}
</style>
