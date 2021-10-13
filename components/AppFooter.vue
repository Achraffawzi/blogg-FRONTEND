<template>
  <div class="app-footer">
    <v-footer class="black">
      <v-container>
        <p class="white--text text-center footer-content">&copy; {{ getCurrentYear }} Copyright - All rights reserved to Blogg community</p>
      </v-container>
    </v-footer>
  </div>
</template>

<script>
  export default {
    name: "AppFooter",

    computed: {
      getCurrentYear() {
        return new Date().getFullYear();
      },
    },
  }
</script>

<style scoped>
.footer-content {
  font-size: 14px !important;
}
</style>
