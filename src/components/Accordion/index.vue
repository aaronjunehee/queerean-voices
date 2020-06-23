<template>
  <div>
    <div class="accordion" v-for="accordion in accordions" :key="accordion.title">
      <BaseAccordion :color="accordion.color">
        <template v-slot:title>{{ accordion.title }}</template>

        <template v-slot:content>
          <img src="" alt="">
          <div>{{ accordion.text }}</div>
        </template>
      </BaseAccordion>
    </div>
  </div>
</template>

<script>
import BaseAccordion from "./BaseAccordion";

export default {
  name: "AccordionSection",
  components: {
    BaseAccordion,
  },
  data() {
    return {
      accordions: [
        {
          title: "About Us",
          text: "All about Vue",
          color: "#E82828"
        },
        {
          title: "Upcoming Events",
          text: "All about Nuxt",
          color: "#FFA207"
        },
        {
          title: "Partners",
          text: "All about webpack",
          color: "#0F9510"
        },
        {
          title: "Resources",
          text: "All about webpack",
          color: "#1EB7BF"
        },
        {
          title: "Our Mission Statement",
          text: "All about webpack",
          color: "#1E6CBF"
        },
         {
          title: "Connect",
          text: "All about webpack",
          color: "#761EBF"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.accordion {
  margin-bottom: 3px;
}

</style>
