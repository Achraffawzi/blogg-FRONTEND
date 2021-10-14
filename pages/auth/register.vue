<template>
  <div class="register">
    <v-container style="width: 600px; max-width: 90vw; margin: auto;">
      <v-form>
        <v-text-field label="username" v-model="username"></v-text-field>
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
      <v-file-input accept="image/*" label="picture"></v-file-input>

      <v-btn class="primary white--text">Register</v-btn>
      </v-form>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Register",

  data() {
    return {
      username: "",
      email: "",
      password: "",
      show1: false
    };
  }
};
</script>

<style scoped></style>
