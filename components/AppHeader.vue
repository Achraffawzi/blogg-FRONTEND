<template>
  <div class="app-header black">
    <v-container class=" white--text">
      <v-row class="align-center">
        <v-col cols="12" sm="6" class="text-right text-h4 branding">
          Blogg
        </v-col>
        <v-col cols="12" sm="6" class="text-right">
          <nuxt-link to="#" class="header-link white--text text-decoration-none mr-5">Sign up</nuxt-link>
          <nuxt-link to="#" class="header-link white--text text-decoration-none">Register</nuxt-link>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
  export default {
    name: "AppHeader"
  }
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Rancho&display=swap');

.branding { font-family: 'Rancho', cursive !important }

.header-link {
  font-size: 14px;
}
</style>
