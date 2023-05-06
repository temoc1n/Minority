<template>
  <router-view></router-view>
</template>
<script>
export default {
  name: "App",
  data() {
    return {
      authenticated: false,
    };
  },
  mounted() {
    if (!this.authenticated) {
      this.$router.push("/login");
    } else {
      this.$router.push("/");
    }
  },
};
</script>
<style>
@import url("/node_modules/bootstrap");
@import url("./assets/style.css");
</style>
