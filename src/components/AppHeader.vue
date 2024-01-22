<template>
  <div>
    <ul>
      <li v-for="(path, index) in paths" :key="index">
        <router-link :to="{ name: path.name }">{{ path.label }}</router-link>
        <!-- <a :href="path.url">{{ path.label }}</a> -->
      </li>
    </ul>
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

<style lang="scss" scoped></style>
