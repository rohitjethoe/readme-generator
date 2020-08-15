<template>
  <div id="app">
    <Header />
    <Create />
  </div>
</template>

<script>
import Header from "./components/Header";
import Create from "./components/Create";

export default {
  name: 'App',
  data() {
    return {
      title: null, subtitle: null, license: "MIT"
    }
  },
  components: {
    Create,
    Header
  }
}
</script>

<style>
 @import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro&display=swap');
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
