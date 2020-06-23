<template>
  <section class="hero-image info-container-layout">
    <div class="info-container">
      <h1>Supporting LGBTQ+ identifying Koreans in Toronto</h1>
      <p>We envision a Korean-Canadian identity that welcomes, celebrates and advocates for LGBTQ+ diversity and seeks to foster health and well-being within our intergenerational and diverse community in Canada.</p>
    </div>
  </section>
</template>

<script>
export default {
  name: "HeroSection"
};
</script>

<style lang="scss" scoped>
.hero-image {
  background-image: url("../../assets/hero-image.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  height: 70vh;
}
.info-container-layout {
  display: flex;
  align-items: center;
}
.info-container {
  background-color: rgba(1,2,23,0.53);
  color: white;
  text-align: left;
  width: 690px;
  padding: 60px 50px;
}

h1 {
  font-family: "Arial Rounded MT Bold";
  font-size: 2.5rem;
  padding-bottom: 10px;
}
p {
  font-family: "Arial Rounded MT Bold";
  font-size: 1rem;
  line-height: 1.4;
}
</style>
