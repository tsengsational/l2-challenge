<template>
  <div id="app">
    <site-nav :site="site" ></site-nav>
    <site-home :site="site"></site-home>
    <site-footer :site="site"></site-footer>
  </div>
</template>

<script>
import SiteNav from "./components/Nav";
import SiteHome from "./components/SiteHome.vue";
import SiteFooter from "./components/Footer";
import site from "./assets/site.json"

export default {
  name: 'app',
  components: {
    SiteNav, SiteHome, SiteFooter
  },
  data: function() {
    return {
      site: site
    }
  }
}
</script>

<style>
#app {
  font-family: 'Roboto', sans-serif;;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  margin: 0;
}
</style>
