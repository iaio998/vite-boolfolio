<template>
  <div>
    <ul>
      <li v-for="project in store.projects" :key="project.id">
        <router-link
          :to="{ name: 'project', params: { slug: project.slug } }"
          >{{ project.title }}</router-link
        >
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
    };
  },
  methods: {
    getApiTest() {
      axios.get(this.store.apiUrl + "projects").then((res) => {
        console.log(res.data);
        this.store.projects = res.data;
      });
    },
  },
  mounted() {
    this.getApiTest();
  },
};
</script>

<style lang="scss" scoped></style>
