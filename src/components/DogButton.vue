<template>
  <div>
    <button @click="getDogImage">Dog Picture</button>
  </div>
</template>

<script>
// 1.import first
import axios from "axios";
import cookies from "vue-cookies";

export default {
  name: "DogButton",
  methods: {
    getDogImage() {
      axios
        .get("https://dog.ceo/api/breeds/image/random")
        .then((response) => {
          let src = response.data.message;
          this.$root.$emit(`newDisplay`, src);
          // setting cookies
          cookies.set(`selection`, "dog");
        })
        .catch((error) => {
          console.log(error);
        })
        .finally(() => {
          "Finally";
        });
    },
  },
  // The purpose of this is if the user clicks on the dog button, t
  // hen when they refersh the page, automatically display dog image
  mounted() {
    let selection = cookies.get(`selection`);
    if (selection == "dog") {
      this.getDogImage();
    }
  },
};
</script>

<style scoped>
</style>