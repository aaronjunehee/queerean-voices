<template>
  <div id="app">
    <nav-bar class="navbar"></nav-bar>
    <router-view class="isShifted" />
  </div>
</template>

<script>
import NavBar from "@/components/NavBar";
export default {
  name: "app",
  components: {
    NavBar
  }
};
</script>

<style lang="scss">
@import "./styles/setup.scss";

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  position: relative
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.isShifted {
  padding-top: 87px;
}

</style>
