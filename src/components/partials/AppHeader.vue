<template>
  <div class="bg-dark">
    <nav class="container navbar navbar-expand-lg">
      <div class="container-fluid">
        <div
          class="d-flex flex-column align-items-center justify-content-around"
        >
          <div class="img-cont">
            <img
              src="../../assets/images/profile.jpg"
              alt="Iacopo De Palatis"
            />
          </div>
          <p class="p-0 m-0">Iacopo De Palatis</p>
        </div>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li
              class="nav-item mx-2"
              v-for="(path, index) in paths"
              :key="index"
              @click="index = index"
              :class="{ active: index == index }"
            >
              <router-link active-class="my-active" :to="{ name: path.name }">{{
                path.label
              }}</router-link>
            </li>
          </ul>
          <form class="d-flex" role="search">
            <input
              class="form-control me-2"
              type="search"
              placeholder="Search"
              aria-label="Search"
            />
            <button class="btn btn-outline-warning" type="submit">
              Search
            </button>
          </form>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "AppHeader",
  components: {},
  data() {
    return {
      paths: [
        {
          label: "Home",
          name: "home",
          class: "active",
        },
        {
          label: "Projects",
          name: "projects",
          class: "active",
        },
      ],
      index: 0,
    };
  },
  methods: {},
  mounted() {},
};
</script>

<style lang="scss" scoped>
.my-active {
  color: green;
  border-bottom: 2px solid green;
}
nav {
  color: white;
  .img-cont {
    width: 80px;
    height: 80px;
    overflow: hidden;
    img {
      width: 100%;
      border-radius: 50%;
    }
  }
  a {
    color: white;
    font-size: 1.1em;
    text-decoration: none;
    transition: 0.5s;
    &:hover {
      color: grey;
      transform: scale(1.2);
    }
  }
}
</style>
