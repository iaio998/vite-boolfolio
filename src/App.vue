<template>
  <header>
    <AppHeader />
  </header>
  <main>
    <router-view></router-view>
  </main>
  <footer>
    <AppFooter />
  </footer>
</template>

<script>
import axios from "axios";
import { store } from "./data/store.js";
import AppHeader from "./components/partials/AppHeader.vue";
import AppFooter from "./components/partials/AppFooter.vue";
export default {
  name: "App",
  components: {
    AppHeader,
    AppFooter,
  },
  data() {
    return {
      store,
    };
  },
  methods: {},
  mounted() {},
};
</script>

<style lang="scss" scoped>
@use "./assets/styles/partials/variables.scss" as *;
h1 {
  color: $font-color;
}
</style>
