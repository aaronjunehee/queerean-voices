<template>
  <nav class="full-width">
    <div class="logo-container">
      <img :src="logo" :alt="logoAlt" />
      <h1 class="title">
        <span class="title-top">queerean</span>
        <span class="title-bottom">voices</span>
      </h1>
    </div>
    <div class="hamburger-container">
      <img :src="hamburgerMenu" alt="" />
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  data: function() {
    return {
      logo: require("@/assets/queerean-voices-logo.svg"),
      logoAlt: "Queerean Voices Logo",
      hamburgerMenu: require("@/assets/hamburger-menu.png")
    };
  },
  computed: {
    // logo: function() {
    //   return "@/assets/queerean-voices-logo.svg";
    // }
  }
};
</script>

<style lang="scss" scoped>
.full-width {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 15px 20px;
  background-color: rgba(255, 255, 255, 0.95);
  width: 100%;
  position: fixed;
}
.logo-container {
  display: flex;
  align-items: center;
}
.title {
  font-family: "Arial Rounded MT Bold";
  padding-left: 7px;
  .title-top {
    position: relative;
    top: 2px;
  }
  .title-bottom {
    display: block;
    font-size: 1.5rem;
  }
}
.hamburger-container {
  img {
    width: 90%;
  }
}
</style>
