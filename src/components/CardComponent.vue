<template>
  <div>
    <div class="img-cont">
      <img :src="image" :alt="title" />
    </div>
    <div class="card-txt">
      <p>{{ title }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
  props: {
    image: String,
    title: String,
  },
  data() {
    return {};
  },
  methods: {},
  mounted() {},
};
</script>

<style lang="scss" scoped>
.img-cont {
  width: 200px;
  height: 150px;
  img {
    width: 100%;
  }
}
</style>
