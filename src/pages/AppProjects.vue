<template>
  <div>
    <ul>
      <li v-for="project in projects" :key="project.id">
        {{ project.title }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
import { store } from "../data/store.js";
export default {
  name: "AppProjects",
  components: {},
  data() {
    return {
      store,
      projects: [],
    };
  },
  methods: {
    getApiTest() {
      axios.get(this.store.apiUrl + "projects").then((res) => {
        console.log(res.data);
        this.projects = res.data;
      });
    },
  },
  mounted() {
    this.getApiTest();
  },
};
</script>

<style lang="scss" scoped></style>
