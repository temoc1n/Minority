<template>
  <div class="conatiner-fluid login-page">
    <div class="row">
      <div class="col-6 image-background-login">
        <div
          class="color-overlay d-flex justify-content-center align-items-center"
          :style="{
            'background-image': 'url(' + image + ') !importante',
          }"
        ></div>
      </div>
      <div class="col-6 login-form">
        <h1 style="color: red">asd</h1>
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
    const images = [require("../assets/background-login-arabic.jpg")];
    const index_number = Math.floor(Math.random() * (images.length - 1));
    console.log("Random Number: " + index_number);
    console.log("Images number: " + (images.length - 1));
    this.image = images[index_number];
  },
};
</script>
<style scoped>
.image-background-login {
  background-image: url("../assets/background-login-arabic.jpg") !important;
}
</style>
