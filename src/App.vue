<template>
  <AppHeader />
  <router-view></router-view>
</template>

<script>
import axios from "axios";
import { store } from "./data/store.js";
import AppHeader from "./components/AppHeader.vue";
export default {
  name: "App",
  components: {
    AppHeader,
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
