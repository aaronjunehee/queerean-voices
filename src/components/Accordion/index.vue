<template>
  <div class="grey-background">
    <div class="accordion" v-for="(accordion, index) in accordions" :key="accordion.title">
      <BaseAccordion :color="accordion.color">
        <template v-slot:title>{{ accordion.title }}</template>

        <template v-slot:content>
          <div v-if="index === 0" class="wrapper about-us">
            <img v-if="accordion.image" :src="accordion.image" alt="">
            <div class="text">
              <h2 v-if="accordion.image">{{ accordion.title }}</h2>
              <p>{{ accordion.text }}</p>
            </div>
          </div>

          <div v-if="index === 1" class="wrapper events">
            <a v-for="(event, index) in accordion.events" :key="event.title" class="event" :class="'event' + '-' + index" :href="event.link" target="_blank">
              <div class="image-container">
                <img :src="event.image" alt="">
              </div>
              <div>
                <h3>{{ event.title }}</h3>
                <p>{{ event.description }}</p>
              </div>
            </a>
          </div>

          <div v-if="index === 2 || index === 3" class="wrapper vision statement">
            <blockquote>
              <p>{{ accordion.text }}</p>
            </blockquote>
          </div>

          <div v-if="index === 4" class="wrapper partners">
            <div v-for="(partner, index) in accordion.partners" :key="partner + index" :class="partner.title" class="partner">
              <img :src="partner.logo" alt="">
            </div>
          </div>

          <div v-if="index === 5" class="wrapper connect">
            <h2>{{ accordion.header }}</h2>
            <p>{{ accordion.description }}</p>
            <a class="button" href="mailto:queerean.voices@gmail.com">Get In Touch</a>
          </div>

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
          text: "Queerean Voices is a grassroots community group that is dedicated to advancing the health and well-being of LGBTQ+ identifying Koreans in Toronto. Our membership includes LGBTQ+ Koreans and allies.",
          color: "#E82828",
          image: require("@/assets/about-us-image.svg")
        },
        {
          title: "Upcoming Events",
          text: "test",
          color: "#FFA207",
          events: [
            {
              title: "VOICES 2.0 (Postponed)",
              image: require("@/assets/event-voices.jpg"),
              description: "Are you LGBTQ+? Korean living in the GTA? Out – or not? Curious, confused? Want to be a supportive ally? Join us for VOICES of Korean LGBTQ+ and allies in the GTA. Come hear their brave stories and experiences. Share yours too. All are welcome."
            },
            {
              title: "Funding For Not-For-Profit",
              image: require("@/assets/event-gofundme.jpg"),
              description: "Currently we are in the process of registering Queerean Voices as a non-profit organization with the Canadian Government to continue our evolving work to support Queer Koreans in the GTA. We hope you consider contributing! Thank you!",
              link: "https://ca.gofundme.com/f/queereanvoices-not-for-profit"
            }
          ]
        },
        {
          title: "Our Vision",
          text: "We envision a Korean-Canadian identity that welcomes, celebrates and advocates for LGBTQ+ diversity and seeks to foster health and well-being within our intergenerational and diverse community in Canada.",
          color: "#0F9510"
        },
        {
          title: "Our Mission Statement",
          text: "To create opportunities for community-building and leadership to support Korean LGBTQ+, their families and their allies in Canada.",
          color: "#1EB7BF"
        },
        {
          title: "Partners",
          partners: [
            {
              logo: require("@/assets/partner-kcsf.png"),
              title: 'kcsf'
            },
            {
              logo: require("@/assets/partner-kpwa.png"),
              title: 'kpwa'

            },
            {
              logo: require("@/assets/partner-pat.png"),
              title: 'pat'
            },
            {
              logo: require("@/assets/partner-kibo.png"),
              title: 'kibo'

            }
          ],
          color: "#1E6CBF"
        },
        {
          title: "Connect",
          header: "We'd love to hear from you",
          description: "Whether you have a question about membership, events, partnerships, or anything else, we'd be happy to answer all your questions.",
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
.grey-background {
  background: #f3f3f3;
}

</style>
