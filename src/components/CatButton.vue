<template>
  <div>
    <button @click="getCatImage">Cat Picture</button>
  </div>
</template>

<script>
import axios from "axios";
import cookies from "vue-cookies";

export default {
  name: "CatButton",
  methods: {
    getCatImage() {
      axios
        .get("https://aws.random.cat/meow")
        .then((response) => {
          let src = response.data.file;
          this.$root.$emit(`newDisplay`, src);
          // setting cookies
          cookies.set(`selection`, "cat");
        })
        .catch((error) => {
          console.log(error);
        })
        .finally(() => {
          "Finally";
        });
    },
  },
  // The purpose of this is if the user clicks on the cat button,
  // then when they refersh the page, automatically display cat image

  mounted() {
    let selection = cookies.get(`selection`);
    if (selection == "cat") {
      this.getCatImage();
    }
  },
};
</script>

<style scoped>
</style>