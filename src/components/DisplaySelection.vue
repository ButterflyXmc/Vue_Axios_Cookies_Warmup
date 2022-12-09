<template>
  <div>
    <h1>HELLO</h1>
    <!-- :binding -->
    <img :src="imageSrc" alt="" />
  </div>
</template>

<script>
export default {
  name: "DisplaySelection",
  data() {
    return {
      imageSrc: "",
    };
  },
  methods: {
    showPicture(src) {
      this.imageSrc = src;
    },
  },
  mounted() {
    // you need to go to the root element
    // and listen for emit that will come from an application from newDisplay
    // then run the function showPicture
    this.$root.$on(`newDisplay`, this.showPicture);
  },
};
</script>

<style scoped>
</style>