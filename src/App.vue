<template>
  <nav-page></nav-page>
  <router-view />
</template>
<script>
// @ is an alias to /src
import navPage from './components/navPage.vue'

export default {
  name: 'App',
  components: {
    navPage
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  overflow: scroll;
  scroll-behavior: smooth;
}

#app::-webkit-scrollbar {
  display: none;
  width: 0px;
  background-color: transparent;
}

body {
  margin: 0;
  padding: 0;
}
</style>
