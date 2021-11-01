<template>
  <div class="register">
    <!-- SNACKBAR MSG -->
    <base-snackbar v-if="show" :snackbarMsg="snackbarMsg" :show="show" />
    <div class="d-flex register-main">
      <div class="skew hidden-sm-and-down"></div>
      <v-form
        ref="registrationForm"
        style="height: 100%"
        class="d-flex flex-column align-center justify-center flex-grow-1 text-center"
      >
        <div class="form__child">
          <h3 class="text-h4 text-uppercase font-weight-bold">Register</h3>
          <p class="subtitle-2 mt-3 mb-5">
            Already have an account?
            <nuxt-link
              to="/auth/login"
              class="font-weight-bold text-decoration-none primary--text"
              >login</nuxt-link
            >
          </p>
          <v-text-field
            label="fullname"
            v-model="fullname"
            outlined
            dense
            :rule="stringRule"
          ></v-text-field>
          <v-text-field
            label="email"
            v-model="email"
            outlined
            dense
            :rules="emailRule"
          ></v-text-field>
          <v-text-field
            outlined
            dense
            v-model="password"
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            :type="show1 ? 'text' : 'password'"
            label="password"
            hint="At least 8 characters"
            counter
            @click:append="show1 = !show1"
            :rules="passwordRule"
          ></v-text-field>
          <v-file-input
            accept="image/*"
            label="picture"
            v-model="picture"
            prepend-icon="mdi-camera"
            required
            :rule="pictureRule"
          ></v-file-input>
          <v-checkbox v-model="isAuthor" label="I'm an author"></v-checkbox>
          <div class="d-flex align-center">
            <v-btn class="primary white--text register-btn" @click="onRegister"
              >Register</v-btn
            >
          </div>
        </div>
      </v-form>
    </div>
  </div>
</template>

<script>
import BaseSnackbar from "../../components/base/BaseSnackbar.vue";
export default {
  components: { BaseSnackbar },
  name: "Register",

  layout: "no-nav",

  data() {
    return {
      snackbarMsg: "",
      show: false,
      fullname: "",
      email: "",
      password: "",
      picture: "",
      isAuthor: false,
      show1: false,

      stringRule: [
        value => value.length > 1 || "Please enter a valid fullname"
      ],
      emailRule: [
        email =>
          /^[a-zA-Z0-9]+(((.|_|-)[a-zA-Z0-9]+)?)+@(gmail|yahoo|hotmail).(com|fr|uk|net)$/.test(
            email
          ) || "please enter a valid email adresse"
      ],
      passwordRule: [
        password =>
          password.length >= 8 || "Password must have at least 8 characters"
      ],
      pictureRule: [value => !!value || "Picture is required"]
    };
  },

  methods: {
    async onRegister() {
      if (this.$refs.registrationForm.validate()) {
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
          this.snackbarMsg = err.response.data.data;
        } finally {
          this.show = true;
        }
      } else {
        this.snackbarMsg = "Please verify your information";
        this.show = true;
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.register {
  height: 100%;

  .register-main {
    height: 100%;

    .skew {
      width: 65%;
      height: 100%;
      transform-origin: bottom right;
      transform: skewX(10deg);
      background-image: url("@/assets/images/skew-bg.jpg");
      background-position: center center;
      background-size: cover;
      background-repeat: no-repeat;
    }
  }
}

.form__child {
  width: 70%;
}

.register-btn {
  width: 100%;
}
</style>
