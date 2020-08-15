<template>
  <div id="app">
    <Header />
    <Create v-if="!load" v-on:create-readme="createReadme"/>
    <File v-if="load" v-bind:config="config" />
  </div>
</template>

<script>
import Header from "./components/Header";
import Create from "./components/Create";
import File from "./components/File";

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
    }
  },
  components: {
    Create,
    Header,
    File
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
</style>
