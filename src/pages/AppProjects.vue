<template>
  <div class="container">
    <select
      @change="getProjectsByCategory()"
      name="category"
      id="category"
      v-model="selectedCategory"
    >
      <option :value="all">All categories</option>
      <option
        v-for="category in store.categories"
        :key="category.slug"
        :value="category.id"
      >
        {{ category.name }}
      </option>
    </select>
    <div class="row py-3 g-3">
      <div
        class="col-4 col-md-4 col-lg-6 text-center"
        v-for="project in store.projects"
        :key="project.id"
      >
        <CardComponent
          :image="store.apiUrlImg + project.image"
          :title="project.title"
          :url="project.url"
          :slug:="project.slug"
        />
        <button>
          <router-link
            :to="{ name: 'project', params: { slug: project.slug } }"
            >{{ project.title }}</router-link
          >
        </button>
      </div>
    </div>
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
      currentPage: 1,
      selectedCategory: "all",
    };
  },
  methods: {
    getApiProjects() {
      axios.get(this.store.apiUrl + "projects").then((res) => {
        console.log(res.data);
        this.store.projects = res.data;
      });
    },
    getApiCategories() {
      axios.get(this.store.apiUrl + "categories").then((res) => {
        console.log(res.data.categories);
        this.store.categories = res.data.categories;
      });
    },
    getProjectsByCategory() {
      if (this.selectedCategory == "all") {
        this.getAllProjects();
      } else {
        axios
          .get(store.apiUrl + "projects", {
            params: { category: this.selectedCategory },
          })
          .then((res) => {
            console.log(res.data);
            this.store.projects = res.data;
          });
      }
    },
  },
  mounted() {
    this.getApiProjects();
    this.getApiCategories();
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
