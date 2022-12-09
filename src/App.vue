<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <DisplaySelection />
    <DogButton />
    <CatButton />
  </div>
</template>

<script>
import DisplaySelection from "@/components/DisplaySelection.vue";
import DogButton from "@/components/DogButton.vue";
import CatButton from "@/components/CatButton.vue";

export default {
  name: "App",
  components: {
    DisplaySelection,
    DogButton,
    CatButton,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
