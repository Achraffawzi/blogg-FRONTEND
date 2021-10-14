<template>
  <div class="home">
    <!-- Banner -->
    <section class="banner py-10">
      <v-container>
        <!-- <v-row>
          <v-row>
            <v-col
              cols="12"
              sm="12"
              class="white--text banner-post-card-container-1"
            >
              <PostCard />
            </v-col>
          </v-row> -->
        <!-- <div class="d-flex align-center justify-end banner-post-card-container-1">
            <div>
              <PostCard />
            </div>
          </div>
          <div class="d-flex flex-column align-center justify-center">
            <div class="banner-post-card-container-2">
              <PostCard />
            </div>
            <div class="banner-post-card-container-3">
              <PostCard />
            </div>
          </div>
          <div class="d-flex flex-column align-center justify-center">
            <div class="banner-post-card-container-2">
              <PostCard />
            </div>
            <div class="banner-post-card-container-3">
              <PostCard />
            </div>
          </div> -->
        <!-- <v-row class="mt-0">
            <v-col
              cols="12"
              sm="12"
              class="white--text banner-post-card-container-2"
            >
              <PostCard />
            </v-col>
            <v-col
              cols="12"
              sm="12"
              class="white--text banner-post-card-container-3"
            >
              <PostCard />
            </v-col>
          </v-row> -->
        <!-- </v-row> -->
      </v-container>
    </section>

    <!-- Big Post -->
    <section class="big-post">
      <v-container class="px-5">
        <v-img
          :src="require('@/assets/images/banner.jpg')"
          height="300"
          class="px-16 py-5 d-flex align-end"
        >
          <div class="post-body">
            <p class="white--text mb-5" style="font-size: 22px; width: 50%">
              In publishing and graphic design, Lorem ipsum is a placeholder
              text commonly.
            </p>
            <div style="width: 50%;" class="d-flex justify-space-between align-center">
              <Publisher />
              <read-more-button />
            </div>
          </div>
        </v-img>
      </v-container>
    </section>
  </div>
</template>

<script>
import PostCard from "@/components/home/PostCard.vue";
import Publisher from "@/components/home/Publisher.vue";
export default {
  name: "Index",

  components: {
    PostCard,
    Publisher
  }
};
</script>

<style lang="scss" scoped>
.banner {
  background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.8)),
    url("@/assets/images/banner.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  // background-position: center center;
  min-height: 350px;

  .banner-post-card-container-1 {
    // width: 200px;
    max-width: 490px;
  }

  .banner-post-card-container-2,
  .banner-post-card-container-3 {
    // width: 50px;
    max-width: 300px;
  }
}
</style>
