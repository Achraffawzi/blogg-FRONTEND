<template>
  <div class="register">
    <v-container style="width: 600px; max-width: 90vw; margin: auto;">
      <!-- SNACKBAR MSG -->
      <v-snackbar v-model="snackbar" top right>
        {{ snackbarMsg }}

        <template v-slot:action="{ attrs }">
          <v-btn color="pink" text v-bind="attrs" @click="snackbar = false">
            Close
          </v-btn>
        </template>
      </v-snackbar>

      <v-form>
        <v-text-field label="fullname" v-model="fullname"></v-text-field>
        <v-text-field label="email" v-model="email"></v-text-field>
        <v-text-field
          v-model="password"
          :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
          :type="show1 ? 'text' : 'password'"
          label="password"
          hint="At least 8 characters"
          counter
          @click:append="show1 = !show1"
        ></v-text-field>
        <v-file-input
          accept="image/*"
          label="picture"
          v-model="picture"
        ></v-file-input>
        <v-checkbox v-model="isAuthor" label="I'm an author"></v-checkbox>
        <v-btn class="primary white--text" @click="onRegister">Register</v-btn>
      </v-form>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Register",

  data() {
    return {
      snackbarMsg: "",
      snackbar: false,
      fullname: "",
      email: "",
      password: "",
      picture: "",
      isAuthor: false,
      show1: false
    };
  },

  methods: {
    async onRegister() {

      let fd = new FormData();

      fd.append("fullname", this.fullname);
      fd.append("email", this.email);
      fd.append("password", this.password);
      fd.append("picture", this.picture);
      fd.append("isAuthor", this.isAuthor);

      try {
        const response = await this.$axios.$post("/auth/register", fd);
        this.snackbarMsg = response.data;
        console.log("response : " + response.data);
      } catch (err) {
        this.snackbarMsg = err.response.data.data
      } finally {
        this.snackbar = true;
      }
    }
  }
};
</script>

<style scoped></style>
