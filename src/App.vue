<template>
  <v-app>
    <Header />
  </v-app>
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: "App",
  comments: {
    Header,
  },
  components: { Header },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.title {
  text-align: center;
}
</style>
