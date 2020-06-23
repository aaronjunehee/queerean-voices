<template>
  <main class="home">
    <HeroSection />
    <AccordionSection />
  </main>
</template>

<script>
// @ is an alias to /src
import HeroSection from "@/components/Hero";
import AccordionSection from "@/components/Accordion";

export default {
  name: "home",
  components: {
    HeroSection,
    AccordionSection
  }
};
</script>

<style lang="scss" scoped>

</style>