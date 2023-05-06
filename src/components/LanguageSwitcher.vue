<template>
  <div class="language text-start">
    <div class="dropdown">
      <button
        class="btn mt-2 btn-secondary dropdown-toggle"
        type="button"
        id="dropdownMenuButton1"
        data-bs-toggle="dropdown"
        aria-expanded="false"
      >
        {{ $t("Language") }}
      </button>
      <ul
        class="dropdown-menu language-menu"
        aria-labelledby="dropdownMenuButton1"
      >
        <li>
          <a class="dropdown-item" href="#" @click="ChangeLanguage('en')"
            >English</a
          >
        </li>
        <li>
          <a class="dropdown-item" href="#" @click="ChangeLanguage('ara')"
            >Arabic</a
          >
        </li>
        <li>
          <a class="dropdown-item" href="#" @click="ChangeLanguage('se')"
            >Swedish</a
          >
        </li>
        <li>
          <a class="dropdown-item" href="#" @click="ChangeLanguage('tr')"
            >Turkish</a
          >
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name: "LanguageSwitcher",
  methods: {
    ChangeLanguage(lang) {
      this.$emit("ChangeLanguage", lang);
    },
  },
};
</script>
<style scoped></style>
