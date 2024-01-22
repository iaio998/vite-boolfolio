<template>
  <div class="container">
    <div class="row">
      <div
        class="col-4 col-md-4 col-lg-12"
        v-for="project in store.projects"
        :key="project.id"
      >
        <CardComponent
          :image="store.apiUrlImg + project.image"
          :title="project.title"
        />
      </div>
    </div>

    <!-- <ul>
      <li v-for="project in store.projects" :key="project.id">
        <img :src="store.apiUrlImg + project.image" alt="" />
        <router-link
          :to="{ name: 'project', params: { slug: project.slug } }"
          >{{ project.title }}</router-link
        >
      </li>
    </ul> -->
  </div>
</template>

<script>
import axios from "axios";
import { store } from "../data/store.js";
import CardComponent from "../components/CardComponent.vue";
export default {
  name: "AppProjects",
  components: {
    CardComponent,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    getApiProjects() {
      axios.get(this.store.apiUrl + "projects").then((res) => {
        console.log(res.data);
        this.store.projects = res.data;
      });
    },
  },
  mounted() {
    this.getApiProjects();
  },
};
</script>

<style lang="scss" scoped></style>
