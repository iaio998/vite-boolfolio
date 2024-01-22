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
            <li class="nav-item">
              <a class="nav-link" aria-current="page" href="#">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Projects</a>
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
          url: "/",
        },
        {
          label: "Projects",
          name: "projects",
          url: "/projects",
        },
      ],
    };
  },
  methods: {},
  mounted() {},
};
</script>

<style lang="scss" scoped>
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
    &:hover {
      color: yellow;
    }
  }
}
</style>
