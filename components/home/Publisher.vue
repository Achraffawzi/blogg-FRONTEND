<template>
  <div class="publisher">
    <v-avatar :size="width">
      <img :src="require('@/assets/images/banner.jpg')" alt="published name" />
    </v-avatar>
    <span class="white--text ml-2">Published name</span>
  </div>
</template>

<script>
export default {
  name: "Publisher",

  props: {
    width: {
      type: Number,
      required: false
    }
  }
};
</script>

<style scoped></style>
