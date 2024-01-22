<template>
  <div class="container">
    <div class="my-2 text-center">
      <CardComponent
        :image="store.apiUrlImg + project.image"
        :title="project.title"
        :url="project.url"
      />
      <button>
        <router-link :to="{ name: 'projects' }">Go back</router-link>
      </button>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import { store } from "../data/store.js";
import CardComponent from "../components/CardComponent.vue";
export default {
  name: "AppProjectShow",
  components: {
    CardComponent,
  },
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

<style lang="scss" scoped>
button {
  margin-top: 6px;
  border-radius: 20px;
  background-color: #212529;
  transition: 0.6s;
  &:hover a {
    color: white;
  }
  &:hover {
    background-color: green;
  }
  a {
    color: white;
  }
}
</style>
