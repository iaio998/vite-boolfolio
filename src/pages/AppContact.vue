<template>
  <div>
    <h1>Contact us</h1>
    <ContactForm />
  </div>
</template>

<script>
import ContactForm from "../components/ContactForm.vue";
export default {
  name: "AppContact",
  components: {
    ContactForm,
  },
};
</script>

<style lang="scss" scoped></style>
