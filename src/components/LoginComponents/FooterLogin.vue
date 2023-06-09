<template>
  <div>
    <footer class="text-center">
      <span class="footer_text"
        >Copyright @ {{ date }} Minorify <a href="/">Terms of Use</a> |
        <a href="/">Privacy Policy</a>
      </span>
    </footer>
  </div>
</template>
<script>
export default {
  name: "FooterLogin",
  data() {
    return {
      date: new Date().getFullYear(),
    };
  },
};
</script>
<style scoped></style>
