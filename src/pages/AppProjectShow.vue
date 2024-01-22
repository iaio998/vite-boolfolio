<template>
  <div>
    <h1>Title</h1>
    <p>{{ project.title }}</p>
  </div>
</template>

<script>
import axios from "axios";
import { store } from "../data/store.js";
export default {
  name: "AppProjectShow",
  components: {},
  data() {
    return {
      store,
      project: {},
    };
  },
  methods: {
    getProjectData() {
      axios
        .get(this.store.apiUrl + "projects/" + this.$route.params.slug)
        .then((res) => {
          console.log(res.data);
          this.project = res.data.project;
          console.log(this.project);
        });
    },
  },
  mounted() {
    this.getProjectData();
  },
};
</script>

<style lang="scss" scoped></style>
