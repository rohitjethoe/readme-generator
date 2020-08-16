<template>
  <div id="app">
    <Header />
    <div class="container">
      <Create v-if="!load" v-on:create-readme="createReadme" />
      <File v-if="load" v-on:try-again="tryAgain" v-bind:config="config" />
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header";
import Create from "./components/Create";
import File from "./components/File";
import Footer from "./components/Footer";

export default {
  name: 'App',
  data() {
    return {
      config: {
      },
      load: false
    }
  },
  methods: {
    createReadme(config) {
      this.config = config;
      this.load = true;
    },
    tryAgain() {
      this.load = false
    }
  },
  components: {
    Create,
    Header,
    File,
    Footer
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@400;600&display=swap');
 
* {
  margin: 0;
  padding: 0;
}

#app {
  font-family: 'Source Sans Pro', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.container {
  min-height: calc(100vh - 345.5px - 28.5px);
}
</style>
