<template>
  <div class="post-card">
    <v-img :src="require('@/assets/images/banner.jpg')">
      <div class="post-body">
        <p class="white--text">In publishing and graphic design, Lorem ipsum is a placeholder text commonly.</p>
        <div class="d-flex align-center">
          <Publisher />
          <read-more-button />
        </div>
      </div>
    </v-img>
  </div>
</template>

<script>
import ReadMoreButton from '../ReadMoreButton.vue'
  export default {
  components: { ReadMoreButton },
    name: "PostCard"
  }
</script>

<style scoped>

</style>
