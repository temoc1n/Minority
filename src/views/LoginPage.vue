<template>
  <div class="container-fluid login-page">
    <div class="row">
      <div class="col-6 d-none d-lg-block image-background-login">
        <div
          class="color-overlay d-flex justify-content-center align-items-center"
          :style="{
            'background-image': 'url(' + image + ') !importante',
          }"
        ></div>
      </div>
      <div class="col-6 login-form text-center">
        <div class="border rounded-5">
          <div class="login">
            <div class="header-login mt-5">
              <h1>Minorify</h1>
              <p>Connect. Share. Empower</p>
            </div>
            <div class="form mt-4">
              <label for="email" class="text-start authentication">{{
                $t("Email")
              }}</label>
              <div class="input-group mb-3 gap-3 ps-3 pe-3">
                <input
                  type="text"
                  :placeholder="$t('Email-Placeholder')"
                  class="form-control authentication"
                  id="email"
                />
              </div>
              <label for="password" class="authentication mt-3">{{
                $t("Password")
              }}</label>
              <div class="input-group mb-3 gap-3 ps-3 pe-3">
                <input
                  type="text"
                  :placeholder="$t('Password-Placeholder')"
                  class="form-control authentication mb-3"
                  id="password"
                />
              </div>
              <div class="validation mb-3">
                <button type="button" class="btn btn-outline-info me-4 w-25">
                  Login
                </button>
                <button type="button" class="btn btn-outline-info w-25">
                  Regiter
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "LoginPage",
  data() {
    return {
      image: undefined,
    };
  },
  mounted() {
    //Choose Background Image
    const images = [
      require("../assets/background-login-thailand.jpg"),
      require("../assets/background-login-senegal.jpg"),
      require("../assets/background-login-turkey.jpg"),
      require("../assets/background-login-mexico.jpg"),
      require("../assets/background-login-india.jpg"),
      require("../assets/background-login-china.jpg"),
    ];
    const index_number = Math.floor(Math.random() * images.length);
    this.image = "url(" + images[index_number] + ")";
    ///

    this.$i18n.locale = "en";
  },
};
</script>
<style scoped>
.image-background-login {
  background-image: v-bind(image) !important;
}
</style>
