<template>
  <div class="wrapper" :style="{ '--accordioncolor': color }">
    <div class="accordion" @click="toggleItem">
      <h2 class="title">
        <slot name="title"></slot>
      </h2>
      <div v-if="!show" class="plus">+</div>
      <div v-else class="minus">-</div>
    </div>
    <div v-show="show" class="content">
      <slot name="content"></slot>
    </div>
  </div>
</template>
<script>
export default {
  props: ['color'],
  data: function() {
    return {
      show: false
    };
  },
  methods: {
    toggleItem: function() {
      this.show = !this.show;
    }
  }
};
</script>
<style lang="scss" scoped>
:root {
  --accordioncolorcolor: #00ADEE;
}
.wrapper {
  margin: 0 auto;
  background: var(--accordioncolor);
  font-family: "Arial Rounded MT Bold";
}
.accordion {
  display: flex;
  cursor: pointer;
  margin: 0;
  padding: 40px 60px;
  display: flex;
  justify-content: space-between;
}
.plus,
.minus {
  font-size: 1.6rem;
  color: white;
}
.title {
  color: white;
  font-size: 1.3rem;
}
.content {
  text-align: left;
  width: 100%;
  background: #f3f3f3;
  padding: 40px 40px;
  .wrapper {
    width: 90%;
    background: #f3f3f3;
    margin: 0 auto;
    display: flex;
    align-items: center;
    padding: 50px 0;
  }
  img {
    padding-right: 90px;
  }
  .text {
    color: black;
    h2 {
      font-size: 3rem;
      padding-bottom: 20px;
    }
    p {
      font-family: "Arial";
      font-size: 1.3rem;
      line-height: 1.5;
    }
  }
  .about-us {
    img {
      width: 100%;
      max-width: 400px;
      min-width: 350px;
    }
  }

// EVENTS STYLES
  .events {
    display: flex;
    justify-content: space-around;
  } 
  .event {
    cursor: pointer;
    text-decoration: none;
    background: white;
    width: 350px;
    height: 350px;
    overflow: hidden;
    box-shadow: 0 2px 5px 0 hsla(0,0%,65.9%,.5);
    .image-container {
      height: 65%;
    }
    img {
      display: block;
      height: 100%;
      padding: 0;
    }
    h3 {
      font-size: 1.3rem;
      padding: 5px 5px;
      color: black;
    }
    p {
      font-size: 0.8rem;
      font-family: "Arial";
      padding: 2px 5px;
      color: black;
      line-height: 1.2;
    }
    &:hover {
      opacity: 0.6;
    }
  }
  .event-0 {
    .image-container {
      height: 60%;
      width: 110%;
    }
    img {
      position: relative;
      bottom: 2px;
    }
  }
  .event-1 {
    .image-container {
      background: #20c071;
    }
    img {
      margin: 0 auto;
    }
  }

  .vision,
  .statement {
    padding: 100px 0;
  }
  blockquote {
    p {
      // display: inline;
      position: relative;
      color: black;
      font-size: 1.5rem;
      text-align: center;
    }
    p:after, p:before {
      color: rgba(122, 122, 122, 0.199);
      font-size: 11rem;                                      
      line-height: 0.8;
      position: absolute;
    } 

    p:after {                                                       
      content: '”';
      display: block;
      right: -10px;
      top: 30px;
    }

    p:before {                                     
      content: '“';
      display: block;
      left: -30px;
      top: -40px;
    }

  }

  .partners {
    display: flex;
    justify-content: space-between;
    flex-wrap: nowrap;
    .partner {
      flex: 0 0 300px;
      img {
        width: 100%;
        padding-right: 100px;
      }
    }
    .kibo {
      flex: 0 0 180px;
    }
  }
  .connect {
    display: flex;
    flex-direction: column;
    text-align: center;
    h2 {
      font-size: 3rem;
    }
    p {
      font-size: 1.5rem;
      font-family: "Arial";
      padding: 25px 0 35px;
      line-height: 1.3;
    }
    .button {
      padding: 20px 30px;
      background: black;
      color: white;
      text-transform: uppercase;
      font-weight: bold;
      font-size: 1.2rem;
      border-radius: 5px;
      text-decoration: none;
    }
  }
}
</style>
