<template>
  <div class="rounded-post-card">
    <v-card class="mx-auto rounded-t-xl" max-width="344">
      <v-img
        :src="require(`@/assets/images/banner.jpg`)"
        height="200px"
        gradient="rgba(0,0,0,.5), rgba(0,0,0,.5)"
        class="d-flex align-end pa-5"
      >
        <div>
          <v-card-title class="white--text subtitle-1">
            In publishing and graphic design, Lorem ipsum is a placeholder text
            commonly.
          </v-card-title>
          <publisher :width="30" />
        </div>
      </v-img>

      <v-card-text>
        In publishing and graphic design, Lorem ipsum is a placeholder text
        commonly.
        In publishing and graphic design, Lorem ipsum is a placeholder text
        commonly.
      </v-card-text
      >

      <v-card-actions>
        <read-more-button />
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
import ReadMoreButton from "../ReadMoreButton.vue";
import Publisher from "./Publisher.vue";
export default {
  components: { ReadMoreButton, Publisher },
  name: "RoundedPostCard"
};
</script>

<style scoped></style>
