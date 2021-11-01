<template>
  <div class="base-snackbar">
    <v-snackbar v-model="snackbar" :timeout="5000" top right>
      {{ snackbarMsg }}

      <template v-slot:action="{ attrs }">
        <v-btn color="pink" text v-bind="attrs" @click="snackbar = false">
          Close
        </v-btn>
      </template>
    </v-snackbar>
  </div>
</template>

<script>
export default {
  name: "BaseSnackbar",
  props: ["snackbarMsg", "show"],
  data() {
    return {
      snackbar: this.show
    };
  }
};
</script>

<style scoped></style>
