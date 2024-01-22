<template>
  <div class="text-center">
    <div class="img-cont">
      <img :src="image" :alt="title" />
    </div>
    <div class="card-txt">
      <p><strong>Project's name:</strong> {{ title }}</p>
      <p><strong>Project's github url:</strong> {{ url }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
  props: {
    image: String,
    title: String,
    url: String,
    slug: String,
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
  margin: 0 auto;
  width: 250px;
  height: 150px;
  overflow: hidden;
  img {
    width: 100%;
    height: 100%;
  }
}
p {
  margin: 0;
  padding: 0;
}
</style>
