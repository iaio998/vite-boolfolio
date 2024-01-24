<template>
  <div class="container my-3">
    <form @submit.prevent="submitForm">
      <div class="mb-3">
        <label for="name" class="form-label">Nome</label>
        <input
          v-model="name"
          type="text"
          class="form-control"
          id="name"
          aria-describedby="emailHelp"
        />
      </div>
      <div class="mb-3">
        <label for="email" class="form-label">Email</label>
        <input
          v-model="email"
          type="email"
          class="form-control"
          id="email"
          aria-describedby="emailHelp"
        />
        <div id="emailHelp" class="form-text">
          We'll never share your email with anyone else.
        </div>
      </div>
      <div class="mb-3">
        <label for="address" class="form-label">Indirizzo</label>
        <input
          v-model="address"
          type="text"
          class="form-control"
          id="address"
        />
      </div>
      <div class="mb-3">
        <label for="message" class="form-label">Messaggio</label>
        <textarea
          v-model="message"
          class="form-control"
          id="message"
          rows="5"
        ></textarea>
      </div>
      <button type="submit" class="btn btn-primary me-3">Submit</button>
      <button type="reset" class="btn btn-secondary">Reset</button>
    </form>
  </div>
</template>

<script>
import axios from "axios";
import { store } from "../data/store.js";
export default {
  name: "ContactForm",
  data() {
    return {
      store,
      name: "",
      email: "",
      address: "",
      message: "",
    };
  },
  methods: {
    submitForm() {
      const formData = {
        name: this.name,
        email: this.email,
        address: this.address,
        message: this.message,
      };
      axios
        .post(this.store.apiUrl + "contacts", formData)
        .then((res) => {
          console.log(res.data);
          (this.name = ""),
            (this.email = ""),
            (this.address = ""),
            (this.message = "");
        })
        .catch((err) => {
          console.log("error", err);
        });
    },
  },
};
</script>

<style lang="scss" scoped></style>
