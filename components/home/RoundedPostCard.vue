<template>
  <div class="rounded-post-card">
    <v-card class="mx-auto rounded-t-xl" max-width="344">
      <v-img
        :src="`http://localhost:3001/uploads/images/${post.image}`"
        height="200px"
        gradient="rgba(0,0,0,.5), rgba(0,0,0,.5)"
        class="d-flex align-end pa-5"
      >
        <div>
          <v-card-title class="white--text subtitle-1">
            {{ post.title }}
          </v-card-title>
          <publisher :width="30" />
        </div>
      </v-img>

      <v-card-text>
        {{ post.content }}
      </v-card-text
      >

      <v-card-actions>
        <read-more-button :id="post._id"/>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
import ReadMoreButton from "../ReadMoreButton.vue";
import Publisher from "./Publisher.vue";
export default {
  components: { ReadMoreButton, Publisher },

  name: "RoundedPostCard",

  props: ["post"]
};
</script>

<style scoped></style>
