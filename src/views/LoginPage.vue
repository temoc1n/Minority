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
      <div class="col-6 login-form">
        <!-- Language Changer -->
        <LanguageSwitcher
          @ChangeLanguage="(language) => (this.lang = language)"
        />
        <!-- Main Board -->
        <div class="login-form">
          <div class="border rounded-5 text-center">
            <div class="login">
              <div class="header-login mt-5">
                <h1>Minorify</h1>
                <p>Connect. Share. Empower.</p>
              </div>
              <div class="form mt-4">
                <label for="email" class="authentication">{{
                  $t("Email")
                }}</label>
                <div class="input-group mb-3 gap-3 ps-3 pe-3">
                  <input
                    type="text"
                    :placeholder="$t('Email-Placeholder-Login')"
                    class="form-control authentication"
                    :class="lang == 'ara' ? 'text-end' : 'text-start'"
                    id="email"
                  />
                </div>
                <label for="password" class="authentication mt-3">{{
                  $t("Password")
                }}</label>
                <div class="input-group mb-3 gap-3 ps-3 pe-3">
                  <input
                    type="text"
                    :placeholder="$t('Password-Placeholder-Login')"
                    class="form-control authentication mb-3"
                    :class="lang == 'ara' ? 'text-end' : 'text-start'"
                    id="password"
                  />
                </div>
                <div class="validation mb-3">
                  <button
                    type="button"
                    class="btn btn-outline-info me-4 w-25 overflow-hidden"
                  >
                    {{ $t("Continue") }}
                  </button>
                  <button
                    type="button"
                    class="btn btn-outline-info w-25 overflow-hidden"
                    @click="this.$router.push('/register')"
                  >
                    {{ $t("Register") }}
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
        <FooterLogin />
      </div>
    </div>
  </div>
</template>
<script>
import LanguageSwitcher from "@/components/LanguageSwitcher.vue";
import FooterLogin from "@/components/LoginComponents/FooterLogin.vue";
export default {
  name: "LoginPage",
  components: {
    LanguageSwitcher,
    FooterLogin,
  },
  data() {
    return {
      image: undefined,
      lang: "en",
    };
  },
  watch: {
    lang() {
      this.$i18n.locale = this.lang;
    },
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
  },
};
</script>
<style scoped>
.image-background-login {
  background-image: v-bind(image) !important;
}
</style>
